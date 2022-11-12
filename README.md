# Files to Check in Repo

```
app/common/Queries.php

app/Models/V2/*.*               // All Files
app/Http/Controllers/V2/*.*     // All Files

App/Repositories/V2/*.*         // All Files
```


## UserInfo
```
api/user/info
```

DB : Synergy

```sql
SELECT public."GetConsumerDetails"(
	<consumerid integer>, 
	<datetime text>
)

```

OR


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

DB : Finance

```sql
SELECT public."GetConsumptionDetails"(
	<metertypeid integer>, 
	<consumerid integer>, 
	<startdate text>, 
	<enddate text>
)

```

OR

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


*Query 1*

```sql
SELECT 
	"DateTime", 
    SUM("AllocatedEnergy") AS "AllocatedEnergy"
FROM 
	"Allocation"."ProducerT1Allocation"
WHERE
	"ConsumerRID" = {CONSUMER_ID} AND 
    "MeterTypeRID" = {METER_TYPE_ID} AND 
	"DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);
GROUP BY
	"DateTime", 
	
```


*Query 2*

```sql
SELECT 
    "DateTime",     
    SUM("AllocatedEnergy") AS "AllocatedEnergy"
FROM 
	"Allocation"."ProducerT2Allocation"
WHERE
	"ConsumerRID" = {CONSUMER_ID} AND 
    "MeterTypeRID" = {METER_TYPE_ID} AND 
	"DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);
GROUP BY
	"DateTime"
	
```


*Query 3*

```sql
SELECT 
	"DateTime", 
	SUM("AllocatedEnergy") AS "AllocatedEnergy"
	
FROM 
	"Allocation"."RetailerAllocation"
WHERE
	"ConsumerRID" = {CONSUMER_ID} AND 
    "MeterTypeRID" = {METER_TYPE_ID} AND 
	"DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);
GROUP BY
	"DateTime"
	
```


*Query 4*

```sql
SELECT 
	"DateTime", 
	SUM("RetailerAmount") AS "RetailerAmount", 
	SUM("T1Amount") AS "T1Amount", 
	SUM("T2ConsumerAmount") AS "T2ConsumerAmount"
FROM 
	"Billing"."ConsumerBilling"
WHERE
	"ConsumerRID" = {CONSUMER_ID} AND 
    "MeterTypeRID" = {METER_TYPE_ID} AND 
	"DateTime" BETWEEN TO_TIMESTAMP({START_DATE}, DateFormat) AND TO_TIMESTAMP({END_DATE}, DateFormat);
GROUP BY
	"DateTime"
```


**Then have to combine the output together from DateTime and send to the Chart**   
Sample PHP script is below

```php
$breakdowns = [];
$counter = 0;

while ($counter != $periodCount) {
    $key = $startDate->copy()->format($dateFormatKey);
    if ($keyBy != Constants::KEY_DAY) {
        $key = $startDate->copy()->setTimezone($timezone)->format($dateFormatKey);
        $key = (int)$key;
    }

    $producerT1AllocatedEnergy = (isset($producerT1Allocations[$key])) ? $producerT1Allocations[$key]->AllocatedEnergy : 0;
    $producerT2AllocatedEnergy = (isset($producerT2Allocations[$key])) ? $producerT2Allocations[$key]->AllocatedEnergy : 0;
    $retailerAllocatedEnergy = (isset($retailerAllocations[$key])) ? $retailerAllocations[$key]->AllocatedEnergy : 0;

    $retailerBillAmount = (isset($consumerBillings[$key])) ? $consumerBillings[$key]->RetailerAmount : 0;
    $producerT1BillAmount = (isset($consumerBillings[$key])) ? $consumerBillings[$key]->T1Amount : 0;
    $producerT2BillAmount = (isset($consumerBillings[$key])) ? $consumerBillings[$key]->T2ConsumerAmount : 0;

    $currentStartDate = $startDate->copy()->format(Constants::DATETIME_FORMAT);
    $currentEndDate = $startDate->copy()->$carbonIncrementFunction($incrementValue)->subMinutes(30)->format(Constants::DATETIME_FORMAT);

    $breakdowns[] = [
        'startDate' => $currentStartDate,
        'endDate' => $currentEndDate,
        'bill' => [
            't1' => Functions::getRoundedToFourDecimals($producerT1BillAmount),
            't2' => Functions::getRoundedToFourDecimals($producerT2BillAmount),
            'retailer' => Functions::getRoundedToFourDecimals($retailerBillAmount),
        ],
        'usage' => [
            't1' => Functions::getRoundedToFourDecimals($producerT1AllocatedEnergy),
            't2' => Functions::getRoundedToFourDecimals($producerT2AllocatedEnergy),
            'retailer' => Functions::getRoundedToFourDecimals($retailerAllocatedEnergy),
        ],
    ];

    $counter++;
    $startDate->$carbonIncrementFunction($incrementValue);
}

return $this->respondWithArray(['meterType' => $meterType, 'data' => array_values(Arr::sort($breakdowns, function ($value) {
    return $value['startDate'];
});

```



## getDailySummary ##

```
api/consumer/{consumer_id}/consumptions/summary-per-day?date=2022-11-12&meterType=1
```



For Daily Summary, we need the same dataset as the Breakdown (Can use the same code above). Difference is, we need to SUM the total allocation (T1 + T2 + Retailer) and multiply each allocation from the Price mentioned in the DB.

Sample PHP Script is below


```PHP
$t1 = [];
$totalT1BillPerPeriod = 0;
$totalT1UsagePerPeriod = 0;

if (isset($producerT1Allocations[$dateKey])) {
    $producerT1Allocation = $producerT1Allocations[$dateKey];
    $currentT1 = [
        'name' => $consumer->ProducerName,
        'usage' => Functions::getRoundedToFourDecimals($producerT1Allocation->AllocatedEnergy),
        'bill' => Functions::getRoundedToFourDecimals(($producerT1Allocation->AllocatedEnergy * $consumer->ProducerPlanPrice)),
    ];

    $totalT1BillPerPeriod = $currentT1['bill'];
    $totalT1UsagePerPeriod = $currentT1['usage'];

    $t1[] = $currentT1;
    $providerCounter++;
}

$t2 = [];
$totalT2BillPerPeriod = 0;
$totalT2UsagePerPeriod = 0;
if (isset($producerT2Allocations[$dateKey])) {
    foreach ($producerT2Allocations[$dateKey] as $producerT2Allocation) {
        $t2Record = [
            'name' => $producerT2Allocation->producer->user->LegalName,
            'usage' => Functions::getRoundedToFourDecimals($producerT2Allocation->AllocatedEnergy),
            'bill' => Functions::getRoundedToFourDecimals(($producerT2Allocation->AllocatedEnergy * $producerT2Allocation->BuyPrice)),
        ];

        $totalT2BillPerPeriod += $t2Record['bill'];
        $totalT2UsagePerPeriod += $t2Record['usage'];
        $t2[] = $t2Record;
        $providerCounter++;
    }
}

$retailer = [];
$totalRetailerBillPerPeriod = 0;
$totalRetailerUsagePerPeriod = 0;

if (isset($retailerAllocations[$dateKey])) {
    $retailerAllocation = $retailerAllocations[$dateKey];
    $currentRetailer = [
        'name' => $consumer->RetailerName,
        'usage' => Functions::getRoundedToFourDecimals($retailerAllocation->AllocatedEnergy),
        'bill' => Functions::getRoundedToFourDecimals(($retailerAllocation->AllocatedEnergy * $consumer->RetailerPlanPrice)),
    ];

    $totalRetailerBillPerPeriod = $currentRetailer['bill'];
    $totalRetailerUsagePerPeriod = $currentRetailer['usage'];
    $retailer[] = $currentRetailer;
    $providerCounter++;
}

$totalT1Bill += $totalT1BillPerPeriod;
$totalT2Bill += $totalT2BillPerPeriod;
$totalRetailerBill += $totalRetailerBillPerPeriod;

$usagePerPeriod = Functions::getRoundedToFourDecimals(($totalT1UsagePerPeriod + $totalT2UsagePerPeriod + $totalRetailerUsagePerPeriod));
$billPerPeriod = Functions::getRoundedToFourDecimals(($totalT1BillPerPeriod + $totalT2BillPerPeriod + $totalRetailerBillPerPeriod));

$transactions[] = [
    'startDate' => $dateKey,
    'endDate' => $startDate->copy()->addMinutes(29)->addSeconds(59)->format(Constants::DATETIME_FORMAT),
    'usagePerPeriod' => $usagePerPeriod,
    'billPerPeriod' => $billPerPeriod,
    'numberOfProviders' => $providerCounter,
    't1' => $t1,
    't2' => $t2,
    'retailer' => $retailer,
];

$startDate->addMinutes(30);

```