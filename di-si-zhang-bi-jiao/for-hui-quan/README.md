# for 迴圈

`for` 迴圈的基本語法之一如下：

```java
for(初始式; 執行結果必須是boolean的重複式; 重複式) {
    陳述句;
}
```

`for` 迴圈語法的圓括號中，初始式只執行一次，通常用來宣告或初始變數，如果是宣告變數，結束 `for` 迴圈後變數就會消失。第一個分號後則是每次執行迴圈本體前會執行一次，必須是 `true` 或 `false` 的結果，`true` 就會執行迴圈本體，`false` 就會結束迴圈，第二個分號後，則是每次執行完迴圈本體後會執行一次。

實際來看個 `for` 迴圈範例，在文字模式下從 1 顯示到 10：

```java
package cc.openhome;

public class OneToTen {
    public static void main(String[] args) {
        for(var i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

這個程式白話讀來，就是從 `i` 等於 1，只要 `i` 小於等於 10 就執行迴圈本體，然後遞增 `i`，這是 `for` 迴圈的常見的應用方式。

如果 `for` 本體只有一行陳述句，`{` 與 `}` 可以省略，不過為了可讀性與可維護性而言，建議就算只有一行陳述句，也要撰寫 `{` 與 `}` 明確定義範圍。

`for` 迴圈圓括號中第二個複合陳述區塊若沒有撰寫，預設就是 `true`，偶而看到有人如下撰寫的話，表示無窮迴圈：

```java
for(;;) {
    ...
}
```

{% hint style="info" %}
原文：[Java :: for、while 迴圈 - OpenHome.cc](https://openhome.cc/zh-tw/java/syntax-abc/for-while/)
{% endhint %}
