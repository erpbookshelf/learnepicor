# Prerequisities

Microsoft Windows and Microsoft SQL Server are required to run Epicor ERP 10. I'm running Epicor on Windows 2012 R2 Server and SQL Server 2014, but it can be run on anything from Windows Server 2008 or Windows 7 and SQL Server 2008. For a production environment, there is a list of certified stacks (combination of operating system and database) upon which Epicor is officially supported so that would be a concern for a production environment, but not for a test setup.

Although not everything below is a requirement, I performed a couple of steps just so that I don't have to go back to the documentation to check what's needed:
* On SQL Server, the Windows SYSTEM doesn't have the sysadmin role by default so it has been granted
* The full-text search component on SQL Server has to be installed
* Install roles and features for the Application Server, Web Server, MSMQ, COM, and Distributed Transations, with .NET 4.5 and .NET 3.5
* .NET WCF TCP activation must be enabled
* Ensure the IIS Management Service has been enabled
* Install VC++ runtimes

Note: Epicor ERP 10.1.400 setup will not run with .NET 4.6 installed.

After Epicor ERP 10.1.500.0 database is set up, the application server license & company are set and the application server deployed. Then, again within Application Server Configuration, the application server client path and config have to be set in the Admin Console Settings, followed by adding session impersonation in the user account properties. The task agent (in the admin console) and system agent (within the application) have to be added before applying the update. To update to 10.1.500.13, deploy the application server and login to the application to initiate the database update.
