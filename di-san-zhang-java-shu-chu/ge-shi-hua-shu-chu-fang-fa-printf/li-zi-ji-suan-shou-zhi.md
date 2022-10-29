# 例子：計算收支

### 問題

假設小明每個月的零用金為新台幣1000元。請撰寫一Java程式，由鍵盤輸入5筆支出費用(三位數整數，單位：新台幣)，程式必須輸出零用金結餘金額，輸出格式如下：

&#x20;\[正、負號]xxxx，xxxx代表四位數整數值，不足四位數者，前面(左邊)補0。

|   | 輸入範例                                             | 輸出範例                                                                                             |
| - | ------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| 1 | <p>123</p><p>256</p><p>99</p><p>65</p><p>399</p> | <p>+1000</p><p>-0123</p><p>-0256</p><p>-0099</p><p>-0065</p><p>-0399</p><p>-----</p><p>+0058</p> |
| 2 | <p>123<br>256<br>99<br>65<br>600</p>             | <p>+1000</p><p>-0123</p><p>-0256</p><p>-0099</p><p>-0065</p><p>-0600</p><p>-----</p><p>-0143</p> |
| 3 | <p>181</p><p>256</p><p>99</p><p>65</p><p>399</p> | <p>+1000</p><p>-0181</p><p>-0256</p><p>-0099</p><p>-0065</p><p>-0399</p><p>-----</p><p>+0000</p> |

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {
		
		float m, n, o;
		Scanner keyin = new Scanner(System.in);
		m = keyin.nextInt();
		n = keyin.nextInt();
		o = m/n;
		
		System.out.printf("%.1f", o);
	}
}
```

`"%.1f"` 代表浮點數並輸出至小數點後一位。

{% hint style="info" %}
參考文章：

1. [Java 格式化、負值、零填充](https://stackoverflow.com/questions/12252780/java-formatting-negative-values-zero-padding)
2. [\[轉載\] Java 字符串格式化：String.format()方法的使用](https://jax-work-archive.blogspot.com/2015/02/java-stringformat.html)
{% endhint %}
