# userSystem 安裝教學

>### 資料夾內容

* java
 * userSystem (原始程式碼)

* war
 * userSystem.war

>### 安裝指示


* 下載

 1.下載 userSystem.war

 2.下載 Tomcat (建議使用9.0版) [[載點](http://us.mirrors.quenda.co/apache/tomcat/tomcat-9/v9.0.21/bin/apache-tomcat-9.0.21.zip)]

 3.下載MSSQL JDBC Driver [[載點](http://central.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/7.0.0.jre8/mssql-jdbc-7.0.0.jre8.jar)]

 4.下載JDK8 (建議使用openjdk 8) [[載點](https://github.com/ojdkbuild/ojdkbuild/releases/download/1.8.0.212-1/java-1.8.0-openjdk-1.8.0.212-1.b04.ojdkbuild.windows.x86_64.zip)]

* 安裝

 * 安裝JDK

 1.解壓縮JDK8 至指定資料夾

 2.自我的電腦或本機Icon按右鍵選取內容

 3.在出現的系統視窗的左側選擇進階系統設定

 4.在出現的系統內容視窗下方選擇環境變數

 5.在系統變數視窗內新增一個**JAVA_HOME**的變數，值為JDK的安裝路徑 (ex : [安裝路徑]\java-1.8.0-openjdk-1.8.0.212-1.b04.ojdkbuild.windows.x86_64)

 6.在系統變數視窗內選擇**Path**變數，點擊編輯

 7.新增一路徑為**%JAVA_HOME%\bin**

 8.打開命令提示字元視窗輸入**java -version** 確認是否有版本資訊出現，若無，請重新確認安裝步驟

 9.打開命令提示字元視窗輸入**javac -version** 確認是否有版本資訊出現，若無，請重新確認安裝步驟

 * 安裝Tomcat
 
 1.解壓縮Tomcat至指定資料夾
 
 2.將MSSQL JDBC Driver放至此路徑： [安裝路徑]\apache-tomcat-9.0.12\lib

 * 安裝userSystem.war

 1.將userSystem.war放置此路徑： [Tomcat安裝路徑]\apache-tomcat-9.0.12\webapps

 2.在此路徑找到**startup.bat**並執行：[Tomcat安裝路徑]\apache-tomcat-9.0.12\bin

>### 操作指示

* API開放端點
 * URL : **/user/api** POST


* 接受資料
 * 資料格式 : JSON
 * 資料內容 : userId / userName / pwd
 * 傳送資料範例 : {"userId":"abc10324","userName":"Sam","pwd":"abc9814016"}

* 回傳資料
 * 資料內容 : userId / userName or errorMsg
 * 傳送資料範例 : {"userName":"Sam5","userId":"abc10324"} / 
{"errorMsg":"ID already registed"}

* 操作

 1.使用ARC或PostMan做Request的發送

 2.打開ARC或PostMan選擇POST並輸入此URL : http://localhost:8080/userSystem/api/user

 3.在Body裡面輸入上述內容的JSON格式字串

 4.點選送出並取得Response

