# sch6393-system-UIP
sch6393-system-UIP

<br>

# ウェブページ
* https://sch6393-system.web.app/
* https://sch6393-system.firebaseapp.com/

<br>

# サーバー
* https://sch6393-system-nodejs.herokuapp.com/

<br>

# タイムゾーン
* Asia/Tokyo (GMT+9)

<br>

# API
* Queue取得
  * URL : `https://sch6393-system-nodejs.herokuapp.com/api/queue/first`
  * Method : POST
  * Parameter : userUid, apikey, factor
  * Return
    ```JSON
    [
      {
        "seqqueue":"---",
        "id":"----------------------------",
        "script":"{
                    "a": "a",
                    "b": "b",
                    "c": "c"
                  }"
      }
    ]
    ```

<br>

# userUid, apikey取得
* [Web Page](#Web-Page) ➞ Dash Board ➞ User Info

<br>

# Task, iTask スクリプト追加
* [Web Page](#Web-Page) ➞ Dash Board ➞ Task ➞ Add Task
* [Web Page](#Web-Page) ➞ Dash Board ➞ iTask ➞ Add iTask
* Script
  ```JSON
  {
    "a": "a",
    "b": "b",
    "c": "c"
  }
  ```

<br>

# グループ (Task)
* [Web Page](#Web-Page) ➞ Dash Board ➞ Task ➞ Add Task ➞ Group ON/OFF
* 登録したiTaskをグループ化し、順序で実行（最大5個）
  >グループで実行されたQueueとTaskは黄色に表示

<br>

# Crontab (Task)
```sh
# *  *  *  *  *
# 分 時 日 月 週

# 例
# 月曜日から金曜日まで毎日に11時30分と15時30分
30 11,15 * * 1-5

# 毎月2番目の月の1日に0時と12時
2番目の　At minute 0 past hour 0 and 12 on day-of-month 1 in every 2nd month
0 0,12 1 */2 *
```
>https://crontab.guru/

<br>

# スクリプトパーシング
```C#
JObject joScript = JObject.Parse(arg_jaHttpReturn[0]["script"].ToString());
String str_a = joScript["a"].ToString();
```

<br>

# サンプルテスト
* サンプルファイル
  * [Process.xaml](Process.xaml)
    >このファイルをProcessフォルダーに入れてテスト
* サンプルスクリプト
  ```C#
  {
    "type": "uipath",
    "xaml": "test.xaml"
  }
  ```

<br>

# README.md
* [英語](README.md)
* [日本語](README_JP.md)
