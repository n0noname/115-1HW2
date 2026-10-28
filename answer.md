# 第2次作業題目-作業-HW2
>
>學號：113111130 (換成自己的)
><br />
>姓名：c黃貫栢 (換成自己的)
><br />
>作業撰寫時間：. (mins，包含程式撰寫時間，換成自己的)
><br />
>最後撰寫文件日期：2026/10/28 (換成自己的)
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x] 說明內容
- [x] 其他 (可以包含心得或是想跟老師反映)

## 說明內容

開始寫說明，該說明需說明想法，
並於之後再對上述想法的每一部分將程式進一步進行展現，
若需引用程式區則使用下面方法，
若為.cs檔內程式除了於敘述中需註明檔案名稱外，
還需使用語法` ```語言種類 程式碼 ``` `，其中語言種類若是要用python則使用py，java則使用java，C/C++則使用cpp，
下段程式碼為語言種類選擇csharp使用後結果：

```csharp
public void mt_getResult(){
    ...
}
```

若要於內文中標示部分網頁檔，則使用以下標籤` ```html 程式碼 ``` `，
下段程式碼則為使用後結果：

```html
<%@ Page Language="C#" AutoEventWireup="true" ...>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
<meta http-equiv="Content-Type" ...>
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
    </form>
</body>
</html>
```
更多markdown方法可參閱[https://ithelp.ithome.com.tw/articles/10203758](https://ithelp.ithome.com.tw/articles/10203758)

請在撰寫"說明程式與內容"該塊內容，請把原該塊內上述敘述刪除，該塊上述內容只是用來指引該怎麼撰寫內容。

# 1-a：
![alt text](img/1.png)
<br />

![alt text](img/2.png)
<br />

![alt text](img/3.png)
<br />

# 1-b：
```
void Update() {                                                   // 生命週期函式：每一影格（Frame）自動執行一次[cite: 1]
    Keyboard keyboard = Keyboard.current;                         // 宣告 Keyboard 變數，取得目前連接的作用中鍵盤裝置[cite: 2, 3]
    if (keyboard == null) {                                       // 防呆判斷：若系統偵測不到任何鍵盤實例[cite: 3]
        return;                                                   // 提早結束當前影格的執行，避免後續存取產生例外錯誤[cite: 3]
    }                                                             // 防呆判斷區塊結束

    // 1. 取得各按鍵目前是否被按下
    bool isW = keyboard.wKey.isPressed;                           // 宣告布林變數 isW，紀錄 W 鍵當前是否處於被按住狀態[cite: 2]
    bool isA = keyboard.aKey.isPressed;                           // 宣告布林變數 isA，紀錄 A 鍵當前是否處於被按住狀態
    bool isS = keyboard.sKey.isPressed;                           // 宣告布林變數 isS，紀錄 S 鍵當前是否處於被按住狀態
    bool isD = keyboard.dKey.isPressed;                           // 宣告布林變數 isD，紀錄 D 鍵當前是否處於被按住狀態

    // 2. 優先判斷 6 種雙鍵複合鍵組合（符合任一組即印出並 return，避免重複印出單鍵）
    if (isW && isA)                                               // 判斷條件：W 鍵與 A 鍵是否同時被按下
    {                                                             // W+A 判斷區塊開始
        Debug.Log("玩家按了 W+A 鍵！");                             // 在主控台輸出 W+A 複合鍵的訊息
        return;                                                   // 結束本次 Update，避免後續單鍵判斷被重複觸發
    }                                                             // W+A 判斷區塊結束

    if (isW && isS)                                               // 判斷條件：W 鍵與 S 鍵是否同時被按下
    {                                                             // W+S 判斷區塊開始
        Debug.Log("玩家按了 W+S 鍵！");                             // 在主控台輸出 W+S 複合鍵的訊息
        return;                                                   // 結束本次 Update，避免後續單鍵判斷被重複觸發
    }                                                             // W+S 判斷區塊結束

    if (isW && isD)                                               // 判斷條件：W 鍵與 D 鍵是否同時被按下
    {                                                             // W+D 判斷區塊開始
        Debug.Log("玩家按了 W+D 鍵！");                             // 在主控台輸出 W+D 複合鍵的訊息
        return;                                                   // 結束本次 Update，避免後續單鍵判斷被重複觸發
    }                                                             // W+D 判斷區塊結束

    if (isA && isS)                                               // 判斷條件：A 鍵與 S 鍵是否同時被按下
    {                                                             // A+S 判斷區塊開始
        Debug.Log("玩家按了 A+S 鍵！");                             // 在主控台輸出 A+S 複合鍵的訊息
        return;                                                   // 結束本次 Update，避免後續單鍵判斷被重複觸發
    }                                                             // A+S 判斷區塊結束

    if (isA && isD)                                               // 判斷條件：A 鍵與 D 鍵是否同時被按下
    {                                                             // A+D 判斷區塊開始
        Debug.Log("玩家按了 A+D 鍵！");                             // 在主控台輸出 A+D 複合鍵的訊息
        return;                                                   // 結束本次 Update，避免後續單鍵判斷被重複觸發
    }                                                             // A+D 判斷區塊結束

    if (isS && isD)                                               // 判斷條件：S 鍵與 D 鍵是否同時被按下
    {                                                             // S+D 判斷區塊開始
        Debug.Log("玩家按了 S+D 鍵！");                             // 在主控台輸出 S+D 複合鍵的訊息
        return;                                                   // 結束本次 Update，避免後續單鍵判斷被重複觸發
    }                                                             // S+D 判斷區塊結束

    // 3. 若沒有同時按雙鍵，才檢查單鍵輸入
    if (isW)                                                      // 條件判斷：若僅按下了 W 鍵
    {                                                             // W 判斷區塊開始
        Debug.Log("玩家按了 W 鍵！");                               // 在主控台輸出 W 鍵的訊息[cite: 2]
    }                                                             // W 判斷區塊結束
    else if (isA)                                                 // 條件判斷：若僅按下了 A 鍵
    {                                                             // A 判斷區塊開始
        Debug.Log("玩家按了 A 鍵！");                               // 在主控台輸出 A 鍵的訊息
    }                                                             // A 判斷區塊結束
    else if (isS)                                                 // 條件判斷：若僅按下了 S 鍵
    {                                                             // S 判斷區塊開始
        Debug.Log("玩家按了 S 鍵！");                               // 在主控台輸出 S 鍵的訊息
    }                                                             // S 判斷區塊結束
    else if (isD)                                                 // 條件判斷：若僅按下了 D 鍵
    {                                                             // D 判斷區塊開始
        Debug.Log("玩家按了 D 鍵！");                               // 在主控台輸出 D 鍵的訊息
    }                                                             // D 判斷區塊結束
}                                                                 // Update 函式結束
```
<br />

![alt text](img/a-s.png)

![alt text](img/s-d.png)

![alt text](img/w-a.png)

![alt text](img/w-d.png)


  



## 其他