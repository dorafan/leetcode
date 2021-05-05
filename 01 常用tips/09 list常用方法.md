<img src="02-1 Arraylist.assets/image-20210419021200211.png" alt="image-20210419021200211" style="zoom:50%;" />

### List接口常用方法：

1、add(Object element)： 向列表的尾部添加指定的元素。

2、size()： 返回列表中的元素个数。

3、get(int index)： 返回列表中指定位置的元素，index从0开始。

4、add(int index, Object element)： 在列表的指定位置插入指定元素。

5、set(int i, Object element)： 将索引i位置元素替换为元素element并返回被替换的元素。

6、clear()： 从列表中移除所有元素。

7、isEmpty()： 判断列表是否包含元素，不包含元素则返回 true，否则返回false。

8、contains(Object o)： 如果列表包含指定的元素，则返回 true。

9、remove(int index)： 移除列表中指定位置的元素，并返回被删元素。

10、remove(Object o)： 移除集合中第一次出现的指定元素，移除成功返回true，否则返回false。

11、iterator()： 返回按适当顺序在列表的元素上进行迭代的迭代器。

ArrayList一样可以使用List的所有方法，所以以ArrayList来演示：

**方法使用：**
1、add(Object element) 向列表的尾部添加指定的元素。
2、size() 返回列表中的元素个数。
3、get(int index) 返回列表中指定位置的元素，index从0开始。
4、add(int index, Object element) 在列表的指定位置（从0开始）插入指定元素。



### LinkedList新增方法

void addFirst(Object o) 将指定数据元素插入此集合的开头,原来元素（如果有）后移
void addLast(Object o) 将指定数据元素插入此集合的结尾
Object getFirst() 返回此集合的第一个数据元素
Object getLast() 返回此集合的最后一个数据元素
Object removeFirst() 移除并返回集合表的第一个数据元素
Object removeLast() 移除并返回集合表的最后一个数据元素





### ArrayList线性表与数组的区别

#### 声明ArrayList线性表与数组的区别:

1 两者本质的区别在与长度是否可变：数组是定长有序的线性集合；线性表是任意长度的线性集合
2 两者添加元素的方式不同：数组使用下标：array [index]；数组线性表使用add方法：list.add(value)
3 两者获取元素的方式不同：数组使用下标：array [index]；数组线性表使用get方法：list.get(index)
4 获取长度的方式不同：数组使用length属性；数组线性表使用size()方法

ArrayList是基于动态数组存储的数组线性表数据结构，使用连续的内存单元存储数据元素，对元素的遍历速度较快，LinkedList在遍历集合元素方面比较慢，因为在遍历过程中需要找寻下个元素的地址；

LinkedList是使用指针关联的双向链表数据结构，前一个元素都记录了后一个元素的地址，后一个元素也记录了前一个元素的地址，当添加或删除数据元素时，LinkedList比较快，因为ArrayList需要移动其被添加（或删除）元素后面（最后一个除外）的全部元素；
