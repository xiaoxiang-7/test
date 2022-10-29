# 第一支Java程式

> 雖然前面幾個章結已經有寫過Java程式了，不過這篇在來深入一點看。

Java是物件導向程式語言，而物件由類別產生，因此我們要設計類別。

```java
class Test{
  /*
    這是第一支Java程式，執行後會在螢幕上顯示文字『Hello Java』
    最外層 class名稱必須與檔名相同 (Test.java)
  */
  public static void main(String[] args){

      System.out.println("Hello Java");  //顯示文字

  }//end of main(String[])

}//end of class Test
```

執行結果

```
Hello Java
```

## 類別定義

```java
class Test{

}//end of class Test
```

最外層的類別需要與檔名同名(Test.java)，裡面的程式碼定義這個類別的屬性、方法。

## 程式進入點 Program Entry

```java
public static void main(String[] args){

}// end of main(String[])
```

JVM在執行程式的時候，第一步會尋找程式進入點，Java的程式進入點被定義為main()，而且『必需』是 **public static void main(String\[] args)**。

public 代表這個方法是公開的，可以由外部被呼叫。

static 靜態的，靜態表示在程式剛開始執行前，就要把這些東西載入到記憶體。所以主程式必須是static ，不然記憶體中沒有你的程式碼是要執行什麼。

void 這是回傳值的型態，void表示沒有回傳東西。

main 是程式進入點的名稱，一定要叫這個名字，這是JVM定義的，大小寫必須相同。

String\[] args ，身為程式進入點的main可以接受字串陣列當做參數，這也是JVM定義好的，String\[] 表示字串陣列，args是為這些字串陣列取的變數名稱，當然也可以寫 main(String\[] aaa)。

## 標準輸出

```java
System.out.println("Hello Java");
```

每個Java的敘述以分號『；』作結尾，同一行可以寫多個敘述。

這個敘述可以這樣看：

System這個物件，裡面有一個欄位叫做 out，而這個out也是一個物件，他有一個方法叫做 println()。這個println()可以接受一個字串參數，可以在螢幕上顯示字串並換行。

## 多行註解

```java
/*
  多行註解範例
  包在裡面的都會被編譯器忽略
  詳細的註解可以幫助思緒清晰
*/
```

利用 /\*\*/ 夾起來的文字都是註解，也可以單行使用(但麻煩)

## 單行註解

```java
// 這是單行註解
```

用 // 後面的文字會被註解掉，適合用來標示這個方法或變數在幹嘛。

詳細的註解可以幫助閱讀，我自己的習慣是方法或類別的右大括號完就會註解一下，寫程式的時候邏輯比較清晰，不用花額外的時間思考，這個是哪邊的右大括號，或是這個方法要代什麼參數。

每個人註解的習慣都不同，但要知道通常你寫的程式不一定只有你會看(可能過幾天自己寫的也看不懂)，別人接到你的程式註解寫清楚會讓別人覺得你很棒棒，使程式碼更方便維護。所以盡量養成寫註解的習慣。
