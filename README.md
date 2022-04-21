# my-logic


 <br />

 ## # shared_preferences
 
 make class helper or whatever you call it for all the function and put this first
 
 `final Future<SharedPreferences> _prefs = SharedPreferences.getInstance();`

### 	• Save Data

<details>
 <summary> View Code </summary>
 
```
Future saveData({data}) async {
    final SharedPreferences prefs = await _prefs;
    prefs.setString('save_name / key', jsonEncode(data));
  }
```
 
</details>

### 	• Load Data

<details>
 <summary> View Code </summary>
 
```
Future loadData({singleData, listData}) async {
    final SharedPreferences prefs = await _prefs;
  
<!--  Single Data  -->
  if (prefs.containsKey('save_name / key')) {
      var prefsSingleData = jsonDecode(prefs.getString('save_name / key')!);
      
      singleData(prefsSingleData); // this is callback to update the screen data it cannot be use like singleData = prefsSingleData
    }
  
<!--  List Data  -->
    if (prefs.containsKey('save_name / key')) {
      final prefsData = jsonDecode(prefs.getString('save_name / key')!);
      for (var i = 0; i < prefsData.length; i++) {
        listData.add(prefsData[i]);
      }
    }
  }
```
 
</details>
 
 ### 	• Delete Data

<details>
 <summary> View Code </summary>
 
```
• remove specific key
 prefs.remove('save_name / key');
    
• remove all key
 prefs.clear();
 
but in the end just use saveData again because the key will be overwrite by it
 
```
 
</details>


<br />


 <br />

 ## # Date Time 
 
 more DateTime skeleton https://api.flutter.dev/flutter/intl/DateFormat-class.html

### 	• [Intl package](https://pub.dev/packages/intl)

<details>
 <summary> View Code </summary>
 
```
• to get current date time year
 var currentDate = DateTime.now();
 
• month day(number) / April 21
 String dateTime = DateFormat.MMMMd().format(DateTime.now());
 
• hour / 9:41 AM
 String hourTime = DateFormat.jm().format(DateTime.now());
   
• year / 2022
 String yearTime = DateFormat.y().format(DateTime.now());
 
• month day, year / July 10, 1996 
 String dateTime = DateFormat.yMMMMd().format(DateTime.now());
 
• month day year plus hour / 7/10/1996 5:08 PM 
 String dateTime = DateFormat.yMd().add_jm().format(DateTime.now());    
 
 
```
 
</details>

<br />

 ## # Git Template Title

### 	• Git Template Widget

<details>
 <summary> View Code </summary>
 
```

```
 
</details>

<br />
