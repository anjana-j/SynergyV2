
# Consumer View


## 24/7 CFE Overview

``
api/consumer/{consumer_id}/overview?month=11&year=2022&meterType=1
``


```json

{
	"data": {
		"meterType": "1",
		"net_earnings": 2350,
		"traded": {
			"name": "traded",
			"allocation": "47",
			"cost": "2350",
			"distributionPercentage": 100
		},
		"energy_load": {
			"name": "energy_load",
			"allocation": "0",
			"cost": "0",
			"distributionPercentage": 0
		}
	}
}

```


## Past 6 Months Usage

``
api/consumer/{consumer_id}/usage?meterType=1
``

```json
{
	"meterType": "1",
	"data": [{
			"startDate": "2019-12-31 17:00:00",
			"endDate": "2020-01-31 16:59:59",
			"bill": {
				"traded": 0,
				"energy_load": 0
			},
			"usage": {
				"traded": 0,
				"energy_load": 0
			}
		},
		{
			"startDate": "2020-01-31 17:00:00",
			"endDate": "2020-02-28 16:59:59",
			"bill": {
				"traded": 0,
				"energy_load": 0
			},
			"usage": {
				"traded": 0,
				"energy_load": 0
			}
		},
		{
			"startDate": "2020-02-28 17:00:00",
			"endDate": "2020-03-31 16:59:59",
			"bill": {
				"traded": 0,
				"energy_load": 0
			},
			"usage": {
				"traded": 0,
				"energy_load": 0
			}
		},
		{
			"startDate": "2020-03-31 17:00:00",
			"endDate": "2020-04-30 16:59:59",
			"bill": {
				"traded": 0,
				"energy_load": 0
			},
			"usage": {
				"traded": 0,
				"energy_load": 0
			}
		},
		{
			"startDate": "2020-04-30 17:00:00",
			"endDate": "2020-05-31 16:59:59",
			"bill": {
				"traded": 0,
				"energy_load": 0
			},
			"usage": {
				"traded": 0,
				"energy_load": 0
			}
		},
		{
			"startDate": "2020-05-31 17:00:00",
			"endDate": "2020-06-30 16:59:59",
			"bill": {
				"traded": 2314.8519,
				"energy_load": 0
			},
			"usage": {
				"traded": 46297.038,
				"energy_load": 0
			}
		}
	]
}

```


## Consumption Breakdown

``
24 period view
`` 

``
api/consumer/{consumer_id}/breakdown?period=D&date=2020-11-12&meterType=1
``


```json

{
  "meterType": "1",
  "data": [
    {
    "startDate": "2022-08-31 17:00:00",
    "endDate": "2022-08-31 17:00:00",
    "bill": {
      "traded": 3.5265,
      "energy_load": 0
    },
    "usage": {
      "traded": 70.53,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-08-31 18:00:00",
    "endDate": "2022-08-31 18:00:00",
    "bill": {
      "traded": 3.27415,
      "energy_load": 0
    },
    "usage": {
      "traded": 65.483,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-08-31 19:00:00",
    "endDate": "2022-08-31 19:00:00",
    "bill": {
      "traded": 3.34705,
      "energy_load": 0
    },
    "usage": {
      "traded": 66.941,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-08-31 20:00:00",
    "endDate": "2022-08-31 20:00:00",
    "bill": {
      "traded": 3.0618,
      "energy_load": 0
    },
    "usage": {
      "traded": 61.236,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-08-31 21:00:00",
    "endDate": "2022-08-31 21:00:00",
    "bill": {
      "traded": 3.83155,
      "energy_load": 0
    },
    "usage": {
      "traded": 76.631,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-08-31 22:00:00",
    "endDate": "2022-08-31 22:00:00",
    "bill": {
      "traded": 3.76585,
      "energy_load": 0
    },
    "usage": {
      "traded": 75.317,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-08-31 23:00:00",
    "endDate": "2022-08-31 23:00:00",
    "bill": {
      "traded": 3.64285,
      "energy_load": 0
    },
    "usage": {
      "traded": 72.857,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 00:00:00",
    "endDate": "2022-09-01 00:00:00",
    "bill": {
      "traded": 4.28945,
      "energy_load": 0
    },
    "usage": {
      "traded": 85.789,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 01:00:00",
    "endDate": "2022-09-01 01:00:00",
    "bill": {
      "traded": 4.1957,
      "energy_load": 0
    },
    "usage": {
      "traded": 83.914,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 02:00:00",
    "endDate": "2022-09-01 02:00:00",
    "bill": {
      "traded": 2.77525,
      "energy_load": 0
    },
    "usage": {
      "traded": 55.505,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 03:00:00",
    "endDate": "2022-09-01 03:00:00",
    "bill": {
      "traded": 3.39035,
      "energy_load": 0
    },
    "usage": {
      "traded": 67.807,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 04:00:00",
    "endDate": "2022-09-01 04:00:00",
    "bill": {
      "traded": 1.2138,
      "energy_load": 0
    },
    "usage": {
      "traded": 24.276,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 05:00:00",
    "endDate": "2022-09-01 05:00:00",
    "bill": {
      "traded": 1.42125,
      "energy_load": 0
    },
    "usage": {
      "traded": 28.425,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 06:00:00",
    "endDate": "2022-09-01 06:00:00",
    "bill": {
      "traded": 2.88585,
      "energy_load": 0
    },
    "usage": {
      "traded": 57.717,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 07:00:00",
    "endDate": "2022-09-01 07:00:00",
    "bill": {
      "traded": 4.8564,
      "energy_load": 0
    },
    "usage": {
      "traded": 97.128,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 08:00:00",
    "endDate": "2022-09-01 08:00:00",
    "bill": {
      "traded": 4.4882,
      "energy_load": 0
    },
    "usage": {
      "traded": 89.764,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 09:00:00",
    "endDate": "2022-09-01 09:00:00",
    "bill": {
      "traded": 3.32095,
      "energy_load": 0
    },
    "usage": {
      "traded": 66.419,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 10:00:00",
    "endDate": "2022-09-01 10:00:00",
    "bill": {
      "traded": 3.63685,
      "energy_load": 0
    },
    "usage": {
      "traded": 72.737,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 11:00:00",
    "endDate": "2022-09-01 11:00:00",
    "bill": {
      "traded": 3.8837,
      "energy_load": 0
    },
    "usage": {
      "traded": 77.674,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 12:00:00",
    "endDate": "2022-09-01 12:00:00",
    "bill": {
      "traded": 4.55795,
      "energy_load": 0
    },
    "usage": {
      "traded": 91.159,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 13:00:00",
    "endDate": "2022-09-01 13:00:00",
    "bill": {
      "traded": 4.597,
      "energy_load": 0
    },
    "usage": {
      "traded": 91.94,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 14:00:00",
    "endDate": "2022-09-01 14:00:00",
    "bill": {
      "traded": 3.5841,
      "energy_load": 0
    },
    "usage": {
      "traded": 71.682,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 15:00:00",
    "endDate": "2022-09-01 15:00:00",
    "bill": {
      "traded": 3.59805,
      "energy_load": 0
    },
    "usage": {
      "traded": 71.961,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 16:00:00",
    "endDate": "2022-09-01 16:00:00",
    "bill": {
      "traded": 3.8451,
      "energy_load": 0
    },
    "usage": {
      "traded": 76.902,
      "energy_load": 0
    }
  }
  ]
}
```


``
D view (30 Days View)
``

``
api/consumer/{consumer_id}/breakdown?period=W&date=2020-11-12&meterType=1
``


```json
{
  "meterType": "1",
  "data": [
    {
    "startDate": "2022-08-31 17:00:00",
    "endDate": "2022-08-31 16:59:59",
    "bill": {
      "traded": 24.44975,
      "energy_load": 0
    },
    "usage": {
      "traded": 488.995,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-01 17:00:00",
    "endDate": "2022-09-01 16:59:59",
    "bill": {
      "traded": 86.2465,
      "energy_load": 0
    },
    "usage": {
      "traded": 1724.93,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-02 17:00:00",
    "endDate": "2022-09-02 16:59:59",
    "bill": {
      "traded": 83.3377,
      "energy_load": 0
    },
    "usage": {
      "traded": 1666.754,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-03 17:00:00",
    "endDate": "2022-09-03 16:59:59",
    "bill": {
      "traded": 68.82865,
      "energy_load": 0
    },
    "usage": {
      "traded": 1376.573,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-04 17:00:00",
    "endDate": "2022-09-04 16:59:59",
    "bill": {
      "traded": 60.329,
      "energy_load": 0
    },
    "usage": {
      "traded": 1206.58,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-05 17:00:00",
    "endDate": "2022-09-05 16:59:59",
    "bill": {
      "traded": 91.50015,
      "energy_load": 0
    },
    "usage": {
      "traded": 1830.003,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-06 17:00:00",
    "endDate": "2022-09-06 16:59:59",
    "bill": {
      "traded": 87.5069,
      "energy_load": 0
    },
    "usage": {
      "traded": 1750.138,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-07 17:00:00",
    "endDate": "2022-09-07 16:59:59",
    "bill": {
      "traded": 82.439,
      "energy_load": 0
    },
    "usage": {
      "traded": 1648.78,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-08 17:00:00",
    "endDate": "2022-09-08 16:59:59",
    "bill": {
      "traded": 86.82875,
      "energy_load": 0
    },
    "usage": {
      "traded": 1736.575,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-09 17:00:00",
    "endDate": "2022-09-09 16:59:59",
    "bill": {
      "traded": 74.63635,
      "energy_load": 0
    },
    "usage": {
      "traded": 1492.727,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-10 17:00:00",
    "endDate": "2022-09-10 16:59:59",
    "bill": {
      "traded": 59.08395,
      "energy_load": 0
    },
    "usage": {
      "traded": 1181.679,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-11 17:00:00",
    "endDate": "2022-09-11 16:59:59",
    "bill": {
      "traded": 58.8442,
      "energy_load": 0
    },
    "usage": {
      "traded": 1176.884,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-12 17:00:00",
    "endDate": "2022-09-12 16:59:59",
    "bill": {
      "traded": 90.6508,
      "energy_load": 0
    },
    "usage": {
      "traded": 1813.016,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-13 17:00:00",
    "endDate": "2022-09-13 16:59:59",
    "bill": {
      "traded": 83.6226,
      "energy_load": 0
    },
    "usage": {
      "traded": 1672.452,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-14 17:00:00",
    "endDate": "2022-09-14 16:59:59",
    "bill": {
      "traded": 82.5421,
      "energy_load": 0
    },
    "usage": {
      "traded": 1650.842,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-15 17:00:00",
    "endDate": "2022-09-15 16:59:59",
    "bill": {
      "traded": 82.3126,
      "energy_load": 0
    },
    "usage": {
      "traded": 1646.252,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-16 17:00:00",
    "endDate": "2022-09-16 16:59:59",
    "bill": {
      "traded": 82.32365,
      "energy_load": 0
    },
    "usage": {
      "traded": 1646.473,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-17 17:00:00",
    "endDate": "2022-09-17 16:59:59",
    "bill": {
      "traded": 60.099,
      "energy_load": 0
    },
    "usage": {
      "traded": 1201.98,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-18 17:00:00",
    "endDate": "2022-09-18 16:59:59",
    "bill": {
      "traded": 63.72185,
      "energy_load": 0
    },
    "usage": {
      "traded": 1274.437,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-19 17:00:00",
    "endDate": "2022-09-19 16:59:59",
    "bill": {
      "traded": 74.3052,
      "energy_load": 0
    },
    "usage": {
      "traded": 1486.104,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-20 17:00:00",
    "endDate": "2022-09-20 16:59:59",
    "bill": {
      "traded": 77.0952,
      "energy_load": 0
    },
    "usage": {
      "traded": 1541.904,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-21 17:00:00",
    "endDate": "2022-09-21 16:59:59",
    "bill": {
      "traded": 69.5437,
      "energy_load": 0
    },
    "usage": {
      "traded": 1390.874,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-22 17:00:00",
    "endDate": "2022-09-22 16:59:59",
    "bill": {
      "traded": 79.47,
      "energy_load": 0
    },
    "usage": {
      "traded": 1589.4,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-23 17:00:00",
    "endDate": "2022-09-23 16:59:59",
    "bill": {
      "traded": 80.80785,
      "energy_load": 0
    },
    "usage": {
      "traded": 1616.157,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-24 17:00:00",
    "endDate": "2022-09-24 16:59:59",
    "bill": {
      "traded": 60.81655,
      "energy_load": 0
    },
    "usage": {
      "traded": 1216.331,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-25 17:00:00",
    "endDate": "2022-09-25 16:59:59",
    "bill": {
      "traded": 62.49815,
      "energy_load": 0
    },
    "usage": {
      "traded": 1249.963,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-26 17:00:00",
    "endDate": "2022-09-26 16:59:59",
    "bill": {
      "traded": 98.03145,
      "energy_load": 0
    },
    "usage": {
      "traded": 1960.629,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-27 17:00:00",
    "endDate": "2022-09-27 16:59:59",
    "bill": {
      "traded": 79.48555,
      "energy_load": 0
    },
    "usage": {
      "traded": 1589.711,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-28 17:00:00",
    "endDate": "2022-09-28 16:59:59",
    "bill": {
      "traded": 78.06145,
      "energy_load": 0
    },
    "usage": {
      "traded": 1561.229,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-29 17:00:00",
    "endDate": "2022-09-29 16:59:59",
    "bill": {
      "traded": 86.57275,
      "energy_load": 0
    },
    "usage": {
      "traded": 1731.455,
      "energy_load": 0
    }
  },
  {
    "startDate": "2022-09-30 17:00:00",
    "endDate": "2022-09-30 16:59:59",
    "bill": {
      "traded": 58.86055,
      "energy_load": 0
    },
    "usage": {
      "traded": 1177.211,
      "energy_load": 0
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
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-01-31 17:00:00",
      "endDate": "2020-02-28 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-02-28 17:00:00",
      "endDate": "2020-03-31 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-03-31 17:00:00",
      "endDate": "2020-04-30 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-04-30 17:00:00",
      "endDate": "2020-05-31 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-05-31 17:00:00",
      "endDate": "2020-06-30 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-06-30 17:00:00",
      "endDate": "2020-07-31 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-07-31 17:00:00",
      "endDate": "2020-08-31 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-08-31 17:00:00",
      "endDate": "2020-09-30 16:59:59",
      "bill": {
        "traded": 2314.8519,
        "energy_load": 0
      },
      "usage": {
        "traded": 46297.038,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-09-30 17:00:00",
      "endDate": "2020-10-31 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    },
    {
      "startDate": "2020-10-31 17:00:00",
      "endDate": "2020-11-30 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0 
      }
    },
    {
      "startDate": "2020-11-30 17:00:00",
      "endDate": "2020-12-31 16:59:59",
      "bill": {
        "traded": 0,
        "energy_load": 0
      },
      "usage": {
        "traded": 0,
        "energy_load": 0
      }
    }
  ]
}
```


## Outstanding Invoices

``
api/consumer/{consumer_id}/invoices?meterType=1
``


```json
{
	"meterType": "1",
	"data": [{
		"startDate": "2022-08-31 17:00:00",
		"endDate": "2020-09-30 16:59:59",
		"total_cost": 2350,
		"traded": {
			"name": "traded",
			"cost": "2350",
			"rec": 47,
			"allocation": "46297.038"
		},
		"open_market": {
			"name": "open_market",
			"cost": "0",
			"rec": 0,
			"allocation": "0"
		}
	}]
}

```



## Paid Invoices

``
api/consumer/{consumer_id}/invoices?meterType=1
``


```json
{
	"meterType": "1",
	"data": [{
		"startDate": "2022-08-31 17:00:00",
		"endDate": "2020-09-30 16:59:59",
		"payment_status": "paid",
		"payment": 2350
	}]
}

```


## 24/7 CFE Daily Tracking


``
api/consumer/{consumer_id}/daily-tracking?date=2020-11-12&meterType=1
``


```json
{
  "meterType": "1",
  "data": {
    "startDate": "2020-10-31 17:00:00",
    "endDate": "2020-11-01 16:59:59",
    "bill": [
      {
        "traded": {
          "name": "traded",
          "cost": "2350",
          "rec": 47,
          "allocation": "46297.038"
        },
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      }
    ],
    "transactions": [
      {
        "startDate": "2022-08-31 17:00:00 17:00:00",
        "endDate": "2022-08-31 17:00:00 16:59:59",
        "usagePerPeriod": 70.53,
        "billPerPeriod": 3.5265,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.5265",
            "rec": 0,
            "allocation": "70.53"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-08-31 18:00:00 17:00:00",
        "endDate": "2022-08-31 18:00:00 16:59:59",
        "usagePerPeriod": 65.483,
        "billPerPeriod": 3.27415,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.27415",
            "rec": 0,
            "allocation": "65.483"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-08-31 19:00:00 17:00:00",
        "endDate": "2022-08-31 19:00:00 16:59:59",
        "usagePerPeriod": 66.941,
        "billPerPeriod": 3.34705,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.34705",
            "rec": 0,
            "allocation": "66.941"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-08-31 20:00:00 17:00:00",
        "endDate": "2022-08-31 20:00:00 16:59:59",
        "usagePerPeriod": 61.236,
        "billPerPeriod": 3.0618,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.0618",
            "rec": 0,
            "allocation": "61.236"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-08-31 21:00:00 17:00:00",
        "endDate": "2022-08-31 21:00:00 16:59:59",
        "usagePerPeriod": 76.631,
        "billPerPeriod": 3.83155,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.83155",
            "rec": 0,
            "allocation": "76.631"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-08-31 22:00:00 17:00:00",
        "endDate": "2022-08-31 22:00:00 16:59:59",
        "usagePerPeriod": 75.317,
        "billPerPeriod": 3.76585,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.76585",
            "rec": 0,
            "allocation": "75.317"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-08-31 23:00:00 17:00:00",
        "endDate": "2022-08-31 23:00:00 16:59:59",
        "usagePerPeriod": 72.857,
        "billPerPeriod": 3.64285,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.64285",
            "rec": 0,
            "allocation": "72.857"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 00:00:00 17:00:00",
        "endDate": "2022-09-01 00:00:00 16:59:59",
        "usagePerPeriod": 85.789,
        "billPerPeriod": 4.28945,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "4.28945",
            "rec": 0,
            "allocation": "85.789"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 01:00:00 17:00:00",
        "endDate": "2022-09-01 01:00:00 16:59:59",
        "usagePerPeriod": 83.914,
        "billPerPeriod": 4.1957,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "4.1957",
            "rec": 0,
            "allocation": "83.914"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 02:00:00 17:00:00",
        "endDate": "2022-09-01 02:00:00 16:59:59",
        "usagePerPeriod": 55.505,
        "billPerPeriod": 2.77525,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "2.77525",
            "rec": 0,
            "allocation": "55.505"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 03:00:00 17:00:00",
        "endDate": "2022-09-01 03:00:00 16:59:59",
        "usagePerPeriod": 67.807,
        "billPerPeriod": 3.39035,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.39035",
            "rec": 0,
            "allocation": "67.807"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 04:00:00 17:00:00",
        "endDate": "2022-09-01 04:00:00 16:59:59",
        "usagePerPeriod": 24.276,
        "billPerPeriod": 1.2138,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "1.2138",
            "rec": 0,
            "allocation": "24.276"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 05:00:00 17:00:00",
        "endDate": "2022-09-01 05:00:00 16:59:59",
        "usagePerPeriod": 28.425,
        "billPerPeriod": 1.42125,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "1.42125",
            "rec": 0,
            "allocation": "28.425"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 06:00:00 17:00:00",
        "endDate": "2022-09-01 06:00:00 16:59:59",
        "usagePerPeriod": 57.717,
        "billPerPeriod": 2.88585,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "2.88585",
            "rec": 0,
            "allocation": "57.717"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 07:00:00 17:00:00",
        "endDate": "2022-09-01 07:00:00 16:59:59",
        "usagePerPeriod": 97.128,
        "billPerPeriod": 4.8564,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "4.8564",
            "rec": 0,
            "allocation": "97.128"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 08:00:00 17:00:00",
        "endDate": "2022-09-01 08:00:00 16:59:59",
        "usagePerPeriod": 89.764,
        "billPerPeriod": 4.4882,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "4.4882",
            "rec": 0,
            "allocation": "89.764"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 09:00:00 17:00:00",
        "endDate": "2022-09-01 09:00:00 16:59:59",
        "usagePerPeriod": 66.419,
        "billPerPeriod": 3.32095,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.32095",
            "rec": 0,
            "allocation": "66.419"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 10:00:00 17:00:00",
        "endDate": "2022-09-01 10:00:00 16:59:59",
        "usagePerPeriod": 72.737,
        "billPerPeriod": 3.63685,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.63685",
            "rec": 0,
            "allocation": "72.737"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 11:00:00 17:00:00",
        "endDate": "2022-09-01 11:00:00 16:59:59",
        "usagePerPeriod": 77.674,
        "billPerPeriod": 3.8837,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.8837",
            "rec": 0,
            "allocation": "77.674"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 12:00:00 17:00:00",
        "endDate": "2022-09-01 12:00:00 16:59:59",
        "usagePerPeriod": 91.159,
        "billPerPeriod": 4.55795,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "4.55795",
            "rec": 0,
            "allocation": "91.159"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 13:00:00 17:00:00",
        "endDate": "2022-09-01 13:00:00 16:59:59",
        "usagePerPeriod": 91.94,
        "billPerPeriod": 4.597,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "4.597",
            "rec": 0,
            "allocation": "91.94"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 14:00:00 17:00:00",
        "endDate": "2022-09-01 14:00:00 16:59:59",
        "usagePerPeriod": 71.682,
        "billPerPeriod": 3.5841,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.5841",
            "rec": 0,
            "allocation": "71.682"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 15:00:00 17:00:00",
        "endDate": "2022-09-01 15:00:00 16:59:59",
        "usagePerPeriod": 71.961,
        "billPerPeriod": 3.59805,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.59805",
            "rec": 0,
            "allocation": "71.961"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      },
      {
        "startDate": "2022-09-01 16:00:00 17:00:00",
        "endDate": "2022-09-01 16:00:00 16:59:59",
        "usagePerPeriod": 76.902,
        "billPerPeriod": 3.8451,
        "numberOfProviders": 1,
        "traded": [
          {
            "name": "Naresuan Hydro",
            "cost": "3.8451",
            "rec": 0,
            "allocation": "76.902"
          }
        ],
        "energy_load": {
          "name": "energy_load",
          "cost": "0",
          "rec": 0,
          "allocation": "0"
        }
      }
    ]
  }
}
```