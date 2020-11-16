

# Namespace/Classes

```javascript
var DataCollectorUtil = (function(ns) {
    ns.isSandbox = false;
    ns.config = {};
     ns.init = function(config) {
        this.config = config;
        this.someSheet={};
     }
     ns.getData = function(apiName) {
       const results = this.someSheet.getDataRange().getValues();
       let jsonDataList = results.map((row, index) => {
            const itemInfo = {
                rowId: index,
                isUpsert: row[4]
            };
            return itemInfo;
        });
       return jsonDataList;
    }
    return ns;
})(DataCollectorUtil || {});
```

