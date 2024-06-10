install-spark:
	sudo wget https://archive.apache.org/dist/spark/spark-3.5.0/spark-3.5.0-bin-hadoop3.tgz --no-check-certificate
	mkdir /opt/spark
	mv spark-3.5.0-bin-hadoop3.tgz /opt/spark/
	tar -zxvf /opt/spark/spark-3.5.0-bin-hadoop3.tgz -C /opt/spark

install-python3:
	sudo yum install -y python3
	sudo unlink /usr/bin/python
	sudo ln -s /usr/bin/python3 /usr/bin/python

install-hive:
	/opt/hive/bin/schematool -initSchema -dbType mysql
	hdfs dfs -mkdir -p /user/hive/warehouse
	hdfs dfs -mkdir -p /tmp/hive
	hdfs dfs -chmod 777 /tmp/
	hdfs dfs -chmod 777 /user/hive/warehouse
	hdfs dfs -chmod 777 /tmp/hive
	/opt/hive/bin/hive --service hiveserver2

start-namenode:
	hdfs namenode &
	sleep 30

start-zeppelin:
	/opt/zeppelin/bin/zeppelin-daemon.sh start
