#判断两个对象是否相等

在 JDK 1.7 之前， 判断两个对象相等一直使用的是该类的equls方法， 这样需要先判断该引用是否是空指针， 才能调用这个方法。 但是在JDK 1.7 开始， 增加了 Objects 工具类， 可以直接使用 Objects.equals()方法判断两个对象是否相等了。
```
//JDK 1.7 之前
if(a != null && a.equls(b)){
   ...
}

//JDK 1.7 之后
if(Object.equals(a, b)){
    ...
}
```