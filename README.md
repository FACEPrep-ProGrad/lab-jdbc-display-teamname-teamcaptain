![Image description](https://i1.faceprep.in/ProGrad/face-logo-resized.png)

# ProGrad Lab | ProGrad Premier League

Like the Indian Premier League (IPL) which happens during April & May every year. Our team organizes ProGrad Premier League at the same time for all the Cricketers in our team. Our PPL schema is a complete repository of limited-over format of Cricket, that includes details like teams competing, player representing each team, scoring details, umpire details etc.

Can you help out with the below task and take our database creation to completion?


## What Should You Do
```
Fork this repo
Clone this repo
Practice Java JDBC - class and object, Statements, Connections and CRUD.
```

## How To Submit
```
Upon completion, run the following commands:

git add .
git commit -m "ProGrad ID"
git push origin master

And finally, create a pull request so your ProGrad Mentor (PM) can review your work.
```

## Instructions

1. ***Do not modify the entire code.***
2. ***Edit the code as per the instructions.***
3. ***Go to Java Resources -> src folder.***
4. ***You database connection code should exist inside the utlity package.***
5. ***Your CREATE, READ, UPDATE and DELETE code should exist inside the dao package.***
6. ***Once the progressions are completed follow the instructions to run the application and test your code.***
7. ***Add appropriate jars to your project directory.***
8. ***To add dependencies, right click on your project, select build path - configure build path - select libraries tab - select add external jars and add the downloaded jar files.***

## Requirements
If you haven't downloaded OJDBC driver (ojdbc6.jar), then download using this link [https://www.oracle.com/database/technologies/jdbcdriver-ucp-downloads.html]

## Schema Diagram

![1 2](https://user-images.githubusercontent.com/61002120/76416050-5807d380-63c0-11ea-8d52-9e8750e800f9.png)


## Progression 0:

1. Right click on src folder and select new - file and name it as jdbc.properties.
2. You can use the jdbc properties given below in the NOTE section.

## Progression 1:

1. Create a class called as `ConnectionManager` inside the utility package.
2. Create a method public static Connection getConnection() which returns a connection object.
3. Use the method public static Properties loadPropertiesFile() to load the jdbc properties from the jdbc.properties file.


## Progression 2:

1. Create a model class called as `TeamCaptain` with below attributes,
	- captainld - Long 
	- captainName - String 

2. Include getter and setter methods for all the attributes
3. Include constructor with below arguments, 
	- public TeamCaptain(captainld, captainName)

## Progression 3:

1. Create a dao-class called as `TeamCaptainDAO` with thee below method,
	- `public TeamCaptain getTeamCaptainBylD(Long id)` - Method used to fetch the Captain information from the database based on the player id. 


## Progression 3:

1. Create a class called as `Team` with below attributes,
	- teamld - Long 
	- name - String 
	- teamCaptain - TeamCaptain 

2. Include getter and setter methods for all the attributes.
3. Include constructor with below arguments, 
	- `public Team(Long teamld, String name, TeamCaptain teamCaptain )`

## Progression 4:

1. Create a dao-class called as `TeamDAO` with below methods, 
	- `public List<Team> getAllTeams()` - Method used to fetch all the teams and their corresponding Captains from the database. 

## Progression 5:
1. Create a controller class called as Main.
2. Create appropriate objects and call the corresponding method to display the details as per the sample output format.


## Points to remember:
_DAO Layer - Data access layer provides the gateway to create, reterive, update or delete any data in the database. All database related operations will be performed in this layer._


### Note:

Use the below code to retreive the connection details from jdbc.properties to establish connection
```
public static Properties loadPropertiesFile() throws Exception {
	Properties prop = new Properties();	
	InputStream in = ConnectionManager.class.getClassLoader().getResourceAsStream("jdbc.properties");
	prop.load(in);
	in.close(); 
	return prop;
}
```
Create a file called as jdbc.properites. To create a file right click on the application - new - file - name the file as jdbc.properties.
```
jdbc.properties
#JDBC properties entry for ORACLE server
driver = oracle.jdbc.OracleDriver
url=jdbc:oracle:thin:@localhost:1521:xe
username=your_username
password=your_password

```    
**Sample Output**
```
List of all team and their captain 
Team Name 	Captain 
England 	Joe Root 
Australia 	Tim Paine
South Africa	Faf du Plessis 
India 		Virat Kohli
```

Happy Coding ProGrad ❤️!
