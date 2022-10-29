# 基本與參考資料型態差異

> 討論兩種類型資料型態的差異，重點放在記憶體配置的不同。

## 記憶體區間

開始本節的討論前，我們需要知道在執行時期，記憶體區間可分為三個部份： 1. Global (全域) 2. Stack (堆疊) 3. Heap (堆積)

### Global 全域

用來放全域變數(global variable)、靜態變數(static variable)。

### Stack 推疊區

作業系統會自動化管理這個區塊，而要讓系統可以清楚的管理這些資訊，代表裡面存放的東西必須事先可以被計算好它的生命週期。這個區塊主要用來存放：區域變數(local variable)、方法的參數(method parameter)與方法的回傳位址(method return address)等。

上述這些東西在編譯時期就可以決定好生命週期，所以系統會管理什麼時候要回收資源。如果Stack區不夠用或是遞回涵式(recursive function)沒寫好，會產 StackOverflowError 。

### Heap 堆積區

可以被預測的資料放在堆疊區(Stack Memory)，而不可被預測的資料就放在堆積區(Heap Memory)。為什麼會有不可預測的資料呢？ 很多時候程式在執行時期才會知道要使用多少記憶體，而且該區塊的記憶體不知道什麼時候會不需要使用，通常透過new關鍵字的東西會被存放在這邊(c++也是，c的話就是malloc()及calloc()。)

這裡的資料系統不會自動回收，沒錯，所以隨著程式執行記憶體會越來越少，所以程式設計師必須自行管理此區的記憶體，但Java還是一貫很貼心的有機制會幫你清理這個Heap區，這個機制叫做『Garbage Collection 垃圾回收』，會幫你檢查哪部份的記憶體已不在使用，就會幫你釋放那部份的記憶體空間，所以Java設計師通常只要專心在程式的撰寫上。倘若Heap區記憶體不夠用，會產生OutOfMemoryError。

順帶一題，這裡的 Heap 與資料結構的 Heap 並無關聯。

global區太單純先不管，我們把焦點放在stack與heap的記憶體配置。

## 基本資料型態的宣告及給值： (int為例)

```java
int value ;
value = 10;
```

記憶體配置圖： ![](broken-reference)

程式剛開始執行，記憶體沒有變數，

`int value;` 執行的時候會在stack區切一塊int大小的空間，Java會初始化為0 (區域變數local variable不會自動初始化，要使用該變數前需要指定其值)，

`value = 10;` 指定整數10給變數value。

## 參考資料型態的宣告及給值： (假設有個自訂類別Human)

```java
Human tina;
tina = new Human();
```

記憶體配置圖： ![](broken-reference)

程式剛開始執行，記憶體沒有變數，

`Human tina;` 宣告了一個變數tina，會在stack區切一個參考(reference)大小的空間出來，這個參考(reference)預期會指向Human物件，Java會初始化內容為 null (指到沒有地方)。

`tina = new Human();` 這個敘述分兩部份看：

第一部份： 關鍵字 new 透過建構子來建構物件，建構出來的物件會放在 Heap 區。

第二部份： 透過指定運算子『=』，把剛剛創造出來的物件在Heap區的起始地址，指定給變數tina。

這就是為什麼，參考型態的類別需要 new 才能使用，如果沒有在Heap區佔有真實物件的資料，那它在Stack區就只是一個參考(reference)而已，而且預設為 null，若存取到 null 的物件變數，會出現NullPointerException 的例外，這也是常見的程式錯誤。

Java並沒有指標(pointer)的概念，在Java稱為『參考(reference)』，為了改善c/c++指標理解、操作不易的問題，全盤捨棄指標改用參考。嘛，雖然這裡的概念很類似。如果你懂指標在幹嘛，可以對照著思考，不懂的話最好去了解一下有個初步認識，畢竟寫程式還是要對記憶體的使用要有一定的理解。

很多人會說，不懂指標(pointer)不能說自己會寫c語言。 (不是我說的..)

那不懂參考(reference)應該就不能說自己會Java了 XD
