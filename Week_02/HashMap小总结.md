## HashMap 的小总结

哈希表（Hash table），也叫散列表，是根据关键码值（Key value）而直接进行访问的数据结构。 

它通过把关键码值映射到表中一个位置来访问记录，以加快查找的速度。 

<u>这个映射函数叫作 散列函数（Hash Function），存放记录的数组叫作  哈希表（或散列表）。</u>

#### 散列函数（Hash Function）作用：

![](https://p0.ssl.qhimg.com/t01dc04e29db8ab1693.png)

相同对象的hashCode一定是相同的，但相同的hashCode不一定是相同的对象。



#### 散列函数（Hash Function）的Hash冲突：

![](https://p5.ssl.qhimg.com/t011e38a327d7fd598c.png)



##### 拉链地址法解决冲突

###### Java 8中使用平衡树来替代链表存储冲突的元素，性能从O(n)提高到O(logn)。

##### 采用这些解决冲突的其他数据结构

HashMap，HashSet，LinkedHashSet，LinkedHashMap，ConcurrentHashMap，HashTable，IdentityHashMap和WeakHashMap



##### HashTable 退化表现：

当size太小或空间太小，经常发生碰撞💥，就会退化为链表，发生最坏的复杂度O(n)

退化成链表的话，性能从O(1)降低到O(n)



##### 链表到平衡树改进意义：

1、O（n）到 O（logn）的时间时间复杂度。

2、恶意攻击Hash算法，在纯链表情况下，大量导致哈希碰撞，不停访问这些key导致HashMap忙于进行线性查找，最终陷入瘫痪，即形成了拒绝服务攻击（DoS）。