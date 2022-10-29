# 三元、型態比對運算子

> 介紹三元運算子的用法及型態比對運算子 instanceof。

## 三元運算子 Ternary Operator

三元，顧名思義要放入三個東西。

```java
判斷式 ？ 若判斷為真執行區塊 ： 若判斷為假執行區塊
```

範例程式：

```java
int a = 10;
int b = 7;
int c = 0;

boolean flag = true;
c = flag ? a : b;
System.out.println(c);

flag = false;
c = flag ? a : b;
System.out.println(c);
```

執行結果：

```java
10
7
```

發現到，三元運算子其實就是 if ... else ...的縮寫！

```java
if(判斷式){
    // 若判斷為真執行區塊
}else{
    // 若判斷為假執行區塊 
}
// 等同於
(判斷式)？(若判斷為真執行區塊)：(若判斷為假執行區塊)；
```

簡單的條件判斷是很不錯的用法，可使程式碼看起來精減。

## 型態比對運算子 Type Comparison Operator

instanceof

我們在設計Java程式的時候，有時候會想知道這個物件是不是屬於某個類別(class)、某個子類別(subclass)、或某個實作介面(interface)。此時就需要這個型態比對運算子 **instanceof** 來幫助我們作判斷，回傳布林值(true of false)。

使用方式：

```java
物件名稱 instanceof 類別名稱
```

範利程式：

```java
public class Main {
    public static void main(String[] args) {
        A a = new A();
        B b = new B();
        System.out.println(a instanceof A);
        System.out.println(a instanceof B);
        System.out.println(b instanceof B);
        System.out.println(b instanceof A);
    }
}
class A { }
class B extends A { }  // class B 繼承 class A，B是A的子類別，A是B的父類別
```

執行結果：

```java
true    // a是A物件
false   // a不是B物件
true    // b是B物件
true    // 因為class B繼承class A，物件b是class A的子類別物件，所以為true
```

詳細繼承概念，於『繼承』章節討論。
