# OptionObject Error Codes

When an OptionObject is returned to Avatar, it requires one of the following single-digit integer Error Codes:

* *0* - No action taken
* *1* - Returns an Error Message with an "Ok" button, and stopsfurther processing of scripts
* *2* - Returns an Error Message with "OK" and "Cancel" buttons, and stops further scripts the user clicks "Cancel")
* *3* - Returns an Error Message with "Ok" button
* *4* - Returns an Error Message with "Yes" and "No" buttons and stops further scripts the user clicks "No")
* *5* - Returns a URL to be opened in a new browser
* *6* - Returns a form to be opened in Avatar
