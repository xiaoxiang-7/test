# 參考資料型態

> 了解Java的資料型態種類，哪些算是參考資料型態。

## 何謂參考資料型態？

參考資料型態，Reference Data Type，在Java語言中，所有非基本資料型態(primitive types)的類型都是參考資料型態(Reference Types)。看完上一章節我們認識了Java預設好的8種基本資料型態，但很明顯，只有這8種是不夠用的！ 字串呢？陣列呢？自己定義的類別呢？

嗯，所有『非基本資料型態』的型態，都是參考資料型態。

基本資料型態與參考資料型態在記憶體配置的機制是不同的。

詳細說明後面章節會提到，這裡重點是要很清楚：

Java 語言可以分成兩種資料型態，

```java
基本資料型態 primitive data type
參考資料型態 reference data type
```

### 基本資料型態是 boolean、char、byte、short、int、long、float、double，這8種。

### 參考資料型態是『除了那8種以外的所有資料型態』：

1. 自定義的類別 (class)
2. 陣列 (Array)
3. 介面 (interface)
4. 列舉 (enum)
