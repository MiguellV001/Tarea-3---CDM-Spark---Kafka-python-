# Tarea-3---CDM-Spark---Kafka-python-
Python descripción

Repositorio de Código Fuente del proyecto en GitHub. Instrucciones de ejecución:

1. Instalamos mediante PIP la librería de Python Kafka 
- pip install kafka-python

2. Descargue, descomprima y mueva de carpeta Apache Kafka 
- wget https://downloads.apache.org/kafka/3.7.2/kafka_2.12-3.7.2.tgz
- tar -xzf kafka_2.12-3.7.2.tgz 
- sudo mv kafka_2.12-3.7.2 /opt/Kafka 

3. Iniciamos el servidor ZooKeeper: 
- sudo /opt/Kafka/bin/zookeeper-server-start.sh /opt/Kafka/config/zookeeper.properties &

4. Iniciamos el servidor Kafka: 
- sudo /opt/Kafka/bin/kafka-server-start.sh /opt/Kafka/config/server.properties &

5. Creamos un tema (topic) de Kafka, el tema se llamará sensor_data 
- /opt/Kafka/bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic sensor_data

6. Implementación del productor(producer) de Kafka 
- Ejecutar el codigo nano kafka_producer.py

7. Implementación del consumidor con Spark Streaming 
- Ejecutar el código nano spark_streaming_consumer.py 

8. Ejecución y análisis
- python3 kafka_producer.py 
- spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.5.3 spark_streaming_consumer.py

9. http://your-server-ip:4040
- http://192.168.101.21:4040/jobs/
