#科学计数法数字的转化


##1. 如何将科学计数法字符串转化为整数类型

在声明 double 或者 float 类型的时候， 支持科学计数法。但是在新建 Double 实例的时候去无法直接转化例如：

```
//科学计算法赋值
double a =  4.2233653E-2;

//但无法将科学计数法字符串直接转化为数值
String s = "4.2233653E-2";
double b = new Double(s);

```