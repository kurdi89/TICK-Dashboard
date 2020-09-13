# Example of using Local files

> using a `.txt` file as an input for Telegraf

use cURL to download the `.txt` file to current dir:

```bash
curl https://s3.amazonaws.com/noaa.water-database/NOAA_data.txt -o NOAA_data.txt
```

Create a datbase in Influx using the influx CLI:

```bash
influx -precision rfc3339
CREATE DATABASE NOAA_water_database
exit
```

Write the data to the InflucxDB:

```bash
influx -import -path='NOAA_data.txt' -precision=s -database='NOAA_water_database'
```

inserting result

```bash
2020/09/13 17:12:19 Processed 1 commands
2020/09/13 17:12:19 Processed 76290 inserts
2020/09/13 17:12:19 Failed 0 inserts
```

Test the queries:

```bash
influx -precision rfc3339 -database NOAA_water_database
SHOW MEASUREMENTS
SELECT COUNT("water_level") FROM h2o_feet
SELECT * FROM h2o_feet LIMIT 10
```

output should be:

```bash
time                 level description    location     water_level
----                 -----------------    --------     -----------
2019-08-17T00:00:00Z below 3 feet         santa_monica 2.064
2019-08-17T00:00:00Z between 6 and 9 feet coyote_creek 8.12
2019-08-17T00:06:00Z below 3 feet         santa_monica 2.116
2019-08-17T00:06:00Z between 6 and 9 feet coyote_creek 8.005
2019-08-17T00:12:00Z below 3 feet         santa_monica 2.028
2019-08-17T00:12:00Z between 6 and 9 feet coyote_creek 7.887
2019-08-17T00:18:00Z below 3 feet         santa_monica 2.126
2019-08-17T00:18:00Z between 6 and 9 feet coyote_creek 7.762
2019-08-17T00:24:00Z below 3 feet         santa_monica 2.041
2019-08-17T00:24:00Z between 6 and 9 feet coyote_creek 7.635
2019-08-17T00:30:00Z below 3 feet         santa_monica 2.051
```
