1、sort(Collection)方法的使用(含义：对集合进行排序)。

```java
例：对已知集合c进行排序
              public class Practice {
                      public static void main(String[] args){
                                   List c = new ArrayList();
                                c.add("l");
                                c.add("o");
                               c.add("v");
                                c.add("e");
                              System.out.println(c);
                                Collections.sort(c);
                                System.out.println(c);
                        }
              }
        运行结果为：[l, o, v, e]
                  [e, l, o, v]  

```

2.reverse()方法的使用(含义：反转集合中元素的顺序)。

```java
public class Practice {
                    public static void main(String[] args){
                             
List list = Arrays.asList("one two three four five six siven".split(""));//无空格
          
System.out.println(list);
       
List list = Arrays.asList("one two three four five six siven".split("  "));//两个空格

System.out.println(list);
      List list = Arrays.asList("one two three four five six siven".split(" "));//一个空格
                            System.out.println(list);
                            Collections.reverse(list);
                           System.out.println(list);
                    }
          }

   运行结果为：
[o, n, e,  , t, w, o,  , t, h, r, e, e,  , f, o, u, r,  , f, i, v, e,  , s, i, x,  , s, i, v, e, n]                  
 [one two three four five six siven]
 [one, two, three, four, five, six, siven]
 [siven, six, five, four, three, two, one]
```

3.shuffle(Collection)方法的使用(含义：对集合进行随机排序)。

shuffle(Collection)的简单示例
           public class Practice {
                     public static void main(String[] args){
                                  List c = new ArrayList();
                             c.add("l");
                              c.add("o");
                              c.add("v");
                             c.add("e");
                                 System.out.println(c);
                               Collections.shuffle(c);
                             System.out.println(c);
                              Collections.shuffle(c);
                               System.out.println(c);
                        }
             }
            运行结果为：[l, o, v, e]
                              [l, v, e, o]
                              [o, v, e, l]
4.fill(List list,Object o)方法的使用(含义：用对象o替换集合list中的所有元素)

public class Practice {
                 public static void main(String[] args){
                            List m = Arrays.asList("one two three four five six siven".split(" "));
                         System.out.println(m);
                          Collections.fill(m, "青鸟52T25小龙");
                         System.out.println(m);
                  }
       }
     运行结果为：
                       [one, two, three, four, five, six, siven]
                       [青鸟52T25小龙, 青鸟52T25小龙, 青鸟52T25小龙, 青鸟52T25小龙, 青鸟52T25小龙, 青鸟52T25小龙, 青鸟52T25小龙]
5.copy(List m,List n)方法的使用(含义：将集合n中的元素全部复制到m中,并且覆盖相应索引的元素)。

 public class Practice {
                    public static void main(String[] args){
                            List m = Arrays.asList("one two three four five six siven".split(" "));
                            System.out.println(m);
                             List n = Arrays.asList("我 是 复制过来的哈".split(" "));
                             System.out.println(n);
                             Collections.copy(m,n);
                                System.out.println(m);
                      }
             }
   运行结果为：[one, two, three, four, five, six, siven]
                         [我, 是, 复制过来的哈]
                        [我, 是, 复制过来的哈, four, five, six, siven]
6.min(Collection),min(Collection,Comparator)方法的使用(前者采用Collection内含自然比较法，后者采用Comparator进行比较)。

public static void main(String[] args){
        List c = new ArrayList();
     c.add("l");
     c.add("o");
    c.add("v");
     c.add("e");
   System.out.println(c);
     System.out.println(Collections.min(c));
}
运行结果：[l, o, v, e]
                e
7.max(Collection),max(Collection,Comparator)方法的使用(前者采用Collection内含自然比较法，后者采用Comparator进行比较)。

public static void main(String[] args){
        List c = new ArrayList();
     c.add("l");
     c.add("o");
    c.add("v");
     c.add("e");
   System.out.println(c);
     System.out.println(Collections.max(c));
}
运行结果：[l, o, v, e]
                v
8.indexOfSubList(List list,List subList)方法的使用(含义：查找subList在list中首次出现位置的索引)。

public static void main(String[] args){
        ArrayList<Integer> intList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5, 6, 6, 6, 7, 3));
        ArrayList<Integer> targetList = new ArrayList<>(Arrays.asList(6));
        System.out.println(Collections.indexOfSubList(intList, targetList));
}
运行结果：5
9.lastIndexOfSubList(List source,List target)方法的使用与上例方法的使用相同

public static void main(String[] args){
        ArrayList<Integer> intList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5, 6, 6, 6, 7, 3));
        ArrayList<Integer> targetList = new ArrayList<>(Arrays.asList(6));
        System.out.println(Collections.lastIndexOfSubList(intList, targetList));
}
运行结果：7
10.rotate(List list,int m)方法的使用(含义：集合中的元素向后移m个位置，在后面被遮盖的元素循环到前面来)。移动列表中的元素，负数向左移动，正数向右移动

public static void main(String[] args){
        ArrayList<Integer> intList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
        System.out.println(intList);
        Collections.rotate(intList, 1);
        System.out.println(intList);
}
运行结果:[1, 2, 3, 4, 5]
             [5, 1, 2, 3, 4]
public static void main(String[] args){
        ArrayList<Integer> intList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
        System.out.println(intList);
        Collections.rotate(intList, -1);
        System.out.println(intList);
}
运行结果：[1, 2, 3, 4, 5]
               [2, 3, 4, 5, 1]
11.swap(List list,int i,int j)方法的使用(含义：交换集合中指定元素索引的位置)
  public class Practice {
                      public static void main(String[] args){
                             List m = Arrays.asList("one two three four five six siven".split(" "));
                              System.out.println(m);
                              Collections.swap(m, 2, 3);
                              System.out.println(m);
                        }
             }
    运行结果为：
           [one, two, three, four, five, six, siven]
           [one, two, four, three, five, six, siven]
12.binarySearch(Collection,Object)方法的使用(含义：查找指定集合中的元素，返回所查找元素的索引)。

binarySearch(Collection,Object)的简单示例
         public class Practice {
                  public static void main(String[] args){
                              List c = new ArrayList();
                          c.add("l");
                          c.add("o");
                           c.add("v");
                           c.add("e");
                          System.out.println(c);
                           int m = Collections.binarySearch(c, "o");
                             System.out.println(m);
                    }
          }
    运行结果为：[l, o, v, e]
                          1
13.replaceAll(List list,Object old,Object new)方法的使用(含义：替换批定元素为某元素,若要替换的值存在刚返回true,反之返回false)。

public class Practice {
                   public static void main(String[] args){
                          List list = Arrays.asList("one two three four five six siven".split(" "));
                             System.out.println(list);
                          List subList = Arrays.asList("three four five six".split(" "));
                           System.out.println(Collections.replaceAll(list, "siven", "siven eight"));
                           System.out.println(list);
                    }
          }
    运行结果为：
                     [one, two, three, four, five, six, siven]
                      true
                      [one, two, three, four, five, six, siven eight]

总结

1. 排序操作（主要针对List接口相关）

reverse(List list)：反转指定List集合中元素的顺序
shuffle(List list)：对List中的元素进行随机排序（洗牌）
sort(List list)：对List里的元素根据自然升序排序
sort(List list, Comparator c)：自定义比较器进行排序
swap(List list, int i, int j)：将指定List集合中i处元素和j出元素进行交换
rotate(List list, int distance)：将所有元素向右移位指定长度，如果distance等于size那么结果不变

 public void testSort() {
        System.out.println("原始顺序：" + list);
        
        Collections.reverse(list);
        System.out.println("reverse后顺序：" + list);
     
        Collections.shuffle(list);
        System.out.println("shuffle后顺序：" + list);
        
        Collections.swap(list, 1, 3);
        System.out.println("swap后顺序：" + list);
     
        Collections.sort(list);
        System.out.println("sort后顺序：" + list);
     
        Collections.rotate(list, 1);
        System.out.println("rotate后顺序：" + list);
    }

输出

原始顺序：[b张三, d孙六, a李四, e钱七, c赵五]
reverse后顺序：[c赵五, e钱七, a李四, d孙六, b张三]
shuffle后顺序：[b张三, c赵五, d孙六, e钱七, a李四]
swap后顺序：[b张三, e钱七, d孙六, c赵五, a李四]
sort后顺序：[a李四, b张三, c赵五, d孙六, e钱七]
rotate后顺序：[e钱七, a李四, b张三, c赵五, d孙六]
2. 查找和替换（主要针对Collection接口相关）

binarySearch(List list, Object key)：使用二分搜索法，以获得指定对象在List中的索引，前提是集合已经排序
max(Collection coll)：返回最大元素
max(Collection coll, Comparator comp)：根据自定义比较器，返回最大元素
min(Collection coll)：返回最小元素
min(Collection coll, Comparator comp)：根据自定义比较器，返回最小元素
fill(List list, Object obj)：使用指定对象填充
frequency(Collection Object o)：返回指定集合中指定对象出现的次数
replaceAll(List list, Object old, Object new)：替换

public void testSearch() {
        System.out.println("给定的list：" + list);
        System.out.println("max：" + Collections.max(list));
        System.out.println("min：" + Collections.min(list));
        System.out.println("frequency：" + Collections.frequency(list, "a李四"));
        Collections.replaceAll(list, "a李四", "aa李四");
        System.out.println("replaceAll之后：" + list);
        
        // 如果binarySearch的对象没有排序的话，搜索结果是不确定的
        System.out.println("binarySearch在sort之前：" + Collections.binarySearch(list, "c赵五"));
        Collections.sort(list);
        // sort之后，结果出来了
        System.out.println("binarySearch在sort之后：" + Collections.binarySearch(list, "c赵五"));
     
        Collections.fill(list, "A");
        System.out.println("fill：" + list);
    }

输出

给定的list：[b张三, d孙六, a李四, e钱七, c赵五]
max：e钱七
min：a李四
frequency：1
replaceAll之后：[b张三, d孙六, aa李四, e钱七, c赵五]
binarySearch在sort之前：-4
binarySearch在sort之后：2
fill：[A, A, A, A, A]

3. 同步控制

Collections工具类中提供了多个synchronizedXxx方法，该方法返回指定集合对象对应的同步对象，从而解决多线程并发访问集合时线程的安全问题。HashSet、ArrayList、HashMap都是线程不安全的，如果需要考虑同步，则使用这些方法。这些方法主要有：synchronizedSet、synchronizedSortedSet、synchronizedList、synchronizedMap、synchronizedSortedMap。

特别需要指出的是，在使用迭代方法遍历集合时需要手工同步返回的集合。

Map m = Collections.synchronizedMap(new HashMap());
      ...
  Set s = m.keySet();  // Needn't be in synchronized block
      ...
  synchronized (m) {  // Synchronizing on m, not s!
      Iterator i = s.iterator(); // Must be in synchronized block
      while (i.hasNext())
          foo(i.next());
  }
4. 设置不可变集合

Collections有三类方法可返回一个不可变集合：

emptyXxx()：返回一个空的不可变的集合对象
singletonXxx()：返回一个只包含指定对象的，不可变的集合对象。
unmodifiableXxx()：返回指定集合对象的不可变视图

public void testUnmodifiable() {
        System.out.println("给定的list：" + list);
        List<String> unmodList = Collections.unmodifiableList(list);
        
        unmodList.add("再加个试试！"); // 抛出：java.lang.UnsupportedOperationException
        
        // 这一行不会执行了
        System.out.println("新的unmodList：" + unmodList);
    }
5. 其它

disjoint(Collection<?> c1, Collection<?> c2) - 如果两个指定 collection 中没有相同的元素，则返回 true。
addAll(Collection<? super T> c, T... a) - 一种方便的方式，将所有指定元素添加到指定 collection 中。示范： 
Collections.addAll(flavors, "Peaches 'n Plutonium", "Rocky Racoon");
Comparator<T> reverseOrder(Comparator<T> cmp) - 返回一个比较器，它强行反转指定比较器的顺序。如果指定比较器为 null，则此方法等同于 reverseOrder()（换句话说，它返回一个比较器，该比较器将强行反转实现 Comparable 接口那些对象 collection 上的自然顺序）。

public void testOther() {
        List<String> list1 = new ArrayList<String>();
        List<String> list2 = new ArrayList<String>();
        
        // addAll增加变长参数
        Collections.addAll(list1, "大家好", "你好","我也好");
        Collections.addAll(list2, "大家好", "a李四","我也好");
        
        // disjoint检查两个Collection是否的交集
        boolean b1 = Collections.disjoint(list, list1);
        boolean b2 = Collections.disjoint(list, list2);
        System.out.println(b1 + "\t" + b2);
        
        // 利用reverseOrder倒序
        Collections.sort(list1, Collections.reverseOrder());
        System.out.println(list1);
    }

输出

true false
[我也好, 大家好, 你好]

————————————————
版权声明：本文为CSDN博主「Shiny0815」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/Shiny0815/article/details/79581317