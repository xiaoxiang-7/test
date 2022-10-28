---
description: >-
  本教程介紹瞭如何獲取小數點後兩位的浮點數，還列舉了一些示例程式碼來理解這個主題。獲取帶兩位小數的浮點數有幾種方法，如使用 printf()
  方法、DecimalFormat 類、String 類的 format() 方法等。我們來仔細看看這些例子。
---

# 如何列印帶有小數位的浮點數

### 使用 Java 中的 `printf()` 方法以 2 個小數位列印浮點數 <a href="#shi-yong-java-zhong-de-printf-fang-fa-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu" id="shi-yong-java-zhong-de-printf-fang-fa-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu"></a>

`printf()` 是一種向控制檯列印格式化輸出的方法。它類似於 C 語言中的 `printf()`。這裡，我們可以指定輸出的數字限制。`"%.2f"`指定它有 2 位小數。請看下面的例子。

```java
public class SimpleTesting
{	
	public static void main(String args[]) 
	{
		float Pi = 3.1415f;
		System.out.println(Pi);
		// Get only 2 decimal points
		System.out.printf("%.2f", Pi);
	}
}
```

輸出：

```
3.1415
3.14
```

### [在 Java 中使用 `DecimalFormat` 類以 2 個小數位列印浮點數](https://www.delftstack.com/zh-tw/howto/java/how-to-print-a-float-with-2-decimal-places-in-java/#%E5%9C%A8-java-%E4%B8%AD%E4%BD%BF%E7%94%A8-decimalformat-%E9%A1%9E%E4%BB%A5-2-%E5%80%8B%E5%B0%8F%E6%95%B8%E4%BD%8D%E5%88%97%E5%8D%B0%E6%B5%AE%E9%BB%9E%E6%95%B8) <a href="#zai-java-zhong-shi-yong-decimalformat-lei-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu" id="zai-java-zhong-shi-yong-decimalformat-lei-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu"></a>

`DecimalFormat` 是一個 Java 類，它提供了 Java 中格式化十進位制值的實用方法。這裡，我們使用 `setMaximumFractionDigits()` 方法來設定小數限制，使用 `format()` 方法來獲取格式化的輸出。

```java
import java.text.DecimalFormat;

public class SimpleTesting
{	
	public static void main(String args[]) 
	{
		float Pi = 3.1415f;
		System.out.println(Pi);
		DecimalFormat frmt = new DecimalFormat();
		frmt.setMaximumFractionDigits(2);
		// Get only 2 decimal points
		System.out.println(frmt.format(Pi));
	}
}
```

輸出：

```
3.1415
3.14
```

### [在 Java 中使用 `format()` 方法以 2 個小數位列印浮點數](https://www.delftstack.com/zh-tw/howto/java/how-to-print-a-float-with-2-decimal-places-in-java/#%E5%9C%A8-java-%E4%B8%AD%E4%BD%BF%E7%94%A8-format-%E6%96%B9%E6%B3%95%E4%BB%A5-2-%E5%80%8B%E5%B0%8F%E6%95%B8%E4%BD%8D%E5%88%97%E5%8D%B0%E6%B5%AE%E9%BB%9E%E6%95%B8) <a href="#zai-java-zhong-shi-yong-format-fang-fa-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu" id="zai-java-zhong-shi-yong-format-fang-fa-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu"></a>

Java `String` 類提供了一個 `format()` 方法來獲取格式化的輸出，但它返回的是一個字串物件，而不是一個浮點數。所以，我們需要將字串轉換為浮點數，以獲得最終的浮點數輸出。請看下面的例子。

```java
public class SimpleTesting
{	
	public static void main(String args[]) 
	{
		float Pi = 3.1415f;
		System.out.println(Pi);
		// Get only 2 decimal points
		String str = String.format("%.02f", Pi);
		Pi = Float.valueOf(str);
		System.out.println(Pi);
	}
}
```

輸出：

```
3.1415
3.14
```

### 在 Java 中使用 `DecimalFormat` 類以 2 個小數位列印浮點數 <a href="#zai-java-zhong-shi-yong-decimalformat-lei-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu-1" id="zai-java-zhong-shi-yong-decimalformat-lei-yi-2-ge-xiao-shu-wei-lie-yin-fu-dian-shu-1"></a>

我們可以使用 `DecimalFormat` 類的建構函式來指定小數位數的限制。在這裡，我們在建構函式中使用 `#` 字元，並使用 `format()` 方法來獲得格式化的輸出。

```java
import java.text.DecimalFormat;

public class SimpleTesting
{	
	public static void main(String args[]) 
	{
		float Pi = 3.1415f;
		System.out.println(Pi);
		DecimalFormat frmt = new DecimalFormat("#.##");
		// Get only 2 decimal points
		System.out.println(frmt.format(Pi));
	}
}
```

輸出：

```
3.1415
3.14
```
