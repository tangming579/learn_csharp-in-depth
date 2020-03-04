## C# 各版本新功能总结

### 1. C# 2.0 - 2005

#### 1.1 泛型

```csharp
//泛型类
public class GenericList<T>
{
    public void Add(T input){}
}
public class TestGenericList
{
    private class ExapleClass {}
    static void Main()
    {
        GenericList<int> list1 = new GenericList<int>();
        GenericList<string> list2 = new GenericList<string>();
        GenericList<TestGenericList> list3 = new GenericList<TestGenericList>();
    }
}
```

#### 1.2 分部类型

拆分一个类、一个结构、一个接口或一个方法的定义到两个或更多的文件中是可能的。每个源文件包含类型或方法定义的一部分，编译应用程序时将把所有部分组合起来。

```csharp
public partial class Empolyee
{
    public void DoWork(){}
}
public partial class Empolyee
{
    public void HaveRest(){}
}
```

#### 1.3 匿名方法

**匿名方法**提供了一种将一段代码块作为委托参数的技术。顾名思义，匿名方法没有名字，只有方法主体。

```csharp
Func<int, int, int> sum = delegate(int a,int b) {return a + b;};
Console.WriteLine(sum(3,4));
```

#### 1.4 可空值类型

```
int? a = null;
```

#### 1.5 迭代器

```
foreach(var a in numbers)
{
	Console.WriteLine(a);
}
```

#### 1.6 协变与逆变

协变和逆变能够实现数组类型、委托类型和泛型类型参数的隐式引用转换。协变保留分配兼容性，逆变则与之相反。

```csharp
delegate Object MyCallback(FileStream s);
string SomeMethod(Stream s);
```

### 2. C# 3.0 - 2007

#### 2.1 自动属性

```
public string Name {get; private set;}
```

#### 2.2 匿名类型

```
var number = 5;
```

#### 2.3 LINQ

```csharp
from p in persons
    where p.Age >20
    select new 
{
    p.Name,
    p.Age
}
```

