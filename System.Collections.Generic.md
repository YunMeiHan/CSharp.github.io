# [`IEnumerator<T>`](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.ienumerator-1?view=net-5.0) :  `IEnumerator`, `IDisposable`
> 作为一个只读迭代器iterator, 配合IEnumerable使用以支持循环迭代(foreach),也是其唯一方法的返回类型
```CSharp
T Current { get; }
bool MoveNext();
void Reset();                   //用于 COM 互操作性，无需完全实现; 相反，实施者可以引发 NotSupportedException 。
```
# [`IEnumerable<T>`](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.ienumerable-1?view=net-5.0) : `IEnumerable`
> 支持`foreach`, `yield`
```CSharp
IEnumerator<T> GetIEnumerator();
```
# [`ICollection<T>`](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.icollection-1?view=net-5.0) : `IEnumerable<T>`
> 定义集合的大小、实现集合的复制、增删查清
```CSharp
int Count { get; }
bool IsSynchronized { get; }      //获取一个值，该值指示是否同步对 ICollection 的访问（线程安全）
object SyncRoot { get; }          //获取可用于同步对 ICollection 的访问的对象。
void CopyTo (Array, int);         //从特定的 ICollection 索引开始，将 Array 的元素复制到一个 Array 中。
bool IsReadOnly { get; }
void Add (T);
void Clear();
bool Contains (T);
void CopyTo (T[], int);
bool Remove(T);
```
## [`IList<T>`](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.ilist-1?view=net-5.0) : `ICollection<T>`
> 支持按索引访问,增删查清
```CSharp
bool IsReadOnly { get; }
void Add(T);
void Clear();
bool Contains(T);
void RemoveAt(int);
T Item[Int32];
int IndexOf(T);
void Insert(int, T);
void RemoveAt(int);
```
## [`List<T>`](https://docs.microsoft.com/zh-cn/dotnet/api/system.collections.generic.list-1?view=net-5.0#examples) : `IList`, `IList<T>`, `IReadOnlyList<T>`
> 完整的顺序集合支持
## [`Array`](https://docs.microsoft.com/zh-cn/dotnet/api/system.array?view=net-5.0) : `IList`, `ICloneable`, `IStructuralComparable`, `IStructuralEquatable`
> 标准数组(`arr[]`),固定容量
> 运行时额外实现`IList<T>`,`IReadOnlyList<T>`接口,添加、插入或删除元素的成员会引发`NotSupportedException`.
