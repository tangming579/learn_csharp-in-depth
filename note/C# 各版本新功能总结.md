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

#### 2.4 Lambda表达式

```
Func<int, int> square = x=> x*x;
Console.WriteLine(square(5));
```

#### 2.5 表达式树

表达式树以树形数据结构表示代码，其中每一个节点都是一种表达式，它将我们原来可以直接由代码编写的逻辑以表达式的方式存储在树状的结构里，从而可以在运行时去解析这个树，然后执行，实现动态的编辑和执行代码。在.Net 里面的Linq to SQL就是对表达式树的解析。

#### 2.6 扩展方法

扩展方法可以用新方法扩展现有类型改变原始类型的定义。扩展方法是静态类的静态方法，其中this修饰符应用于第一个参数。第一个参数的类型将是扩展的类型。

#### 2.7 分部方法

通常我们会使用工具来生成分部方法的声明，要用partial关键字标记，无主体。然后开发者会实现这个声明，也需要用partial关键字标记，有主体。
分部方法有一个性能优势在于如果没有实现分部方法，编译器不会生成任何代表分部方法的元数据。此外，编译器不会生成任何调用分部方法的IL指令。

```csharp
partial class A
{
    // 分部方法的声明
    partial void DoSomething(string s);
}
partial class B
{
    partial void DoSomething(string s)
    {
        Console.WriteLine(s);
    }
}
```

### 3. C# 4.0版 - 2010

#### 3.1 dynamic

该特性使得 CLR 不得不进行一次修改。使C#也能像 js、php、python等弱类型语言一样写代码：

```csharp
dynamic a = 3;
a = 3.14;
a = "Hello";
a = new[] {1,2,3};
```

#### 3.2 命名参数/可选参数

*命名实参*，你可以为特定形参指定实参，方法是将实参与该形参的名称关联，而不是与形参在形参列表中的位置关联。可选参数，你可以为某些形参省略实参。 这两种技术都可与方法、索引器、构造函数和委托一起使用。

```

```

