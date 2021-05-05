# Java算法技巧——字符串类

## String

### 字符串转数字

```java
String s = "123";
int value = Integer.parseInt(s); // => 123
value = Integer.valueOf(s) // => 123
```

### 数字转字符串

```java
int value = 123;
String s = Integer.toString(value); // => "123"
s = String.valueOf(value); // => "123"
s = "" + value // => "123"
```

### 字符串，转字符（数组）

```java
String s = "abc";
char[] chars = s.toCharArray(); // => ['a','b','c']
chars[2] == s.charAt(2) // => true
```

### 字符数组转字符串

```java
char[] a = {'1', '2', '3', '4'};
String str = String.valueOf(a); // => "1234" 调用valueOf方法
str = String.valueOf(a, 2 ,2);  // => "34"，valueOf(data[], offset, count) 
str = new String(a);  // => "1234" 构造函数转换
```

### 子串

```java
String s = "abc"
String sub = s.substring(1, 3); // => "bc"
sub = s.substring(1,2); // => "b"，(start,end)，start->end-1，不包含end
```

### 分割

```java
public String[] split(String regex, int limit)
public String[] split(String regex)

String s = "ab-bc-cd-de"
String[] str = s.split("-") // => ["ab", "bc", "cd", "de"]
str = s.split("-", 2) // => ["ab","bc-cd-de"], 分割为2段，
str = s.split("-", 1) // => ["ab-bc-cd-de"]，1->不分割，0->全分割
```

> 参考：[java split](http://www.tutorialspoint.com/java/java_string_split.htm)

### 查找

```java
// 查找返回位置
String str = "abcdecdedf"
str.indexOf("cde") // => 2
str.indexOf("xyz") // => -1
str.lastIndexOf("cde") // => 5，从后往前
// 仅判断是否存在
str.contains("cde") // => true
str.contains("xyz") // => false
```

### 去除行首行末空格

```java
String str = "   hello  ".trim() // => "hello"
```

## StringBuilder

> String提供的字符串增删改功能不完善，且效率较低，StringBuilder提供了十分高效的方法

### StringBuilder常用方法

```java
StringBuilder result = new StringBuilder();
char[] chars = {'a', 'b', 'c', 'd', 'e'};
// 尾部添加
result.append(1);  // => "1"，自动将数字转为字符，不需要额外操作
result.append('2');  // => "12"，参数可以是 String, char[],double,int,char等
result.append(chars, 2, 2); // => "12cd"，append(chars[], offset, count),后2个参数可选
// 删除
result.delete(1,2);   // => "1cd", delete(start, end),不含end 
result.deleteCharAt(1);  // => "1d"
// 插入
result.insert(0, "abc"); // => "abc1d" // 在某个位置前插入char[]，String，int等
// 修改
result.setCharAt(1, 'B'); // => "aBc1d" // 修改
result.setLength(3);  // => "aBc"，后面的字符将被删除 
```



#### String类有哪些方法？

**参考答案**

String类是Java最常用的API，它包含了大量处理字符串的方法，比较常用的有：

- char charAt(int index)：返回指定索引处的字符；
- String substring(int beginIndex, int endIndex)：从此字符串中截取出一部分子字符串；
- String[] split(String regex)：以指定的规则将此字符串分割成数组；
- String trim()：删除字符串前导和后置的空格；
- int indexOf(String str)：返回子串在此字符串首次出现的索引；
- int lastIndexOf(String str)：返回子串在此字符串最后出现的索引；
- boolean startsWith(String prefix)：判断此字符串是否以指定的前缀开头；
- boolean endsWith(String suffix)：判断此字符串是否以指定的后缀结尾；
- String toUpperCase()：将此字符串中所有的字符大写；
- String toLowerCase()：将此字符串中所有的字符小写；
- String replaceFirst(String regex, String replacement)：用指定字符串替换第一个匹配的子串；
- String replaceAll(String regex, String replacement)：用指定字符串替换所有的匹配的子串。

**注意事项**

String类的方法太多了，你没必要都记下来，更不需要一一列举。面试时能说出一些常用的方法，表现出对这个类足够的熟悉就可以了。另外，建议你挑几个方法仔细看看源码实现，面试时可以重点说这几个方法。





**二、String类对象的创建**
字符串声明：String stringName;
字符串创建：stringName = new String(字符串常量);或stringName = 字符串常量;
**三、String类构造方法**
1、**public String()**
无参构造方法，用来创建空字符串的String对象。
 1 String str1 = new String(); 
2、**public String(String value)**
用已知的字符串value创建一个String对象。
 1 String str2 = new String("asdf"); 2 String str3 = new String(str2); 
3、**public String(char[] value)**
用字符数组value创建一个String对象。

```java
1 char[] value = {'a','b','c','d'};
2 String str4 = new String(value);//相当于String str4 = new String("abcd");
```


4、**public String(char chars[], int startIndex, int numChars)**
用字符数组chars的startIndex开始的numChars个字符创建一个String对象。

```java
1 char[] value = {'a','b','c','d'};
2 String str5 = new String(value, 1, 2);//相当于String str5 = new String("bc");
```


5、**public String(byte[] values)**
用比特数组values创建一个String对象。

```java
1 byte[] strb = new byte[]{65,66};
2 String str6 = new String(strb);//相当于String str6 = new String("AB");
```

**四、String类常用方法**
1、求字符串长度
**public int length()**//返回该字符串的长度

```
1 String str = new String("asdfzxc");
2 int strlength = str.length();//strlength = 7
```


2、求字符串某一位置字符
**public char charAt(int index)**//返回字符串中指定位置的字符；注意字符串中第一个字符索引是0，最后一个是length()-1。

```
1 String str = new String("asdfzxc");
2 char ch = str.charAt(4);//ch = z
```


3、提取子串
用String类的substring方法可以提取字符串中的子串，该方法有两种常用参数:
1)**public String substring(int beginIndex)**//该方法从beginIndex位置起，从当前字符串中取出剩余的字符作为一个新的字符串返回。
2)**public String substring(int beginIndex, int endIndex)**//该方法从beginIndex位置起，从当前字符串中取出到endIndex-1位置的字符作为一个新的字符串返回。

```
1 String str1 = new String("asdfzxc");
2 String str2 = str1.substring(2);//str2 = "dfzxc"
3 String str3 = str1.substring(2,5);//str3 = "dfz"
```


4、字符串比较
1)**public int compareTo(String anotherString)**//该方法是对字符串内容按字典顺序进行大小比较，通过返回的整数值指明当前字符串与参数字符串的大小关系。若当前对象比参数大则返回正整数，反之返回负整数，相等返回0。
2)**public int compareToIgnore(String anotherString)**//与compareTo方法相似，但忽略大小写。
3)**public boolean equals(Object anotherObject)**//比较当前字符串和参数字符串，在两个字符串相等的时候返回true，否则返回false。
4)**public boolean equalsIgnoreCase(String anotherString)**//与equals方法相似，但忽略大小写。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
1 String str1 = new String("abc");
2 String str2 = new String("ABC");
3 int a = str1.compareTo(str2);//a>0
4 int b = str1.compareToIgnoreCase(str2);//b=0
5 boolean c = str1.equals(str2);//c=false
6 boolean d = str1.equalsIgnoreCase(str2);//d=true
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)


5、字符串连接
**public String concat(String str)**//将参数中的字符串str连接到当前字符串的后面，效果等价于"+"。

```
1 String str = "aa".concat("bb").concat("cc");
2 相当于String str = "aa"+"bb"+"cc";
```


6、字符串中单个字符查找
1)**public int indexOf(int ch/String str)**//用于查找当前字符串中字符或子串，返回字符或子串在当前字符串中从左边起首次出现的位置，若没有出现则返回-1。
2)**public int indexOf(int ch/String str, int fromIndex)**//改方法与第一种类似，区别在于该方法从fromIndex位置向后查找。
3)**public int lastIndexOf(int ch/String str)**//该方法与第一种类似，区别在于该方法从字符串的末尾位置向前查找。
4)**public int lastIndexOf(int ch/String str, int fromIndex)**//该方法与第二种方法类似，区别于该方法从fromIndex位置向前查找。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
1 String str = "I am a good student";
2 int a = str.indexOf('a');//a = 2
3 int b = str.indexOf("good");//b = 7
4 int c = str.indexOf("w",2);//c = -1
5 int d = str.lastIndexOf("a");//d = 5
6 int e = str.lastIndexOf("a",3);//e = 2
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)


7、字符串中字符的大小写转换
1)**public String toLowerCase()**//返回将当前字符串中所有字符转换成小写后的新串
2)**public String toUpperCase()**//返回将当前字符串中所有字符转换成大写后的新串

```
1 String str = new String("asDF");
2 String str1 = str.toLowerCase();//str1 = "asdf"
3 String str2 = str.toUpperCase();//str2 = "ASDF"
```


8、字符串中字符的替换
1)**public String replace(char oldChar, char newChar)**//用字符newChar替换当前字符串中所有的oldChar字符，并返回一个新的字符串。
2)**public String replaceFirst(String regex, String replacement)**//该方法用字符replacement的内容替换当前字符串中遇到的第一个和字符串regex相匹配的子串，应将新的字符串返回。
3)**public String replaceAll(String regex, String replacement)**//该方法用字符replacement的内容替换当前字符串中遇到的所有和字符串regex相匹配的子串，应将新的字符串返回。

```
1 String str = "asdzxcasd";
2 String str1 = str.replace('a','g');//str1 = "gsdzxcgsd"
3 String str2 = str.replace("asd","fgh");//str2 = "fghzxcfgh"
4 String str3 = str.replaceFirst("asd","fgh");//str3 = "fghzxcasd"
5 String str4 = str.replaceAll("asd","fgh");//str4 = "fghzxcfgh"
```


9、其他类方法
1)**String trim()**//截去字符串两端的空格，但对于中间的空格不处理。

```
1 String str = " a sd ";
2 String str1 = str.trim();
3 int a = str.length();//a = 6
4 int b = str1.length();//b = 4
```


2)**boolean startsWith(String prefix)**或**boolean endWith(String suffix)**//用来比较当前字符串的起始字符或子字符串prefix和终止字符或子字符串suffix是否和当前字符串相同，重载方法中同时还可以指定比较的开始位置offset。

```
1 String str = "asdfgh";
2 boolean a = str.startsWith("as");//a = true
3 boolean b = str.endWith("gh");//b = true
```


3)**regionMatches(boolean b, int firstStart, String other, int otherStart, int length)**//从当前字符串的firstStart位置开始比较，取长度为length的一个子字符串，other字符串从otherStart位置开始，指定另外一个长度为length的字符串，两字符串比较，当b为true时字符串不区分大小写。
4)**contains(String** **str)**//判断参数s是否被包含在字符串中，并返回一个布尔类型的值。

```
1 String str = "student";
2 str.contains("stu");//true
3 str.contains("ok");//false
```


5)**String[] split(String str)**//将str作为分隔符进行字符串分解，分解后的字字符串在字符串数组中返回。

```
1 String str = "asd!qwe|zxc#";
2 String[] str1 = str.split("!|#");//str1[0] = "asd";str1[1] = "qwe";str1[2] = "zxc";
```

**五、字符串与基本类型的转换**
1、字符串转换为基本类型
java.lang包中有Byte、Short、Integer、Float、Double类的调用方法：
1)**public static byte parseByte(String s)**
2)**public static short parseShort(String s)**
3)**public static short parseInt(String s)**
4)**public static long parseLong(String s)**
5)**public static float parseFloat(String s)**
6)**public static double parseDouble(String s)**
例如：

```
1 int n = Integer.parseInt("12");
2 float f = Float.parseFloat("12.34");
3 double d = Double.parseDouble("1.124");
```


2、基本类型转换为字符串类型
String类中提供了String valueOf()放法，用作基本类型转换为字符串类型。
1)**static String valueOf(char data[])**
2)**static String valueOf(char data[], int offset, int count)**
3)**static String valueOf(boolean b)**
4)**static String valueOf(char c)**
5)**static String valueOf(int i)**
6)**static String valueOf(long l)**
7)**static String valueOf(float f)**
8)**static String valueOf(double d)**
例如：

```
1 String s1 = String.valueOf(12);
2 String s1 = String.valueOf(12.34);
```


3、进制转换
使用Long类中的方法得到整数之间的各种进制转换的方法：
Long.toBinaryString(long l)
Long.toOctalString(long l)
Long.toHexString(long l)
Long.toString(long l, int p)//p作为任意进制