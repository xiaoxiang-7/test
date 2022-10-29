# 例子：正負數前面補 "0"

負數-143和正數58，前面加上0，獲得四位數整數值：

```java
public class Main
{
	public static void main(String[]args) {
		
	int n = -143;
        int p = 58;
        
        String positive = String.format("%05d", n); //負數前面的"-"也算是一個，所以是5個字符
        System.out.println(positive);
        
        String negative = String.format("+%04d", p);//正數輸出"+"和4個字符
        System.out.println(negative);
	}
}
```

輸出：

```
-0143
+0058
```
