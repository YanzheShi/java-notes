#数字精度的控制
处理小数时，Java 默认的类型是 double。但是 double 类型在做乘除运算时，得到的结果可能会与期望有些差距。例如 1.0 可能会变成 0.9999 。

所以做乘除运算时，一般是将 double 类型转化为 BigDecimal 后，再调用相应的方法计算。

需要说明的是， 将 double 转化为 BigDecimal 时，推荐使用工厂方法
`BigDecimal.valueOf()` 而不是构造方法 `new BigDecimal()` 。因为使用工厂方法效率更高。**而且如果直接使用 double 类型值构造    BigDecimal 时， 得到的 BigDecimal 并不一定与原来的 double 值相等。**

另外，BigDecimal的除法， 要指定scale， 即小数位数， 否者会出现**ArithmeticException**异常