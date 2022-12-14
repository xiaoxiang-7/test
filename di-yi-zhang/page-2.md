# 資料型態

> 介紹Java的資料型態。

## 何謂資料型態？

我們都很清楚資料在電腦裡的都是以位元(0或1)的方式儲存。

而 8個位元(bits)又組成1個位元組(byte)，一個byte被視為是一個資料的最小單位。

一個byte的內容可能是 "00100010"，這對程式來說到底代表著什麼？要怎麼使用這些資料呢？ 其實對電腦來說，那些就真的只是0跟1的數據，代表著什麼意義、怎樣去解讀他，都是程式設計師決定的。

00100010 可能可以解讀成，這是一個1byte大小的整數，代表十進位的66。或是代表1byte的字元，可能是'B'。因為解讀方式不同而在程式設計上需要的處理也不同，所以Java有一些事先定義好的資料型態，讓程式設計師可以直接利用。

## Java 的資料型態種類

1. 基本資料型態 Primitive type
2. 參考資料型態 Reference type

接下來章節會討論兩種類型的資料型態及差異。

總攬

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
