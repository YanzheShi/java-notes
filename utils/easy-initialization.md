# 一种简单的初始化方式

一般的， 想设置一个静态集合成员（field），通常是先声明变量， 然后通过静态语句块来添加元素。类似这样：

```
    //先声明变量， 初始化为一个空集合
    public static Map<String, String> stringMap1 = new HashMap<>();

    //然后在静态语句块中给集合添加元素
    static {
        stringMap1.put("1", "2");
        stringMap1.put("2", "3");
    }
```

但是有一个更简洁的办法， 叫做双大括号初始化（ double brace initialzation \)。 例如：

```
    public static Map<String, String> stringMap = new HashMap<>(){{
        stringMap.put("a", "b");
        stringMap.put("b", "c");
    }};
```

乍一看， 确实比较陌生。 其实原理是利用了匿名类。  第一层花括号是表示声明一个继承HashMap的匿名内部类。 第二层花括号实际上是这个匿名内部类的构造方法块。 因为这个类没有名字， 所以构造方法直接是方法体。 可以换一种更好理解的形式：

```
    public static Map<String, String> stringMap = new HashMap<>() {
        {
            //构造方法
            stringMap.put("a", "b");
            stringMap.put("b", "c");
        }

        //可以添加其他实例方法
        public void method() {
            System.out.println("method");
        }
    };
```

双大括号初始化不仅可以用于静态成员的初始化， 还可以用于普通成员的初始化，已经方法调用中参数的初始化，局部变量的初始化等。由于机制是内部类， 他可能在效率上会稍微低一点。 另外它会影响代码的可读性。 所以类的成员变量初始化的时候可以使用（非静态成员变量初始化似乎只能用这种方式）， 不建议在其他地方使用。

需要说明的是，从JDK 9 

