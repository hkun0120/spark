# spark
关于spark的项目，学历笔记以及其他spark相关
# 集群配置
    1、pd搭建5台centos虚拟机集群，分别为master，master2，spark001，spark002，spark003
    2、集群分布
      spark1.4.0：master、spark001、spark002
      hadoop2.5.2：master(nn1)、master2(nn2)、spark001、spark002、spark003
      zookeeper3.4.6:master、spark001、spark002
      kafka_2.10-0.8.2.1:master、spark001、spark002
# 测试kafka集群
     ./kafka-server-start.sh ../config/server.properties &
     bin/kafka-console-prucer.sh --topic car_events --broker-list master:9092
     ./kafka-console-consumer.sh --topic car_events --zookeeper master:2181 --from-beginning
     
# 测试spark集群
    bin/spark-shell --help  
    bin/spark-shell --master spark://10.211.55.10:7077 //在运行集群，指定master即spark的standalone模式
