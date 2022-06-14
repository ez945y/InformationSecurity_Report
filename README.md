# 109AB0716資安報告

# 壹、WSL

## 一、安裝WSL

**SETP1  啟用 Windows 子系統 Linux 版**

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

**SETP2  啟用虛擬機器功能**

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

**SETP3  從以下連結下載 Linux 核心更新套件**

> [https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
> 

**SETP4  將 WSL 2 設定為預設版本**

```powershell
wsl --set-default-version 2
```

**SETP5  到微軟商店安裝Linux，這裡我選用Ubuntu 20.04.4 LTS**

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled.png)

## 二、檢查目錄

### 我們先來嘗試找出Ubuntu的檔案根目錄，結果發現裡面檔案都被隱藏起來了

### 這是為了避免用Window介面意外更動到Linux的檔案，造成錯誤

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%201.png)

## 三、Ubuntu教學

### 1.利用 `login`登入，並且輸入密碼

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%202.png)

### 2.BASH基本指令

- `pwd` 顯示目前所在位置(print word)
- `ls` 顯示目前所在位置的檔案(list)
- `cd` 切換當前所在位置的檔案(change word)
- `.` 代表目前所在位置
- `..` 代表目前所在位置的父資料夾
- `mkdir` 建立一個新的資料夾(make direction)
- `touch` 建立一個新檔案
- `vim` 開啟Vim編輯器

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%203.png)

### 3. 這樣我們就進到vim編輯器中

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%204.png)

### 4.按 I 進入編輯模式

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%205.png)

### 5. `#!` 代表通往直譯器的路徑，而我們直譯器 `bash` 預設放在 `/bin` 目錄中

### 若 `#` 就代表備註，此行並不會被執行

### 這裡我們用 `read`指令讀進input，並用 `$name`抓取變數name，`echo`印出結果

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%206.png)

### 6.嘗試利用`:p` 指令儲存 `hello.sh`檔案並退出 `vim` 筆記本

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%207.png)

### 7.但這樣會跳出來退出失敗，這是由於還並沒有儲存

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%208.png)

### 8.利用`:wp` 指令儲存 `hello.sh`檔案並退出 `vim` 編輯器

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%209.png)

### 9.利用`cat` 指令查看 `hello.sh`檔案內容

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2010.png)

### 10.利用`bash` 指令執行 `hello.sh`檔案

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2011.png)

# 貳、WSL的GUI

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2012.png)

### **1. 安裝VcXsrv**

下載點：[https://sourceforge.net/projects/vcxsrv/files/latest/download](https://sourceforge.net/projects/vcxsrv/files/latest/download)

### **2. 透過WSL安裝環境**

```bash
sudo apt-get install ubuntu-desktop gnome-tweak-tool

```

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2013.png)

### **3. 新增一個Bash Script用來啟動gui**

```bash
touch gui.sh
chmod u+x gui.sh
```

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2014.png)

### 4**. 以**vim編輯內容

```bash
#!/bin/bash
sudo service dbus restart
/mnt/c/Program\ Files/VcXsrv/vcxsrv.exe :0 -ac &
DISPLAY=0:0 XDG_SESSION_TYPE=x11 gnome-session
/mnt/c/Windows/System32/taskkill.exe /IM vcxsrv.exe /T /F
```

### 5**. 執行**

```bash
sudo ./gui.sh
```

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2015.png)

### 6**. 開啟X server**

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2016.png)

### 6**. 修改用戶名稱**

```bash
sudo chown –R username:username .cache
```

### 7.**理論上這樣就可以了，但我還是打不開**

# 參、改用套件來安裝GUI

### 1.****更新apt-get，確保list汰舊換新****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2017.png)

### 2.****安裝 Gedit****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2018.png)

### 3.****安裝 GIMP****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2019.png)

### 4.****安裝 Nautilus****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2020.png)

### 5.****安裝 VLC****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2021.png)

### 6.****安裝 X11 應用程式****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2022.png)

### 7.****安裝 Google Chrome for Linux****

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2023.png)

### 切換到暫存目錄： `cd /tmp`

### 透過 wget 安裝套件： `sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb`

### 取得穩定的版本： `sudo dpkg -i google-chrome-stable_current_amd64.deb`

### 修正安裝套件： `sudo apt install --fix-broken -y`

### 再設定一次套件：`sudo dpkg -i google-chrome-stable_current_amd64.deb`

![Untitled](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/Untitled%2024.png)

### 然後還是失敗了，不過還是有學到很多東西

# 肆、WebGoat

## 一、安裝流程:

### 1.下載JDK

![1.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/1.png)

### 2.下載Webgoat

![2.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/2.png)

### 3.設定環境變數

![3.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/3.png)

### 4.打開終端機

![4.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/4.png)

### 5.輸入指令開啟Webgoat

![5.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/5.png)

### 6.開啟瀏覽器，輸入[http://localhost:8080/WebGoat](http://localhost:8080/WebGoat)

![6.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/6.png)

## 二、使用流程

### 1.註冊帳號

![6.5.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/6.5.png)

### 2.登入成功!

![7.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/7.png)

### 3.打開Lession 1

![8.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/8.png)

### 4.第二節內容，輸入名字

![9.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/9.png)

### 5.當打開F12後發現是一個POST

![10.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/10.png)

### 6.查驗magic number，先送出之後觀測header

![11.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/11.png)

## 三、模擬Proxy

### 1.下載ZAP

![11.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/11%201.png)

### 2.設定port為8081

![12.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/12.png)

### 3.打開工具裡的選項

![15.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/15.png)

### 4.生成憑證且儲存

![16.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/16.png)

### 5.打開瀏覽器→設定→安全性→隱私→憑證

![17.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/17.png)

### 6.選擇受信任的根憑證授權單位

![18.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/18.png)

### 7.確認無誤點擊完成

![19.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/19.png)

### 8.設定→查詢→開啟電腦的Proxy設定

![13.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/13.png)

### 9.設定為一樣的8081

![螢幕擷取畫面 2022-05-16 123957.png](109AB0716%E8%B3%87%E5%AE%89%E5%A0%B1%E5%91%8A%20ef50ef32dd314e61b3726ed9c79a1e7c/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2_2022-05-16_123957.png)

# 

# 伍、Markdown語法

`H1`

# 測試文字

# 測試文字

---

`H3`

## 測試文字

## 測試文字

---

`H6`

### 測試文字

### 測試文字

---

`斜體`

*測試文字*

*測試文字*

---

`粗體`

**測試文字**

**測試文字**

---

`刪除線`

~測試文字~

~~測試文字~~

---

`小區間`

`測試文字`

`測試文`

---

`大區間`

/Callout

<aside>
📎

</aside>

---

`程式碼`

/code

```python
print("Hello World")
```

---

`代辦`

[]

- [ ]  

---

`引用`

>

- 

---

`清單`

- 測試文字

+ 測試文字

* 測試文字

- 測試文字

---

`數字清單`

1.

1.  

---

`照片`

/image

---

`字體顏色`

/color

---

`超連結`

/web

---

`目錄`

/toc

---

![GIHUB](httpts ”雙氣”) 

# 陸、參考資料

****[Windows PowerShell基本語法及常用命令](https://www.796t.com/content/1541753845.html)****

[Windows 10 WSL GUI介面 - HackMD](https://hackmd.io/@Luote/luotenote/%2F%40Luote%2Fwsl-gui#%E6%96%B9%E6%B3%95%E4%B8%80-%E9%80%8F%E9%81%8E-X-Server)

[[Ubuntu][教學] Linux基本指令#04. 產生空白資料夾、檔案與命名注意事項 - YouTube](https://www.youtube.com/watch?v=23fx6zNMX2c&list=PL2SrkGHjnWcwe-wh-JpOPNldKBh0094GH&index=9&ab_channel=ProgressBar%E9%80%B2%E5%BA%A6%E6%A2%9D%E7%B7%9A%E4%B8%8A%E8%AA%B2%E7%A8%8B)

[鳥哥私房菜 - 第十二章、學習 Shell Scripts (vbird.org)](https://linux.vbird.org/linux_basic/centos7/0340bashshell-scripts.php)

[Bash Shell Script教學與心得 (google.com)](https://sites.google.com/site/tiger2000/home)

[Shell echo命令 | 菜鸟教程 (runoob.com)](https://www.runoob.com/linux/linux-shell-echo.html)

[使用 WSL 執行 Linux GUI 應用程式 | Microsoft Docs](https://docs.microsoft.com/zh-tw/windows/wsl/tutorials/gui-apps)

[[Day 13] 來玩WebGoat！之1：安裝 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天 (ithome.com.tw)](https://ithelp.ithome.com.tw/articles/10206165)

****[Markdown - 易編易讀，優雅的寫文吧！](https://ithelp.ithome.com.tw/articles/10203758)****

**[筆記＆寫作神器 MarkDown 真希望我學生時期就懂](https://www.youtube.com/watch?v=vlFm3EVVj6Y&ab_channel=%E8%A8%AD%E8%A8%88%E5%B8%ABRexTheDesigner)**

**[Draw Diagrams With Markdown](https://support.typora.io/Draw-Diagrams-With-Markdown/)**

**[Math and Academic Functions](https://support.typora.io/Math/)**

**[為什麼許多人都改用 Notion 做為主力筆記軟體？看完這個你就明白了](https://www.youtube.com/watch?v=Q_PfYlAtvHc&t=441s)**

# 柒、心得

  由於WINDOW的關係跟老師介面不太一樣，只好去試著載WSL，安裝其實很順利，但很不清楚怎麼運行BASH，前期光要看清楚別人在幹嘛就很困難了，在做SCRIPT時更是花了很多文章，最後才總結出來，老實說我覺得網路文章真的很不詳細，而且大多都有版本差，一堆小小的差異就得要DUBUG上許久，但感覺研究之後真的清楚很多，相信未來有走程式都一定用的到LINUX，因此絕對是值得去學習的。
  至於資安這部分其實真的還是有很多需要去精進的，資安的世界真的是博大精深，雖然說以後不一定會走資安，但至少學幾招在身上自己用也很好，未來也會帶給我們幫助，並且過程中一步一步去實現，克服困難後的成就感，其時我還蠻喜歡的，另外在所有之中尤其是最喜歡MARKDOWN，後來學會之後真的幾乎都不用DOC了，真是太方便太好用了，配合NOTION使用實在是太讚了，整理筆記、作業甚麼的都可以簡單做出很精美的成品，謝謝老師們。
