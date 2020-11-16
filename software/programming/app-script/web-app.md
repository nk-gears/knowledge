# Web App

#### Post API

```javascript
function doPost(e){

  const queryString=e.queryString;
  const apiName=e.parameter.api;
  const token=e.parameter.token;
  const postData=e.postData.contents;
 
  }
  return ContentService.createTextOutput(JSON.stringify(response)).setMimeType(ContentService.MimeType.JSON);
  
}

```

