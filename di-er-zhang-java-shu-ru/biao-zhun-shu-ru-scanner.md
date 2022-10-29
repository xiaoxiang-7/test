# 標準輸入 Scanner



> 介紹使用Scanner物件做標準輸入

我們設計程式時常常會需要夠造一個可以跟使用者互動的感覺，希望某個變數的值可以由使用者從鍵盤輸入，而一般電腦系統預設的標準輸入就是鍵盤(keyboard)。

## Scanner

Scanner 是一個簡單的文字讀取器，可以解析字串成各個基本資料型態。

這個Scanner類別被放在 java.util套件中，別忘了事先import：

```java
import java.util.Scanner;
```

Scanner 是個類別，類別需要被初始化(實體化)成物件才能使用，所以我們先來看看Java內建的Scanner有哪些建構子：

| Scanner Constructor(.)                                  |   |
| ------------------------------------------------------- | - |
| Scanner(File source)                                    |   |
| Scanner(File source, String charsetName)                |   |
| Scanner(InputStream source)                             |   |
| Scanner(InputStream source, String charsetName)         |   |
| Scanner(Path source)                                    |   |
| Scanner(Path source, String charsetName)                |   |
| Scanner(Readable source)                                |   |
| Scanner(ReadableByteChannel source)                     |   |
| Scanner(ReadableByteChannel source, String charsetName) |   |
| Scanner(String source)                                  |   |

好，有一堆建構子可以用，但我們需要的是可以讀標準輸入流的Scanner，所以選擇Scanner(InputStream)。

那Java要怎麼取得這個標準輸入流呢？ 就是System物件裡面的靜態欄位in。 順便來看一下System有哪些欄位：

| 修飾子、型態             | 欄位  | 描述                                  |   |
| ------------------ | --- | ----------------------------------- | - |
| static PrintStream | err | The "standard" error output stream. |   |
| static InputStream | in  | The "standard" input stream.        |   |
| static PrintStream | out | The "standard" output stream.       |   |

好，現在我知道要在Java取得標準輸入流(standard input stream)，就是System.in這個東東，那就用他來初始化我們的Scanner物件吧。

```java
Scanner s = new Scanner(System.in);
```

現在我們有一個Scanner物件，取名為s，他可以幫我們從標準輸入流拿資料進來。

### 怎麼使用？ how to use?

Scanner 可以把一整行(line)的字串切成很多的token，預設是以空白(或tab)為基礎隔開，在透過各種next的方法，解析並轉換成我們需要的資料型態，然後回傳。

> 這裡所謂的token，硬要翻譯應該是『切割單元』。
>
> 舉個例：
>
> "My name is yubin." 這個字串對於Scanner來說，預設(空白分隔)會分成4個token，
>
> 分別是："My"、"name"、"is"、"yubin."，這就是token的概念。

來看一下Scanner提供的各種next方法：

| 回傳型態       | 方法               | 描述                           |   |
| ---------- | ---------------- | ---------------------------- | - |
| String     | next()           | 找下一個token並回傳。                |   |
| BigDecimal | nextBigDecimal() | 找下一個token並轉換成 BigDecimal 回傳。 |   |
| BigInteger | nextBigInteger() | 找下一個token並轉換成 BigInteger 回傳。 |   |
| boolean    | nextBoolean()    | 找下一個token並轉換成 boolean 回傳。    |   |
| byte       | nextByte()       | 找下一個token並轉換成 byte 回傳。       |   |
| double     | nextDouble()     | 找下一個token並轉換成 double 回傳。     |   |
| float      | nextFloat()      | 找下一個token並轉換成 float 回傳。      |   |
| int        | nextInt()        | 找下一個token並轉換成 int 回傳。        |   |
| long       | nextLong()       | 找下一個token並轉換成 long 回傳。       |   |
| short      | nextShort()      | 找下一個token並轉換成 short 回傳。      |   |
| String     | nextLine()       | 讀一整行的字串回傳。(包含空白，讀到換行為止)      |   |

這些是比較常用的next方法，基本上可以滿足大部份的需求，要進一步了解還是要養成看[doucment](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html)的習慣，沒事多翻翻增加熟練度。

範例程式：

```java
import java.util.Scanner;
public class Test {
    public static void main(String[] args){

        Scanner s=new Scanner(System.in);

        System.out.println("你好我是JP，請問你的名字是？");
        String name = s.next();
        System.out.println(name+"，很高興認識你，請問您今年幾歲？");
        int age =s.nextInt();
        System.out.println(age+"歲呀，可惜我不清處我幾歲 Q_Q");
        System.out.println("嗯...那你喜歡喝什麼飲料呢？");
        String drink =s.next();
        System.out.println(drink+"是嗎！我沒喝過，我馬上去嘗試一下，掰掰囉~");

        System.out.println("===== 系統提示 =====");
        System.out.println("JP(Java Program)已無回應，程式結束。");

        s.close();    // 程式結束前關閉Scanner物件是好習慣。
    }//end of main(String[])
}//end of class Test
```

執行結果：

```
你好我是JP，請問你的名字是？
// 使用者輸入：小婷
小婷，很高興認識你，請問您今年幾歲？
// 使用者輸入：18
18歲呀，可惜我不清處我幾歲 Q_Q
嗯...那你喜歡喝什麼飲料呢？
// 使用者輸入：水
水是嗎！我沒喝過，我馬上去嘗試一下，掰掰囉~
===== 系統提示 =====
JP(Java Program)已無回應，程式結束。
```

利用Scanner物件接到標準輸入流就可以營造出互動的感覺。 (應該有吧XD)

### 示意圖(從左到右)：

![](broken-reference) 可以把資料流想像成水流，Scanner是我們的接水工具，接進來利用他的方法處理資料。

## 讀到結束

很多時候我們會希望程式可以一直讀，讀到檔案結束或輸入結束，Scanner當然也可以透過方法做到。

hasNext()系列方法，回傳boolean，表示接下來還有沒有東西：

| 回傳值     | 方法                  | 描述                                 |   |
| ------- | ------------------- | ---------------------------------- | - |
| boolean | hasNext()           | 如果還有token可以讀回傳true。                |   |
| boolean | hasNextBigDecimal() | 如果下個token可以被解析成 BigDecimal 回傳true。 |   |
| boolean | hasNextBigInteger() | 如果下個token可以被解析成 BigInteger 回傳true。 |   |
| boolean | hasNextBoolean()    | 如果下個token可以被解析成 boolean 回傳true。    |   |
| boolean | hasNextByte()       | 如果下個token可以被解析成 byte 回傳true。       |   |
| boolean | hasNextDouble()     | 如果下個token可以被解析成 double 回傳true。     |   |
| boolean | hasNextFloat()      | 如果下個token可以被解析成 float 回傳true。      |   |
| boolean | hasNextInt()        | 如果下個token可以被解析成 int 回傳true。        |   |
| boolean | hasNextLong()       | 如果下個token可以被解析成 long 回傳true。       |   |
| boolean | hasNextShort()      | 如果下個token可以被解析成 short 回傳true。      |   |
| boolean | hasNextLine()       | 如果還有下一行回傳true。                     |   |

依需求，使用這一系列的方法就可以做到輸入到結束為止。

大概像這樣：

```java
Scanner s =new Scanner(System.in);
while(s.hasNext()){
    System.out.println(s.next());
}
s.close();
```
