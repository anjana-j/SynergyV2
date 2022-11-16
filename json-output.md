# Consumer View


## Consumption Overview

``
api/consumer/{consumer_id}/overview?month=11&year=2022&meterType=1
``


```json

{
  "data": {
    "meterType": "1",
    "total_cost": 2300,
    "traded": {
      "name": "traded",
      "allocation": "150",
      "cost": "2050",
      "distributionPercentage": 80,
      "providers": [
        {
          "planName": "Prosumer A",
          "providerName": "Prosumer A",
          "energyType": "REX",
          "price": "0.005",
          "allocation": "19374.374",
          "cost": "2050"
        }
      ]
    },
    "energy_load": {
      "name": "energy_load",
      "allocation": "50",
      "cost": "250",
      "distributionPercentage": 20,
      "providers": [
        {
          "planName": "Brown Energy Plan",
          "providerName": "EGAT",
          "energyType": "Conventional",
          "price": "0.010",
          "allocation": "2500",
          "cost": "250"
        }
      ]
    }
  }
}

```



---



# Generator View

## Green Attribute Transactions

``
api/prosumer/{prosumer_id}/transactions?month=11&year=2022&meterType=1
``


```json

{
  "data": {
    "meterType": "1",
    "net_earnings": 2300, // previous_tag : total_cost

    "traded": { // UI Label : 24/7 CFE
      "name": "traded",
      "cost": "2050",   // bhat/dollar value
      "rec": 41,        // nearest 1000 rounded value
      "allocation": "40019.3714", // kwh value
    },
    "open_market": {
      "name": "open_market",
      "cost": "2750",
      "rec": 55,
      "allocation": "54865.8765",
    },
    "unsold": {
      "name": "unsold",
      "cost": "1450",
      "rec": 29,
      "allocation": "57465.8763",
    }
  }
}

```


## Green Attribute Distribution

``
api/prosumer/{prosumer_id}/distribution?month=11&year=2022&meterType=1
``

```json
{
  "data": {
    "meterType": "1",
    "traded": {
      "name": "traded",     // UI Label : 24/7 CFE
      "total_allocation" : "55243.238", // kwh value 
      "total_cost": "2800", // bhat/dollar value
      "distributionPercentage": 80, // pie-chart percentage
      "providers": [
        {
          "planName": "Norwegian Embassy",
          "providerName": "Norwegian Embassy",
          "price": "0.005",
          "allocation": "19374.374", // kwh value
          "cost": "1000"
        },
        {
          "planName": "ETRAN",
          "providerName": "ETRAN",
          "price": "0.005",
          "allocation": "12374.284", // kwh value
          "cost": "650"
        },
        {
          "planName": "BMW",
          "providerName": "BMW",
          "price": "0.005",
          "allocation": "23495.123", // kwh value
          "cost": "1200"
        },
      ]
    },
    "open_market": {
      "name": "open_market",
      "allocation": "0",
      "cost": "0",
      "distributionPercentage": "0",
      "providers": [], // empty string coz no allocations
    },
    "unsold": {
      "name": "unsold",
      "allocation": "23450.2837", // kwh value
      "cost": "1200",
      "distributionPercentage": 20,
    }
  }
}

```


## Production

``
24 period view
`` 

``
api/prosumer/{prosumer_id}/breakdown?period=D&date=2020-11-12&meterType=1
``


```json

{
  "meterType": "1",
  "data": [
    {
      "startDate": "2020-10-31 17:00:00",
      "endDate": "2020-10-31 17:00:00",
      "bill": {
        "traded": 1.0392,
        "unsold": 0.0392
      },
      "usage": {
        "traded": 2.227,
        "unsold": 0.227
      }
    },
    {
      "startDate": "2020-10-31 18:00:00",
      "endDate": "2020-10-31 18:00:00",
      "bill": {
        "traded": 1.5425,
        "unsold": 0.0425
      },
      "usage": {
        "traded": 2.246,
        "unsold": 0.246
      }
    },
    {
      "startDate": "2020-10-31 19:00:00",
      "endDate": "2020-10-31 19:00:00",
      "bill": {
        "traded": 1.0399,
        "unsold": 0.0399
      },
      "usage": {
        "traded": 1.231,
        "unsold": 0.231
      }
    },
    {
      "startDate": "2020-10-31 20:00:00",
      "endDate": "2020-10-31 20:00:00",
      "bill": {
        "traded": 1.0213,
        "unsold": 0.0213
      },
      "usage": {
        "traded": 2.123,
        "unsold": 0.123
      }
    },
    {
      "startDate": "2020-10-31 21:00:00",
      "endDate": "2020-10-31 21:00:00",
      "bill": {
        "traded": 1.0206,
        "unsold": 0.0206
      },
      "usage": {
        "traded": 2.119,
        "unsold": 0.119
      }
    },
    {
      "startDate": "2020-10-31 22:00:00",
      "endDate": "2020-10-31 22:00:00",
      "bill": {
        "traded": 4.0207,
        "unsold": 0.0207
      },
      "usage": {
        "traded": 0.67,
        "unsold": 0.12
      }
    },
    {
      "startDate": "2020-10-31 23:00:00",
      "endDate": "2020-10-31 23:00:00",
      "bill": {
        "traded": 1.0228,
        "unsold": 0
      },
      "usage": {
        "traded": 3.117,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 00:00:00",
      "endDate": "2020-11-01 00:00:00",
      "bill": {
        "traded": 2.0228,
        "unsold": 0
      },
      "usage": {
        "traded": 0.117,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 01:00:00",
      "endDate": "2020-11-01 01:00:00",
      "bill": {
        "traded": 4.0244,
        "unsold": 0
      },
      "usage": {
        "traded": 3.125,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 02:00:00",
      "endDate": "2020-11-01 02:00:00",
      "bill": {
        "traded": 5.0218,
        "unsold": 0
      },
      "usage": {
        "traded": 0.112,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 03:00:00",
      "endDate": "2020-11-01 03:00:00",
      "bill": {
        "traded": 10.047,
        "unsold": 0
      },
      "usage": {
        "traded": 2.241,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 04:00:00",
      "endDate": "2020-11-01 04:00:00",
      "bill": {
        "traded": 3.0213,
        "unsold": 0
      },
      "usage": {
        "traded": 0.109,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 05:00:00",
      "endDate": "2020-11-01 05:00:00",
      "bill": {
        "traded": 3.0156,
        "unsold": 1.0156
      },
      "usage": {
        "traded": 0.08,
        "unsold": 1.08
      }
    },
    {
      "startDate": "2020-11-01 06:00:00",
      "endDate": "2020-11-01 06:00:00",
      "bill": {
        "traded": 0.0109,
        "unsold": 1.0109
      },
      "usage": {
        "traded": 0.056,
        "unsold": 1.056
      }
    },
    {
      "startDate": "2020-11-01 07:00:00",
      "endDate": "2020-11-01 07:00:00",
      "bill": {
        "traded": 3.0107,
        "unsold": 1.0107
      },
      "usage": {
        "traded": 1.055,
        "unsold": 3.055
      }
    },
    {
      "startDate": "2020-11-01 08:00:00",
      "endDate": "2020-11-01 08:00:00",
      "bill": {
        "traded": 2.0121,
        "unsold": 1.0121
      },
      "usage": {
        "traded": 0.062,
        "unsold": 1.062
      }
    },
    {
      "startDate": "2020-11-01 09:00:00",
      "endDate": "2020-11-01 09:00:00",
      "bill": {
        "traded": 0.0131,
        "unsold": 0
      },
      "usage": {
        "traded": 0.067,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 10:00:00",
      "endDate": "2020-11-01 10:00:00",
      "bill": {
        "traded": 0.0137,
        "unsold": 0
      },
      "usage": {
        "traded": 0.07,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-11-01 11:00:00",
      "endDate": "2020-11-01 11:00:00",
      "bill": {
        "traded": 2.0543,
        "unsold": 0.0543
      },
      "usage": {
        "traded": 2.314,
        "unsold": 0.314
      }
    },
    {
      "startDate": "2020-11-01 12:00:00",
      "endDate": "2020-11-01 12:00:00",
      "bill": {
        "traded": 0.314,
        "unsold": 0.0529
      },
      "usage": {
        "traded": 0.0529,
        "unsold": 0.306
      }
    },
    {
      "startDate": "2020-11-01 13:00:00",
      "endDate": "2020-11-01 13:00:00",
      "bill": {
        "traded": 2.0543,
        "unsold": 0.05
      },
      "usage": {
        "traded": 2.0543,
        "unsold": 0.289
      }
    },
    {
      "startDate": "2020-11-01 14:00:00",
      "endDate": "2020-11-01 14:00:00",
      "bill": {
        "traded": 0.0486,
        "unsold": 0.0486
      },
      "usage": {
        "traded": 0.0486,
        "unsold": 0.2812
      }
    },
    {
      "startDate": "2020-11-01 15:00:00",
      "endDate": "2020-11-01 15:00:00",
      "bill": {
        "traded": 1.0163,
        "unsold": 0.0163
      },
      "usage": {
        "traded": 0.0163,
        "unsold": 0.094
      }
    },
    {
      "startDate": "2020-11-01 16:59:59",
      "endDate": "2020-11-01 16:59:59",
      "bill": {
        "traded": 0.0195,
        "unsold": 0.0195
      },
      "usage": {
        "traded": 1.0195,
        "unsold": 1.113
      }
    }
  ]
}
```


``
D view (30 Days View)
``

``
api/prosumer/{prosumer_id}/breakdown?period=W&date=2020-11-12&meterType=1
``


```json
{
  "meterType": "1",
  "data": [
    {
      "startDate": "2020-10-31 17:00:00",
      "endDate": "2020-10-31 16:59:59",
      "bill": {
        "traded": 10.0392,
        "unsold": 12.0392
      },
      "usage": {
        "traded": 12.227,
        "unsold": 10.227
      }
    },
    {
      "startDate": "2020-11-01 17:00:00",
      "endDate": "2020-11-01 16:59:59",
      "bill": {
        "traded": 11.5425,
        "unsold": 10.0425
      },
      "usage": {
        "traded": 12.246,
        "unsold": 10.246
      }
    },
    {
      "startDate": "2020-11-02 17:00:00",
      "endDate": "2020-11-02 16:59:59",
      "bill": {
        "traded": 11.0399,
        "unsold": 10.0399
      },
      "usage": {
        "traded": 11.231,
        "unsold": 10.231
      }
    },
    {
      "startDate": "2020-11-03 17:00:00",
      "endDate": "2020-11-03 16:59:59",
      "bill": {
        "traded": 11.0213,
        "unsold": 10.0213
      },
      "usage": {
        "traded": 12.123,
        "unsold": 9.123
      }
    },
    {
      "startDate": "2020-11-04 17:00:00",
      "endDate": "2020-11-04 16:59:59",
      "bill": {
        "traded": 14.0206,
        "unsold": 20.0206
      },
      "usage": {
        "traded": 14.119,
        "unsold": 20.119
      }
    },
    {
      "startDate": "2020-11-05 17:00:00",
      "endDate": "2020-11-05 16:59:59",
      "bill": {
        "traded": 14.0207,
        "unsold": 10.0207
      },
      "usage": {
        "traded": 15.67,
        "unsold": 12.12
      }
    },
    {
      "startDate": "2020-11-06 17:00:00",
      "endDate": "2020-11-06 16:59:59",
      "bill": {
        "traded": 15.0228,
        "unsold": 2.0
      },
      "usage": {
        "traded": 15.117,
        "unsold": 2.0
      }
    },
    {
      "startDate": "2020-11-07 17:00:00",
      "endDate": "2020-11-07 16:59:59",
      "bill": {
        "traded": 10.0392,
        "unsold": 12.0392
      },
      "usage": {
        "traded": 12.227,
        "unsold": 10.227
      }
    },
    {
      "startDate": "2020-11-08 17:00:00",
      "endDate": "2020-11-08 16:59:59",
      "bill": {
        "traded": 11.5425,
        "unsold": 10.0425
      },
      "usage": {
        "traded": 12.246,
        "unsold": 10.246
      }
    },
    {
      "startDate": "2020-11-09 17:00:00",
      "endDate": "2020-11-09 16:59:59",
      "bill": {
        "traded": 11.0399,
        "unsold": 10.0399
      },
      "usage": {
        "traded": 11.231,
        "unsold": 10.231
      }
    },
    {
      "startDate": "2020-11-10 17:00:00",
      "endDate": "2020-11-10 16:59:59",
      "bill": {
        "traded": 11.0213,
        "unsold": 10.0213
      },
      "usage": {
        "traded": 12.123,
        "unsold": 9.123
      }
    },
    {
      "startDate": "2020-11-11 17:00:00",
      "endDate": "2020-11-11 16:59:59",
      "bill": {
        "traded": 14.0206,
        "unsold": 20.0206
      },
      "usage": {
        "traded": 14.119,
        "unsold": 20.119
      }
    },
    {
      "startDate": "2020-11-12 17:00:00",
      "endDate": "2020-11-12 16:59:59",
      "bill": {
        "traded": 14.0207,
        "unsold": 10.0207
      },
      "usage": {
        "traded": 15.67,
        "unsold": 12.12
      }
    },
    {
      "startDate": "2020-11-13 17:00:00",
      "endDate": "2020-11-13 16:59:59",
      "bill": {
        "traded": 15.0228,
        "unsold": 2.0
      },
      "usage": {
        "traded": 15.117,
        "unsold": 2.0
      }
    },
    {
      "startDate": "2020-11-14 17:00:00",
      "endDate": "2020-11-14 16:59:59",
      "bill": {
        "traded": 10.0392,
        "unsold": 12.0392
      },
      "usage": {
        "traded": 12.227,
        "unsold": 10.227
      }
    },
    {
      "startDate": "2020-11-15 17:00:00",
      "endDate": "2020-11-15 16:59:59",
      "bill": {
        "traded": 11.5425,
        "unsold": 10.0425
      },
      "usage": {
        "traded": 12.246,
        "unsold": 10.246
      }
    },
    {
      "startDate": "2020-11-16 17:00:00",
      "endDate": "2020-11-16 16:59:59",
      "bill": {
        "traded": 11.0399,
        "unsold": 10.0399
      },
      "usage": {
        "traded": 11.231,
        "unsold": 10.231
      }
    },
    {
      "startDate": "2020-11-17 17:00:00",
      "endDate": "2020-11-17 16:59:59",
      "bill": {
        "traded": 11.0213,
        "unsold": 10.0213
      },
      "usage": {
        "traded": 12.123,
        "unsold": 9.123
      }
    },
    {
      "startDate": "2020-11-18 17:00:00",
      "endDate": "2020-11-18 16:59:59",
      "bill": {
        "traded": 14.0206,
        "unsold": 20.0206
      },
      "usage": {
        "traded": 14.119,
        "unsold": 20.119
      }
    },
    {
      "startDate": "2020-11-19 17:00:00",
      "endDate": "2020-11-19 16:59:59",
      "bill": {
        "traded": 14.0207,
        "unsold": 10.0207
      },
      "usage": {
        "traded": 15.67,
        "unsold": 12.12
      }
    },
    {
      "startDate": "2020-11-20 17:00:00",
      "endDate": "2020-11-20 16:59:59",
      "bill": {
        "traded": 15.0228,
        "unsold": 2.0
      },
      "usage": {
        "traded": 15.117,
        "unsold": 2.0
      }
    },
    {
      "startDate": "2020-11-21 17:00:00",
      "endDate": "2020-11-21 16:59:59",
      "bill": {
        "traded": 10.0392,
        "unsold": 12.0392
      },
      "usage": {
        "traded": 12.227,
        "unsold": 10.227
      }
    },
    {
      "startDate": "2020-11-22 17:00:00",
      "endDate": "2020-11-22 16:59:59",
      "bill": {
        "traded": 11.5425,
        "unsold": 10.0425
      },
      "usage": {
        "traded": 12.246,
        "unsold": 10.246
      }
    },
    {
      "startDate": "2020-11-23 17:00:00",
      "endDate": "2020-11-23 16:59:59",
      "bill": {
        "traded": 11.0399,
        "unsold": 10.0399
      },
      "usage": {
        "traded": 11.231,
        "unsold": 10.231
      }
    },
    {
      "startDate": "2020-11-24 17:00:00",
      "endDate": "2020-11-24 16:59:59",
      "bill": {
        "traded": 11.0213,
        "unsold": 10.0213
      },
      "usage": {
        "traded": 12.123,
        "unsold": 9.123
      }
    },
    {
      "startDate": "2020-11-25 17:00:00",
      "endDate": "2020-11-25 16:59:59",
      "bill": {
        "traded": 14.0206,
        "unsold": 20.0206
      },
      "usage": {
        "traded": 14.119,
        "unsold": 20.119
      }
    },
    {
      "startDate": "2020-11-26 17:00:00",
      "endDate": "2020-11-26 16:59:59",
      "bill": {
        "traded": 14.0207,
        "unsold": 10.0207
      },
      "usage": {
        "traded": 15.67,
        "unsold": 12.12
      }
    },
    {
      "startDate": "2020-11-27 17:00:00",
      "endDate": "2020-11-27 16:59:59",
      "bill": {
        "traded": 15.0228,
        "unsold": 2.0
      },
      "usage": {
        "traded": 15.117,
        "unsold": 2.0
      }
    },
    {
      "startDate": "2020-11-28 17:00:00",
      "endDate": "2020-11-28 16:59:59",
      "bill": {
        "traded": 14.0206,
        "unsold": 20.0206
      },
      "usage": {
        "traded": 14.119,
        "unsold": 20.119
      }
    },
    {
      "startDate": "2020-11-29 17:00:00",
      "endDate": "2020-11-29 16:59:59",
      "bill": {
        "traded": 14.0207,
        "unsold": 10.0207
      },
      "usage": {
        "traded": 15.67,
        "unsold": 12.12
      }
    },
    {
      "startDate": "2020-11-30 17:00:00",
      "endDate": "2020-11-30 16:59:59",
      "bill": {
        "traded": 15.0228,
        "unsold": 2.0
      },
      "usage": {
        "traded": 15.117,
        "unsold": 2.0
      }
    }
  ]
}
```




``
M view (Monthly View)
``

``
api/prosumer/{prosumer_id}/breakdown?period=Y&date=2020-11-12&meterType=1
``


```json
{
  "meterType": "1",
  "data": [
    {
      "startDate": "2019-12-31 17:00:00",
      "endDate": "2020-01-31 16:59:59",
      "bill": {
        "traded": 10.0392,
        "unsold": 12.0392
      },
      "usage": {
        "traded": 12.227,
        "unsold": 10.227
      }
    },
    {
      "startDate": "2020-01-31 17:00:00",
      "endDate": "2020-02-28 16:59:59",
      "bill": {
        "traded": 11.5425,
        "unsold": 10.0425
      },
      "usage": {
        "traded": 12.246,
        "unsold": 10.246
      }
    },
    {
      "startDate": "2020-02-28 17:00:00",
      "endDate": "2020-03-31 16:59:59",
      "bill": {
        "traded": 11.0399,
        "unsold": 10.0399
      },
      "usage": {
        "traded": 11.231,
        "unsold": 10.231
      }
    },
    {
      "startDate": "2020-03-31 17:00:00",
      "endDate": "2020-04-30 16:59:59",
      "bill": {
        "traded": 11.0213,
        "unsold": 10.0213
      },
      "usage": {
        "traded": 12.123,
        "unsold": 9.123
      }
    },
    {
      "startDate": "2020-04-30 17:00:00",
      "endDate": "2020-05-31 16:59:59",
      "bill": {
        "traded": 14.0206,
        "unsold": 20.0206
      },
      "usage": {
        "traded": 14.119,
        "unsold": 20.119
      }
    },
    {
      "startDate": "2020-05-31 17:00:00",
      "endDate": "2020-06-30 16:59:59",
      "bill": {
        "traded": 14.0207,
        "unsold": 10.0207
      },
      "usage": {
        "traded": 15.67,
        "unsold": 12.12
      }
    },
    {
      "startDate": "2020-06-30 17:00:00",
      "endDate": "2020-07-31 16:59:59",
      "bill": {
        "traded": 15.0228,
        "unsold": 2.0
      },
      "usage": {
        "traded": 15.117,
        "unsold": 2.0
      }
    },
    {
      "startDate": "2020-07-31 17:00:00",
      "endDate": "2020-08-31 16:59:59",
      "bill": {
        "traded": 10.0392,
        "unsold": 12.0392
      },
      "usage": {
        "traded": 12.227,
        "unsold": 10.227
      }
    },
    {
      "startDate": "2020-08-31 17:00:00",
      "endDate": "2020-09-30 16:59:59",
      "bill": {
        "traded": 11.5425,
        "unsold": 10.0425
      },
      "usage": {
        "traded": 12.246,
        "unsold": 10.246
      }
    },
    {
      "startDate": "2020-09-30 17:00:00",
      "endDate": "2020-10-31 16:59:59",
      "bill": {
        "traded": 11.0399,
        "unsold": 10.0399
      },
      "usage": {
        "traded": 11.231,
        "unsold": 10.231
      }
    },
    {
      "startDate": "2020-10-31 17:00:00",
      "endDate": "2020-11-30 16:59:59",
      "bill": {
        "traded": 0,
        "unsold": 0
      },
      "usage": {
        "traded": 0,
        "unsold": 0 
      }
    },
    {
      "startDate": "2020-11-30 17:00:00",
      "endDate": "2020-12-31 16:59:59",
      "bill": {
        "traded": 0,
        "unsold": 0
      },
      "usage": {
        "traded": 0,
        "unsold": 0
      }
    },
  ]
}
```


## Monthly Revenue

``
api/prosumer/{prosumer_id}/revenue?meterType=1
``


```json
{
  "meterType": "1",
  "data": [
    {
      "startDate": "2022-09-30 17:00:00",
      "endDate": "2020-10-31 16:59:59",
      "total_cost": 2300,
      "traded": { // UI Label : 24/7 CFE
        "name": "traded",
        "cost": "2050",   // bhat/dollar value
        "rec": 41,        // nearest 1000 rounded value
        "allocation": "40019.3714", // kwh value
      },
      "open_market": {
        "name": "open_market",
        "cost": "2750",
        "rec": 55,
        "allocation": "54865.8765",
      },
      "unsold": {
        "name": "unsold",
        "cost": "2750",
        "rec": 55,
        "allocation": "57465.8763",
      }
    },
    {
      "startDate": "2022-08-31 17:00:00",
      "endDate": "2022-09-30 16:59:59",
      "total_cost": 2100,
      "traded": { // UI Label : 24/7 CFE
        "name": "traded",
        "cost": "2050",   // bhat/dollar value
        "rec": 41,        // nearest 1000 rounded value
        "allocation": "40019.3714", // kwh value
      },
      "open_market": {
        "name": "open_market",
        "cost": "2750",
        "rec": 55,
        "allocation": "54865.8765",
      },
      "unsold": {
        "name": "unsold",
        "cost": "2750",
        "rec": 55,
        "allocation": "57465.8763",
      }
    },
    {
      "startDate": "2022-07-31 17:00:00",
      "endDate": "2022-08-31 16:59:59",
      "total_cost": 1800,
      "traded": { // UI Label : 24/7 CFE
        "name": "traded",
        "cost": "2050",   // bhat/dollar value
        "rec": 41,        // nearest 1000 rounded value
        "allocation": "40019.3714", // kwh value
      },
      "open_market": {
        "name": "open_market",
        "cost": "2750",
        "rec": 55,
        "allocation": "54865.8765",
      },
      "unsold": {
        "name": "unsold",
        "cost": "2750",
        "rec": 55,
        "allocation": "57465.8763",
      }
    },
    {
      "startDate": "2022-06-30 17:00:00",
      "endDate": "2022-07-31 16:59:59",
      "traded": { // UI Label : 24/7 CFE
        "name": "traded",
        "cost": "2050",   // bhat/dollar value
        "rec": 41,        // nearest 1000 rounded value
        "allocation": "40019.3714", // kwh value
      },
      "open_market": {
        "name": "open_market",
        "cost": "2750",
        "rec": 55,
        "allocation": "54865.8765",
      },
      "unsold": {
        "name": "unsold",
        "cost": "2750",
        "rec": 55,
        "allocation": "57465.8763",
      }
    }
  ]
}

```



## Monthly Payments

``
api/prosumer/{prosumer_id}/payments?meterType=1
``


```json
{
  "meterType": "1",
  "data": [
    {
      "startDate": "2022-09-30 17:00:00",
      "endDate": "2020-10-31 16:59:59",
      "payment_status" : "paid",
      "payment": 2300,
    },
    {
      "startDate": "2022-08-31 17:00:00",
      "endDate": "2022-09-30 16:59:59",
      "payment_status" : "paid",
      "payment": 2100,
    },
    {
      "startDate": "2022-07-31 17:00:00",
      "endDate": "2022-08-31 16:59:59",
      "payment_status" : "paid",
      "payment": 1900,
    },
    {
      "startDate": "2022-06-30 17:00:00",
      "endDate": "2022-07-31 16:59:59",
      "payment_status" : "paid",
      "payment": 2500
    }
  ]
}

```


## 24/7 CFE Daily Tracking


``
api/prosumer/{prosumer_id}/daily-tracking?date=2020-11-12&meterType=1
``


```json

{
  "meterType": "1",
  "data": {
    "startDate": "2020-10-31 17:00:00",
    "endDate": "2020-11-01 16:59:59",
    "bill": [
          {
        "traded": { // UI Label : 24/7 CFE
          "name": "traded",
          "cost": "2050",   // bhat/dollar value
          "rec": 41,        // nearest 1000 rounded value
          "allocation": "40019.3714" // kwh value
        },
        "unsold": {
          "name": "unsold",
          "cost": "1450",
          "rec": 29,
          "allocation": "57465.8763"
        }
      }
    ],
  "transactions": [
      {
        "startDate": "2020-10-31 17:00:00",
        "endDate": "2020-10-31 17:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-10-31 18:00:00",
        "endDate": "2020-10-31 18:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-10-31 19:00:00",
        "endDate": "2020-10-31 19:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-10-31 20:00:00",
        "endDate": "2020-10-31 20:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-10-31 21:00:00",
        "endDate": "2020-10-31 21:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-10-31 22:00:00",
        "endDate": "2020-10-31 22:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-10-31 23:00:00",
        "endDate": "2020-10-31 23:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 00:00:00",
        "endDate": "2020-11-01 00:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 01:00:00",
        "endDate": "2020-11-01 01:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 02:00:00",
        "endDate": "2020-11-01 02:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 03:00:00",
        "endDate": "2020-11-01 03:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 04:00:00",
        "endDate": "2020-11-01 04:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 05:00:00",
        "endDate": "2020-11-01 05:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 06:00:00",
        "endDate": "2020-11-01 06:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 07:00:00",
        "endDate": "2020-11-01 07:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 08:00:00",
        "endDate": "2020-11-01 08:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 09:00:00",
        "endDate": "2020-11-01 09:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 10:00:00",
        "endDate": "2020-11-01 10:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 11:00:00",
        "endDate": "2020-11-01 11:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 12:00:00",
        "endDate": "2020-11-01 12:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 13:00:00",
        "endDate": "2020-11-01 13:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 14:00:00",
        "endDate": "2020-11-01 14:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 15:00:00",
        "endDate": "2020-11-01 15:00:00",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      },
      {
        "startDate": "2020-11-01 16:59:59",
        "endDate": "2020-11-01 16:59:59",
        "usagePerPeriod": 2.227,
        "billPerPeriod": 1.0392,
        "numberOfProviders": 2,
        "traded": [
          { 
            "name": "Consumer A",
            "cost": "100",   
            "rec": 2,       
            "allocation": "194.3714" 
          },
          { 
            "name": "Consumer B",
            "cost": "500",   
            "rec": 5,       
            "allocation": "473.6841" 
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "150",
          "rec": 3,
          "allocation": "148.8842"
        }
      }
    ]
  }
}
```
