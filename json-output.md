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







# Generator View

## Green Energy Transactions

``
api/prosumer/{prosumer_id}/overview?month=11&year=2022&meterType=1
``


```json

{
  "data": {
    "meterType": "1",
    "total_cost": 2300,

    "traded": {
      "name": "traded",
      "cost": "2050",
      "rec": 41,
      "allocation": "40019.371",
    },
    "open_market": {
      "name": "open_market",
      "cost": "2750",
      "rec": 55,
      "allocation": "54865.876",
    },
    "unsold": {
      "name": "unsold",
      "allocation": "57465.876",
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
D view (Weekly View)
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