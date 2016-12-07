# redisgametransaction
在大型游戏中经常使用分布式，分布式中因为游戏逻辑会经常游戏事务，借助redis某些特性我们可以实现分布式锁和分布式事务。很多redis集群不支持redis的事务特性。
这个框架用来解决分布式服务器下redis集群事务失效的情况下多线程分布式锁和分布式锁，让开发者可以有更多时间侧重游戏逻辑.

互斥锁使用例子 可参考test下的entity.

1.生成事务原因 GameTransactionCauseImpl里面构造.
2.生成锁实体 GameTransactionEntityFactoryImpl里面构造.
3.提交锁实体跟事务  transactionService.commitTransaction里面提交.
4.后去事务提交结果 根据返回值做出判断.

读取锁使用例子 可参考test下的read 可以设置默认是否成功读取到
1.生成读取事务原因 GameTransactionCause里面已经构造好了.
2.生成读取锁实体 GameTransactionEntityFactory里面已经构造好了.
3.提交读取锁实体跟事务  transactionService.commitTransaction里面提交.
4.后去事务提交结果 根据返回值做出判断.

代码最后通过ant打包,发布代码存在dist下
作者qq 330258845
QQ群310158485
