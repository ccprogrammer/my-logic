# my-logic


 <br />

 ## # shared_preferences
 
 put this first
 
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
<!-- remove specific key  -->
 prefs.remove('save_name / key');
    
<!-- remove all key  -->
 prefs.clear();
 
<!-- but in the end just use saveData again because the key will be overwrite by it  -->
 
```
 
</details>


<br />


 <br />

 ## # Git Template Title

### 	• Git Template Widget

<details>
 <summary> View Code </summary>
 
```

```
 
</details>

<br />
