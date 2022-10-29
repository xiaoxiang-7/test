# 例子：買雞蛋

### 問題

使用 Java 撰寫一個程式，印出以下問題的結果 (由鍵盤分別輸入整數m與n)。 假設小明的媽媽請小明幫忙買雞蛋，媽媽給小明新台幣 m 元，每顆雞蛋販售價格為新台幣 n 元，請計算小明可以買幾顆雞蛋回家。

輸入範例： `100 8`

輸出範例： `12`

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {
		
		int m, n, o;
		Scanner keyin = new Scanner(System.in);
		m = keyin.nextInt();
		n = keyin.nextInt();
		o = m/n;
		
		System.out.print(o);
	}
}
```

{% hint style="info" %}
參考資料：[Java 格式化輸出 (翻轉工作)](http://www.tsnien.idv.tw/Java1\_WebBook/chap2/2-5%20%E6%A0%BC%E5%BC%8F%E5%8C%96%E8%BC%B8%E5%87%BA.html)
{% endhint %}
