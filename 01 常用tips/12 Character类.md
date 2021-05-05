Character 类用于对单个字符进行操作，该对象中包装一个基本类型 char 的值。
Character 类提供了一系列方法来操纵字符。你可以使用Character的构造方法创建一个Character类对象，当你将一个char类型的参数传递给需要一个 Character 类型参数的方法时，这时编译器会自动将char类型参数转化为 Character 类型参数，这样我们可以称其为装箱，反之为拆箱。

在 Character 类中，我们还需要了解转义序列（前面有反斜杠（\）的字符代表转义字符，它对编译器来说是有特殊含义的）

![img](https://img2020.cnblogs.com/blog/1743552/202003/1743552-20200306132505189-1805276710.png)

Character 类的常用方法：

1、isLetter() 方法

isLetter() 方法用于判断指定字符是否为字母。

语法：boolean isLetter(char ch)

其中ch = 要测的字符；当字符为字母时，则返回 true，否则返回 false。（以下ch都为要测的字符）

2、isDigit() 方法

isDigit() 方法用于判断指定字符是否为数字，如果字符为数字，则返回 true；否则返回 false。

语法：public static boolean isDigit(char ch)

3、isWhitespace() 方法

isWhitespace() 方法用于判断指定字符是否为空白字符，空白符包含：空格、tab 键、换行符，如果字符为空白字符，则返回 true；否则返回 false。

语法：boolean isWhitespace(char ch)

4、isUpperCase() 方法

isUpperCase() 方法用于判断指定字符是否为大写字母，如果字符为大写，则返回 true；否则返回 false。

语法：boolean isUpperCase(char ch)

5、isLowerCase() 方法

isLowerCase() 方法用于判断指定字符是否为小写字母，如果字符为小写，则返回 true；否则返回 false。

语法：boolean isLowerCase(char ch)

6、toUpperCase() 方法

toUpperCase() 方法用于将小写字符转换为大写，如果有的话，返回转换后字符的大写形式；否则返回字符本身。

语法：char toUpperCase(char ch)

7、toLowerCase() 方法

toLowerCase() 方法用于将大写字符转换为小写，如果有的话，返回转换后字符的小写形式；否则返回字符本身。

语法：char toLowerCase(char ch)

8、toString() 方法

toString() 方法用于返回一个表示指定 char 值的 String 对象。结果是长度为 1 的字符串，仅由指定的 char 组成。

语法：String toString(char ch)