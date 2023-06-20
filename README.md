//How to set current user resolved in client people picker with jquery and SPServices (or without)

SP.SOD.executeFunc('clientpeoplepicker.js" 'SPClientPeoplePicker',function(){

var userName= $().SPServices.SPGetCurrentUser();

//or var loginName = _spPageContextInfo.userLoginName;

SetUserFieldValue(fieldDisplayName,userName);

});

function SetUserFieldValue(fieldName, userName) {

var divPeoplePicker = $("[id$='ClientPeoplePicker'][title='" + fieldName + "']");

var PeoplePickerEditor = divPeoplePicker.find("input.sp-peoplepicker-editorInput[title='" + fieldName + "']")[0];

var PeoplePicker = SPClientPeoplePicker.PickerObjectFromSubElement(Peop1ePickerEditor);

PeoplePicker.AddUserKeys(userName);

}
