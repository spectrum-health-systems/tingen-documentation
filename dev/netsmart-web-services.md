LIVE: <https://spectrumcsp.netsmartcloud.com/csp/spectrum/avpm/WEBSVC.UserManagement.CLS?WSDL>
SBOX: <https://spectrumcsp.netsmartcloud.com/csp/spectrumsbox/avpm/WEBSVC.UserManagement.CLS?WSDL>


1. Right-click on your project
2. Click **Add**
3. Click **Service Reference**
4. Click the **Advanced** button
4. Click the **Add Web Service** button
4. In the *URL* field, put the name of the Web Service you want to add. It should look something like this:

 ```
 http://<SERVER>:<PORT>/csp/AVPM/WEBSVC.<WEBSERVICE-NAME>.CLS?WSDL
 ```

 For example, to add the User Management Web Service, you would put:

 ```
 http://SANDBOX:8972/csp/AVPM/WEBSVC.ClientAdmission.CLS?WSDL
 ```

5. Click the arrow icon to the right of the URL. The Web Service should be found.

6. In the *Web reference name* field, give the Web Service a name. This is the name that your project will use to reference
    the Web Service, so make it something meaningful. For example:

  `NTSTWebSvcUATUserManagement`

7. Click **Add Reference**.

If you encounter an error at step #4, copy/paste the Web Service URL into a web browser. The WSDL code should be displayed.



1. Added the Web Service stuff (steps above)