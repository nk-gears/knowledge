# Background Processing

### Que Based Processing

```javascript

 function processNextItemInQueRecursively(params){

   const dcUtil= params.dcUtil;
   var sheetObject = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Request-Que");
   var lastRow=sheetObject.getLastRow();
   while(lastRow>1){
   var requestItem=sheetObject.getRange(`A${lastRow}:G${lastRow}`).getValues()[0];
   sheetObject.deleteRow(lastRow);
    //Do the Processing here
    lastRow=sheetObject.getLastRow();
   }

 }

```

