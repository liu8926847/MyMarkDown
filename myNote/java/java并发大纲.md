## 一.Java 多线程知识点总结

### 1.1.多线程基础

1. 什么是线程和进程? 线程与进程的关系,区别及优缺点？
2. 说说并发与并行的区别?
3. 为什么要使用多线程呢?
4. 使用多线程可能带来什么问题?（内存泄漏、死锁、线程不安全等等）
5. 创建线程有哪几种方式？（a.继承 Thread 类;b.实现 Runnable 接口;c. 使用 Executor 框架;d.使用 FutureTask）
6. 说说线程的生命周期和状态?
7. 什么是上下文切换?
8. 什么是线程死锁?如何避免死锁?
9. 说说 sleep() 方法和 wait() 方法区别和共同点?
10. 为什么我们调用 start() 方法时会执行 run() 方法，为什么我们不能直接调用 run() 方法？
11. ......

### 1.2.多线程知识进阶

#### volatile 关键字

1. Java 内存模型（**JMM**）;
2. 重排序与 happens-before 原则了解吗?
3. volatile 关键字的作用;
4. 说说 synchronized 关键字和 volatile 关键字的区别;
5. ......

#### ThreadLocal

1. 有啥用（解决了什么问题）？怎么用？
2. 原理了解吗？
3. 内存泄露问题了解吗？

#### 线程池

1. 为什么要用线程池？
2. 你会使用线程池吗？
3. 如何创建线程池比较好？ （推荐使用 `ThreadPoolExecutor` 构造函数创建线程池）
4. `ThreadPoolExecutor` 类的重要参数了解吗？`ThreadPoolExecutor` 饱和策略了解吗？
5. 线程池原理了解吗？
6. 几种常见的线程池了解吗？为什么不推荐使用`FixedThreadPool`？
7. 如何设置线程池的大小？
8. ......

#### AQS

1. 简介
2. 原理
3. AQS 常用组件。
   - **Semaphore(信号量)**-允许多个线程同时访问
   - **CountDownLatch （倒计时器）**-CountDownLatch 允许 count 个线程阻塞在一个地方，直至所有线程的任务都执行完毕。
   - **CyclicBarrier(循环栅栏)**-CyclicBarrier 和 CountDownLatch 非常类似，它也可以实现线程间的技术等待，但是它的功能比 CountDownLatch 更加复杂和强大。主要应用场景和 CountDownLatch 类似。
   - **ReentrantLock 和 ReentrantReadWriteLock**
   - ......

#### 锁

锁的常见分类

1. 可重入锁和非可重入锁
2. 公平锁与非公平锁
3. 读写锁和排它锁

**synchronized 关键字**

1. 说一说自己对于 synchronized 关键字的了解；
2. 说说自己是怎么使用 synchronized 关键字，在项目中用到了吗;
3. 讲一下 synchronized 关键字的底层原理；
4. 说说 JDK1.6 之后的 synchronized 关键字底层做了哪些优化，可以详细介绍一下这些优化吗；
5. 谈谈 synchronized 和 ReentrantLock 的区别；
6. ......

**ReentrantLock 和 ReentrantReadWriteLock**

**ReadWriteLock**

**StampedLock（JDK8）**

#### **Atomic 与 CAS**

**CAS:**

1. 介绍
2. 原理

**Atomic 原子类：**

1. 介绍一下 Atomic 原子类；
2. JUC 包中的原子类是哪 4 类?；
3. 讲讲 AtomicInteger 的使用；
4. 能不能给我简单介绍一下 AtomicInteger 类的原理。
5. ......

#### 并发容器

JDK 提供的这些容器大部分在 `java.util.concurrent` 包中。

- **ConcurrentHashMap:** 线程安全的 HashMap
- **CopyOnWriteArrayList:** 线程安全的 List，在读多写少的场合性能非常好，远远好于 Vector.
- **ConcurrentLinkedQueue:** 高效的并发队列，使用链表实现。可以看做一个线程安全的 LinkedList，这是一个非阻塞队列。
- **BlockingQueue:** 这是一个接口，JDK 内部通过链表、数组等方式实现了这个接口。表示阻塞队列，非常适合用于作为数据共享的通道。
- **ConcurrentSkipListMap:** 跳表的实现。这是一个 Map，使用跳表的数据结构进行快速查找。
- ......

#### Future 和 CompletableFuture