��1����������Quartz�ǳ��õ�demo
2��quartz-spring-demo-master.zipû������Ⱥ������Ҳ��������洢�� ram�� jobstore
	spring-quartz-cluster-sample-master.zip,���˼�Ⱥ������,����洢�����ݿ��� jobstore

3��quartz-spring-demo-master job��implements jos ������job,���Ҷ� ����ִ�лص��������װ��
 spring-quartz-cluster-sample-master job �Ǽ̳� spring��QuartzJobBean(һ����̳а��е�QuartzJobBean��
         �磺��һ����������Ҫ����executeInternal��JobExecutionContext�������������������ʱ�䵽��ʱ�Զ�ִ�еķ���)������ģ�û�жԷ����ص�����װ
 ��������һ���������ѯ���ݿ�����װ��job
 �����ʵ��Ӧ�ðѶ��߽��һ������������
4��ͬ�����첽ִ�У�
	@DisallowConcurrentExecution ��ֹ����ִ�ж����ͬ�����JobDetail, ���ע���Ǽ���Job���ϵ�, ����˼�����ǲ���ͬʱִ�ж��Job, 
		���ǲ��ܲ���ִ��ͬһ��Job Definition(��JobDetail����), ���ǿ���ͬʱִ�ж����ͬ��JobDetail��
	@PersistJobDataAfterExecution ͬ��, Ҳ�Ǽ���Job��,��ʾ������ִ����Job��, JobDataMap�е�����Ӧ�ñ��Ķ�, �Ա���һ�ε���ʱ�á�
		��ʹ��@PersistJobDataAfterExecution ע��ʱ, Ϊ�˱��Ⲣ��ʱ, �洢������ɻ���, ǿ�ҽ����@DisallowConcurrentExecutionע��Ҳ���ϡ�