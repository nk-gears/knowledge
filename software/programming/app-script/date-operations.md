# Date Operations

```javascript
function getDateByTimestamp(timestamp) {
    return new Date(timestamp * 1000);
}

```


```javascript
function getDateByTimestamp(timestamp) {
    return new Date(timestamp * 1000);
}

```

```javascript

function getScriptTimeZone() {
    return SpreadsheetApp.getActive().getSpreadsheetTimeZone();
}


function computeInterval(start_time) {
    var end_time = new Date().getTime();
    return ((end_time - start_time) + ' ms');
}



function getUnixTimestamp(curDate) {
   
    if (!curDate) curDate = new Date();
    return Math.round((curDate).getTime() / 1000);

}


function getTimeByFormat(dateObject,_format) {
  var format="YYYY-MM-dd hh:mm a";
  if(_format)  format=_format;
 
  return Utilities.formatDate(dateObject, Session.getScriptTimeZone(),format);
}
function Sample(){
 log(Utilities.formatDate(new Date(), "Asia/Kolkata","YYYY-MM-dd'T'HH:mm:ssZZZZZ") );
}

function getTimestamp() {
    
    return Utilities.formatDate(new Date(), Session.getScriptTimeZone(),"YYYY-MM-dd'T'HH:mm:ssZZZZZ");

}
```

