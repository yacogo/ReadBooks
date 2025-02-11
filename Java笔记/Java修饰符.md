修饰符可分为两类：
* 访问修饰符：
    * `default`修饰符：在同一包内可见，不使用任何修饰符
    * `private`修饰符：在同一类内可见
    * `public`修饰符：对所有类可见
    * `protected`修饰符：对同一包内的类和所有子类可见
    * **访问和继承**：
        * 父类中声明为 `public` 的方法在子类中也必须为 `public`
        * 父类中声明为 `protected` 的方法在子类中要么声明为 `protected`，要么声明为 `public`，不能声明为 `private`
        * 父类中声明为 `private` 的方法，不能够被继承
* 非访问修饰符：
    * `static`修饰符:
        * 静态变量：声明独立于对象的静态变量，无论一个类实例化多少对象，它的静态变量只有一份拷贝
        * 静态方法：声明独立于对象的静态方法。静态方法不能使用类的非静态变量。
    * `final`修饰符:
        * `final`变量：被显式地初始化并且只能初始化一次。被声明为 `final` 的对象的引用不能指向不同的对象。但是 `final` 对象里的数据可以被改变。也就是说 `final` 对象的引用不能改变，但是里面的值可以改变
        * `final`方法：可以被子类继承，但是不能被子类修改
        * `final` 类：不能被继承，没有类能够继承 `final` 类的任何特性
    * `abstract` 修饰符:
        * 抽象类：不能用来实例化对象，声明抽象类的唯一目的是为了将来对该类进行扩充
            * 一个类不能同时被 `abstract` 和 `final` 修饰。如果一个类包含抽象方法，那么该类一定要声明为抽象类，否则将出现编译错误。
            * 抽象类可以包含抽象方法和非抽象方法。
        * 抽象方法：抽象方法是一种没有任何实现的方法，该方法的的具体实现由子类提供
            * 抽象方法不能被声明成 final 和 static
            * 任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类
            * 如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法
    * `synchronized` 修饰符：`synchronized` 关键字声明的方法同一时间只能被一个线程访问
    * `transient` 修饰符：序列化的对象包含被 `transient` 修饰的实例变量时，java 虚拟机(JVM)跳过该特定的变量。该修饰符包含在定义变量的语句中，用来预处理类和变量的数据类型。
    ```
    public transient int limit = 55;   // 不会持久化
    public int b; // 持久化
    ```
    * `volatile` 修饰符:`volatile` 修饰的成员变量在每次被线程访问时，都强制从共享内存中重新读取该成员变量的值。而且，当成员变量发生变化时，会强制线程将变化值回写到共享内存。这样在任何时刻，两个不同的线程总是看到某个成员变量的同一个值


    
