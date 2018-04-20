#避免冗余代码

##接口中的访问修饰符
接口中的所有方法都是公共的, 所以在接口方法声明中加上 public 是完全没有必要的

##this修饰符
this 修饰符是用来区分重名变量或方法的. 除此之外, 其他地方使用 this, 不仅没有任何意义, 反而显得不够美观.

##使用diamond表达式
在 JDK 7 以后, 定义泛型不需要重复指明泛型类型了.
例如:
```
// List<Integer> list = new ArrayList<Integer>(); deprecated
List<Integer> list = new ArrayList<>();
```

##利用逻辑表达式的返回值
每个逻辑表达式都有返回值, 要么是 true, 要么是 false. 如果想保存或返回布尔类型值, 不需要用 **if** 来判断.
例如:
```
/*
redundance
if (a > b) {
flag = true;
} else {
flag = false;
}
*/
        
flag = a > b;
```
