# Triggers



#### Default Triggers

```javascript

function onOpen() {   
 var sheet = SpreadsheetApp.getActive();
 var menu = [ 
    {"name": "Configure Script Check Frequency", "functionName": "_configureTriggers"}
  ];  
  
  sheet.addMenu("📂  Utility", menu);  

}
```

#### Custom Triggers

```javascript

function _configureTriggers(){
  var minutesCheck=5;
  
  var ui = SpreadsheetApp.getUi(); // Same variations.

  var result = ui.prompt(
      'Configure Script Frequency',
      'Enter the minutes for the script check frequency',
      ui.ButtonSet.OK_CANCEL);

  // Process the user's response.
  var button = result.getSelectedButton();
  var text = result.getResponseText();
  if (button == ui.Button.OK) {
    // User clicked "OK".
    minutesCheck=parseInt(text);
  } else if (button == ui.Button.CANCEL) {
    // User clicked "Cancel".
   
  } else if (button == ui.Button.CLOSE) {
    // User clicked X in the title bar.
     
  }
  

  const controlSheetId=SpreadsheetApp.getActiveSpreadsheet().getId();
  const triggers = ScriptApp.getProjectTriggers();
  
  for (var i = 0; i < triggers.length; i++) {
    ScriptApp.deleteTrigger(triggers[i]);
  }

  ScriptApp.newTrigger('_scheduleHandler')
  .timeBased()
  .everyMinutes(minutesCheck)
  .create();
  
  runSetup();
  
}
```

