1 线程模型
   1.1 单线程
       创建服务端ServerBootStrap调用group方法传入的NioEventGroup对象为同一个，且构造函数传入线程数为1；
   1.2 多线程
       创建服务端ServerBootStrap调用group方法传入的NioEventGroup对象不同，分别进行监听和业务处理，监听对象线程数为1，而业务处理线程组线程数为多个线程；
       该类型适合客户端少，长连接情况。
   1.3 主从多线程
       创建服务端ServerBootStrap调用group方法传入的NioEventGroup对象不同，分别进行监听和业务处理，监听线程组和业务处理线程组线程数均为多个；
       该类型适合客户端多，长连接情况。