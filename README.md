# OpenMRS-FamilyMedicalHistory

This FamilyMedicalHistory module was created to enhance functionality for the OpenMRS opensource medical record system.

------------------------------------------------------------------------
------------------------------------------------------------------------

PROJECT DETAILS:

This project was designed around trying to add to the OpenMRS software to make it more functional.
After review one thing found to be missing was a family medical history page for the patients.

A database schema for the family history was designed after discussions about what can and cannot go into a patients records concerning their family; due to confidentiality reasons. A vague 'relationship' status, condition and severity schema was implemented into the patients record from their record page, and can be viewed from there.

------------------------------------------------------------------------
------------------------------------------------------------------------
LIMITATIONS:


The module is tested to work on Windows 10 (64-bit).

The JDK version used is Oracle JDK 7 update 79 -- jdk-7u79-windows-x64.exe
	(NEEDS TO BE DOWNLOADED FROM http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html )
	( CLICK ACCEPT AGREEMENT BEFORE CLICKING TO DOWNLOAD )

The maven version used is 3.3.9
	(NEEDS TO BE DOWNLOADED FROM https://maven.apache.org/download.cgi -- click Binary zip archive -- apache-maven-3.3.9-bin.zip)
	
The openMRS version used is 2.3.1
	(NEEDS TO BE DOWNLOADED FROM http://openmrs.org/download/)


There is no guarantee that the module will work with either of these things altered.

------------------------------------------------------------------------
------------------------------------------------------------------------
THE SETUP:


Step 1: Install the dependencies:
	- Install the JDK (jdk-7u79-windows-x64.exe)
		* To confirm that it works, run 'java -version'
	- Extract and install the Maven (apache-maven-3.3.9-bin.zip)
		* Installation steps are described here: http://www.mkyong.com/maven/how-to-install-maven-in-windows/
		* Make sure the environment variables are set like in the tutorial
		* Run 'mvn -v' in command prompt to make sure maven is installed and works
	
Step 2: Set up the OpenMRS SDK for maven:
	- In command prompt, run 'mvn mvn org.openmrs.maven.plugins:openmrs-sdk-maven-plugin:setup-sdk'
	- After the process completes, update the SDK by running 'mvn openmrs-sdk:help -U'
	
Step 3: Build the family history module
	- Navigate to the directory \module\familymedicalhistory in command prompt with the use of 'cd' command
	- Run 'mvn install' inside that directory

------------------------------------------------------------------------
------------------------------------------------------------------------
RUNNING OPENMRS:


Step 1: Start up the openmrs standalone
	- Make sure you downloaded the standalone from http://openmrs.org/download/
	- Before starting, ensure you have no running instances of tomcat, mysql, or other server-like software
	- Run the \openmrs-standalone-2.3.1\openmrs-standalone.jar
	- If prompted, choose the "demonstration mode" 
		* Give it time to start up. Once finished, it will automatically attempt to open a browser window with the login screen.
		
Step 2: Log in to the "Impatient Ward" using these credentials:
	- Username: admin
	- Password: Admin123
	
------------------------------------------------------------------------
------------------------------------------------------------------------
THE DEPLOYMENT:


Step 1: Once logged in (see the steps 1 and 2 in 'RUNNING OPENMRS' section), navigate to the Module management page:
	- Go through System Administration -> Advanced Administration -> Manage Modules
	- Click "Add or upgrade the module"
	- Click "Choose file" under "Add module"\
	- Select the OMOD file: familymedicalhistory-1.omod from the directory \module\familymedicalhistory\omod\target
	- Click upload.
		* Give it some time to upload and deploy the module.
		
		
WARNING: If you wish to redeploy the module, make sure to undeploy it first:
	- Click trash can icon next to the module name and wait a minute
		
------------------------------------------------------------------------
------------------------------------------------------------------------
THE TESTING:


Step 1: Log in (see the steps 1 and 2 in 'RUNNING OPENMRS' section)

Step 2: Navigate to the Find Patient Record section

Step 3: Type in a random name (like Betty). Do it so that at least one of the patients from the demo database pop up.

Step 4: Click on any of the patients

Step 5: Once in the patient summary page, click on "Family Medical History" in the "General actions" tab (purple tab on the right)

Step 6: Enter the name of the patient you wish to edit the medical history of

Step 7: Click "Add to Family Medical History"

	- Once you enter the values, the added row(s) should show up in the table.
