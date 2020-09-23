<div align="center">

## Validate an HTML form control against a database without submission


</div>

### Description

I was fed up with entering a username on various websites, posting the form only for it to return with a server posted message that the username was already in use. This function will alert the user if the value he had entered was found to be already existing without the form being submitted. Later flavours of I.E. only
 
### More Info
 
Assumes that the user can create the simple ASP that does the Database lookup on the text that was entered.

Only supported by I.E 5 +


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Simon Goodwin](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/simon-goodwin.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |
**Category**       |[Forms Validation Processing](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/forms-validation-processing__2-76.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/simon-goodwin-validate-an-html-form-control-against-a-database-without-submission__2-3595/archive/master.zip)





### Source Code

```
// <!-- script for the header/js file --> //
function validateuserid(item,suserid)
{
	document.body.style.cursor='wait';
	// Create an instance of the XML HTTP Request object
	var oXMLHTTP = new ActiveXObject( "Microsoft.XMLHTTP" );
	// Prepare the XMLHTTP object for a HTTP POST to our validation ASP page
	// enter the path to your validation ASP[X]
	var sURL = "http://yourdomain/yourvalidatingpage.asp?userID=" + suserid
	oXMLHTTP.open( "GET", sURL, false );
	// Execute the request
	oXMLHTTP.send();
	if (oXMLHTTP.responseText == "exists") // if the ASP response.writes the string "exists" then
	{
		alert("Sorry - the User ID\n " + suserid + "\nalready exists!");
		item.value="";
		item.focus();
	}
	document.body.style.cursor='auto';
}
// <!-- HTML form control to validate --> //
<INPU[T] type=text maxLength=30 size=30 value="" name="username" class=TextBox onblur="validateuserid(this,this.value);">
```

