# 關係、條件運算子

> 介紹關係、條件運算子的基本使用方法

## 關係運算子 Relational Operators

關係運算子是二元運算子，判斷兩個數值之間的關係：等於、不等於、大於、大於等於、小於、小於等於，回傳布林值(true or false)。

| Operator 運算子 | 描述    |   |
| ------------ | ----- | - |
| ==           | 等於    |   |
| !=           | 不等於   |   |
| >            | 大於    |   |
| >=           | 大於或等於 |   |
| <            | 小於    |   |
| <=           | 小於或等於 |   |

範例程式：

```java
int a = 1;
int b = 2;
System.out.println(a == b);
System.out.println(a != b);
System.out.println(a > b);
System.out.println(a >= b);
System.out.println(a < b);
System.out.println(a <= b);
```

執行結果：

```java
false
true
false
false
true
true
```

## 條件運算子 Conditional Operators

條件運算子是二元運算子，可以做邏輯的或(or)運算以及邏輯的和(and)運算。

| Operator 運算子 | 描述         |   |
| ------------ | ---------- | - |
| &&           | 邏輯和(and)運算 |   |
| \|\|         | 邏輯或(or)運算  |   |

Java的條件運算子具有『短路(short-circuiting)』特性，這代表從左到右只要確定運算式的結果了，就不會繼續運算下去。

範利程式：

```java
boolean t = true;
boolean f = false;
System.out.println(t && t);
System.out.println(t && f);
System.out.println(f && t);
System.out.println(f && f);
System.out.println(t || t);
System.out.println(t || f);
System.out.println(f || t);
System.out.println(f || f);
```

執行結果：

```java
true
false
false
false
true
true
true
false
```

## 真值表：

&& (and)的原則是，全部都要為true，最後才會是true。

| &&        | **true** | **false** |   |
| --------- | -------- | --------- | - |
| **true**  | true     | false     |   |
| **false** | false    | false     |   |

|| (or)的原則是，只要有一個為true，最後就是true。

| \|\|      | **true** | **false** |   |
| --------- | -------- | --------- | - |
| **true**  | true     | true      |   |
| **false** | true     | false     |   |

## 短路(short-circuiting)特性：

若有一個條件計算式為：

```java
true || (true && false || (ture || false && true))
```

不管後面有多少，程式判斷到第一個true後面接的是or運算子，後面不管是什麼最後結果一定為true，所以後面的都會被『無視』，不會被執行、判斷到。

只要邏輯判斷式可以100%確定回傳結果，後面的都會被忽略。

通常是『true接到or』或『false接到and』，前者立刻回傳true，後者立刻回傳false。
