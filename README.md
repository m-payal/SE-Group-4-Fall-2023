# Scorecards
All the scorecards are placed in the Scorecards sub-directory. 

|**Project Name** | **Scorecard Filename**|
|-----------------|-----------------------|
|GITS             | SE Project - GITS.csv |
|ClassMateBot     | SE Project - ClassmateBot.csv|
|Simplii          | SE Project - Simplii.csv|
|Units_Converter_Extension | SE Project - units_converter_extension.csv |
|WolfTrack | SE Project - WolfTrack 3.0.csv|

# Project Demo Video (Simplii)
https://youtu.be/lQ1bWZrHnJk

# SE Project 1 Essay


## What was hard about this process:

Overall, we felt pain in these places. 
First of all, even though the database was hosted using cloud services like AWS, there were no clear instructions provided on how to modify the connections using our own accounts. 
The database connection needed aceess to an AWS account owned by previous developers and hence was not easily accessible.  
Since we were not able get credentials for one account and there were no instructions for a local setup, we had to abandon one project. This example was discovered in two repos, Wolftrack and Simplii. There was no way to immediately test if the project functions properly because the directions for setting up the local database were unclear.
Also, one project (Classmate_bot) was dependent on Heroku and needed an active Heroku account. Since Heroku removed free tier access, testing it was not possible. 

Second, the use cases of projects are not supported by the current implementation. The software is only functional for the use case shown in the repo and does not work for any other use case.
For instance, the units_converter_extension does not work with Chromium-based browsers like Chrome or Brave since such browsers do not support the JavaScript functions module.exports and require("module"). 

Additionally, obsolete systems may use libraries that are no longer supported or updated. Numerous packages, including gensim, are present for the project WolfTrack but are incompatible with the most recent Python version. The other dependencies of the project are incompatible with the working version of this package. 

The future scope of projects like GITS, Wolftrack, units_converter is not written in the docs. However, in the project Classmate_bot the future scope is mentioned clearly with all the different directions that we can take. 

Further, in the project Simplii, the database schema described in the docs is not complete. There are many intermediate views that need to be created. The only way to find this out was through database logs from in the code. This made the process harder since a lot of time was spent debugging by assuming all required tables were already created.  
In addition to this, the error messages sent from the system were not logged and only generic messages were sent to the user that did not give a clear indication of what went wrong. Hence the process of tracing errors became harder since we had to first trace the flow without the proper database tables and then figure out the exact error. 

 
## How that pain could have been avoided

+ If the instructions for utilizing the database were explicit and the database credentials were easily available, the problems mentioned may have been avoided.
+ The projects should be independent of any systems and versions since they were based on libraries that were version-based.
+ For the projects using Databases, a clear schema of all the tables as well as the intermediate tables that are required should be clearly mentioned. 
+ Last but not least, all the projects should have clear instructions on how to test on local environments and projects shouldn’t be dependent on online cloud services which cannot be accessed.


## What practices you are committing to perform in project2 to avoid that pain.

We intend to implement the following in our project2 implementations to address the aforementioned problems: 
+ Use the most recent versions of third-party packages and stay away from any that are still functional but have been marked as deprecated or will be deprecated in the near future. This ensures that the software setup is seamless at least in the short and medium term.
+ To enable the developers to quickly determine whether the project is functional, clearly describe how to test the software on the local system with local database servers. So that projects do not depend solely on cloud services like Heroku or cloud-based database like AWS
+ Have a clearly defined document that mentions the setup instructions clearly such that there is no ambiguity; like we found for the project GITS which ran after following the instructions as written on GitHub.
+ Testing software continuously, for example, check if you update any library to the latest version and, if is it compatible with existing libraries. If an update has changed the library significantly such that it no longer works with the rest of the project, mention it clearly so that next time, the developers know which libraries will get affected if a particular library is changed.
+ Creating a support document which will have all the common issues and how to resolve them. In addition to this, packages which are critical to the project as well as dependent on other libraries. Hence it would be easy to track which libraries work with specific versions of a language or other libraries. 
+ Add future scope which mentions the directions in which the project can be taken including short descriptions of what those features should achieve.
