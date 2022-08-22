# sch6393-system-UIP
sch6393-system-UIP

<br>

# README.md
* [英語](README.md)
* [日本語](README_JP.md)

<br>

# サーバー
* https://sch6393-system-nodejs.herokuapp.com/

<br>

# ウェブページ
* https://sch6393-system.web.app/
* https://sch6393-system.firebaseapp.com/

<br>

# タイムゾーン
* Asia/Tokyo (GMT+9)

<br>

# サンプルテスト
1. [userUid, apikeyを取得](#useruid-apikey取得)し、そのキーファイルを`ApiKey`フォルダーの内に移動
2. 以下のサンプルファイルを`Process`フォルダーの内に移動
    * [Process.xaml](Process.xaml)
    * [Sample.xaml](Sample.xaml)
3. `Add Task`ページでサンプルTaskを作成し、サンプルスクリプトを作成 
    ```JSON
    {
      "type": "uipath",
      "xaml": "Sample.xaml"
    }
    ```

<br>

# API
* Queue取得
  * 情報
    |Name|Value|
    |-|-|
    |URL|`https://sch6393-system-nodejs.herokuapp.com/api/queue/first`|
    |Method|POST|

  * 要請パラメータ (Request Parameters)
    |Name|Type|Description|
    |-|-|-|
    |userUid|String||
    |apikey|String||
    |factor|String|Client Classification|

  * 応答 (Response)
    ```JSON
    [
      {
        "seqqueue":"----------------------",
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
* [Web Page](#Web-Page) ➞ About
  * キーファイル作成
    ```
    userUid
    apikey
    factor
    ```
    >ファイル名 : `sch6393-system.key`

<br>

# Taskスクリプト追加
* [Web Page](#Web-Page) ➞ Task List ➞ Add Task

<br>

```
# iTaskスクリプト追加
* [Web Page](#Web-Page) ➞ iTask List ➞ Add iTask
```
>Suspend

<br>

```
# グループ (Task)
* [Web Page](#Web-Page) ➞ Dash Board ➞ Task ➞ Add Task ➞ Group ON/OFF
* 登録したiTaskをグループ化し、順序で実行（最大5個）
  >グループで実行されたQueueとTaskは黄色に表示
```
>Suspend

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
