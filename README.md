
Readme
------

ACME has a utility which generates audit reports - lists of files owned by
users. Substitute JAVA_HOME with your JVM installation and you can build & run
the utility like this:
    
    export JAVA_HOME=/usr/lib/jvm/java-7-oracle
    
    Install Maven .

Please see this article [article](http://www.mkyong.com/maven/how-to-install-maven-in-windows/) on installing Maven.

	Read this on getting up to speed with [Maven](http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

    Go to the root of your project in the terminal and type:

    mvn clean
    
    After you see Build Successful and All Tests are passed type:
    
    mvn package
    
    After you see Package Successful, goto <target> folder and type. 

	java -jar  audit-reporter.jar data/users.csv data/files.csv
	
	You can give full path for users and files input.

Example output:

	Audit Report
	============
	## User: jpublic
	* audit.xlsx ==> 1638232 bytes
	* movie.avi ==> 734003200 bytes
	* marketing.txt ==> 150680 bytes
	## User: atester
	* pic.jpg ==> 5372274 bytes
	* holiday.docx ==> 570110 bytes


Options
---------

### CSV Output
You can report - *CSV output format*.
    
    java -jar  audit-reporter.jar data/users.csv data/files.csv -c

Example output:

	jpublic,audit.xlsx,1638232
	jpublic,movie.avi,734003200
	jpublic,marketing.txt,150680
	atester,pic.jpg,5372274
	atester,holiday.docx,570110


### TOP #n files
You can report *TOP #n files*.

    java -jar  audit-reporter.jar data/users.csv data/files.csv --topN 3

Example output:

	movie.avi,jpublic,734003200
    pic.jpg,atester,5372274
    audit.xlsx,jpublic,1638232

