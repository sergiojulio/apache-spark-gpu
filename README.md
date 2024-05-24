 
spark-submit \  
--packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.2.3 \  
--conf spark.driver.extraJavaOptions="-Divy.cache.dir=/tmp -Divy.home=/tmp" \  
--driver-class-path postgresql-42.6.2.jar \  
--jars postgresql-42.6.2.jar,rapids-4-spark_2.12-24.04.0.jar,cudf-21.12.2-cuda11.jar \  
--master spark://spark:7077 \  
--deploy-mode client \  
--driver-memory 2g \  
--num-executors 2 \  
--executor-cores 4 \  
--executor-memory 2g \ 
./main.py
