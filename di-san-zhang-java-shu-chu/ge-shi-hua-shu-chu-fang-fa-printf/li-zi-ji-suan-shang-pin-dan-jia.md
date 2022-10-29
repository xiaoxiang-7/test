# 例子：計算商品單價

### 問題

使用 Java 撰寫一個程式，印出以下問題的結果 (由鍵盤輸入兩個整數 m 與 n，分別代表一盒雞蛋售價 m 元，每一盒中包含 n 顆雞蛋)。 假設小明的媽媽請小明幫忙買盒裝雞蛋，不同品牌、不同包裝、不同種類有不同的價格，媽媽請小明分析哪一種雞蛋的單價最便宜，請計算每顆雞蛋販售的單價為何？ 輸出至小數點後一位。

輸入範例： `99 8`

輸出範例： `12.4`

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
