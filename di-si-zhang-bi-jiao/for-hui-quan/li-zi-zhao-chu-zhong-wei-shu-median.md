# 例子：找出中位數(median)

### 問題

臺灣發行了200、500、1000等不同面額的五倍券，每人可領取1000元面額3張、500元面額2張、200元面額5張共5000元。若消費者欲使用五倍券支付消費金額，而且只能使用自己領取的5000元消費券，使用消費券支付不找零，消費券不足額部分改以其他方式支付。請使用Java撰寫一程式，讓消費者可以使用最少張的五倍券支付消費款項。

輸入說明:&#x20;

正整數N&#x20;

輸出說明:&#x20;

200-N1, 500-N2, 1000-N3 (N1, N2, N3為大於等於零的整數)

輸入範例： `1980`

輸出範例： `200-2, 500-1, 1000-1`

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {	
	    
	int N1 = 0;
	int N2 = 0;
	int N3 = 0;
	Scanner sc = new Scanner(System.in);
	int N = sc.nextInt();
		
	for(int s = 0; N >= 1000; s++) {
	N = N - 1000;
	N3 = N3 + 1;
        }
        for(int s = 0; N >= 500; s++) {
            N = N - 500;
            N2 = N2 + 1;
        }
        for(int s = 0; N >= 200; s++) {
            N = N - 200;
            N1 = N1 + 1;
        }
        
        System.out.print("200-");
        System.out.print(N1);
        System.out.print(", 500-"+N2);
	System.out.print(", 1000-"+N3);
	}
}
```

{% hint style="info" %}
參考資料：[Java :: for、while 迴圈 - OpenHome.cc](https://openhome.cc/zh-tw/java/syntax-abc/for-while/)
{% endhint %}
