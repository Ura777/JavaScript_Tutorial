# JavaScript_Tutorial
## 目錄
* [環境設置](https://github.com/Ura777/JavaScript_Tutorial#%E7%92%B0%E5%A2%83%E8%A8%AD%E7%BD%AE)
* [Java環境變數設置](https://github.com/Ura777/JavaScript_Tutorial#java%E7%92%B0%E5%A2%83%E8%AE%8A%E6%95%B8%E8%A8%AD%E7%BD%AE)
* [Visual Studio Code相關設定](https://github.com/Ura777/JavaScript_Tutorial#visual-studio-code%E7%9B%B8%E9%97%9C%E8%A8%AD%E5%AE%9A)
* [課程介紹](https://github.com/Ura777/JavaScript_Tutorial#%E8%AA%B2%E7%A8%8B%E4%BB%8B%E7%B4%B9)
  * [Ch00 - Tomcat的管理](https://github.com/Ura777/JavaScript_Tutorial#ch00---tomcat%E7%9A%84%E7%AE%A1%E7%90%86)
  * [Ch01 - 基礎的JavaScript](https://github.com/Ura777/JavaScript_Tutorial#ch01---%E5%9F%BA%E7%A4%8E%E7%9A%84javascript)
  * [Ch02 - 變數、資料型態、運算元、運算子](https://github.com/Ura777/JavaScript_Tutorial#ch02---%E8%AE%8A%E6%95%B8%E8%B3%87%E6%96%99%E5%9E%8B%E6%85%8B%E9%81%8B%E7%AE%97%E5%85%83%E9%81%8B%E7%AE%97%E5%AD%90)
  * [Ch03 - 流程控制](https://github.com/Ura777/JavaScript_Tutorial#ch03---%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6)
  * [Ch04 - 函數與物件](https://github.com/Ura777/JavaScript_Tutorial#ch04---%E5%87%BD%E6%95%B8%E8%88%87%E7%89%A9%E4%BB%B6)
  * [Ch05 - 內建物件](https://github.com/Ura777/JavaScript_Tutorial#ch05---%E5%85%A7%E5%BB%BA%E7%89%A9%E4%BB%B6)
  * [Ch06 - DOM模型](https://github.com/Ura777/JavaScript_Tutorial#ch06---dom%E6%A8%A1%E5%9E%8B)
  * [Ch07 - Html5 API Canvas]()
* * *
## 環境設置
* 作業系統 = Windows 7
* JDK版本 = [1.8.0_171](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* Apache Tomcat版本 = [9.0.8](https://tomcat.apache.org/download-90.cgi)
* Visual Studio Code版本 = [Windows x64 User Installer Stable Build](https://aka.ms/win32-x64-user-stable)
* * *
## Java環境變數設置
* 取得並複製JDK安裝路徑  
 
        路徑通常為：  
		C:\Program Files\Java\jdk1.8.0_162
 
* 控制台 &gt; 所有控制台項目 &gt; 系統 &gt; 點選右邊的進階系統設定 &gt; 點選上方的進階標籤 &gt; 環境變數
* 在Administrator的使用者變數(U)區塊中點選新增按鈕，根據對應的欄位輸入以下的資料：  
 
    | 欄位名稱      | 輸入內容                            |
    |:-------------:|:-----------------------------------:|
    | 變數名稱(N)   | JAVA_HOME                           |
    | 變數值(V)     | C:\Program Files\Java\jdk1.8.0_162  |
 
* 在系統變數(S)的區塊中點選變數名稱為Path的選項 &gt; 點選編輯按鈕
* 按下鍵盤的右方向鍵 &gt; 輸入分號 &gt; 輸入以下內容：  
 
        %JAVA_HOME%\bin;
 
* 輸入完之後，一直按下確定按鈕。
* 打開命令提示字元視窗，輸入以下指令後按下Enter：  
 
        java
 
* 出現列表Java的功能列表，代表環境變數設置成功。
* * *
## Visual Studio Code相關設定
* 更改字體大小
  * 上方選單點選檔案 &gt; 喜好設定 &gt; 設定
  * 點選右邊視窗的使用者設定標籤，在下方輸入以下程式碼：
 
        {  
            "editor.fontSize": 22
        }
 
  * 按下快捷鍵Ctrl+S儲存
* * *
## 課程介紹
## Ch00 - Tomcat的管理
* 更改通訊埠
  * 去安裝Tomcat的路徑中尋找server.xml
 
        路徑通常為：  
		C:\Program Files\Apache Software Foundation\Tomcat 9.0\conf\server.xml
 
  * 使用文字編輯器開啟server.xml &gt; 尋找以下的程式碼：
 
        <Connector port="8080" protocol="HTTP/1.1"  
               connectionTimeout="20000"  
               redirectPort="8443" /> 
 
  * 將8080改成想要設定的數字
 
        例如：
		80
 
  * 修改完成後儲存檔案 &gt; 重新啟動Tomcat
* 虛擬資料夾與真實資料夾的對應
  * 去安裝Tomcat的路徑中尋找server.xml
 
        路徑通常為：  
		C:\Program Files\Apache Software Foundation\Tomcat 9.0\conf\server.xml
 
  * 使用文字編輯器開啟server.xml &gt; 尋找以下的程式碼：
 
        <Host name="localhost"  appBase="webapps"  
            unpackWARs="true" autoDeploy="true">
 
  * 在上述的程式碼下方新增以下的程式碼：
 
        <Context path="/虛擬資料夾名稱" docBase = "實體資料夾位置" debug="0" />  
		  
		例如：  
		<Context path="/test" docBase = "C:\JavaScript_Tutorial" debug="0" />
 
  * 修改完成後儲存檔案 &gt; 重新啟動Tomcat
  * 虛擬資料夾與實體資料夾的名稱都不能有中文字
* * *
## Ch01 - 基礎的JavaScript
* 程式碼撰寫在&lt;script&gt;&lt;/script&gt;標籤區塊內
* 在Head區塊的JavaScript程式碼
* 在Body區塊的JavaScript程式碼
* 引入外部JavaScript程式檔案
  * 在&lt;script&gt;內使用scr屬性
* 第1個JavaScript程式
  * Hello World
* * *
## Ch02 - 變數、資料型態、運算元、運算子
* 變數的宣告
* 判斷變數是否存在
* 數值的資料型態
  * 整數
  * 浮點數
* 字串的資料型態
  * 不支援單一字元的函數，例如chr()。
* 其他資料型態
  * 布林
  * Null
  * Undefined
* 跳脫字元
  * 使用反斜線「\」
* 運算子的優先順序
* 遞增與遞減運算子
* 比較運算子
* 邏輯運算子
* 位元運算子
  * Not運算：~
  * 左移運算：&lt;&lt;
  * 右移運算：&gt;&gt;
  * 無符號右移：&gt;&gt;&gt;
  * And運算：&amp;
  * Xor運算：^
  * Or運算：|
* 指定運算子
  * x+=y相當於x=x+y
* 資料型態的轉換
  * 會自動進行強制轉換
  * 轉換成整數：parseInt()
  * 轉換成浮點數：parseFloat()
* eval()
  * 將運算式的字串參數當作運算式，可以傳回運算式的計算結果。
* typeof()
  * 可以取得變數的資料型態
* * *
## Ch03 - 流程控制
* if
* if-else
* 巢狀if
* switch-case
* 條件運算子
  * ?:
* for
* for-in
* while
* do-while
  * 最少會跑1次迴圈
  * while後方要加上分號
* break
* continue
* 巢狀迴圈
* * *
## Ch04 - 函數與物件
* 自訂函數
* 擁有參數的函數
* 有回傳值的函數
* 自訂物件
* 使用with定義物件的屬性
* 建構元
* 物件的階層架構
  * 物件的屬性值可以是另外1個物件
* 增加新的物件函數之方法
* Prototype物件
* 增加新的Prototype物件函數之方法
* 擴充JavaScript內建物件
* Prototype物件的繼承
* * *
## Ch05 - 內建物件
* 物件種類
  * 隱性物件
  * 顯性物件
* Boolean物件
* Function物件
* Number物件
* String物件
  * 回傳Html標籤
  * 屬性length
  * toUpperCase()
  * toLowerCase()
  * indexOf()
  * lastIndexOf()
  * match()
  * search()
  * replace()
  * split()
  * substr()
  * substring()
  * concat()
* Array物件
  * 1維陣列
  * 多維陣列
  * 走訪方式
  * 屬性length
  * join()
  * concat()
  * reverse()
  * sort()
* Date物件
  * getTimezoneOffset()
  * toUTCString()
  * toLocaleString()
  * Date.parse()
  * Date.UTC()
* Math物件
  * 四捨五入：round()
  * 亂數：random()
* Global物件
  * 不能使用new來建立
  * 腳本語言引擎初始化後就會自動建立
  * 直接使用的屬性名稱
    * Infinity
    * NaN
* 例外處理
  * try-catch-finally
  * finally視情況而寫
* 內建物件的共用屬性
  * constructor
  * Global與Math物件不支援
* 內建物件的共用函數
  * toString()
  * valueOf()
* * *
## Ch06 - DOM模型
* Document Object Model
* DOM組成部分
  * DOM Core
  * DOM HTML
* 取得元素
  * getElementById()
  * getElementsByTagName()
    * 會回傳NodeList物件
* 取得指定的節點物件
  * item()
* 修改元素的內容
  * 屬性innerHTML
* 存取元素的尺寸與位置
  * 屬性offsetLeft
  * 屬性offsetTop
  * 屬性offsetWidth
  * 屬性offsetHeight
  * 屬性offsetParent
  * scrollIntoView()
* 瀏覽父節點
  * 屬性parentNode
* 瀏覽兄弟節點
  * 屬性previousSibling
* 瀏覽子節點
  * 屬性childNodes
    * 會回傳NodeList物件
* 存取標籤的屬性
  * item(index).屬性名稱
 
        例如：
        var pArray = document.getElementsByTagName("p");
        document.write("第1個段落的align屬性值：" + pArray.item(0).align);
 
* 新增節點
  * appendChild
* 插入節點
  * insertBefore()
* 刪除節點
  * removeChild()
* * *
## Ch07 - Html5 API Canvas
* 利用JavaScript取得Canvas元件
* 繪製長方形
* 繪製直線
* 繪製圓形
* 清除圖案
* 線條的粗細
* 線條的終端樣式
* 線性漸層
* 圓形漸層
* * *


