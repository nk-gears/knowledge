# Modal Dialogs

```javascript

function _showModal() {

  var html = HtmlService
  .createTemplateFromFile('ui-data-manager')
  .evaluate()
  .getContent();
  
  var sheetName = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet().getName();
  var template = HtmlService.createTemplate(html + "<script> var defaultArgs=" + JSON.stringify({sheetName:sheetName}) + " </script>");
  
 
  var htmlF= template.evaluate().setXFrameOptionsMode(HtmlService.XFrameOptionsMode.DEFAULT)
  .setHeight(400)
  .setWidth(750)
  
  SpreadsheetApp.getUi().showModalDialog(htmlF, ' Utility');
 
}
```

