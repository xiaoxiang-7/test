# Java 輸出換行

### java 輸出換行 (`print`、`println` 與 `printf` 的分別)

不換行打印：

```java
System.out.print();
```

換行打印，輸出之後會自動換行：

```java
System.out.println();
```

按格式輸出：

```java
System.out.printf();
```

例如說以下程式碼：

{% code lineNumbers="true" %}
```java
public class Main
{
    public static void main(String[] args) {
         
        System.out.println(1111); //換行打印,輸出後自動換行
        System.out.print(1111); //不換行打印
        System.out.printf("分數是：%d",88); //按格式輸出
         
    }
    
}

```
{% endcode %}

會輸出：

```
1111
1111分數是：88
```
