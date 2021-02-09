# String、StringBuffer、StringBuilder

（关键点：可变与不可变、线程安全与不安全）

**1.可变与不可变**


​		**String是不可变的。** 底层使用 private final char value[] 的字节数组保存字符串。因为有“final”修饰符，所以String对象是不可变的。String对象一旦被创建，就不能修改它的值。对一个String对象的修改都是重新创建一个新的对象，把值复制进去并把指针引用指向新的对象。

​		**StringBuffer与StringBuilder都是可变的。** 二者继承自AbstractStringBuilder类，其底层是使用char[] value的字符数组保存字符串。 

**2.线程安全与不安全**

​		**String对象是线程安全的。** 其对象是不可变的，可以理解为常量，显然安全。

​		**StringBuffer是线程安全的，StringBuilder是线程不安全的。**
​		StringBuffer对方法加了Synchronized同步锁或者对调用的方法加了同步锁，所以是线程安全的。StringBuilder并没有对方法加同步锁。

**3.性能分析：**
		每次对String类型进行改变的时候，都会生成一个新的String对象，然后将指针指向新的String对象
		StringBuffer每次都是对自身对象进行操作，而不是生成新的对象并改变对象的引用		
		相同情况下使用StringBuilder相比使用StringBuffer仅能获得10%~15%左右的性能提升，却要冒着多线程不安全的风险。

**总结：**
		操作少量数据，适合使用String
		单线程操作字符串缓冲区下大量数据，适合用StringBuilder
		多线程操作字符串缓冲区下大量数据，适合用StringBuffer