# 例子：找出中位數(median)

### 問題

輸入三個正整數a、b、c，輸出a、b、c三數的中位數。

\[提示]：若X1、X2、…、Xn為經過排序(由小到大或由大到小)的數列，n是奇數，則中位數即為X(n+1)/2

輸入範例： `123 789 456`

輸出範例： `456`

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {	
	    
	    Scanner sc = new Scanner(System.in);
		int a = sc.nextInt();
		int b = sc.nextInt();
		int c = sc.nextInt();
		
		if (a>b && a>c) {
		    if (b>c)
		    System.out.print(b);
		    else
		    System.out.print(c);
		}
		else if (b>a && b>c) {
		    if (a>c)
		    System.out.print(a);
		    else
		    System.out.print(c);
		    
		}
		else {
		    if (a>b)
		    System.out.print(a);
		    else
		    System.out.print(b);
		    
		}
	}
}
```

{% hint style="danger" %}
解ˇ能
{% endhint %}
