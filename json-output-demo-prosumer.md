# Generator View

## Green Attribute Transactions

``
api/prosumer/{prosumer_id}/transactions?month=11&year=2022&meterType=1
``


```json

{
  "data": {
    "meterType": "1",
    "net_earnings": 2600, // previous_tag : total_cost

    "traded": { // UI Label : 24/7 CFE
      "name": "traded",
      "cost": "2600",   // bhat/dollar value
      "rec": 52,        // nearest 1000 rounded value
      "allocation": "51987.098", // kwh value
    },
    "open_market": {
      "name": "open_market",
      "cost": "0",
      "rec": 0,
      "allocation": "0",
    },
    "unsold": {
      "name": "unsold",
      "cost": "1750",
      "rec": 35,
      "allocation": "3466907.902",
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
      "total_allocation" : "51987.098", // kwh value 
      "total_cost": "2600", // bhat/dollar value
      "distributionPercentage": 100, // pie-chart percentage
      "providers": [
        {
          "planName": "Norwegian Embassy",
          "providerName": "Norwegian Embassy",
          "price": "0.05",
          "allocation": "46297.038", // kwh value
          "cost": "2314.8519"
        },
        {
          "planName": "ETRAN",
          "providerName": "ETRAN",
          "price": "0.05",
          "allocation": "5690.06", // kwh value
          "cost": "284.503"
        },
        {
          "planName": "BMW",
          "providerName": "BMW",
          "price": "0.05",
          "allocation": "0", // kwh value
          "cost": "0"
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
      "allocation": "3466907.902", // kwh value
      "cost": "1750",
      "distributionPercentage": 0,
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
      "startDate": "2022-08-31 17:00:00",
      "endDate": "2022-08-31 17:00:00",
      "bill": {
        "traded": 3.5400,
        "unsold": 265.9600
      },
      "usage": {
        "traded": 70.8000,
        "unsold": 5319.2000
      }
    },
    {
      "startDate": "2022-08-31 18:00:00",
      "endDate": "2022-08-31 18:00:00",
      "bill": {
        "traded": 4.0372,
        "unsold": 266.7129
      },
      "usage": {
        "traded": 80.7430,
        "unsold": 5334.2570
      }
    },
    {
      "startDate": "2022-08-31 19:00:00",
      "endDate": "2022-08-31 19:00:00",
      "bill": {
        "traded": 3.8656,
        "unsold": 267.1345
      },
      "usage": {
        "traded": 77.3110,
        "unsold": 5342.6890
      }
    },
    {
      "startDate": "2022-08-31 20:00:00",
      "endDate": "2022-08-31 20:00:00",
      "bill": {
        "traded": 3.3908,
        "unsold": 268.3592
      },
      "usage": {
        "traded": 67.8160,
        "unsold": 5367.1840
      }
    },
    {
      "startDate": "2022-08-31 21:00:00",
      "endDate": "2022-08-31 21:00:00",
      "bill": {
        "traded": 4.3001,
        "unsold": 267.2000
      },
      "usage": {
        "traded": 86.0010,
        "unsold": 5343.9990
      }
    },
    {
      "startDate": "2022-08-31 22:00:00",
      "endDate": "2022-08-31 22:00:00",
      "bill": {
        "traded": 3.7929,
        "unsold": 268.7072
      },
      "usage": {
        "traded": 75.8570,
        "unsold": 5374.1430
      }
    },
    {
      "startDate": "2022-08-31 23:00:00",
      "endDate": "2022-08-31 23:00:00",
      "bill": {
        "traded": 3.8454,
        "unsold": 269.6547
      },
      "usage": {
        "traded": 76.9070,
        "unsold": 5393.0930
      }
    },
    {
      "startDate": "2022-09-01 00:00:00",
      "endDate": "2022-09-01 00:00:00",
      "bill": {
        "traded": 4.4790,
        "unsold": 212.5211
      },
      "usage": {
        "traded": 89.5790,
        "unsold": 4250.4210
      }
    },
    {
      "startDate": "2022-09-01 01:00:00",
      "endDate": "2022-09-01 01:00:00",
      "bill": {
        "traded": 4.2077,
        "unsold": 97.2923
      },
      "usage": {
        "traded": 84.1540,
        "unsold": 1945.8460
      }
    },
    {
      "startDate": "2022-09-01 02:00:00",
      "endDate": "2022-09-01 02:00:00",
      "bill": {
        "traded": 2.7853,
        "unsold": 274.2148
      },
      "usage": {
        "traded": 55.7050,
        "unsold": 5484.2950
      }
    },
    {
      "startDate": "2022-09-01 03:00:00",
      "endDate": "2022-09-01 03:00:00",
      "bill": {
        "traded": 3.4004,
        "unsold": 275.0997
      },
      "usage": {
        "traded": 68.0070,
        "unsold": 5501.9930
      }
    },
    {
      "startDate": "2022-09-01 04:00:00",
      "endDate": "2022-09-01 04:00:00",
      "bill": {
        "traded": 1.8448,
        "unsold": 283.1552
      },
      "usage": {
        "traded": 36.8960,
        "unsold": 5663.1040
      }
    },
    {
      "startDate": "2022-09-01 05:00:00",
      "endDate": "2022-09-01 05:00:00",
      "bill": {
        "traded": 2.8053,
        "unsold": 281.4448
      },
      "usage": {
        "traded": 56.1050,
        "unsold": 5628.8950
      }
    },
    {
      "startDate": "2022-09-01 06:00:00",
      "endDate": "2022-09-01 06:00:00",
      "bill": {
        "traded": 3.7314,
        "unsold": 281.0187
      },
      "usage": {
        "traded": 74.6270,
        "unsold": 5620.3730
      }
    },
    {
      "startDate": "2022-09-01 07:00:00",
      "endDate": "2022-09-01 07:00:00",
      "bill": {
        "traded": 6.2999,
        "unsold": 278.2001
      },
      "usage": {
        "traded": 125.9980,
        "unsold": 5564.0020
      }
    },
    {
      "startDate": "2022-09-01 08:00:00",
      "endDate": "2022-09-01 08:00:00",
      "bill": {
        "traded": 5.8497,
        "unsold": 279.4003
      },
      "usage": {
        "traded": 116.9940,
        "unsold": 5588.0060
      }
    },
    {
      "startDate": "2022-09-01 09:00:00",
      "endDate": "2022-09-01 09:00:00",
      "bill": {
        "traded": 4.1530,
        "unsold": 280.8471
      },
      "usage": {
        "traded": 83.0590,
        "unsold": 5616.9410
      }
    },
    {
      "startDate": "2022-09-01 10:00:00",
      "endDate": "2022-09-01 10:00:00",
      "bill": {
        "traded": 3.7204,
        "unsold": 280.5297
      },
      "usage": {
        "traded": 74.4070,
        "unsold": 5610.5930
      }
    },
    {
      "startDate": "2022-09-01 11:00:00",
      "endDate": "2022-09-01 11:00:00",
      "bill": {
        "traded": 4.9572,
        "unsold": 282.7928
      },
      "usage": {
        "traded": 99.1440,
        "unsold": 5655.8560
      }
    },
    {
      "startDate": "2022-09-01 12:00:00",
      "endDate": "2022-09-01 12:00:00",
      "bill": {
        "traded": 5.7600,
        "unsold": 283.9901
      },
      "usage": {
        "traded": 115.1990,
        "unsold": 5679.8010
      }
    },
    {
      "startDate": "2022-09-01 13:00:00",
      "endDate": "2022-09-01 13:00:00",
      "bill": {
        "traded": 4.6185,
        "unsold": 285.6315
      },
      "usage": {
        "traded": 92.3700,
        "unsold": 5712.6300
      }
    },
    {
      "startDate": "2022-09-01 14:00:00",
      "endDate": "2022-09-01 14:00:00",
      "bill": {
        "traded": 4.0026,
        "unsold": 286.9974
      },
      "usage": {
        "traded": 80.0520,
        "unsold": 5739.9480
      }
    },
    {
      "startDate": "2022-09-01 15:00:00",
      "endDate": "2022-09-01 15:00:00",
      "bill": {
        "traded": 4.3086,
        "unsold": 286.1915
      },
      "usage": {
        "traded": 86.1710,
        "unsold": 5723.8290
      }
    },
    {
      "startDate": "2022-09-01 16:00:00",
      "endDate": "2022-09-01 16:00:00",
      "bill": {
        "traded": 3.9051,
        "unsold": 281.3449
      },
      "usage": {
        "traded": 78.1020,
        "unsold": 5626.8980
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
    "startDate": "2022-08-31 17:00:00",
    "endDate": "2022-08-31 16:59:59",
    "bill": {
      "traded": 26.772,
      "unsold": 1873.7285
    },
    "usage": {
      "traded": 535.435,
      "unsold": 37474.565
    }
  },
  {
    "startDate": "2022-09-01 17:00:00",
    "endDate": "2022-09-01 16:59:59",
    "bill": {
      "traded": 99.7176,
      "unsold": 6475.0336
    },
    "usage": {
      "traded": 1994.34,
      "unsold": 129500.66
    }
  },
  {
    "startDate": "2022-09-02 17:00:00",
    "endDate": "2022-09-02 16:59:59",
    "bill": {
      "traded": 96.7308,
      "unsold": 6846.0204
    },
    "usage": {
      "traded": 1934.604,
      "unsold": 136920.396
    }
  },
  {
    "startDate": "2022-09-03 17:00:00",
    "endDate": "2022-09-03 16:59:59",
    "bill": {
      "traded": 79.9221,
      "unsold": 6339.8288
    },
    "usage": {
      "traded": 1598.433,
      "unsold": 126796.567
    }
  },
  {
    "startDate": "2022-09-04 17:00:00",
    "endDate": "2022-09-04 16:59:59",
    "bill": {
      "traded": 67.8665,
      "unsold": 7253.1345
    },
    "usage": {
      "traded": 1357.32,
      "unsold": 145062.68
    }
  },
  {
    "startDate": "2022-09-05 17:00:00",
    "endDate": "2022-09-05 16:59:59",
    "bill": {
      "traded": 105.0351,
      "unsold": 6206.7158
    },
    "usage": {
      "traded": 2100.693,
      "unsold": 124134.307
    }
  },
  {
    "startDate": "2022-09-06 17:00:00",
    "endDate": "2022-09-06 16:59:59",
    "bill": {
      "traded": 88.1949,
      "unsold": 6218.3061
    },
    "usage": {
      "traded": 1763.888,
      "unsold": 124366.112
    }
  },
  {
    "startDate": "2022-09-07 17:00:00",
    "endDate": "2022-09-07 16:59:59",
    "bill": {
      "traded": 92.9836,
      "unsold": 6911.7676
    },
    "usage": {
      "traded": 1859.66,
      "unsold": 138235.34
    }
  },
  {
    "startDate": "2022-09-08 17:00:00",
    "endDate": "2022-09-08 16:59:59",
    "bill": {
      "traded": 99.9468,
      "unsold": 7565.0543
    },
    "usage": {
      "traded": 1998.925,
      "unsold": 151301.075
    }
  },
  {
    "startDate": "2022-09-09 17:00:00",
    "endDate": "2022-09-09 16:59:59",
    "bill": {
      "traded": 88.453,
      "unsold": 6781.2983
    },
    "usage": {
      "traded": 1769.047,
      "unsold": 135625.953
    }
  },
  {
    "startDate": "2022-09-10 17:00:00",
    "endDate": "2022-09-10 16:59:59",
    "bill": {
      "traded": 69.084,
      "unsold": 6387.9171
    },
    "usage": {
      "traded": 1381.669,
      "unsold": 127758.331
    }
  },
  {
    "startDate": "2022-09-11 17:00:00",
    "endDate": "2022-09-11 16:59:59",
    "bill": {
      "traded": 69.1163,
      "unsold": 6146.3849
    },
    "usage": {
      "traded": 1382.314,
      "unsold": 122927.686
    }
  },
  {
    "startDate": "2022-09-12 17:00:00",
    "endDate": "2022-09-12 16:59:59",
    "bill": {
      "traded": 103.5569,
      "unsold": 3378.1943
    },
    "usage": {
      "traded": 2071.126,
      "unsold": 67563.874
    }
  },
  {
    "startDate": "2022-09-13 17:00:00",
    "endDate": "2022-09-13 16:59:59",
    "bill": {
      "traded": 91.1082,
      "unsold": 2301.393
    },
    "usage": {
      "traded": 1822.152,
      "unsold": 46027.848
    }
  },
  {
    "startDate": "2022-09-14 17:00:00",
    "endDate": "2022-09-14 16:59:59",
    "bill": {
      "traded": 82.5427,
      "unsold": 2555.4585
    },
    "usage": {
      "traded": 1650.842,
      "unsold": 51109.158
    }
  },
  {
    "startDate": "2022-09-15 17:00:00",
    "endDate": "2022-09-15 16:59:59",
    "bill": {
      "traded": 82.3129,
      "unsold": 2786.4377
    },
    "usage": {
      "traded": 1646.252,
      "unsold": 55728.748
    }
  },
  {
    "startDate": "2022-09-16 17:00:00",
    "endDate": "2022-09-16 16:59:59",
    "bill": {
      "traded": 82.3242,
      "unsold": 3478.1769
    },
    "usage": {
      "traded": 1646.473,
      "unsold": 69563.527
    }
  },
  {
    "startDate": "2022-09-17 17:00:00",
    "endDate": "2022-09-17 16:59:59",
    "bill": {
      "traded": 60.0994,
      "unsold": 4529.9014
    },
    "usage": {
      "traded": 1201.98,
      "unsold": 90598.02
    }
  },
  {
    "startDate": "2022-09-18 17:00:00",
    "endDate": "2022-09-18 16:59:59",
    "bill": {
      "traded": 70.1448,
      "unsold": 5256.8561
    },
    "usage": {
      "traded": 1402.887,
      "unsold": 105137.113
    }
  },
  {
    "startDate": "2022-09-19 17:00:00",
    "endDate": "2022-09-19 16:59:59",
    "bill": {
      "traded": 87.7746,
      "unsold": 6890.9762
    },
    "usage": {
      "traded": 1755.484,
      "unsold": 137819.516
    }
  },
  {
    "startDate": "2022-09-20 17:00:00",
    "endDate": "2022-09-20 16:59:59",
    "bill": {
      "traded": 86.4376,
      "unsold": 5332.5632
    },
    "usage": {
      "traded": 1728.744,
      "unsold": 106651.256
    }
  },
  {
    "startDate": "2022-09-21 17:00:00",
    "endDate": "2022-09-21 16:59:59",
    "bill": {
      "traded": 82.0673,
      "unsold": 6088.9339
    },
    "usage": {
      "traded": 1641.334,
      "unsold": 121778.666
    }
  },
  {
    "startDate": "2022-09-22 17:00:00",
    "endDate": "2022-09-22 16:59:59",
    "bill": {
      "traded": 91.7885,
      "unsold": 5930.7125
    },
    "usage": {
      "traded": 1835.76,
      "unsold": 118614.24
    }
  },
  {
    "startDate": "2022-09-23 17:00:00",
    "endDate": "2022-09-23 16:59:59",
    "bill": {
      "traded": 93.7435,
      "unsold": 6233.0078
    },
    "usage": {
      "traded": 1874.857,
      "unsold": 124660.143
    }
  },
  {
    "startDate": "2022-09-24 17:00:00",
    "endDate": "2022-09-24 16:59:59",
    "bill": {
      "traded": 69.2097,
      "unsold": 6256.7916
    },
    "usage": {
      "traded": 1384.181,
      "unsold": 125135.819
    }
  },
  {
    "startDate": "2022-09-25 17:00:00",
    "endDate": "2022-09-25 16:59:59",
    "bill": {
      "traded": 72.9382,
      "unsold": 6241.0629
    },
    "usage": {
      "traded": 1458.753,
      "unsold": 124821.247
    }
  },
  {
    "startDate": "2022-09-26 17:00:00",
    "endDate": "2022-09-26 16:59:59",
    "bill": {
      "traded": 107.3271,
      "unsold": 6846.4242
    },
    "usage": {
      "traded": 2146.529,
      "unsold": 136928.471
    }
  },
  {
    "startDate": "2022-09-27 17:00:00",
    "endDate": "2022-09-27 16:59:59",
    "bill": {
      "traded": 93.7176,
      "unsold": 6731.0335
    },
    "usage": {
      "traded": 1874.341,
      "unsold": 134620.659
    }
  },
  {
    "startDate": "2022-09-28 17:00:00",
    "endDate": "2022-09-28 16:59:59",
    "bill": {
      "traded": 91.4651,
      "unsold": 6110.2862
    },
    "usage": {
      "traded": 1829.289,
      "unsold": 122205.711
    }
  },
  {
    "startDate": "2022-09-29 17:00:00",
    "endDate": "2022-09-29 16:59:59",
    "bill": {
      "traded": 96.6533,
      "unsold": 6521.3478
    },
    "usage": {
      "traded": 1933.055,
      "unsold": 130426.945
    }
  },
  {
    "startDate": "2022-09-30 17:00:00",
    "endDate": "2022-09-30 16:59:59",
    "bill": {
      "traded": 70.3369,
      "unsold": 4870.6638
    },
    "usage": {
      "traded": 1406.731,
      "unsold": 97413.269
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
        "traded": 0,
        "unsold": 0
      },
      "usage": {
        "traded": 0,
        "unsold": 0
      }
    },
    {
      "startDate": "2020-01-31 17:00:00",
      "endDate": "2020-02-28 16:59:59",
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
      "startDate": "2020-02-28 17:00:00",
      "endDate": "2020-03-31 16:59:59",
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
      "startDate": "2020-03-31 17:00:00",
      "endDate": "2020-04-30 16:59:59",
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
      "startDate": "2020-04-30 17:00:00",
      "endDate": "2020-05-31 16:59:59",
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
      "startDate": "2020-05-31 17:00:00",
      "endDate": "2020-06-30 16:59:59",
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
      "startDate": "2020-06-30 17:00:00",
      "endDate": "2020-07-31 16:59:59",
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
      "startDate": "2020-07-31 17:00:00",
      "endDate": "2020-08-31 16:59:59",
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
      "startDate": "2020-08-31 17:00:00",
      "endDate": "2020-09-30 16:59:59",
      "bill": {
        "traded": 2599.3712,
        "unsold": 173345.4114
      },
      "usage": {
        "traded": 51987.098,
        "unsold": 3466907.902
      }
    },
    {
      "startDate": "2020-09-30 17:00:00",
      "endDate": "2020-10-31 16:59:59",
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
      "startDate": "2022-08-31 17:00:00",
      "endDate": "2022-09-30 16:59:59",
      "total_cost": 2600,
      "traded": { // UI Label : 24/7 CFE
        "name": "traded",
        "cost": "2600",   // bhat/dollar value
        "rec": 52,        // nearest 1000 rounded value
        "allocation": "51987.098", // kwh value
      },
      "open_market": {
        "name": "open_market",
        "cost": "0",
        "rec": 0,
        "allocation": "0",
      },
      "unsold": {
        "name": "unsold",
        "cost": "1750",
        "rec": 35,
        "allocation": "3466907.902",
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
      "payment": 0,
    },
    {
      "startDate": "2022-08-31 17:00:00",
      "endDate": "2022-09-30 16:59:59",
      "payment_status" : "paid",
      "payment": 0,
    },
    {
      "startDate": "2022-07-31 17:00:00",
      "endDate": "2022-08-31 16:59:59",
      "payment_status" : "paid",
      "payment": 0,
    },
    {
      "startDate": "2022-06-30 17:00:00",
      "endDate": "2022-07-31 16:59:59",
      "payment_status" : "paid",
      "payment": 0
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
    "startDate": "2022-08-31 17:00:00",
    "endDate": "2022-09-01 16:59:59",
    "bill": [
      {
        "traded": {
          "name": "traded",
          "cost": "97.6009",
          "rec": 20,
          "allocation": "1952.0040"
        },
        "unsold": {
          "name": "unsold",
          "cost": "6404.4005",
          "rec": 129,
          "allocation": "128087.9960"
        }
      }
    ],
    "transactions": [
      {
        "startDate": "2022-08-31 17:00:00 17:00:00",
        "endDate": "2022-08-31 17:00:00 16:59:59",
        "usagePerPeriod": 70.8,
        "billPerPeriod": 3.54,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.5265",
            "rec": 0,
            "allocation": "70.53"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.0135",
            "rec": 0,
            "allocation": "0.27"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5319.2000",
          "rec": 0,
          "allocation": "265.9600"
        }
      },
      {
        "startDate": "2022-08-31 18:00:00 17:00:00",
        "endDate": "2022-08-31 18:00:00 16:59:59",
        "usagePerPeriod": 80.743,
        "billPerPeriod": 4.0372,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.27415",
            "rec": 0,
            "allocation": "65.483"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.763",
            "rec": 0,
            "allocation": "15.26"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5334.2570",
          "rec": 0,
          "allocation": "266.7129"
        }
      },
      {
        "startDate": "2022-08-31 19:00:00 17:00:00",
        "endDate": "2022-08-31 19:00:00 16:59:59",
        "usagePerPeriod": 77.311,
        "billPerPeriod": 3.8656,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.34705",
            "rec": 0,
            "allocation": "66.941"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.5185",
            "rec": 0,
            "allocation": "10.37"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5342.6890",
          "rec": 0,
          "allocation": "267.1345"
        }
      },
      {
        "startDate": "2022-08-31 20:00:00 17:00:00",
        "endDate": "2022-08-31 20:00:00 16:59:59",
        "usagePerPeriod": 67.816,
        "billPerPeriod": 3.3908,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.0618",
            "rec": 0,
            "allocation": "61.236"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.329",
            "rec": 0,
            "allocation": "6.58"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5367.1840",
          "rec": 0,
          "allocation": "268.3592"
        }
      },
      {
        "startDate": "2022-08-31 21:00:00 17:00:00",
        "endDate": "2022-08-31 21:00:00 16:59:59",
        "usagePerPeriod": 86.001,
        "billPerPeriod": 4.3001,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.83155",
            "rec": 0,
            "allocation": "76.631"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.4685",
            "rec": 0,
            "allocation": "9.37"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5343.9990",
          "rec": 0,
          "allocation": "267.2000"
        }
      },
      {
        "startDate": "2022-08-31 22:00:00 17:00:00",
        "endDate": "2022-08-31 22:00:00 16:59:59",
        "usagePerPeriod": 75.857,
        "billPerPeriod": 3.7929,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.76585",
            "rec": 0,
            "allocation": "75.317"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.027",
            "rec": 0,
            "allocation": "0.54"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5374.1430",
          "rec": 0,
          "allocation": "268.7072"
        }
      },
      {
        "startDate": "2022-08-31 23:00:00 17:00:00",
        "endDate": "2022-08-31 23:00:00 16:59:59",
        "usagePerPeriod": 76.907,
        "billPerPeriod": 3.8454,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.64285",
            "rec": 0,
            "allocation": "72.857"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.2025",
            "rec": 0,
            "allocation": "4.05"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5393.0930",
          "rec": 0,
          "allocation": "269.6547"
        }
      },
      {
        "startDate": "2022-09-01 00:00:00 17:00:00",
        "endDate": "2022-09-01 00:00:00 16:59:59",
        "usagePerPeriod": 89.579,
        "billPerPeriod": 4.479,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "4.28945",
            "rec": 0,
            "allocation": "85.789"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.1895",
            "rec": 0,
            "allocation": "3.79"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "4250.4210",
          "rec": 0,
          "allocation": "212.5211"
        }
      },
      {
        "startDate": "2022-09-01 01:00:00 17:00:00",
        "endDate": "2022-09-01 01:00:00 16:59:59",
        "usagePerPeriod": 84.154,
        "billPerPeriod": 4.2077,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "4.1957",
            "rec": 0,
            "allocation": "83.914"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.012",
            "rec": 0,
            "allocation": "0.24"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "1945.8460",
          "rec": 0,
          "allocation": "97.2923"
        }
      },
      {
        "startDate": "2022-09-01 02:00:00 17:00:00",
        "endDate": "2022-09-01 02:00:00 16:59:59",
        "usagePerPeriod": 55.705,
        "billPerPeriod": 2.7853,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "2.77525",
            "rec": 0,
            "allocation": "55.505"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.01",
            "rec": 0,
            "allocation": "0.2"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5484.2950",
          "rec": 0,
          "allocation": "274.2148"
        }
      },
      {
        "startDate": "2022-09-01 03:00:00 17:00:00",
        "endDate": "2022-09-01 03:00:00 16:59:59",
        "usagePerPeriod": 68.007,
        "billPerPeriod": 3.4004,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.39035",
            "rec": 0,
            "allocation": "67.807"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.01",
            "rec": 0,
            "allocation": "0.2"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5501.9930",
          "rec": 0,
          "allocation": "275.0997"
        }
      },
      {
        "startDate": "2022-09-01 04:00:00 17:00:00",
        "endDate": "2022-09-01 04:00:00 16:59:59",
        "usagePerPeriod": 36.896,
        "billPerPeriod": 1.8448,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "1.2138",
            "rec": 0,
            "allocation": "24.276"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.631",
            "rec": 0,
            "allocation": "12.62"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5663.1040",
          "rec": 0,
          "allocation": "283.1552"
        }
      },
      {
        "startDate": "2022-09-01 05:00:00 17:00:00",
        "endDate": "2022-09-01 05:00:00 16:59:59",
        "usagePerPeriod": 56.105,
        "billPerPeriod": 2.8053,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "1.42125",
            "rec": 0,
            "allocation": "28.425"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "1.384",
            "rec": 0,
            "allocation": "27.68"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5628.8950",
          "rec": 0,
          "allocation": "281.4448"
        }
      },
      {
        "startDate": "2022-09-01 06:00:00 17:00:00",
        "endDate": "2022-09-01 06:00:00 16:59:59",
        "usagePerPeriod": 74.627,
        "billPerPeriod": 3.7314,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "2.88585",
            "rec": 0,
            "allocation": "57.717"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.8455",
            "rec": 0,
            "allocation": "16.91"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5620.3730",
          "rec": 0,
          "allocation": "281.0187"
        }
      },
      {
        "startDate": "2022-09-01 07:00:00 17:00:00",
        "endDate": "2022-09-01 07:00:00 16:59:59",
        "usagePerPeriod": 125.998,
        "billPerPeriod": 6.2999,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "4.8564",
            "rec": 0,
            "allocation": "97.128"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "1.4435",
            "rec": 0,
            "allocation": "28.87"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5564.0020",
          "rec": 0,
          "allocation": "278.2001"
        }
      },
      {
        "startDate": "2022-09-01 08:00:00 17:00:00",
        "endDate": "2022-09-01 08:00:00 16:59:59",
        "usagePerPeriod": 116.994,
        "billPerPeriod": 5.8497,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "4.4882",
            "rec": 0,
            "allocation": "89.764"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "1.3615",
            "rec": 0,
            "allocation": "27.23"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5588.0060",
          "rec": 0,
          "allocation": "279.4003"
        }
      },
      {
        "startDate": "2022-09-01 09:00:00 17:00:00",
        "endDate": "2022-09-01 09:00:00 16:59:59",
        "usagePerPeriod": 83.059,
        "billPerPeriod": 4.153,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.32095",
            "rec": 0,
            "allocation": "66.419"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.832",
            "rec": 0,
            "allocation": "16.64"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5616.9410",
          "rec": 0,
          "allocation": "280.8471"
        }
      },
      {
        "startDate": "2022-09-01 10:00:00 17:00:00",
        "endDate": "2022-09-01 10:00:00 16:59:59",
        "usagePerPeriod": 74.407,
        "billPerPeriod": 3.7204,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.63685",
            "rec": 0,
            "allocation": "72.737"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.0835",
            "rec": 0,
            "allocation": "1.67"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5610.5930",
          "rec": 0,
          "allocation": "280.5297"
        }
      },
      {
        "startDate": "2022-09-01 11:00:00 17:00:00",
        "endDate": "2022-09-01 11:00:00 16:59:59",
        "usagePerPeriod": 99.144,
        "billPerPeriod": 4.9572,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.8837",
            "rec": 0,
            "allocation": "77.674"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "1.0735",
            "rec": 0,
            "allocation": "21.47"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5655.8560",
          "rec": 0,
          "allocation": "282.7928"
        }
      },
      {
        "startDate": "2022-09-01 12:00:00 17:00:00",
        "endDate": "2022-09-01 12:00:00 16:59:59",
        "usagePerPeriod": 115.199,
        "billPerPeriod": 5.76,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "4.55795",
            "rec": 0,
            "allocation": "91.159"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "1.202",
            "rec": 0,
            "allocation": "24.04"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5679.8010",
          "rec": 0,
          "allocation": "283.9901"
        }
      },
      {
        "startDate": "2022-09-01 13:00:00 17:00:00",
        "endDate": "2022-09-01 13:00:00 16:59:59",
        "usagePerPeriod": 92.37,
        "billPerPeriod": 4.6185,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "4.597",
            "rec": 0,
            "allocation": "91.94"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.0215",
            "rec": 0,
            "allocation": "0.43"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5712.6300",
          "rec": 0,
          "allocation": "285.6315"
        }
      },
      {
        "startDate": "2022-09-01 14:00:00 17:00:00",
        "endDate": "2022-09-01 14:00:00 16:59:59",
        "usagePerPeriod": 80.052,
        "billPerPeriod": 4.0026,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.5841",
            "rec": 0,
            "allocation": "71.682"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.4185",
            "rec": 0,
            "allocation": "8.37"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5739.9480",
          "rec": 0,
          "allocation": "286.9974"
        }
      },
      {
        "startDate": "2022-09-01 15:00:00 17:00:00",
        "endDate": "2022-09-01 15:00:00 16:59:59",
        "usagePerPeriod": 86.171,
        "billPerPeriod": 4.3086,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.59805",
            "rec": 0,
            "allocation": "71.961"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.7105",
            "rec": 0,
            "allocation": "14.21"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5723.8290",
          "rec": 0,
          "allocation": "286.1915"
        }
      },
      {
        "startDate": "2022-09-01 16:00:00 17:00:00",
        "endDate": "2022-09-01 16:00:00 16:59:59",
        "usagePerPeriod": 78.102,
        "billPerPeriod": 3.9051,
        "numberOfProviders": 2,
        "traded": [
          {
            "name": "Netherlands Embassy",
            "cost": "3.8451",
            "rec": 0,
            "allocation": "76.902"
          },
          {
            "name": "SMYAN-ETRAN",
            "cost": "0.06",
            "rec": 0,
            "allocation": "1.2"
          }
        ],
        "unsold": {
          "name": "unsold",
          "cost": "5626.8980",
          "rec": 0,
          "allocation": "281.3449"
        }
      }
    ]
  }
}
```

