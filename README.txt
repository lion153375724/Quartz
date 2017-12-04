工1、两个都是Quartz非常好的demo
2、quartz-spring-demo-master.zip没有做集群化处理，也就是任务存储在 ram里 jobstore
	spring-quartz-cluster-sample-master.zip,做了集群化处理,任务存储在数据库里 jobstore

3、quartz-spring-demo-master job是implements jos 来定义job,并且对 方法执行回调做反射封装，
 spring-quartz-cluster-sample-master job 是继承 spring的QuartzJobBean(一个类继承包中的QuartzJobBean类
         如：是一个抽象类需要重载executeInternal（JobExecutionContext）方法。这个方法是在时间到来时自动执行的方法)来定义的，没有对方法回调做封装
 二者容器一启动都会查询数据库重新装载job
 如果做实际应用把二者结合一样，重新做下
4、同步与异步执行：
	@DisallowConcurrentExecution 禁止并发执行多个相同定义的JobDetail, 这个注解是加在Job类上的, 但意思并不是不能同时执行多个Job, 
		而是不能并发执行同一个Job Definition(由JobDetail定义), 但是可以同时执行多个不同的JobDetail。
	@PersistJobDataAfterExecution 同样, 也是加在Job上,表示当正常执行完Job后, JobDataMap中的数据应该被改动, 以被下一次调用时用。
		当使用@PersistJobDataAfterExecution 注解时, 为了避免并发时, 存储数据造成混乱, 强烈建议把@DisallowConcurrentExecution注解也加上。