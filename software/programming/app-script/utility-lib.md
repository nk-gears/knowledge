# Utility Lib

#### Column to Letter and Letter to Column

```javascript
function columnToLetter(column) {
    var temp, letter = '';
    while (column > 0) {
        temp = (column - 1) % 26;
        letter = String.fromCharCode(temp + 65) + letter;
        column = (column - temp - 1) / 26;
    }
    return letter;
}

function letterToColumn(letter) {
    var column = 0,
        length = letter.length;
    for (var i = 0; i < length; i++) {
        column += (letter.charCodeAt(i) - 64) * Math.pow(26, length - i - 1);
    }
    return column;
}
```



```javascript

function parseDotNotation(str, val, obj) {
    var currentObj = obj,
        keys = str.split("."),
        i, l = Math.max(1, keys.length - 1),
        key;

    for (i = 0; i < l; ++i) {
        key = keys[i];
        currentObj[key] = currentObj[key] || {};
        currentObj = currentObj[key];
    }

    currentObj[keys[i]] = val;
    delete obj[str];
}

Object.expand = function(obj) {
    for (var key in obj) {
        if (key.indexOf(".") !== -1) {
            parseDotNotation(key, obj[key], obj);
        }
    }
    return obj;
};
```



```javascript
function testCall(){
  var obj={"Productcode":"FANT_9336473029905","Title":"Cotton Terry King Fitted Waterproof Mattress Protector","Image0":"https://images.skulibrary.com/media/sys_master/hd8/h60/10431103500318.jpg?response-content-disposition=inline;filename=FANT-9336473029905-0.jpg","Image2":"https://images.skulibrary.com/media/sys_master/hc0/hfd/10436504780830.jpg?response-content-disposition=inline;filename=FANT-9336473029905-2.jpg","Image3":"https://images.skulibrary.com/media/sys_master/h60/h90/10436505370654.jpg?response-content-disposition=inline;filename=FANT-9336473029905-3.jpg","Image4":"https://images.skulibrary.com/media/sys_master/hf7/hb9/10436505829406.jpg?response-content-disposition=inline;filename=FANT-9336473029905-4.jpg","Image5":"https://images.skulibrary.com/media/sys_master/h5a/h98/10436506288158.jpg?response-content-disposition=inline;filename=FANT-9336473029905-5.jpg","BuyerApproved":"true","SupplierCode":"F0353KNG0","GTIN":"9336473029905","Material":"Cotton","Colour":"White","Size":"King","CostPriceExGst":"34.99","SellPriceIncGst":"55","OverallHeight(MM)":"2040","OverallWidth(MM)":"1830","OverallDepth(MM)":"500","Box1Height":"70","Box1Width":"275","Box1Depth":"285","Box1CBM":"0.005486250000000001"};
  var resp=Object.entries(obj)
   for (const [curr, currElem] of Object.entries(obj)) {
    
   }
  
}


const findPaths = (
    obj,
    searchValue, {
        searchKeys = typeof searchValue === "string",
        maxDepth = 30
    } = {}
) => {
    const paths = []
    const notObject = typeof searchValue !== "object"
    const gvpio = (obj, maxDepth, prefix) => {
        if (!maxDepth) return

        for (const [curr, currElem] of Object.entries(obj)) {
            //if (searchKeys && curr === searchValue) {
            // To search for property name too ...
            paths.push(prefix + curr)
            // }

            if (typeof currElem === "object") {
                // object is "object" and "array" is also in the eyes of "typeof"
                // search again :D
                gvpio(currElem, maxDepth - 1, prefix + curr + "/")
                if (notObject) continue
            }
            // it's something else... probably the value we are looking for
            // compares with "searchValue"
            if (currElem == searchValue) {
                // return index AND/OR property name
                // paths.push(prefix + curr)
            }
        }
    }
    gvpio(obj, maxDepth, "")
    return paths
}

//prepareDataset(sourceInfo, products);



const getValuePathInObject = (obj, searchValue, bCompareValuesOnly, maxDeepLevel, currDeepLevel) => {

    var bShowInfo = false;

    maxDeepLevel = (maxDeepLevel || maxDeepLevel == 0) ? maxDeepLevel : 20;
    currDeepLevel = currDeepLevel ? currDeepLevel : 1;

    if (currDeepLevel > maxDeepLevel) {
        return [];
    } else {
        var charSeparator = "/";
        var paths = [];
        var i = 0;

        for (var curr in obj) {
            var currElem = obj[curr];

            if (currDeepLevel == 1 && bShowInfo) {
                console.log("getValuePathInObject_> Looking property \"" + curr + "\" ");
            }

            if (!bCompareValuesOnly && curr === searchValue) { // To search for property name too ...
                paths.push(curr);
            }

            if (typeof currElem == "object") { // object is "object" and "array" is also in the eyes of "typeof"
                // search again :D
                var deepPaths = getValuePathInObject(currElem, searchValue, bCompareValuesOnly, maxDeepLevel, currDeepLevel + 1);

                for (var e = 0; e < deepPaths.length; e++) {
                    paths.push(curr + charSeparator + deepPaths[e]);
                }
            } else { // it's something else ... problably the value we are looking for
                // compares with "searchValue"
                if (currElem === searchValue) {
                    // return index AND/OR property name
                    paths.push(curr);
                }
            }
            i++;
        }

        return paths;
    }
}


/**
 * Flatten an object.
 * https://stackoverflow.com/a/19101235/1027723
 *
 * @param {Object} data object to flatten
 * @return {Object} the flattened result
 */
function flatten(data) {
    var result = {};
    function recurse (cur, prop) {
        if (Object(cur) !== cur) {
            result[prop] = cur;
        } else if (Array.isArray(cur)) {
             for(var i=0, l=cur.length; i<l; i++)
                 recurse(cur[i], prop ? prop+"_"+i : ""+i);
            if (l == 0)
                result[prop] = [];
        } else {
            var isEmpty = true;
            for (var p in cur) {
                isEmpty = false;
                recurse(cur[p], prop ? prop+"_"+p : p);
            }
            if (isEmpty)
                result[prop] = {};
        }
    }
    recurse(data, "");
    return result;
}
```

