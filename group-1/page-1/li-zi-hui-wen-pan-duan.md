# 例子：迴文判斷

### 問題

請撰寫一Java程式，判斷由鍵盤輸入的字串是否為迴文(英文大小寫視為相同)。若是則輸出YES；否則輸出NO。

\[提示]迴文是指一字串s由左至右讀取和由右至左讀取皆為同一字串。例如：racecar、686皆為迴文。

|   | 輸入範例    | 輸出範例 |
| - | ------- | ---- |
| 1 | Racecar | YES  |
| 2 | 5566    | NO   |

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {	
	    
		String str = "";
		Scanner input = new Scanner(System.in);
		str = input.next();
		str = str.toLowerCase(); // 將Str字符串中的字母全部轉為小寫
 
		StringBuffer sb = new StringBuffer(str);
		sb.reverse();// 將Str中的字符串倒置
 
		int count = 0;
		for (int i = 0; i < str.length(); i++) {
			if (str.charAt(i) == sb.charAt(i)) {
				count++;
			}
		}
		if (count == str.length()) {
			
			System.out.println("YES");
		} else {
			System.out.println("NO");
		}
	}
}
```

{% hint style="info" %}
參考文章：

1. [\[Java\] 將字元、字串轉成大寫或小寫](https://www.inote.tw/java-change-letter-to-uppercase-or-lowercase)
2. [java判断回文字符串的几种方法](https://blog.csdn.net/u013248516/article/details/38044979)
{% endhint %}
