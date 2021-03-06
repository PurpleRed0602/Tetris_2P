Tetris 2P
===
###### tags:`GitHub`, `schoolwork`, `c#`

![](https://i.imgur.com/0rlGku3.png)

## Introduction
**Made by PurpleRed in 2021**

This repository is my personal final project of **"109-2 視窗程式設計"**. The game is based on the popurlar game in Facebook: **Tetris Battle**.


## How to Play
Just like Tetris, but the opponent will give you some "mines" when he/she get score. You have to eliminate all of them ASAP, or you will die if your blocks and mines heap too high. So get more scores and KOs if you can!


## Control
### Player 1: 
* **A/D**: move left/right
* **S**: let the block fall faster
* **W**: rotate the block
* **B** or **Tab**: hold the block
* **Space** or **Caps Lock**: Straight falling
* Note: **B & Space** for those who prefer using left hand to control the block. **Tab & Caps Lock** for the others.

### Player 2: 
* **Left/Right**: move left/right
* **Down**: let the block fall faster
* **Up**: rotate the block
* **<** or **Numpad 2**: hold the block
* **>** or **Numpad 0**: Straight falling
* Note: **Numpad 2 & Numpad 0** for those who prefer using left hand to control the block. **< & >** for the others.


## Tools & Environments
**This repository is a Visual Studio 2019 project.**
* Language: Microsoft .NET Framework 4.7.2
* IDE: Microsoft Visual Studio 2019

**Make sure all of the header files & source files be added in the Visual Studio project before compiling on vs2019.**


## Special Thanks
**Thanks for those who test my game when it's unstable. I can't finish it without their help.**

Chien / 巨根君峰 / 卍煞氣a嘎珉卍 / [BoyBen](https://github.com/boyben001)<br>
子筠 / Mike / Ken / 77 / Ckyna / 靖哥 / 涵<br>
阿哲 / 渝涵 / 童龍龍 / Tom / Steven


## Release Log
* **version 0.1-beta (2021/05/25):**
    * 基本遊戲架構及排版
    * 視窗大小為 1200*700，但是好像有一點誤差
    * 目前只有1P能遊玩(2P尚未實作)
    * 兩分鐘倒數計時是數好玩的，遊戲實際上是不會結束的，除非你把它關掉
    * 方塊堆到最高也不會Game Over，尚未實作
    * 按鈕只有 **START!** 跟 **EXIT** 有被實作
* **version 0.1.1-beta (2021/05/25):**
    * **上版控 & GitHub**
    * 修正hold之後方塊沒有進行互換，而是一直保持在最先hold的某個方塊
    * 修正**方塊T**在第二型態(72)時，在地圖最左邊旋轉成73會跳出例外狀況(index out of range)
    * 修正**方塊J**在第四型態(64)時，在地圖最左邊旋轉成61會跳出例外狀況(index out of range)
    * 修正2P介面pictureBox的跑版問題(誤差問題真的有點...)
    * 為了讓視覺平衡，更改視窗大小為 1215*700
    * 1P按鍵修正，變得更直覺 & 人性化了 :D
    * Release Log內容改用中文撰寫，因為作者英文太爛
* **version 0.2-beta (2021/05/30):**
    * 添加地雷機制，為了測試壓力條跟地雷，**2P現在會每隔5秒發送2格壓力給1P**
    * 實作KO機制，方塊被疊滿是會被KO的(僅限1P)，2P那邊也會添加KO分數
    * 兩分鐘倒數計時終於有用了，也可以顯示誰輸誰贏(因為2P沒有遊玩，因此只要1P被KO一次就一定會輸)
    * 遊戲結束後，將會有一個按鈕可以回到主畫面(初始狀態)
    * 暫時移掉部分音效，版本確定穩定後會再加回來
    * 這版bug修好久...最好給我沒事
* **version 0.2.1-alpha (2021/05/31):**
    * **重要：這版已知有閃退的大問題，但是發生機率太低且發生時沒有任何相關數據，因此目前無法修正，將會邀請更多玩家來測試**
    * 有一位測試玩家回報1P的快速下降按鍵(S)時不時會卡住，甚至沒有反應，但是我玩得很順暢，因此不確定問題是出在程式上還是測試玩家的設備上，也是會交給更多玩家來測試看看
    * 降低遊戲難度，2P現在改為**每隔8秒發送2格壓力給1P**
    * 修正hold的數值在遊戲重新開始(第二局之後)未被初始化的問題，此漏洞導致新遊戲開始時第一個hold的方塊，會變成上一局遊戲中最後一個hold上去的方塊
    * 放置方塊的音效回來了
    * 修正README檔案資訊錯誤(連這個也會筆誤...)
    * 地雷機制想要還原原作，不過實施難度偏高，考慮開一個新分支試著寫寫看，但是暫不納入正規進度
* **version 0.2.2-beta (2021/06/01):**
    * 為了測試方便，在2P實作之前，**1P的WSAD鍵位暫時分別以上下左右鍵代替**
    * 修正1P在按下**方塊快速下降鍵**的同時被KO之後，1P方塊下降速率沒有回到正常速度的問題
    * 修正receiveMine函式中，新增的地雷數計算結果可能會產生負整數的情況，此漏洞導致在重新繪製grids時會跳出例外狀況(index out of range)
* **version 0.2.3-beta (2021/06/03):**
    * 有一位優質的測試玩家在遊戲還在倒數的時候，手指很健康的一直按**方塊直接下降鍵**，意外發現了在倒數畫面時，方塊就可以讓玩家直接下降的漏洞，此漏洞會使偵測KO的邏輯錯誤，導致誤判玩家KO的情況發生
    * 重新撰寫偵測鍵盤按鍵的程式邏輯，此改進將會使玩家的操作更加順暢
* **version 0.3-beta (2021/06/11):**
    * 2P實作完成！現在已經可以雙人遊玩了
    * 所有鍵位恢復正常，請依此檔案中的規範為準
    * 修正玩家一直按下**方塊直接下降鍵**時，堆到最上面不會被KO的情況
    * 更新README檔案內容
* **version 0.3.1-beta (2021/06/14):**
    * 改進方塊隨機邏輯，現在不會再出現連續掉落相同方塊的情況了！
    * 新增更多音效(方塊直接落下時觸底的音效、勝利平手音效)
* **version 0.4-beta (2021/06/19):**
    * 此版將進行最終調校和細部功能實作
    * 主畫面按鈕更改，將RULES按鈕改為SETTINGS，將OPTION按鈕改為ABOUT
    * 實作SETTINGS按鈕，玩家可以**調整自己的方塊落下速率**藉由按下此按鈕
    * 實作ABOUT按鈕，將可以查看此專題的相關資訊(GitHub, 版本號...等)
    * 再次改善偵測鍵盤的程式邏輯，此改進將避免發生按一次按鈕卻直接下降兩個方塊的情況
    * 修正一直按下**方塊快速下降鍵**的時候，方塊留在原地不會下降的情況
* **version 1.0 (2021/06/20):**
    * **正式發行版本，沒意外的話也是最後一版，enjoy the game :)**
    * 在README檔案以及程式內補上致謝名單，感謝所有參與測試的玩家！
    * 目前已發現的遊戲體驗缺陷：一直按著某個鍵是可以連續移動或旋轉的，但是只要按下其它按鍵，就無法繼續連續移動或旋轉。在版本號0.3.1-beta不會有這個問題，只是此寫法會造成版本號0.4-beta所發現的bug(按一次按鈕卻下降兩個方塊)，比較嚴重性之後，因此選擇犧牲此遊戲體驗
* **version 1.0.1 (2021/06/20):**
    * 緊急修正抵銷壓力函式的計算錯誤