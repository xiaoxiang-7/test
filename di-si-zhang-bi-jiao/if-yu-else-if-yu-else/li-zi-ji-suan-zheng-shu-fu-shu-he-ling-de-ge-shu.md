# 例子：計算正數、負數和零的個數

### 問題

請撰寫一Java程式，由鍵盤輸入五個整數，程式需計算輸入的五個整數中，正整數、負整數以及0的個數，並依序輸出。

輸入範例：

`5 -2 339 -1 10`

輸出範例：

`3 2 0`

### 解答

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {	
	
	int positive = 0;
	int negative = 0;
	int zero = 0;
	Scanner sc = new Scanner(System.in);
	int b = sc.nextInt();
	int c = sc.nextInt();
	int d = sc.nextInt();
	int e = sc.nextInt();
	int f = sc.nextInt();
        
        if (b > 0) {positive = positive + 1;}
        else if (b < 0) {negative = negative + 1;}
        else {zero = zero + 1;}
        
        if (c > 0) {positive = positive + 1;}
        else if (c < 0) {negative = negative + 1;}
        else {zero = zero + 1;}
        
        if (d > 0) {positive = positive + 1;}
        else if (d < 0) {negative = negative + 1;}
        else {zero = zero + 1;}
        
        if (e > 0) {positive = positive + 1;}
        else if (e < 0) {negative = negative + 1;}
        else {zero = zero + 1;}
        
        if (f > 0) {positive = positive + 1;}
        else if (f < 0) {negative = negative + 1;}
        else {zero = zero + 1;}
        
        System.out.print(positive);
        System.out.printf(" " + negative);
        System.out.printf(" " + zero);
	}
}
```
