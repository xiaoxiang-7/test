# 字串

> 介紹字串類別及常用方法。

字串String可以代表字元的串列，例如 "abc" 就是一個字串類別的實體。字串是常數(constant)，在記憶體中被初始化就無法再做更改。

### 初始化String <a href="#chu-shi-hua-string" id="chu-shi-hua-string"></a>

String 類別身為參考資料型態，一樣必須實體化才有資料，而String的實體化方式非常自由。

```java
String str = "abc";
```

利用兩個雙引號『" "』夾起來的字元就會在Heap初始化物件產生空間，回傳reference給String變數。記憶體配置：

<figure><img src="https://3235187699-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MLRnhT9aTkN9HvaBP28%2Fsync%2Ff92c510850eec1d8dd43de339d23cc012da6aa5c.jpg?generation=1604653622757299&#x26;alt=media" alt=""><figcaption></figcaption></figure>

String 的建構子非常多元，也可以透過字元陣列去創造字串：

```java
char[] data = {'a','b','c'};
String str = new String(data);  // 利用字元陣列去初始化物件內容
String str2 = new String(str);  // 利用另一個字串去初始化物件內容
```

更多String的建構子請參考[document](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)，因為真的太多了。

## 字串串接 String Concat

很多時候我們會希望把兩個或以上的字串串在一起做輸出，在Java要如何辦到呢？

```java
String a = "Hello";
String b = "Java";

String result = a + b;
String result2 = a.concat(b);

System.out.println(result);
System.out.println(result2);
```

執行結果：

```
HelloJava
HelloJava
```

字串串接的方法； 1. 利用加號運算子『+』。 2. 呼叫 .concat(String) 方法，會回傳自己的內容串接參數內容的結果字串。

## 字串的修改？

在本章結開頭第二行提到，字串是常數，被初始化後就不能改變其值，那為什麼上面還可以對字串做串接的動作呢？

事實上，字串還是沒有被修改到，而是你的reference被指到了另一個物件。

舉個例子：

```java
String a = "happy";
a = a + "day";
```

#### 第一行 `String a = "happy";` <a href="#di-yi-hang-stringa-happy" id="di-yi-hang-stringa-happy"></a>

記憶體在Stack區有一個字串變數 a ，內容指到Heap區的 "happy"物件。

<figure><img src="https://3235187699-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MLRnhT9aTkN9HvaBP28%2Fsync%2F737e68d7452a78d7050f8e2ce7c40e336be8b7c0.jpg?generation=1604653622539645&#x26;alt=media" alt=""><figcaption></figcaption></figure>

### 第二行 `a = a + "day";`

程式在Heap區另外開了一個新的字串物件，該物件的資料內容是"happyday"，也就是實際兩字串串接的結果，再把這個新的物件參考(reference)指定給變數a。 完成這個『看起來字串有增長』的動作。

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

那，那個可憐的 "happy" 怎麼辦？

如果程式中沒有任何參考(reference)指向他，那他在Heap區就如同垃圾一般的存在，在Java執行垃圾回收(Garbage Collection)時他的資源會被釋放掉。

這就是字串串接內部的動作，由於字串是常數，所以任何會改變其內容的動作(串接、取代、刪除等)，在記憶體中都是以類似的方法動作的。

### 字串相等 String Equals <a href="#zi-chuan-xiang-deng-string-equals" id="zi-chuan-xiang-deng-string-equals"></a>

在處理字串時常常會需要判斷兩個字串是否相等，要怎麼做呢？

來看一個例子：

```java
String a = new String("hello");
String b = new String("hello");
System.out.println(a==b);
```

執行結果：

```java
false
```

如果你的目的是判斷兩個字串物件的『內容值』有沒有相等，顯然不能用『==』去做比對。用『==』運算子比對的是 變數a 與 變數b 的『值』有沒有相等，字串是參考資料型態，變數a及變數b只是存放在Stack區的變數，他們的內容值是真實物件的reference，並不是物件內容。

記憶體配置圖：

<figure><img src="https://3235187699-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MLRnhT9aTkN9HvaBP28%2Fsync%2F54373961b5ad1d9de07b314303ff256c2ba9d5ed.jpg?generation=1604653623118214&#x26;alt=media" alt=""><figcaption></figcaption></figure>

從圖中很明顯看到，如果用『==』運算子的話，只會做 0100==0110 的比較，那當然會回傳false，但我們目的不是要比較reference有沒有相等，而是比較字串物件的內容有沒有相等，所以不應該用『==』。

需要比對字串內容值的話，需要的是字串方法： equals()

**public boolean equals(String str) 回傳str是否與自身物件的內容值相等。**

範例程式：

```java
String a = new String("hello");
String b = new String("hello");
System.out.println(a.equals(b));
```

執行結果：

```java
true
```

### 好用方法 useful Method <a href="#hao-yong-fang-fa-useful-method" id="hao-yong-fang-fa-useful-method"></a>

雖然方法還是建議大家去看[document](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)然後實際操作過，不過這邊講幾個超常用的方法給新手參考參考，以後如果有需要就可以直接用了。

<table data-header-hidden><thead><tr><th></th><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td>修飾子 回傳型態</td><td>方法</td><td>描述</td><td>​</td></tr><tr><td>char</td><td>charAt(int index)</td><td>回傳第index的字元</td><td>​</td></tr><tr><td>String</td><td>concat(String str)</td><td>回傳串接上str的字串</td><td>​</td></tr><tr><td>boolean</td><td>contains(CharSequence s)</td><td>是否包含字串s</td><td>​</td></tr><tr><td>boolean</td><td>endsWith(String suffix)</td><td>是否為suffix結尾</td><td>​</td></tr><tr><td>boolean</td><td>equals(Object anObject)</td><td>是否與anObject相等</td><td>​</td></tr><tr><td>static String</td><td>format(String format, Object... args)</td><td>回傳利用format為格式的字串</td><td>​</td></tr><tr><td>int</td><td>indexOf(String str)</td><td>回傳str在此字串的索引值</td><td>​</td></tr><tr><td>int</td><td>lastIndexOf(String str)</td><td>回傳最後一個str在此字串的索引值</td><td>​</td></tr><tr><td>int</td><td>length()</td><td>回傳字串長度</td><td>​</td></tr><tr><td>boolean</td><td>matches(String regex)</td><td>是否與正規表示式regex相符</td><td>​</td></tr><tr><td>String</td><td>replaceAll(String regex, String replacement)</td><td>把字串中的regex都換成replacement</td><td>​</td></tr><tr><td>String</td><td>replaceFirst(String regex, String replacement)</td><td>把字串中第一個regex換成replacement</td><td>​</td></tr><tr><td>String[]</td><td>split(String regex)</td><td>回傳利用regex切割過的字串陣列</td><td>​</td></tr><tr><td>boolean</td><td>startsWith(String prefix)</td><td>是否為prefix開頭</td><td>​</td></tr><tr><td>String</td><td>substring(int beginIndex)</td><td>回傳從beginIndex開始到結尾的子字串</td><td>​</td></tr><tr><td>String</td><td>substring(int beginIndex, int endIndex)</td><td>回傳從beginIndex開始到endIndex(不涵)的子字串</td><td>​</td></tr><tr><td>char[]</td><td>toCharArray()</td><td>回傳此字串的字元陣列</td><td>​</td></tr><tr><td>String</td><td>toLowerCase()</td><td>回傳把所有英文字母都變小寫的字串</td><td>​</td></tr><tr><td>String</td><td>toUpperCase()</td><td>回傳把所有英文字母都變大寫的字串</td><td>​</td></tr><tr><td>String</td><td>trim()</td><td>回傳刪除前後空白的字串</td><td>​</td></tr></tbody></table>
