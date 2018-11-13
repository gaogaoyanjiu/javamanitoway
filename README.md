# javamanitoway  JAVA 大神 之路

电商

1、后台系统  一般是异步更新缓存

2、前台系统  一般是多级缓存抵抗高并发（nginx缓存、redis分布式缓存、ehcache本地堆缓存）

3、监控系统

4、系统保护

5、网络安全

6、项目部署

7、数据库设计  mysql 主从复制（一主多从，读写分离）
  |
  |___索引优化
  |
  |———存储过程、存储函数
  |
  |___sql优化
  |
  |___慢查询
  
 8、系统熔断保护
 
 
 9、分布式系统的问题
 
 
10、事务
 
 |
 |----数据库事务的几个特性：原子性(Atomicity )、一致性( Consistency )、隔离性或独立性( Isolation)和持久性(Durabilily)，简称就是ACID。
 |
 |----分布式事务的CAP定理 
      一致性(Consistency) ： 客户端知道一系列的操作都会同时发生(生效)
      可用性(Availability) ： 每个操作都必须以可预期的响应结束
      分区容错性(Partition tolerance) ： 即使出现单个组件无法可用,操作依然可以完成。
      具体地讲在分布式系统中，在任何数据库设计中，一个Web应用至多只能同时支持上面的两个属性。显然，任何横向扩展策略都要依赖于数据分区。因此，设计人员必须在一致性与可用性之间做出选择。
 
 |
 |---BASE理论
 |
 |BASE理论指的是：
     Basically Available（基本可用）
     Soft state（软状态）
     Eventually consistent（最终一致性）
     BASE理论是对CAP中的一致性和可用性进行一个权衡的结果，理论的核心思想就是：我们无法做到强一致，但每个应用都可以根据自身的业务特点，采用适当的方式      来使系统达到最终一致性（Eventual consistency）。
     
 在分布式系统中，要实现分布式事务，无外乎那几种解决方案。
    一、两阶段提交（2PC）
    二、补偿事务（TCC）
    三、本地消息表（异步确保）
    四、MQ 事务消息
    五、Sagas 事务模型


思考1：数据库是如何实现事务的？
    数据库是由两个文件组成的，一个数据库文件和一个日志文件，通常情况下，日志文件都要比数据库文件大很多。数据库进行任何写入操作的时候都是要先写日志       的，同样的道理，我们在执行事务的时候数据库首先会记录下这个事务的redo操作日志，然后才开始真正操作数据库，在操作之前首先会把日志文件写入磁盘，那么     当突然断电的时候，即使操作没有完成，在重新启动数据库时候，数据库会根据当前数据的情况进行undo回滚或者是redo前滚，这样就保证了数据的强一致性。
    
思考2：    


设计模式：http://www.runoob.com/design-pattern/design-pattern-tutorial.html

单例模式：http://www.runoob.com/design-pattern/singleton-pattern.html


锁机制：悲观锁、乐观锁


hash算法：


区块链：

