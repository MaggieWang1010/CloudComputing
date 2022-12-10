# Kafka + Spark Streaming + PySpark
![image](https://user-images.githubusercontent.com/55336314/206823704-11b072ca-a0ad-43d8-9443-189dd28beb17.png)

## Step 1: Set up PySpark on GCP (Kafka + Spark)
![image](https://user-images.githubusercontent.com/55336314/206823743-e7f46e6b-1b4e-408c-b334-0e49d4927fe7.png)
![image](https://user-images.githubusercontent.com/55336314/206823760-a8255349-57e8-47f6-ba75-0388df033201.png)

## Step 2: Create two Kafka Topics (input_event and output_event)
$ cd kafka_2.12-3.3.1/
$ bin/kafka-topics.sh --create --topic input_event --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1
$ bin/kafka-topics.sh --create --topic output_event --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1
## Step 3: Create consumer.py, then run it 
## Step 4: Create producer.py, then run it
## Step 5: Running spark_processor.py

---
More on Google slides [Slides](https://docs.google.com/presentation/d/1g_GliOsjGzCb2gdNcClvWx-7j8VjZxtCyNuMeBczPls/edit?usp=sharing)
