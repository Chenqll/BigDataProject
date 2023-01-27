# Basic data info
- use the flowing code to gain the basic info of data and show it below
```python
from pyspark.sql import SparkSession
# Start the SparkSession
spark = SparkSession.builder.appName("Basics").getOrCreate()
# Read people.json file
df = spark.read.parquet(r'D:\yellow_tripdata_2022-01.parquet')
# showing data
df.show(5)
# print schema
df.printSchema()
df.columns
df.describe()
```

- info

```bash
+--------+--------------------+---------------------+---------------+-------------+----------+------------------+------------+------------+------------+-----------+-----+-------+----------+------------+---------------------+------------+--------------------+-----------+
|VendorID|tpep_pickup_datetime|tpep_dropoff_datetime|passenger_count|trip_distance|RatecodeID|store_and_fwd_flag|PULocationID|DOLocationID|payment_type|fare_amount|extra|mta_tax|tip_amount|tolls_amount|improvement_surcharge|total_amount|congestion_surcharge|airport_fee|
+--------+--------------------+---------------------+---------------+-------------+----------+------------------+------------+------------+------------+-----------+-----+-------+----------+------------+---------------------+------------+--------------------+-----------+
|       1| 2022-01-01 08:35:40|  2022-01-01 08:53:29|            2.0|          3.8|       1.0|                 N|         142|         236|           1|       14.5|  3.0|    0.5|      3.65|         0.0|                  0.3|       21.95|                 2.5|        0.0|
|       1| 2022-01-01 08:33:43|  2022-01-01 08:42:07|            1.0|          2.1|       1.0|                 N|         236|          42|           1|        8.0|  0.5|    0.5|       4.0|         0.0|                  0.3|        13.3|                 0.0|        0.0|
|       2| 2022-01-01 08:53:21|  2022-01-01 09:02:19|            1.0|         0.97|       1.0|                 N|         166|         166|           1|        7.5|  0.5|    0.5|      1.76|         0.0|                  0.3|       10.56|                 0.0|        0.0|
|       2| 2022-01-01 08:25:21|  2022-01-01 08:35:23|            1.0|         1.09|       1.0|                 N|         114|          68|           2|        8.0|  0.5|    0.5|       0.0|         0.0|                  0.3|        11.8|                 2.5|        0.0|
|       2| 2022-01-01 08:36:48|  2022-01-01 09:14:20|            1.0|          4.3|       1.0|                 N|          68|         163|           1|       23.5|  0.5|    0.5|       3.0|         0.0|                  0.3|        30.3|                 2.5|        0.0|
+--------+--------------------+---------------------+---------------+-------------+----------+------------------+------------+------------+------------+-----------+-----+-------+----------+------------+---------------------+------------+--------------------+-----------+
only showing top 5 rows

root
 |-- VendorID: long (nullable = true)
 |-- tpep_pickup_datetime: timestamp (nullable = true)
 |-- tpep_dropoff_datetime: timestamp (nullable = true)
 |-- passenger_count: double (nullable = true)
 |-- trip_distance: double (nullable = true)
 |-- RatecodeID: double (nullable = true)
 |-- store_and_fwd_flag: string (nullable = true)
 |-- PULocationID: long (nullable = true)
 |-- DOLocationID: long (nullable = true)
 |-- payment_type: long (nullable = true)
 |-- fare_amount: double (nullable = true)
 |-- extra: double (nullable = true)
 |-- mta_tax: double (nullable = true)
 |-- tip_amount: double (nullable = true)
 |-- tolls_amount: double (nullable = true)
 |-- improvement_surcharge: double (nullable = true)
 |-- total_amount: double (nullable = true)
 |-- congestion_surcharge: double (nullable = true)
 |-- airport_fee: double (nullable = true)

                                                                                
Process finished with exit code 0

```