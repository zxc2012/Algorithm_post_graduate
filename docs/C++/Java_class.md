# Java Application Design--Class

## Primitive Data Types

|Type|Storage(bits)|Min Value|Max Value|
|-|-|-|-|
|byte|8|-128|127|
|short|16|$-2^{15}$|$2^{15}-1$|
|int|32|$-2^{31}$|$2^{31}-1$|
|long|64|$-2^{63}$|$2^{63}-1$|
|float|32|Approximately-3.4e+38 with 7 significant digits|Approximately3.4e+38 with 7 significant digits|
|double|64|Approximately-1.7e+308 with 15 significant digits|Approximately-1.7e+308 with 15 significant digits|

![vs](https://img-blog.csdnimg.cn/20201013163013271.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5MzgwMjMw,size_16,color_FFFFFF,t_70#pic_center)

## Cleanup:finalize()

When the garbage collector is ready to release the storage used for your object,it will first call its **finalize()**
But **finalize()** is totally different from destructor of C++:
- (1)Garbage collection is not destruction,it is only abour memory.
- (2)Your objects might not get garbage-collected.

## Order of Initialization

1.Staic members is to be initialized in the loading of the class,属于类的数据(C++全局)

2.When a new object is create,顺序:
- Allocate enough storage for an object on the heap.
- Setting **all** the primitives in the object to their default values.(Any initializations that occur at the point of field definition are executed.)
- Constructors are executed.

## Polymorphism

**Overriding**:子类定义与父类名称、返回值类型、参数列表完全相同的方法

**Overloading**:同一类中名称相同、参数列表不同的方法
Eg:

```java
System.out.println(true?Integer.valueOf(1):Double.valueOf(2))
//输出1.0,因为java是编译语言不是解释语言，编译器看到函数调用不会立即执行
//而是根据double确定println overload为double类型
```
## Object Class

|Function|Interpretion|
|-|-|
|public boolean equals(Object w)|判断两个对象变量是否指向同一个对象|
|public String toString()||
|public final Class getClass()||
|protected Object clone()|返回调用该方法的对象的一个副本|