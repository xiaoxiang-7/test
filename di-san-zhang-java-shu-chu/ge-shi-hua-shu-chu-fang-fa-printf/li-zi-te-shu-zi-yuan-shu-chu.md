# 例子：特殊字元輸出

### 問題

請使用Java撰寫一程式，該程式輸出以下的字串符號：

"//^=^\\"/

### 解答

```java
public class Main
{
	public static void main(String[] args) {
	
	System.out.print("\\");
        System.out.print("\"");
        System.out.print("//^=^");
        System.out.print("\\");
        System.out.print("\\");
        System.out.print("\"");
        System.out.print("/");
        
	}
}
```

`"\\"` 代表輸出`\`。

`"\""` 代表輸出`"`。

輸出：

```
\"//^=^\\"/
```
