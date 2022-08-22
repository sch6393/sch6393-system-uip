# sch6393-system-UIP
sch6393-system-UIP

<br>

# README.md
* [English](README.md)
* [Japanese](README_JP.md)

<br>

# Server
* https://sch6393-system-nodejs.herokuapp.com/

<br>

# Web Page
* https://sch6393-system.web.app/
* https://sch6393-system.firebaseapp.com/

<br>

# TimeZone
* Asia/Tokyo (GMT+9)

<br>

# Sample Test
1. [Create key file](#get-useruid-apikey) and put key file in `ApiKey` folder
2. Put this sample file in `Process` folder
    * [Process.xaml](Process.xaml)
    * [Sample.xaml](Sample.xaml)
3. Create sample task and write sample script in `Add Task`
    ```JSON
    {
      "type": "uipath",
      "xaml": "Sample.xaml"
    }
    ```

<br>

# API
* Get Queue
  * Info
    |Name|Value|
    |-|-|
    |URL|`https://sch6393-system-nodejs.herokuapp.com/api/queue/first`|
    |Method|POST|

  * Request Parameters
    |Name|Type|Description|
    |-|-|-|
    |userUid|String||
    |apikey|String||
    |factor|String|Client Classification|

  * Response
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

# Get userUid, apikey
* [Web Page](#Web-Page) ➞ About
  * Create key file
    ```
    userUid
    apikey
    factor
    ```
    >File name : `sch6393-system.key`

<br>

# Add Task Script
* [Web Page](#Web-Page) ➞ Task List ➞ Add Task

<br>

```
# Add iTask Script
* [Web Page](#Web-Page) ➞ iTask List ➞ Add iTask
```
>Suspend

<br>

```
# Group (Task)
* [Web Page](#Web-Page) ➞ Dash Board ➞ Task ➞ Add Task ➞ Group ON/OFF
* Execute in order by registered iTasks on group (Limit 5 iTasks)
  >Queues, Tasks are Displayed yellow by executed in group
```
>Suspend

<br>

# Crontab (Task)
```sh
# *       *     *    *      *
# Minutes Hours Days Months Week

# Example
# At minute 30 past hour 11 and 15 on every day-of-week from Monday through Friday
30 11,15 * * 1-5

# At minute 0 past hour 0 and 12 on day-of-month 1 in every 2nd month
0 0,12 1 */2 *
```
>https://crontab.guru/

<br>

# Parsing Script
```C#
JObject joScript = JObject.Parse(arg_jaHttpReturn[0]["script"].ToString());
String str_a = joScript["a"].ToString();
```

<br>
