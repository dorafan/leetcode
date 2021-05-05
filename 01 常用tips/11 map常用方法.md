### Map 初始化

Java | 复制

```java
Map<String, String> map = ``new` `HashMap<String, String>();
```

### 插入元素

Java | 复制

```java
map.put(``"key1"``, ``"value1"``);
```

### 获取元素

Java | 复制

```java
map.get(``"key1"``)
```

### 移除元素

Java | 复制

```java
map.remove(``"key1"``);
```

### 清空map

Java | 复制

```java
map.clear();
```





**4.Map接口中常用的方法：**

(1)V put(K key, V value); 向集合中添加元素。

(2)V get(Object key); 通过指定key获取value。

(3)int size(); 获取集合中元素的个数。

(4)void clear(); 清空集合，元素个数清0。

(5)boolean isEmpty(); 判断集合元素个数是否为0。

(6)boolean containsKey(Object key); 判断集合中是否包含指定key。

(7)boolean containsValue(Object value); 判断集合中是否包含指定value。

注意：contains()方法底层都调用了equals()方法，再次强调存入集合元素的类一定要重写equals()方法。

(8)Set keySet(); 获取集合中所有的key，返回一个包含所有key元素的Set集合。

(9)Collection values(); 获取集合中所有的value，返回一个包含所有value元素的Collection集合。

(10)V remove(Object key); 删除指定key的键值对。

(11)default boolean replace(K key, V oldValue, V newValue) 修改键值对<key, oldValue>的value为newValue。

(12)Set<Map.Entry<K,V>> entrySet(); 将Map集合转换成Set集合

Map集合中每个键值对组成一个元素（key=value），存入Set集合，每个元素的类型是Map.Entry<K,V>。





```java
import java.util.*;

public class Test01 {
    public static void main(String[] args) {
        // 创建Map集合
        Map<Integer, String> hashMap = new HashMap<Integer, String>();  // 泛型指定键值对为<Integer, String>类型

        // 添加键值对
        hashMap.put(1, "张三");  // 这里的1会自动装箱成Integer类型
        hashMap.put(1, "张三三");  // 会添加成功吗？可以，但key不能相同，所以会覆盖原来的数据
        // 输出集合中元素的个数
        System.out.println(hashMap.size());  // 1

        hashMap.put(2, "张三三");  // 会添加成功吗？会的，键值对的value可以相同
        System.out.println(hashMap.size());  // 2

        // 删除集合中key为2的键值对
        hashMap.remove(2);
        System.out.println(hashMap.size());  // 1

        // 获取键值对key为1的value
        String value = hashMap.get(1);
        System.out.println(value);  // 张三三

        // 修改指定键值对的value值
        hashMap.replace(1, "张三三", "张三");
        System.out.println(hashMap.get(1));  // 张三

        hashMap.put(2, "李四");
        hashMap.put(3, "王五");
        hashMap.put(4, "赵六");

        // 是否包含指定key
        boolean cKey1 = hashMap.containsKey(2);
        boolean cKey2 = hashMap.containsKey(6);
        System.out.println(cKey1);  // true
        System.out.println(cKey2);  // false

        // 是否包含指定value
        boolean cValue1 = hashMap.containsValue("李四");
        boolean cValue2 = hashMap.containsValue("熊大");
        System.out.println(cValue1);  // true
        System.out.println(cValue2);  // false

        // 获取Map集合中所有的key
        Set<Integer> keys = hashMap.keySet();  // Map中所有的key没有相同的，故返回的是一个Set集合
        // 遍历Set集合
        for (Integer i : keys) {
            System.out.print(i + "   ");  // 1   2   3   4
        }
        System.out.println();

        // 获取Map集合中所有的value
        Collection<String> values = hashMap.values();  // Map中所有的value是可以相同的，故返回的是一个Collection集合
        // 遍历Collection集合
        for (String str : values) {
            System.out.print(str + "   ");  // 张三   李四   王五   赵六
        }
        System.out.println();

        // 把Map集合转换成Set集合
        Set<Map.Entry<Integer, String>> mapToSet = hashMap.entrySet();  // 每个键值对的key与value合并成“key=value”，组成Set的一个元素
        // 遍历转换后的Set集合
        for (Map.Entry<Integer, String> m : mapToSet) {
            System.out.print(m + "   ");  // 1=张三   2=李四   3=王五   4=赵六
        }
        System.out.println();

		// Map集合的元素清空
        hashMap.clear();
        System.out.println(hashMap.isEmpty());  // true
        System.out.println(hashMap.size());  // 0

    }
}
```

 