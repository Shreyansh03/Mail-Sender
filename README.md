# Mail-Sender
function myFunction() {
  
    var ss=SpreadsheetApp.openByUrl("https://docs.google.com/spreadsheets/d/1XTTD_pbrqughywwdSeIkjand8BZaGFyp4XKT61bzJ0k/edit#gid=0");
    var events=ss.getActiveSheet();
    var course = events.getSheetName();
    var firstrow=2;
    var numberofrows=events.getLastRow();
    for(var i=firstrow;i<=numberofrows;i++)
    {
        var name=events.getRange(i,1).getValue();
        var rollno=events.getRange(i,2).getValue();
        var email=events.getRange(i,3).getValue();
        var message=events.getRange(i,4).getValue();
        var score=events.getRange(i,5).getValue();
        var subject="Your Score";
        var message1 = "Hello "+ name+"\n"+"Roll no. - "+rollno+"\nYou scored "+score+" marks in "+course+" course\n"+message+"\n\nRegards \nShreyansh Agarwal";
        MailApp.sendEmail(email,subject , message1);
    } 
  }
  function mybutton()
  {
    myFunction();
  }
  
  
