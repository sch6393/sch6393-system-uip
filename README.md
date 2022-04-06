# sch6393-system-UIP
sch6393-system-UIP

<br>

# Web Page
* https://sch6393-system.web.app/
* https://sch6393-system.firebaseapp.com/

<br>

# Server
* https://sch6393-system-nodejs.herokuapp.com/

<br>

# TimeZone
* Asia/Tokyo (GMT+9)

<br>

# API
* Get Queue 
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

# Get userUid, apikey
* [Web Page](#Web-Page) ➞ Dash Board ➞ User Info

<br>

# Add Task, iTask Script
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

# Group (Task)
* [Web Page](#Web-Page) ➞ Dash Board ➞ Task ➞ Add Task ➞ Group ON/OFF
* Execute in order by registered iTasks on group (Limit 5 iTasks)
  >Queues, Tasks are Displayed yellow by executed in group

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

# Sample Test
* Sample File
  * [Process.xaml](Process.xaml)
* Sample Script
  ```C#
  {
    "type": "uipath",
    "xaml": "test.xaml"
  }
  ```

<br>

# README.md
* [English](README.md)
* [Japanese](README_JP.md)
