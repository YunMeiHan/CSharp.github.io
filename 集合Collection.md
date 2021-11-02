# 集合
> namespace System.Collections          非泛型
> namespace System.Collections.Generic  泛型
## [IEnumerator](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.ienumerator?view=net-5.0)
> 作为一个只读迭代器iterator, 配合IEnumerable使用以支持循环迭代(foreach),也是其唯一方法的返回类型
```CSharp
object Current { get; }
bool MoveNext();
void Reset();                       //用于 COM 互操作性，无需完全实现; 相反，实施者可以引发 NotSupportedException 。
```
## [IEnumerator\<T>](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.ienumerator-1?view=net-5.0) :  IEnumerator, IDisposable
```CSharp
T Current { get; }
```
## [IEnumerable](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.ienumerable?view=net-5.0)
> 支持foreach, yield
```CSharp
IEnumerator GetIEnumerator();
```
# [IEnumerable\<T>](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.ienumerable-1?view=net-5.0) : IEnumerable
```CSharp
IEnumerator<T> GetIEnumerator();
```
# [ICollection](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.icollection?view=net-5.0) : IEnumerable
> 定义集合的大小、实现集合的复制
```CSharp
int Count { get; }
bool IsSynchronized { get; }          //获取一个值，该值指示是否同步对 ICollection 的访问（线程安全）
object SyncRoot { get; }              //获取可用于同步对 ICollection 的访问的对象。
void CopyTo (Array, int);             //从特定的 ICollection 索引开始，将 Array 的元素复制到一个 Array 中。
```
## [ICollection\<T>](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.icollection-1?view=net-5.0) : IEnumerable<T>, IEnumerable
```CSharp
bool IsReadOnly { get; }
void Add (T);
void Clear();
bool Contains (T);
void CopyTo (T[], int);
bool Remove(T);
```
# IList : ICollection
支持按索引访问
Add(Object)
Clear()
Contains(Object)
IndexOf(Object)
Insert(int, Object)
Remove(Object)
RemoveAt(int)
