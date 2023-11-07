
# MIST 4610 Project 1 Group 10
## Team Name
Group 10
## Team Members
1. Victoria Wiest https://github.com/victoriawiest/MIST4610Project1
2. Liam Kilner https://github.com/liamkilner/Project-1-SQL
3. Ashley Potts https://github.com/ashley-potts/MIST-4610-Project1
4. Emma Surbrook https://github.com/emmasurbrook/MIST-Project
5. Hayden Soley https://github.com/HaydenSoley/MIST-4610-Project-1


## Problem Description
The current project is to create a relational database that models the general operations of a soccer club. The primary entity of the model is the Teams entity with the Teams representing each individual team that belongs to the UGA United Soccer Club. The Team entity has various relationships with other entities in the model such as Players, Coaches, Tournaments, etc. We are interested in accurately depicting these relationships and generating sample data to ensure that the goals of the database are achieved. Additionally we plan to execute queries on the sample data to provide information that is relevant to the club from a managerial perspective. Our client for this project was the chatbot known as ChatGPT. A link to the conversation is listed here :

https://chat.openai.com/share/9caffb44-f79b-49e1-b32b-cafb7354c765

## Data Model
Our model is based on a Soccer Club, called UGA United Soccer Club. Our “Teams” table serves as our central entity, branching to many other tables throughout the model. “Teams” includes many important attributes, such as team name, age group, and practice schedules. Our “Teams” table has a one-to-many relationship, as well as a one-to-one relationship with our “Coaches” table. There are many coaches per team, with one being the head coach, shown by the one-to-one relationship. Our “Coaches” table gives important information about each coach, such as name, contact information, and coaching experience. Additionally, “Teams” links, as a one-to-many relationship, to “Registration”. There are many registrations per team. There is also one player per registration. Our “Registrations” entity as a one-to-one relationship with “Players”. This table includes information such as name, age, contact information, and emergency contacts. “Teams” continues its relationships by having a one-to-many relationship with “Sponsors”. Each team can have multiple sponsors, each of different levels and payments. There is also a one-to-many relationship between “Teams” and “Tournaments”. Each tournament is linked to multiple teams. This table includes important information such as the name, location, and date of the tournaments, as well as the winning team. Our “Tournaments” entity branches to “Facilities”, with multiple facilities as a part of each tournament. Our facilities offer different field conditions, such as turf or grass, and multiple fields within the facility. The “Facilities” entity also links to our “Staff” entity through a one-to-many relationship. Each facility has multiple staff members, where we can find information about their contact information and position. The “Tournaments” entity also links to another entity, “Matches”, through a one-to-many relationship. There are multiple games in each tournament, and also multiple referees in each match. This is shown by the “Matches” and “Referees” entities being connected with a one-to-many relationship. Our “Teams” entity connects to one more entity, “Practice Sessions”, through a one-to-many relationship since there are multiple practice sessions for each team. Since many facilities can have many practice sessions, there is an associative entity between “Practice Sessions” and “Facilities” called “Practice_Sessions_has_Facilities”. This shows which practice sessions are occurring at each facility. Our conversation with our client included three more entities, “Parents/Guardians”, “Payments”, and “Merchandise”, but we felt that it made more sense to include these as attributes in the other existing entities.

![P1G10 Data Model](https://github.com/victoriawiest/MIST4610Project1/assets/148873180/1a078321-3813-4e7b-aed2-053ca7887cb5)


##  Data Dictionary
<img width="881" alt="Players" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/1bc98441-39f3-4c8d-9105-6e3e78183a0e">
<img width="899" alt="Coaches" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/ab607458-e337-4bd5-9811-72b26b66d466">
<img width="891" alt="Teams" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/71856c83-d4c9-4fe7-9693-8c54acf753c7">
<img width="887" alt="Matches" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/9bdffc22-41d7-4ce1-b4fa-459aba957a99">
<img width="898" alt="Tournaments" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/dc764d54-0c59-4a4f-bf0c-83fb985cd8c9">
<img width="882" alt="Facilities" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/6b3e7630-6dfd-4b85-8a1c-073ed1fadbfe">
<img width="889" alt="Practice Sessions" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/def831cc-3a01-411a-844d-60f5beed8ef3">
<img width="893" alt="Registrations" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/8963b4ab-9050-4afa-8c72-5d83b241cc09">
<img width="891" alt="Injuries" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/20b32615-5c5c-4d7d-ac37-eae3358ab2b6">
<img width="889" alt="Sponsors" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/f82d27a6-4902-427a-8da8-fd1361774119">
<img width="892" alt="Staff" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/777bf78c-2315-4c9c-adcd-a3267be6d91b">
<img width="902" alt="Referees" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/4f184bab-0140-45a8-81b5-2a095cfda24b">


## Queries

<img width="848" alt="Matrix" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/5a1b6e63-9e5c-4d26-9ea9-7e2428bd4557">

1. Retrieve all players who have not suffered any injuries:
This query lists the first name, last name, and team name of all the players who have not suffered any injuries.

<img width="1002" alt="q1" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/a7ce3b30-3bb9-4e91-8e76-b12fa4477dfa">

      From a managerial perspective, this query would be important because knowing what players have not been injured in the past and whether or not they are currently injured or not would be significant in understanding the state of the team and help predict how they would fare in a tournament. For a team that has many injured players it would not be wise to send them to participate in a tournament because they wouldn’t be able to perform on a competitive level with many injured players. 

2. Retrieve the names of the teams and their respective head coaches that won a tournament:
This query lists out the head coaches for teams that won each tournament.

<img width="935" alt="q2" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/c23af8bd-9e12-4fe0-8443-aec5fef4d8d7">

The manager would want to know who the head coach is for every team that won the different tournament. This would be important that the manager was aware of which coaches were in charge of the overall winners of the four tournaments. 

3.Write a query that lists the first name of the players on the Lions team.
This query lists the first name of every player on the Lions team.

<img width="1111" alt="q3" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/745f682c-bd74-430a-9079-d3270b889845">

This information would be important for a manager who is interested in the Lions team and wants to know who each player is in order to do research on the stats of each player.


4. Write a query to list the names of the teams that played in the S.M.A.S.H tournament and order them in alphabetical order. 
This query lists those teams that played in the S.M.A.S.H tournaments and then orders those teams alphabetically.

<img width="1082" alt="q4" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/9635c6a4-5aca-41fa-a7f2-a128137c81d0">

This query is important from a managerial perspective because the S.M.A.S.H. tournament was the last one of the season. It is important to see which teams practiced the longest before playing in any tournaments to compare performance evaluations.

5. Write a query that shows sponsors who have paid more than the average payment:
This query lists out the name and the payment of those sponsors whose payment amount is greater than the average payment amount made by all the sponsors.

<img width="1079" alt="q5" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/c8cc6f1e-1687-4a84-bf31-b850523f503b">

A manager would want to know this information because it would show which sponsors are the most generous in comparison to the rest. The sponsors that donate the most money would be put on the jerseys of the players. 


6. List of referees for each match:
This query lists the first name and last name of the referees of each match played by the bulldogs. 

<img width="1083" alt="q6" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/f2bc0959-c882-4ca5-869d-6f5d0bfed15a">

A manager would want to know this information to determine if the bulldogs are cheating so they want to know the referees in order to contact them.

7. List the maintenance staff name from each facility whose field condition is turf:
This query lists all the staff that are maintenance workers at facilities with field conditions that are turf.

<img width="1084" alt="q7" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/c44b185d-3473-4413-8651-28af75a694a3">

This query would be significant to a manager who would want to understand how many maintenance workers are at a particular facility that has turf.


8. List the team names and the average number of coaching years between those team’s coaches whose average is over 15 years of experience
This query shows the average number of years of experience coaches have for each team where the number of years of experience is greater than 15

<img width="1065" alt="q8" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/deec469f-ed41-42f9-9493-b131b010fcc9">

The manager would want to know this information to understand the individual experience of each coach and which teams have coaches with the most experience. This would allow the manager to assign head coaches to competition levels that are appropriate for their experience level. Coaches with more coaching experience should be assigned to higher competition levels, and the opposite could be said for coaches with less experience. 

9. List the first and last name of each coach that does not have a coaching certificate & their respective team. 
This query shows the first and last name of each individual coach that has no coaching  certification along with the team that they coach for.

<img width="1078" alt="q9" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/0f1cfd55-65c6-4499-b4c7-68c920a3ebdc">

The owner of the Bulldog United soccer club would want to know this information to track each coach’s progress towards obtaining their coaching certification. This would be relevant when coaches are up for evaluation and would help in determining what coaches would be qualified to become a head coach of a team for the upcoming season. 

10. List the tournament name that had a payment average from its teams that was greater than the overall average sponsor payment.
This query shows the name of the tournament that had an average amount of payments that was higher than the average total amount of payments from all sponsors.

<img width="1084" alt="q10" src="https://github.com/victoriawiest/MIST4610Project1/assets/148873180/f8f3625e-ee0b-49e2-b678-336bed9fa7fd">

A manager would be interested in this information to determine which tournament had the highest amount of money from its sponsors. It would help them see which tournament was the biggest, most profitable event to these sponsors. This particular tournament had a group of teams that brought money in from some of the highest paying sponsors.

## Database Information
The name of the database is : cs_g10p1

Additional information: Each query created is marked in the database using stored procedures. The stored procedures can be called using the following format : CALL Q1();
