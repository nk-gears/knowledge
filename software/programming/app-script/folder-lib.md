# Folder Operations

````javascript

//Create folder if does not exists only
function createFolder(folderID, folderName) {
    var parentFolder = DriveApp.getFolderById(folderID);
    var subFolders = parentFolder.getFolders();
    var doesntExists = true;
    var newFolder = '';

    // Check if folder already exists.
    while (subFolders.hasNext()) {
        var folder = subFolders.next();

        //If the name exists return the id of the folder
        if (folder.getName() === folderName) {
            doesntExists = false;
            newFolder = folder;
            return newFolder;
        };
    };
    //If the name doesn't exists, then create a new folder
    if (doesntExists = true) {
        //If the file doesn't exists
        newFolder = parentFolder.createFolder(folderName);
        return newFolder;
    };
};


function createFolderBasic(folderID, folderName) {
    var folder = DriveApp.getFolderById(folderID);
    var newFolder = folder.createFolder(folderName);
    return newFolder.getId();
};

function createSpreadsheet(spreadsheetName, parentFolderId) {

    var ssNew = SpreadsheetApp.create(spreadsheetName, 50, 5);
    var finalFile = moveFileToAnotherFolder(ssNew.getId(), parentFolderId);
    return finalFile;

}



function moveFileToAnotherFolder(fileID, targetFolderID) {

    var file = DriveApp.getFileById(fileID);

    // Remove the file from all parent folders
    var parents = file.getParents();
    while (parents.hasNext()) {
        var parent = parents.next();
        parent.removeFile(file);
    }

    DriveApp.getFolderById(targetFolderID).addFile(file);
    return file;
}


````

