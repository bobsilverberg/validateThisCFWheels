CFWheels with ValidateThis 

http://cfwheels.riaforge.org/
http://validatethis.riaforge.org/

requires:
# CFWheels 0.9.4
# ValidateThis 0.851
 
Download ValidateThis
Unzip validateThis's zip and place the validateThis folder in webroot of with the cfwheels application.
 
Exampe Of Directory Layout:
webroot
==index.cfm
==IsapiRewrite4.ini
==Application.cfc
====wheels
====views
====models
====events
====controllers
====validateThis
 
In events/onapplicationstart.cfm place this code:
<cfscript>
ValidateThisConfig = {JSRoot="/javascripts/",definitionPath="/models/"};
application.ValidateThis = createObject("component","ValidateThis.ValidateThis").init(ValidateThisConfig);
</cfscript>

Place the validateThis-XX.XX.zip plugin in the plugins folder of cfwheels.

Reload your cfwheels application.
Example: http://localhost/index.cfm?reload=true
 
You should be good to go now.
 
ADDITIONAL FOR DEMO

Follow the instructions in ValidateThis to setup the tables and datasource.
/ValidateThis/docs/DemoSetup.txt
http://github.com/bobsilverberg/ValidateThis/blob/master/ValidateThis/docs/DemoSetup.txt

In config/settings.cfm place this code:
<cfset set(dataSourceName="vtDemo")>
 
Unzip the Demo-XX-XX.zip file into CFWheel's webroot.

*** WARNING: Demo contains Models\Model.cfc which will be overwritten if you have code there, please copy and paste the Demo Models\Model.cfc code into yours ***

Reload your cfwheels application.
Example: http://localhost/index.cfm?reload=true

ValidateThis/CFWheels Demo: http://localhost/index.cfm/validateThis

You should be good to go now.