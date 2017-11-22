1、两个都是Quartz非常好的demo
2、quartz-spring-demo-master.zip没有做集群化处理，也就是任务存储在 ram里 jobstore
	spring-quartz-cluster-sample-master.zip,做了集群化处理,任务存储在数据库里 jobstore

3、quartz-spring-demo-master job是implements jos 来定义job,并且对 方法执行回调做反射封装，
 spring-quartz-cluster-sample-master job 是继承 spring的QuartzJobBean来定义的，没有对方法回调做封装
 二者容器一启动都会查询数据库重新装载job
 如果做实际应用把二者结合一样，重新做下