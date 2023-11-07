
# Team 10 MIST 4610 Project 1
## Team Name
## Team Members
1. Victoria Wiest @victoriawiest
2. Ashley Potts @ashley-potts
3. Emma Surbrook @emmasurbrook
4. Hayden Soley @HaydenSoley
5. Liam Kilner @liamkilner


## Problem Description
Pretend you are the owner/operator of a tennis (or football, soccer - your choice) club needing to build a relational database. You hired some students from the MIST 4610 class at the University of Georgia to create the database for you. They need to know more about your organization to identify which entities, attributes, and relationships are important for you. Start by describing your business as a real client. At least 12-15 entities are needed including their respective attributes and relationships. 
## Data Model
Our model is based on a Soccer Club, called UGA United Soccer Club. Our “Teams” table serves as our central entity, branching to many other tables throughout the model. “Teams” includes many important attributes, such as team name, age group, and practice schedules. Our “Teams” table has a one-to-many relationship, as well as a one-to-one relationship with our “Coaches” table. There are many coaches per team, with one being the head coach, shown by the one-to-one relationship. Our “Coaches” table gives important information about each coach, such as name, contact information, and coaching experience. Additionally, “Teams” links, as a one-to-many relationship, to “Registration”. There are many registrations per team. There is also one player per registration. Our “Registrations” entity as a one-to-one relationship with “Players”. This table includes information such as name, age, contact information, and emergency contacts. “Teams” continues its relationships by having a one-to-many relationship with “Sponsors”. Each team can have multiple sponsors, each of different levels and payments. There is also a one-to-many relationship between “Teams” and “Tournaments”. Each tournament is linked to multiple teams. This table includes important information such as the name, location, and date of the tournaments, as well as the winning team. Our “Tournaments” entity branches to “Facilities”, with multiple facilities as a part of each tournament. Our facilities offer different field conditions, such as turf or grass, and multiple fields within the facility. The “Facilities” entity also links to our “Staff” entity through a one-to-many relationship. Each facility has multiple staff members, where we can find information about their contact information and position. The “Tournaments” entity also links to another entity, “Matches”, through a one-to-many relationship. There are multiple games in each tournament, and also multiple referees in each match. This is shown by the “Matches” and “Referees” entities being connected with a one-to-many relationship. Our “Teams” entity connects to one more entity, “Practice Sessions”, through a one-to-many relationship since there are multiple practice sessions for each team. Since many facilities can have many practice sessions, there is an associative entity between “Practice Sessions” and “Facilities” called “Practice_Sessions_has_Facilities”. This shows which practice sessions are occurring at each facility. Our conversation with our client included three more entities, “Parents/Guardians”, “Payments”, and “Merchandise”, but we felt that it made more sense to include these as attributes in the other existing entities.
<img width="406" alt="Screenshot 2023-11-02 at 4 00 04 PM" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/de548084-92eb-49e9-aa80-92b505770966">
<img width="651" alt="Screenshot 2023-11-02 at 3 57 51 PM" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/4f47cdcf-39a7-48ca-b8e4-fb7c3b1332b8">



## Project Description
The current project is to create a relational database that models the general operations of a soccer club. The primary entity of the model is the Teams entity with the Teams representing each individual team that belongs to the UGA United Soccer Club. The Team entity has various relationships with other entities in the model such as Players, Coaches, Tournaments, etc. We are interested in accurately depicting these relationships and generating sample data to ensure that the goals of the database are achieved. Additionally, we plan to execute queries on the sample data to provide information that is relevant to the club from a managerial perspective.

##  Data Dictionary

## Queries
1. Retrieve all players who have not suffered any injuries:
This query lists the first name, last name, and team name of all the players who have not suffered any injuries.

Execute:
> SELECT f_name, l_name, teamName 
FROM Players, Teams, Registrations 
WHERE Players.playerID = Registrations.Players_playerID 
AND Teams.teamID = Registrations.Teams_teamID 
AND Players_playerID NOT IN (select Players_playerID from Injuries);

+ ----------- + ----------- + ------------- +
| f_name      | l_name      | teamName      |
+ ----------- + ----------- + ------------- +
| Hayden      | Soley       | Eagles        |
| Molli       | Kinane      | Eagles        |
| Melodie     | Kinig       | Eagles        |
| Linus       | Kobes       | Eagles        |
| Mimi        | Reading     | Eagles        |
| Kalil       | Pettigree   | Eagles        |
| Winifield   | De Ferraris | Eagles        |
| Constantia  | Weinham     | Eagles        |
| Zeb         | Benedit     | Eagles        |
| Ignacius    | Danick      | Eagles        |
| Calv        | O'Reagan    | Bulldogs      |
| Nels        | Lindstrom   | Bulldogs      |
| Cad         | Scurr       | Bulldogs      |
| Jozef       | Small       | Bulldogs      |
| Otha        | Brundell    | Bulldogs      |
| Irwinn      | Kubyszek    | Bulldogs      |
| Zarla       | Giercke     | Bulldogs      |
| Charlot     | Mixon       | Bulldogs      |
| Cyril       | Eccleston   | Bulldogs      |
| Rubin       | Faunt       | Bulldogs      |
| Byran       | Huson       | Lions         |
| Cherilyn    | Moultrie    | Lions         |
| Cos         | Riddell     | Lions         |
| Danit       | Penkman     | Lions         |
| Galina      | Moors       | Lions         |
| Dee dee     | Caffery     | Lions         |
| Kerr        | Allchin     | Lions         |
| Shermy      | Pauley      | Lions         |
| Linzy       | McCloughlin | Lions         |
| Erminia     | Knowlson    | Lions         |
| Urbano      | Arkill      | Lions         |
| Ed          | Neward      | Lizards       |
| Georgine    | Moyes       | Lizards       |
| Reid        | Gravenor    | Lizards       |
| Berton      | Ballsdon    | Lizards       |
| Greggory    | Chalker     | Lizards       |
| Sheilah     | Pilbury     | Lizards       |
| Jeno        | Abeles      | Lizards       |
| Elset       | Ragles      | Lizards       |
| Wright      | Earl        | Lizards       |
| Darcy       | Coad        | Lizards       |
| Garvin      | Lodo        | Lizards       |
| Antons      | Kembrey     | Hawks         |
| Terrill     | Vines       | Hawks         |
| Mair        | Abramson    | Hawks         |
| Hashim      | Conboy      | Hawks         |
| Gunilla     | Norcock     | Hawks         |
| Berty       | Louca       | Hawks         |
| Nolana      | Reightley   | Hawks         |
| Jennette    | Wraighte    | Hawks         |
| Hilarius    | Risby       | Hawks         |
| Ronna       | Lepper      | Hawks         |
| Jourdain    | Dowthwaite  | Hawks         |
| Carl        | Francke     | Leopards      |
| Sonja       | Simmans     | Leopards      |
| Kendall     | Ringham     | Leopards      |
| Willy       | Borkin      | Leopards      |
| D'arcy      | Mc Corley   | Leopards      |
| Mendie      | Drysdell    | Leopards      |
| Dolf        | Peschet     | Leopards      |
| Ailina      | Petrol      | Leopards      |
| Valentijn   | Gotfrey     | Leopards      |
| Shea        | Brotheridge | Leopards      |
| Debor       | Geach       | Leopards      |
| Annette     | Matterson   | Tigers        |
| Nicholle    | Ganiclef    | Tigers        |
| Goober      | Spenton     | Tigers        |
| Katrina     | Attwill     | Tigers        |
| Gustavo     | Joules      | Tigers        |
| Frederic    | Doggart     | Tigers        |
| Shanta      | Joly        | Tigers        |
| Burton      | Wickersley  | Tigers        |
| Helaina     | Royal       | Tigers        |
| Ira         | Janks       | Tigers        |
| Selig       | Crips       | Dolphins      |
| Shelby      | Guy         | Dolphins      |
| Lesley      | Osman       | Dolphins      |
| Garik       | Larham      | Dolphins      |
| Loutitia    | Benz        | Dolphins      |
| Torr        | Khristoforov | Dolphins      |
| Joann       | Dionsetti   | Dolphins      |
| Kalle       | Buie        | Dolphins      |
| Ichabod     | Attenbrow   | Dolphins      |
| Tiffi       | Buzek       | Dolphins      |
| Dina        | Hopfer      | Dolphins      |
| Donnie      | Ramirez     | Bears         |
| Ware        | Grunwall    | Bears         |
| Uriah       | Stearnes    | Bears         |
| Dehlia      | Martschik   | Bears         |
| Tobin       | Labeuil     | Bears         |
| Norene      | Muldowney   | Bears         |
| Juliane     | Pablo       | Bears         |
| Modesta     | Conyard     | Bears         |
| Egon        | Pepperrall  | Bears         |
| Louella     | Gaskal      | Bears         |
| Gregor      | Forder      | Bears         |
| Eliot       | Pastor      | Rhinos        |
| Kris        | Prium       | Rhinos        |
| Frasier     | Markwell    | Rhinos        |
| Dede        | Stair       | Rhinos        |
| Florette    | Abramamov   | Rhinos        |
| Frederico   | Juliff      | Rhinos        |
| Geri        | Spreadbury  | Rhinos        |
| Mikkel      | Corwin      | Rhinos        |
| Rosmunda    | Iorillo     | Rhinos        |
| Russell     | Greengrass  | Rhinos        |
| Reba        | Jebb        | Rhinos        |
| Aubert      | Ronca       | Sharks        |
| Janka       | Lillywhite  | Sharks        |
| Marie       | Bozward     | Sharks        |
| Taddeo      | Pasby       | Sharks        |
| Moses       | Ingall      | Sharks        |
| Joeann      | Condliffe   | Sharks        |
| Albina      | Kyrkeman    | Sharks        |
| Cybil       | McNeill     | Sharks        |
| Annalee     | Clibbery    | Sharks        |
| Rona        | Goldstone   | Sharks        |
| Beale       | Moye        | Sharks        |
| Theodosia   | Ferriman    | Cobras        |
| Meggie      | Calloway    | Cobras        |
| Lissi       | Dowdell     | Cobras        |
| Sarine      | Baldcock    | Cobras        |
| Melanie     | Rebbeck     | Cobras        |
| Jan         | Happert     | Cobras        |
| Julina      | Ferguson    | Cobras        |
| Arleen      | Hodgen      | Cobras        |
| Betsey      | Brassill    | Cobras        |
| Chanda      | Dyers       | Cobras        |
| Alasteir    | Janman      | Cobras        |
| Alejandra   | Seth        | Jaguars       |
| Desmund     | Coie        | Jaguars       |
| Gilberto    | Overpool    | Jaguars       |
| Corby       | Scourge     | Jaguars       |
| Taffy       | Teresse     | Jaguars       |
| Somerset    | Fretter     | Jaguars       |
| Chilton     | Lauchlan    | Jaguars       |
| Delainey    | Matfin      | Jaguars       |
| Ambrose     | Murr        | Jaguars       |
| Bryant      | Every       | Jaguars       |
| Kasey       | Brass       | Ravens        |
| Zonda       | Ormerod     | Ravens        |
| Trenton     | Griss       | Ravens        |
| Willow      | Bartoszinski | Ravens        |
| Yurik       | Rickasse    | Ravens        |
| Hasty       | Weth        | Ravens        |
| Jabez       | Negro       | Ravens        |
| Averyl      | Volette     | Ravens        |
| Isadore     | Giffaut     | Ravens        |
| Tuck        | Staddon     | Ravens        |
| Tarrance    | Dellenbroker | Scorpions     |
| Ermin       | Novis       | Scorpions     |
| Borden      | Domenici    | Scorpions     |
| Anett       | Pobjay      | Scorpions     |
| Leonid      | Balf        | Scorpions     |
| Quincey     | Massen      | Scorpions     |
| Leila       | Bestiman    | Scorpions     |
| Silvano     | Roisen      | Scorpions     |
| Merrile     | Beslier     | Scorpions     |
| Candace     | Keatch      | Scorpions     |
| Wilburt     | Lemm        | Dragons       |
| Thadeus     | Carbett     | Dragons       |
| Avram       | Paulazzi    | Dragons       |
| Pierrette   | Kempshall   | Dragons       |
| Jemimah     | Roullier    | Dragons       |
| Alameda     | Seniour     | Dragons       |
| Adrianne    | Vink        | Dragons       |
| Minta       | Carbett     | Dragons       |
| Alonzo      | Kirkby      | Dragons       |
| Shelby      | Corro       | Dragons       |
| Yolane      | Lough       | Panthers      |
| Twyla       | Read        | Panthers      |
| Daniela     | Fogden      | Panthers      |
| Martino     | Fedynski    | Panthers      |
| Jennine     | Chester     | Panthers      |
| Kenn        | Bacher      | Panthers      |
| Deane       | Seldon      | Panthers      |
| Matty       | Summerell   | Panthers      |
| Georgia     | Stubbs      | Panthers      |
| Farica      | Lawlings    | Panthers      |
| Berny       | Payn        | Panthers      |
| Auberon     | Fayerman    | Cougars       |
| Herve       | Bampton     | Cougars       |
| Franciskus  | Keyzman     | Cougars       |
| Cordula     | Josuweit    | Cougars       |
| Delcine     | Glyn        | Cougars       |
| Arvy        | McCosh      | Cougars       |
| Bonni       | Romei       | Cougars       |
| Nicolis     | Leighton    | Cougars       |
| Grantham    | Dongall     | Cougars       |
| Bordy       | Langston    | Cougars       |
| Hasty       | Leguey      | Falcons       |
| Dov         | Topper      | Falcons       |
| Vincent     | Lared       | Falcons       |
| Shelby      | Georgescu   | Falcons       |
| Lori        | Pascall     | Falcons       |
| Salaidh     | Laurenson   | Falcons       |
| Sinclare    | Gilstoun    | Falcons       |
| Shanon      | McConnulty  | Falcons       |
| Dicky       | Voysey      | Falcons       |
| Culver      | Ruckhard    | Falcons       |
| Christen    | Gillespie   | Falcons       |
| Felita      | Godlee      | Cheetahs      |
| Paco        | Bulstrode   | Cheetahs      |
| Rabi        | Canto       | Cheetahs      |
| Mariele     | Pringell    | Cheetahs      |
| Alicia      | Balston     | Cheetahs      |
| Rafe        | Bulley      | Cheetahs      |
| Grata       | Fanti       | Cheetahs      |
| Ailene      | Freeth      | Cheetahs      |
| Joey        | Vergine     | Cheetahs      |
+ ----------- + ----------- + ------------- +
210 rows

      From a managerial perspective, this query would be important because knowing what players have not been injured in the past and whether or not they are currently injured or not would be significant in understanding the state of the team and help predict how they would fare in a tournament. For a team that has many injured players it would not be wise to send them to participate in a tournament because they wouldn’t be able to perform on a competitive level with many injured players. 

2. Retrieve the names of the teams and their respective head coaches that won a tournament:
This query lists out the head coaches for teams that won each tournament.
Execute:
> SELECT Distinct f_name, l_name, teamName 
FROM Teams, Coaches 
WHERE Teams.Coaches_coachID = Coaches.coachID 
AND teamName IN (SELECT winning_team FROM Tournaments);

+ ----------- + ----------- + ------------- +
| f_name      | l_name      | teamName      |
+ ----------- + ----------- + ------------- +
| Geno        | Diver       | Eagles        |
| Clementine  | Donoghue    | Bulldogs      |
| Lexie       | Chark       | Lions         |
| Christian   | Dilleston   | Lizards       |
+ ----------- + ----------- + ------------- +
4 rows


The manager would want to know who the head coach is for every team that won the different tournament. This would be important that the manager was aware of which coaches were in charge of the overall winners of the four tournaments. 

3.Write a query that lists the first name of the players on the Lions team.
This query lists the first name of every player on the Lions team.
Execute:
> SELECT f_name
FROM Teams, Players, Registrations
WHERE Teams.teamID = Registrations.Teams_teamID
AND Players.playerID = Registrations.Players_playerID
AND teamName REGEXP "Lions";

+ ----------- +
| f_name      |
+ ----------- +
| Byran       |
| Cherilyn    |
| Cos         |
| Danit       |
| Galina      |
| Dee dee     |
| Kerr        |
| Shermy      |
| Linzy       |
| Erminia     |
| Urbano      |
+ ----------- +
11 rows

This information would be important for a manager who is interested in the Lions team and wants to know who each player is in order to do research on the stats of each player.


4. Write a query to list the names of the teams that played in the S.M.A.S.H tournament and order them in alphabetical order. 
This query lists those teams that played in the S.M.A.S.H tournaments and then orders those teams alphabetically.

Execute:
> SELECT teamName
FROM Tournaments, Teams
WHERE Tournaments.tournamentID = Teams.Tournaments_tournamentID
AND Tournaments.name regexp "S.M.A.S.H"
ORDER BY teamName;

+ ------------- +
| teamName      |
+ ------------- +
| Bears         |
| Hawks         |
| Jaguars       |
| Lizards       |
| Panthers      |
+ ------------- +
5 rows

This query is important from a managerial perspective because the S.M.A.S.H. tournament was the last one of the season. It is important to see which teams practiced the longest before playing in any tournaments to compare performance evaluations.

5. Write a query that shows sponsors who have paid more than the average payment:
This query lists out the name and the payment of those sponsors whose payment amount is greater than the average payment amount made by all the sponsors.
Execute:
> SELECT name, payment
FROM Sponsors 
WHERE payment > (SELECT AVG(payment) FROM Sponsors);

+ --------- + ------------ +
| name      | payment      |
+ --------- + ------------ +
| Katz      | 59561.31     |
| Dablist   | 72601.60     |
| Oyoloo    | 94531.44     |
| Feedbug   | 55742.74     |
| Dynazzy   | 64070.49     |
| Blognation | 63267.26     |
| Livepath  | 85479.54     |
| Bubbletube | 91249.26     |
| Tazz      | 83443.84     |
| Centidel  | 68334.20     |
| Voonte    | 48882.63     |
| Yadel     | 89386.20     |
| Trudoo    | 90764.52     |
| Quamba    | 73282.87     |
| Meembee   | 95073.69     |
| Devpoint  | 59119.40     |
| Vitz      | 68263.37     |
| Linklinks | 50357.43     |
| InnoZ     | 86371.18     |
| Feednation | 71245.54     |
+ --------- + ------------ +
20 rows

A manager would want to know this information because it would show which sponsors are the most generous in comparison to the rest. The sponsors that donate the most money would be put on the jerseys of the players. 


6. List of referees for each match:
This query lists the first name and last name of the referees of each match played by the bulldogs. 
Execute:
> SELECT DISTINCT CONCAT(f_name, ' ', l_name) 
FROM Referees, Teams, Tournaments, Matches 
WHERE Teams.Tournaments_tournamentID = Tournaments.tournamentID 
AND Tournaments.tournamentID = Matches.Tournaments_tournamentID 
AND Matches.matchID = Referees.Matches_matchID 
AND opponent regexp 'bulldogs|Bulldogs';

+ -------------------------------- +
| concat(f_name, ' ', l_name)      |
+ -------------------------------- +
| Artemas Gouley                   |
| Raven Stowgill                   |
| Melinda Adamovitch               |
| Janenna Thurling                 |
| Jaquelin Bertomeu                |
| Elvira Pegrum                    |
| Lib Hissie                       |
| Klara Hundal                     |
| Tracey Jelks                     |
| Jaime Waadenburg                 |
+ -------------------------------- +
10 rows

A manager would want to know this information to determine if the bulldogs are cheating so they want to know the referees in order to contact them.

7. List the maintenance staff name from each facility whose field condition is turf:
This query lists all the staff that are maintenance workers at facilities with field conditions that are turf.
Execute:
> SELECT Staff.f_name, Staff.l_name, Facilities.name 
FROM Staff, Facilities
WHERE Facilities.facilityID = Staff.Facilities_facilityID
AND position = "maintenance"
AND field_condition REGEXP "turf|Turf";

+ ----------- + ----------- + --------- +
| f_name      | l_name      | name      |
+ ----------- + ----------- + --------- +
| Lucia       | Ismirnioglou | Oloo      |
| Shayne      | Yven        | Bubblebox |
+ ----------- + ----------- + --------- +
2 rows
This query would be significant to a manager who would want to understand how many maintenance workers are at a particular facility that has turf.


8. List the team names and the average number of coaching years between those team’s coaches whose average is over 15 years of experience
This query shows the average number of years of experience coaches have for each team where the number of years of experience is greater than 15
Execute:
> SELECT teamName, AVG(coaching_experience)
FROM Teams, Coaches
WHERE Teams.teamID = Coaches.Teams_teamID
GROUP BY teamName
HAVING AVG(coaching_experience) > 15 
ORDER BY AVG(coaching_experience) DESC;

+ ------------- + ----------------------------- +
| teamName      | AVG(coaching_experience)      |
+ ------------- + ----------------------------- +
| Hawks         | 23.5                          |
| Cougars       | 22.5                          |
| Lizards       | 21.5                          |
| Cobras        | 18.5                          |
| Leopards      | 17                            |
| Rhinos        | 16.5                          |
| Jaguars       | 16.5                          |
| Lions         | 15.5                          |
| Dragons       | 15.5                          |
| Panthers      | 15.5                          |
+ ------------- + ----------------------------- +
10 rows

The manager would want to know this information to understand the individual experience of each coach and which teams have coaches with the most experience. This would allow the manager to assign head coaches to competition levels that are appropriate for their experience level. Coaches with more coaching experience should be assigned to higher competition levels, and the opposite could be said for coaches with less experience. 

9. List the first and last name of each coach that does not have a coaching certificate & their respective team. 
This query shows the first and last name of each individual coach that has no coaching  certification along with the team that they coach for.


Execute:
> SELECT CONCAT(l_name,", ",f_name), teamName
FROM Coaches, Teams
WHERE Coaches.Teams_teamID = Teams.teamID 
AND coaching_certification REGEXP 'no';

+ ------------------------------- + ------------- +
| CONCAT(l_name,", ",f_name)      | teamName      |
+ ------------------------------- + ------------- +
| Wadlow, Lenka                   | Eagles        |
| Randalston, Modestine           | Lizards       |
| Rosoni, Kellsie                 | Bears         |
| Gatling, Rubia                  | Scorpions     |
| Norcutt, Frederico              | Panthers      |
| St. Louis, Rica                 | Falcons       |
+ ------------------------------- + ------------- +
6 rows
The owner of the Bulldog United soccer club would want to know this information to track each coach’s progress towards obtaining their coaching certification. This would be relevant when coaches are up for evaluation and would help in determining what coaches would be qualified to become a head coach of a team for the upcoming season. 

10. List the tournament name that had a payment average from its teams that was greater than the overall average sponsor payment.
This query shows the name of the tournament that had an average amount of payments that was higher than the average total amount of payments from all sponsors.

Execute:
>SELECT Distinct Tournaments.name, avg(payment) 
FROM Tournaments, Teams, Sponsors 
WHERE Tournaments.tournamentID = Teams.Tournaments_tournamentID 
AND Teams.teamID = Sponsors.Teams_teamID 
GROUP BY Tournaments.name 
HAVING AVG(payment) > (SELECT AVG(payment) FROM Sponsors);

+ --------- + ----------------- +
| name      | AVG(payment)      |
+ --------- + ----------------- +
| Air Force | 53933.413000      |
+ --------- + ----------------- +
1 rows

A manager would be interested in this information to determine which tournament had the highest amount of money from its sponsors. It would help them see which tournament was the biggest, most profitable event to these sponsors. This particular tournament had a group of teams that brought money in from some of the highest paying sponsors.

## Database Information
The name of the database is : cs_g10p1

Additional information: Each query created is marked in the database using stored procedures. The stored procedures can be called using the following format : CALL Q1();
