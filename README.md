![Image description](https://i1.faceprep.in/ProGrad/face-logo-resized.png)

# ProGrad Lab | ProGrad Premier League


## Progression 1:

Create `Main.java` with main method

Create `TeamCaptain.java` domain class with below attributes, 
```
captainld - Long 
captainName - String 
```
Include getter and setter method for all the attributes 
Include constructor with below arguments, 
`public TeamCaptain(captainld, captainName)` 


## Progression 2:

Create `TeamCaptainDAO.java` class with thee below method, 
`public TeamCaptain getTeamCaptainBylD(Long id)` - Method used to fetch the Captain information from the database based on the player id. 


## Progression 3:

Create `Team.java` domain class with below attributes, 
```
teamld - Long 
name - String 
teamCaptain - TeamCaptain 
```
Include getter and setter method for all the attributes Include constructor with below arguments, 
`public Team(Long teamld, String name, TeamCaptain teamCaptain )`


## Progression 4:

Create `TeamDAO.java` class with below methods, 
`public List<Team> getAllTeams()` - Method used to fetch all the teams and their corresponding Captains from the database. 


![1 2](https://user-images.githubusercontent.com/61002120/76416050-5807d380-63c0-11ea-8d52-9e8750e800f9.png)


### Note:

Use the below code to retreive the connection details from mysql.properties to establish connection
```
public static Properties loadPropertiesFile() throws Exception {
	Properties prop = new Properties();	
	InputStream in = ConnectionManager.class.getClassLoader().getResourceAsStream("jdbc.properties");
	prop.load(in);
	in.close(); 
	return prop;
}
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
