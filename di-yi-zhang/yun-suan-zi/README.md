# 運算子

> 介紹Java中運算子有哪些種類

## 何謂運算子？What is Operator?

我們知道數學上 1+2 的結果是 3，這個 1、2 是運算元，+ 是運算子，3 是運算子的計算結果。在Java上也是類似的，程式設計師宣告了變數後勢必要對資料作一些運算。

運算子是一些特殊的符號可以對一個或兩個或三個運算元進行處理，從而得到結果。

## 運算子優先權 Operator Precedence

下表是運算子的優先度，由高到低。

優先度較高的運算子會比優先度較低的運算子更早進行運算。

同一行表示擁有相同優先度，若優先度相同的運算子同時出現：二元運算子除了指定運算子皆為**從左到右**執行，指定運算子是**從右到左**。

| 運算子Operators               | 優先度Precedence                                       |
| -------------------------- | --------------------------------------------------- |
| 後綴 postfix                 | expr++   expr--                                     |
| 單元 unary                   | ++expr   --expr   +expr   -expr   \~   !            |
| 乘法 multiplicative          | \* /  %                                             |
| 加法 additive                | + -                                                 |
| 位移 shift                   | <<  >>  >>>                                         |
| 關係 relational              | <  >  <=  >=  instanceof                            |
| 相等 equality                | ==  !=                                              |
| 位元和 bitwise AND            | &                                                   |
| 位元互斥或 bitwise exclusive OR | ^                                                   |
| 位元或 bitwise inclusive OR   | \|                                                  |
| 邏輯和 logical AND            | &&                                                  |
| 邏輯或 logical OR             | \| \|                                               |
| 三元 ternary                 | ? :                                                 |
| 指定 assignment              | =  +=  -=  \*=  /=  %=  &=  ^=  \|=  <<=  >>=  >>>= |

(表格來源：[Java Document](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html))
