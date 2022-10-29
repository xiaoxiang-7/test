# 例子：身分證驗證

### 問題

我國的身分證字號有底下這樣的規則，因此對於任意輸入的身分證字號可以有一些基本的判斷原則，請您來判斷一個身分證字號是否是正常的號碼(不代表確有此號、此人)。

(1) 英文代號以下表轉換成數字

|          |          |          |
| -------- | -------- | -------- |
| A=10 台北市 | J=18 新竹縣 | S=26 高雄縣 |
| B=11 台中市 | K=19 苗栗縣 | T=27 屏東縣 |
| C=12 基隆市 | L=20 台中縣 | U=28 花蓮縣 |
| D=13 台南市 | M=21 南投縣 | V=29 台東縣 |
| E=14 高雄市 | N=22 彰化縣 | W=32 金門縣 |
| F=15 台北縣 | O=35 新竹市 | X=30 澎湖縣 |
| G=16 宜蘭縣 | P=23 雲林縣 | Y=31 陽明山 |
| H=17 桃園縣 | Q=24 嘉義縣 | Z=33 連江縣 |
| I=34 嘉義市 | R=25 台南縣 |          |

(2) 英文轉成的數字, 十位數的數字再加上個位數乘9

(3) 各數字從左到右依次乘以 8、7、6、5、4、3、2、1

(4) 求出(2),(3) 及最後一碼的和

(5) 步驟(4)計算的結果再除以10，若整除，則輸出"Valid ID"，否則輸出"Invalid ID"

例：T112663836 => 27112663836

2 + 7_9 + 1_8 + 1_7 + 2_6 + 6_5 + 6_4 + 3_3 + 8_2 + 3\*1 + 6 = 180

除以 10 整除，因此為通過驗證的身分證字號

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {	
	    
	    Scanner sc = new Scanner(System.in);
		String str = sc.next();
		int[] letterNums = {10,11,12,13,14,15,16,17,34,18,19,20,21,22,35,23,24,25,26,27,28,29,32,30,31,33};
		
		char letter = str.charAt(0); //取出第一個字母
		str = letterNums[letter - 'A'] + str.substring(1); 

		
		int total = str.charAt(0)-'0';
		for(int i=1; i<10 ; i++) {
			total += (str.charAt(i)-'0') * (10-i); //依序加總
		}
		//以10減去加總值之個位數後取個位數
		int checkNum = (10 - total % 10) % 10;
		
		//計算結果和最後一位數比較
		if(checkNum == (str.charAt(10)-'0')) {
			System.out.println("Valid ID");
		}else {
			System.out.println("Invalid ID");
		}
	}
}
```

{% hint style="info" %}
參考文章：

1. [字串（String） - Java學習筆記](https://kent010341.github.io/java-tutorial/basic-input.html)
2. [請教Java身分證字號驗證程式碼問題](https://ithelp.ithome.com.tw/questions/10206804)
{% endhint %}
