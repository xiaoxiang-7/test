# 基本資料型態

> 介紹8個Java的基本資料型態。

## 基本資料型態

Java預先定義好的資料型態有這八種： char, byte, short, int, long, float, double, boolean

| 型態名稱    | 位元數 | 表示範圍                                                 | 預設值      |
| ------- | --- | ---------------------------------------------------- | -------- |
| boolean |     | true or false                                        | false    |
| char    | 16  | '\u0000' to '\uFFFF'                                 | '\u0000' |
| byte    | 8   | -128 to +127                                         | 0        |
| short   | 16  | -32768 to +32767                                     | 0        |
| int     | 32  | -2147483648 to +2147483647                           | 0        |
| long    | 64  | -9223372036854775808 to +9223372036854775807         | 0L       |
| float   | 32  | -3.40292347E+38 to +3.40292347E+38                   | 0f       |
| double  | 64  | -1.7976931348623157E+308 to +1.7976931348623157E+308 | 0d       |

## 布林 boolean

boolean 只有兩個值，true 或 false。使用此資料型態可以簡單的表示真(true)或假(false)的狀態，方便做條件判斷使用。boolean型態表示著一位元的0或1的資料，但他的型態大小沒有被精確的定義。

```java
System.out.println(true);   // 印出 true
System.out.println(false);  // 印出 false
```

## 字元 char

用來儲存字元，一個單位的字元佔16-bits大小，Java的字元採用Unicode編碼(前128字元與ASCII相容)。表示範圍為'\u0000' (0) 到 '\uffff' (65,535)，在Java中一個英文字元或符號或中文字元或XX文字元都是一個char，而字元的本質其實就是數字，所以也有與整數型態相同的特性，可以做算數運算。字元常數用單引號夾起字元，如：'a'，表示字元 a 。

```java
System.out.println('a');  // 印出 a
```

## 整數 byte, short, int ,long

用來儲存整數，有正負號。依所佔的記憶體大小可以在細分成位元組（byte, 8-bits）、短整數（short, 16-bits）、整數（int, 32-bits）與長整數（long, 64-bits），在記憶體佔有越多的空間所可以表示的範圍也就越大。整數可以做算數運算，具有我們熟知一般整數的特性。除非對於記憶體有嚴格的要求，否則int與long是一般工程師常用的整數型態。在Java程式中，『整數數字』被稱為符號常數，預設型態是int。

```java
System.out.println(1+2+3);   // 印出數字6，內部運作是 (int)1+(int)2+(int)3
System.out.println(1L+2L);   // 印出數字3，內部運作是 (long)1+(long)2
```

## 浮點數 float, double

只有整數的運算很明顯不能滿足現實的需求，浮點數代表著有小數點的數。依所佔記憶體大小分為浮點數（float, 32-bits）與倍精度浮點數（double, 64-bits），同樣的在記憶體佔有越多的位元可以表示的範圍與精確度越高。相關轉換規範是依照IEEE 754 floating point的定義，聽聽就好我們只需要知道，在只有0/1構成的電腦資料中，任何浮點數都是依循一定的規則被模擬出來的，所以都存在誤差。一般來說float可以保證在小數點後6位是精確的，而double可以到保證小數點後15位。在Java程式中，『浮點數數字』，預設型態是double。

```java
System.out.println(1.0+0.5);      // 輸出1.5，內部運作是 (double)1.0+(double)0.5
System.out.println(0.1f+0.2f);    // 輸出0.3，內部運作是 (float)0.1+(float)0.2
```

## 溢位 Overload

各個基本資料型態都有它的表示範圍，如果運算超出了它能表示的範圍，就會發生溢位。舉個例子：

```java
int value =2000000000;
System.out.println(value);
value = value *2;
System.out.println(value);
```

執行結果：

```java
2000000000
-294967296
```

我們知道int的表示範圍大約是21億，我宣告我的value是20億，然後讓它乘以二，預期得到40億的結果，但事實上程式跑出來卻是-294967296。這是因為在記憶體中int所能記錄的資料就是那32個bits，根據乘法運算出來的結果，可能有些資訊被遺失了，所以編譯器解讀那塊記憶體空間出來的數值不是我們預期的結果。

溢位是常見的程式錯誤，程式設計師必須要清楚自己所處理的資料可能會到多少數值範圍，而選用適當的資料型態，以上面的例子來說，不應該用int而應該改用long。

```java
long value =2000000000;
System.out.println(value);
value = value *2;
System.out.println(value);
```

執行結果：

```java
2000000000
4000000000
```
