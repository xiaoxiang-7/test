# 指定、算數、單元運算子

> 介紹指定運算子、算數運算子、單元運算子

## 最簡單的指定運算子 Assignment Operator

就是等於符號『=』，可以把右邊的東西『指定』到左邊，**並非**一般數學上的『等於』

```java
int value;
value = 10;  // 指定10 給value這個變數。
```

也用於物件參考(reference)的指定。

## 算數運算子 Arithmetic Operators

Java的算數運算子跟一般你學過的數學差不多，有加、減、乘、除，符號也一樣。另外還有『 % 』符號做取餘數的運算。

| 運算子Operator | 描述           |   |
| ----------- | ------------ | - |
| +           | 加法運算，也用於字串相加 |   |
| -           | 減法運算         |   |
| \*          | 乘法運算         |   |
| /           | 除法運算         |   |
| %           | 取餘數運算        |   |

使用範例：

```java
int a = 10;
int b = 7;
String str = "Hello";
String str2 = "Java";
System.out.println(a+b);
System.out.println(a-b);
System.out.println(a*b);
System.out.println(a/b);  
System.out.println(a%b);
System.out.println(str+str2);
```

執行結果：

```java
17 // 加法
3  // 減法
70 // 乘法
1  // 注意整數的除法也是整數，若要保留小數點，需要至少一種型態為浮點數
3  // 取餘數：10 / 7 = 1 ...3
HelloJava  // 字串串接
```

## 合併

算數運算子可以跟指定運算子合併，也是一般常看到的寫法。

下面兩行是等價的：

```java
a = a+1;
a += 1;
```

假設a是變數, b是變數或數值：

| Operator | 等價         |   |
| -------- | ---------- | - |
| a += b   | a = a + b  |   |
| a -= b   | a = a - b  |   |
| a \*=b   | a = a \* b |   |
| a /= b   | a = a / b  |   |
| a %= b   | a = a % b  |   |

純粹就是可以少打幾個字，不過因為方便也很多人這樣做，很多語言都是這樣，必須要清楚。

## 單元運算子 Unary Operators

單元的意思是，這個運算子是用來處理『單個』運算元的，也可稱為一元運算子。

| Operator | 敘述                              |   |
| -------- | ------------------------------- | - |
| +        | 正號運算子 (但就算沒加，預設就是正值)            |   |
| -        | 負號運算子 (讓負值變正，正值變負)              |   |
| ++       | 遞增運算子，遞增1                       |   |
| --       | 遞減運算子，遞減1                       |   |
| !        | 布林反向運算子 (true變false，false變true) |   |

使用範例：

```java
int a = +10 ;
System.out.println(a);
int b = -a;
System.out.println(b);
a++;
System.out.println(a);
b--;
System.out.println(b);
boolean flag = true;
flag = !flag;
System.out.println(flag);
```

執行結果：

```java
10
-10
11
-11
false
```

## 遞增/遞減運算子的前綴(prefix)後綴(postfix)差異

我們知道 a++ 其實就是 a=a+1 ，其實 a++ 也可以寫成 ++a，**但意義上完全不一樣**。

a++ ，存取完a的值後，做++的動作。

\++a ，先做++的動作，在讓別人存取。

看個範例：

```java
int a = 10;
System.out.println(a++);  // 印出a的值(10)後才做++，執行完這行a為11
System.out.println(a);    // 印出a的值(11)
System.out.println(++a);  // 先把a做++，在印出a的值(12)
System.out.println(a);    // 印出a的值(12)
```

執行結果：

```java
10
11
12
12
```

\++跟--是同樣的邏輯，如果計算式寫的多又長要注意避免搞混，最簡單避免錯誤的方法就是分開寫，不要擠在一行，但每個人寫程式習慣都不同，還是要多留意。

放變數前面是先做運算，再供別人做存取。 放變數後面是存取完，再做運算。
