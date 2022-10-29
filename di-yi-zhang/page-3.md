# 變數

> 變數的宣告、使用及命名的規則

## 為什麼要有變數 Why Variables？

程式設計師利用程式處理資料，有時候需要把資料暫時儲存在記憶體中，然而記憶體的地址一般來說是一串16進位的數值，程式設計師要把資料存放在記憶體，如果還要去記這一串位址才能存取到資料，很明顯太不方便了。

因此我需要一個小標籤，幫助我存取我的資料。

![](broken-reference) 如此一來，程式設計師就不用煩惱到底資料存放在記憶體的哪個位置，只要知道他的變數叫什麼名稱，就可以順利做存取的動作，那麼要如何定義變數呢？

## 定義變數

```java
資料型態 變數名稱; // 宣告
變數名稱 = 值; // 指定數值給該變數
```

例如：宣告一個整數變數名稱為 i ，指定變數i為10。

```java
int i;
i=10;
// 也可以寫成一行
int i = 10;
```

定義好變數之後，就可以利用該變數做運算、存取數值。

## 變數命名規則

1. 不能與保留字相同
2. 字首不能是數字
3. 字首可以是底線('\_')或錢字符號('$')
4. Java將大小寫英文視為不同字元

例如：

```java
a, apple, APPLE, _apple, $apple (合法變數名稱)
87apple, 1, (apple, case (非法變數名稱)
```

## 保留字 reserved word

Java中，命名的變數名稱或類別名稱，不能與保留字相同(此處相同指大小寫完全一樣，若其中一處大小寫不同則視為不同字)，因此我們需要知道Java中有哪些保留字。

|          |          |            |           |              |
| -------- | -------- | ---------- | --------- | ------------ |
| abstract | continue | for        | new       | switch       |
| assert   | default  | goto       | package   | synchronized |
| boolean  | do       | if         | private   | this         |
| break    | double   | implements | protected | throw        |
| byte     | else     | import     | public    | throws       |
| case     | enum     | instanceof | return    | transient    |
| catch    | extends  | int        | short     | try          |
| char     | final    | interface  | static    | void         |
| class    | finally  | long       | strictfp  | volatile     |
| const    | float    | native     | super     | while        |

各個保留字都有它的意思，大部分的保留字我們會在之後的章節提到，但有些已經被遺忘以久快被淘汰了，只要知道這些字不能當做識別字(自訂的變數或類別或方法名稱)使用。

這個表格從Java的Document複製過來，基本上不用背，看過去有個印象就好，如果使用到這些關鍵字的話Eclipse會立刻出現警告，否則編譯時會出錯，基本上是可以很輕易發現的程式錯誤。

## 變數命名習慣

有一個統一的命名習慣，可以增加程式的可讀性，一般來說會希望變數名稱有英文上的意義，除非那就真的是一個很不重要的變數。

```java
int money = 100;
String name = "tina";
double average = 50.5;
long numberOfMyHair = 4000000000L;
int MAX_SIZE = 10000;
int temp = 1;
```

習慣上，常數會定義成每個字母大寫： int MAX\_VALUE=100;

由多個英文單字組成的名稱，會字首大寫：myBestFriends

變數名稱越不重要，看程式的人會認為這個變數沒有什麼意義，可能只是為了運算上的需求而宣告，所以要讓別人快速理解你的程式，一個有意義的變數名稱是絕對重要的。

## 題外話

由於Java是以Unicode編碼，所以其實識別字的名稱可以是中文\~ (或其他莫名其妙文)。

```java
int 錢 = 10;
錢 = 錢*10;
System.out.println(錢);
```

執行結果：

```java
100
```

這樣是合法的，但是使用中文字會因為文字編輯器的不同，有時候會有很麻煩的事情發生，而且可能會被別人瞧不起，這件事你知道我知道就好，平常不要輕易嘗試。
