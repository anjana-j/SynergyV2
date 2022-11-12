## UserInfo
```
api/user/info
```

```sql
DECLARE
    DateFormat TEXT DEFAULT 'YYYY-MM-DD HH24:MI:SS';
    CountryName VARCHAR;
    TimeZone VARCHAR;
    LegalName VARCHAR;
    StreetAddress VARCHAR;
    Unit NUMERIC;
    Floor NUMERIC;
    ZipCode VARCHAR;
    Mssl VARCHAR;
    RetailerPlanName VARCHAR;
    ProducerPlanName VARCHAR;
    ProducerPlanPrice NUMERIC;
    RetailerPlanPrice NUMERIC;
    Contract{START_DATE} TIMESTAMP;
    Contract{END_DATE} TIMESTAMP;
    DepositAmount NUMERIC;
BEGIN
    SELECT 
        c."CountryName", 
        c."TimeZone", 
        r."LegalName", 
        p."StreetAddress", 
        p."Unit", 
        p."Floor", 
        p."ZipCode", 
        rp."PlanName" "RetailerPlanName",
        rp."Price" "RetailerPlanPrice", 
        pp."PlanName" "ProducerPlanName", 
        pp."ProducerSellPrice" "ProducerPlanPrice", 
        cs."Contract{START_DATE}",
        cs."Contract{END_DATE}", 
        p."Mssl", 
        cs."DepositAmount"
    INTO 
        CountryName, 
        TimeZone, 
        LegalName, 
        StreetAddress, 
        Unit, 
        Floor, 
        ZipCode, 
        RetailerPlanName, 
        RetailerPlanPrice, 
        ProducerPlanName,
        ProducerPlanPrice, 
        Contract{START_DATE}, 
        Contract{END_DATE},
        Mssl, 
        DepositAmount
    FROM 
        "User"."RegistrationInfo" r, 
        "User"."UserInfo" u, 
        "Reference"."Country" c, 
        "User"."Premise" p,
        "Consumer"."ConsumerSubscription" cs LEFT JOIN "Producer"."ProducerPlan" pp ON cs."ProducerPlanRID" = pp."PlanID",
        "Retailer"."RetailerPlan" rp
    WHERE 
        r."UserRegID" = u."UserRegRID" AND 
        u."CountryRID" = c."CountryID" AND 
        u."UserID" = p."UserRID" AND 
        cs."UserRID" = u."UserID" AND 
        rp."PlanID" = cs."RetailerPlanRID" AND 
        cs."Contract{START_DATE}" <= TO_TIMESTAMP(DateTime, DateFormat) AND 
        u."UserID" = {CONSUMER_ID}
    ORDER BY 
        cs."Contract{START_DATE}" DESC LIMIT 1;

    IF ProducerPlanName IS NULL THEN ProducerPlanName = ''; END IF;
    IF ProducerPlanPrice IS NULL THEN ProducerPlanPrice = 0; END IF;

    RETURN QUERY SELECT 
        CountryName, 
        TimeZone, 
        LegalName, 
        StreetAddress, 
        Unit, 
        Floor, 
        ZipCode, 
        Mssl, 
        RetailerPlanName, 
        RetailerPlanPrice,
        ProducerPlanName, 
        ProducerPlanPrice, 
        Contract{START_DATE}, 
        Contract{END_DATE},
        DepositAmount;
END

```



## Consumption Overview
```
api/consumer/{consumer_id}/consumptions/overview?month={month_number}&year={year_number}&meterType=1
```

```sql
DECLARE
    DateFormat TEXT DEFAULT 'YYYY-MM-DD HH24:MI:SS';
    T1Energy NUMERIC;
    T1Earning NUMERIC;
    T2Energy NUMERIC;
    T2ConsumerAmount NUMERIC;
    T2BuyPrice NUMERIC;
    RetailerEnergy NUMERIC;
    RetailerEarning NUMERIC;
BEGIN
    SELECT 
        SUM("AllocatedEnergy") 
    INTO 
        T1Energy 
    FROM 
        "Allocation"."ProducerT1Allocation"
    WHERE 
        "ConsumerRID" = {CONSUMER_ID} AND 
        "MeterTypeRID" = {METER_TYPE_ID} AND 
        "DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);

    SELECT 
        SUM("Amount")
    INTO 
        T1Earning 
    FROM 
        "Earning"."ProducerT1Earning"
    WHERE 
        "ConsumerRID" = {CONSUMER_ID} AND 
        "MeterTypeRID" = {METER_TYPE_ID} AND 
        "DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);

    SELECT 
        SUM("AllocatedEnergy"), 
        AVG("BuyPrice") 
    INTO 
        T2Energy, 
        T2BuyPrice
    FROM 
        "Allocation"."ProducerT2Allocation" 
    WHERE 
        "ConsumerRID" = {CONSUMER_ID} AND 
        "MeterTypeRID" = {METER_TYPE_ID} AND 
        "DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);

    SELECT 
        SUM("ConsumerAmount") 
    INTO 
        T2ConsumerAmount 
    FROM 
        "Earning"."ProducerT2Earning"
    WHERE 
        "ConsumerRID" = {CONSUMER_ID} AND 
        "MeterTypeRID" = {METER_TYPE_ID} AND 
        "DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);

    SELECT 
        SUM("AllocatedEnergy") 
    INTO 
        RetailerEnergy 
    FROM 
        "Allocation"."RetailerAllocation"
    WHERE 
        "ConsumerRID" = {CONSUMER_ID} AND 
        "MeterTypeRID" = {METER_TYPE_ID} AND 
        "DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);

    SELECT 
        SUM("Amount") 
    INTO 
        RetailerEarning 
    FROM 
        "Earning"."RetailerEarning"
    WHERE 
        "ConsumerRID" = {CONSUMER_ID} AND 
        "MeterTypeRID" = {METER_TYPE_ID} AND 
        "DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);

    IF T1Energy IS NULL THEN T1Energy = 0; END IF;
    IF T1Earning IS NULL THEN T1Earning = 0; END IF;
    IF T2Energy IS NULL THEN T2Energy = 0; END IF;
    IF T2ConsumerAmount IS NULL THEN T2ConsumerAmount = 0; END IF;
    IF T2BuyPrice IS NULL THEN T2BuyPrice = 0; END IF;
    IF RetailerEnergy IS NULL THEN RetailerEnergy = 0; END IF;
    IF RetailerEarning IS NULL THEN RetailerEarning = 0; END IF;

    RETURN QUERY SELECT 
        T1Energy, 
        T1Earning, 
        T2Energy, 
        T2ConsumerAmount, 
        RetailerEnergy, 
        RetailerEarning, 
        T2BuyPrice;
END


```


## Past 6 Months Usage
```
api/consumer/{consumer_id}/consumptions/usage?meterType=1
```


DB : Finance

```sql

SELECT 
    "BilledFrom", 
    SUM("ProducerAllocation") "ProducerAllocation", 
    SUM("RetailerAllocation") "RetailerAllocation", 
    SUM("TotalConsumerAmount") "TotalConsumerAmount" 
FROM 
    "Billing"."ConsumerBillingBatches" 
WHERE 
    "BilledFrom" >= {START_DATE} AND 
    "BilledTo" <= {END_DATE} AND 
    "ConsumerRID" = {CONSUMER_ID} AND 
    "MeterTypeRID" ={METER_TYPE_ID}
GROUP BY 
    "BilledFrom"'

```




### Breakdown
```
api/consumer/{consumer_id}/consumptions/breakdown?period={day/month/year}&date=2022-11-12&meterType=1
```

**This endpoint is a combination of 4 different tables**.  
After get the data, its group together in the API logic.

#### Tables

- ProducerT1Allocation
- ProducerT2Allocation
- RetailerAllocation
- ConsumerBilling

