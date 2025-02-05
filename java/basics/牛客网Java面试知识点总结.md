1. `static`的执行顺序问题。在JVM调用mian方法之前先用进行静态内容的初始化。顺序为：父类的静态变量， 父类的静态代码块 ，子类的静态变量，子类的静态代码块。





# 异常处理

1. Java异常都继承自类`Throwable`，`Throwable`子类有`Error`和`Exception`，其中`Exception`又分为运行时异常和编译时异常。运行异常，可以通过java虚拟机来自行处理。非运行异常（编译时异常），应该捕获或者抛出。

![img](https://gitee.com/koala010/typora/raw/master/img/Java异常处理图.png)

2. Java语言中的异常处理包括声明异常、抛出异常、捕获异常和处理异常四个环节。

   ①throw用于抛出异常。

   ②throws关键字可以在方法上声明该方法要抛出的异常，然后在方法内部通过throw抛出异常对象。

   ③try是用于检测被包住的语句块是否出现异常，如果有异常，则抛出异常，并执行catch语句。

   ④cacth用于捕获从try中抛出的异常并作出处理。

   ⑤finally语句块是不管有没有出现异常都要执行的内容。



# 事务

> 原子性：事务是一组不可分割的操作单元，这组单元要么同时成功要么同时失败（由DBMS的==事务管理子系统==来实现）；
> 一致性：事务前后的数据完整性要保持一致（由DBMS的==完整性子系统==执行测试任务）；
> 隔离性:多个用户的事务之间不要相互影响，要相互隔离（由DBMS的==并发控制子系统==实现）；
> 持久性:一个事务一旦提交，那么它对数据库产生的影响就是永久的不可逆的，如果后面再回滚或者出异常，都不会影响已提交的事务（由DBMS的==恢复管理子系统==实现的）