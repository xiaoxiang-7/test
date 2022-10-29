# 例子：特定月份的日數

### 問題

請用Java撰寫一程式，由鍵盤輸入一整數m，0 < m <13，程式輸出m對應月份的日數。(假設該年度非閏年)

|   | 輸入範例 | 輸出範例 |
| - | ---- | ---- |
| 1 | `1`  | `31` |
| 2 | `2`  | `28` |

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {	
	    
	    Scanner sc = new Scanner(System.in);
		int m = sc.nextInt();
        
        if (m == 1) {
        System.out.print("31");
        }
        else if (m == 2) {
        System.out.print("28");
        }
        else if (m == 3) {
        System.out.print("31");
        }
        else if (m == 4) {
        System.out.print("30");
        }
        else if (m == 5) {
        System.out.print("31");
        }
        else if (m == 6) {
        System.out.print("30");
        }
        else if (m == 7) {
        System.out.print("31");
        }
        else if (m == 8) {
        System.out.print("31");
        }
        else if (m == 9) {
        System.out.print("30");
        }
        else if (m == 10) {
        System.out.print("31");
        }
        else if (m == 11) {
        System.out.print("30");
        }
        else if (m == 12) {
        System.out.print("31");
        }
        else {
        }
	}
}
```
