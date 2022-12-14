# CPU (Central Processing Unit / 中央處理器)


## What is CPU?

* 龐大的執行部門。

> 中央處理器 （英語：Central Processing Unit，縮寫：CPU）是電腦的主要裝置之一，功能主要是解釋電腦指令以及處理電腦軟體中的資料。1970年代以前，中央處理器由多個獨立單元構成，後來發展出由積體電路製造的中央處理器，這些高度收縮的元件就是所謂的微處理器，其中分出的中央處理器最為複雜的電路可以做成單一微小功能強大的單元，也就是所謂的核心。


## What is CPU 效能?

* 如何定義 CPU 的效能 (不是很準但堪用)：在某個時間內可以做多少工作。

> CPU的效能和速度取決於時鐘頻率（一般以赫茲或十億赫茲計算，即hz與Ghz）和每週期可處理的指令（IPC），兩者合併起來就是每秒可處理的指令（IPS）。IPS值代表了CPU在幾種人工指令序列下「高峰期」的執行率，指示和應用。而現實中CPU組成的混合指令和應用，可能需要比IPS值顯示的，用更長的時間來完成。而記憶體層次結構的效能也大大影響中央處理器的效能。通常工程師便用各種已標準化的測試去測試CPU的效能，已標準化的測試通常被稱為「基準」（Benchmarks）。如SPECint，此軟仵試圖類比現實中的環境。測量各常用的應用程式，試圖得出現實中CPU的績效。


## 核心數 與 CPU 效能

* 概算得出的效能當然無法與核心數成為 1:1 的線性關係，但大抵而言還是線性關係。

* 多核心比起單核心更能預防(電腦)運算崩潰。

> 提高電腦的處理效能，亦使用多核心處理器。原理基本上是一個積體電路插入兩個以上的個別處理器（意義上稱為核心）。在理想的情況下，雙核心處理器效能將是單核心處理器的兩倍。然而，在現實中，因不完善的軟體演算法，多核心處理器效能增益遠遠低於理論，增益只有50％左右。但增加核心數量的處理器，依然可增加一台計算機可以處理的工作量。這意味著該處理器可以處理大量的不同步的指令和事件，可分擔第一核心不堪重負的工作。有時，第二核心將和相鄰核心同時處理相同的任務，以防止崩潰。


## Reference

* [中央處理器 (wiki)](https://zh.m.wikipedia.org/zh-tw/%E4%B8%AD%E5%A4%AE%E5%A4%84%E7%90%86%E5%99%A8)