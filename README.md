# Tietokanta
suc nut
![alt](https://github.com/AverageKasper/Tietokanta/blob/main/Pirat_Nation-1831723969499787363-01.jpg)
![Picture1](https://github.com/user-attachments/assets/6b3345d9-53be-43c1-b0b0-a4c30bebb0c6)

<details>
<summary> Tentti 1, Yhteen tauluun kohdistuvien kyselyiden harjoitukset</summary>
  
### 1
select * from goal;
  
![Screenshot 2024-09-16 130633](https://github.com/user-attachments/assets/b419320c-bfad-41d6-af84-42ee717390b8)

### 2
select name, type <br>
from airport <br>
where iso_country = "FI";

![Screenshot 2024-09-16 115340](https://github.com/user-attachments/assets/9175f0be-4fc4-4d2a-904e-28e4c46ab607)

### 3
select name <br>
from airport <br>
where iso_country <br>
like '%FI%' order by name asc;

![image](https://github.com/user-attachments/assets/a83ddf3b-08e0-4f47-aec5-c11c1c307016)

### 4
select name,type <br>
from airport <br>
where iso_country = 'FI' <br>
order by type , name;

![image](https://github.com/user-attachments/assets/7a345703-b68c-4219-8f27-36379e05a737)

### 5
select name <br>
from country <br>
where name like "F%";

![image](https://github.com/user-attachments/assets/4b3f1a3d-30cc-4c28-beee-6cda8cb9653c)

### 6
select name <br>
from country <br>
where name like "%f%";

![image](https://github.com/user-attachments/assets/df8ad6f4-5cc8-4324-bc7c-399b798eac9e)

### 7
select location <br>
from game <br>
where screen_name like "Vesa";

![image](https://github.com/user-attachments/assets/885e3049-3da6-47b3-ac1a-e2e3e5640994)

### 8
select co2_consumed <br>
from game <br>
where screen_name like "Ilkka";

![image](https://github.com/user-attachments/assets/b4e41208-040f-4a1f-9a12-404c1cbf6abf)

### 9
select distinct co2_budget <br>
from game;

![image](https://github.com/user-attachments/assets/9cebbcc3-09b1-439e-bb8c-42aa0c496a8a)

</details>

<details>
<summary> Tentti 2, Where-osan liitosehto harjoitukset</summary>

### 1
select country.name as "country name", airport.name as "airport name" 
from country, airport 
where country.name = "Iceland"
and airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/92664947-9985-4e55-82d5-cc461b0a9e6e)

### 2
select airport.name as "airport name" 
from airport, country
where country.name = "France"
and airport.iso_country = country.iso_country
and airport.type = "large_airport";

![image](https://github.com/user-attachments/assets/68f856de-2bd6-49b9-a3aa-18a2089ea303)

### 3
select country.name as country_name, airport.name as airport_name
from country, airport
where country.continent = "AN"
and airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/c62ac0cb-1e96-4695-a6c6-dd5f46146c87)

### 4
select airport.elevation_ft 
from airport, game
where game.screen_name = "Heini"
and airport.ident = game.location;

![image](https://github.com/user-attachments/assets/5f9f1696-0d8a-4555-b743-176ded6d0660)

### 5
select airport.elevation_ft * 0.3048 as elevation_m 
from airport, game
where game.screen_name = "Heini"
and airport.ident = game.location;

![image](https://github.com/user-attachments/assets/7b19a3e0-1203-4522-a8f5-45db43095041)

### 6
select airport.name 
from airport, game
where game.screen_name = "Ilkka"
and game.location = airport.ident;

![image](https://github.com/user-attachments/assets/9c0e73d8-a532-4122-86ae-772cf8cdd48d)

### 7
select country.name
from airport, game, country
where game.screen_name = "Ilkka"
and game.location = airport.ident
and airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/bf7595f8-8df5-4484-88ed-fdcbfde2431b)

### 8
select goal.name 
from goal, goal_reached, game
where game.screen_name = "Heini"
and game.id = goal_reached.game_id
and goal_reached.goal_id = goal.id;

![image](https://github.com/user-attachments/assets/7662f587-0bf2-45f3-88be-ad195391b958)

### 9
select airport.name 
from airport, game, goal_reached, goal
where game.location = airport.ident
and goal_reached.game_id = game.id
and goal_reached.goal_id = goal.id
and game.screen_name = "Ilkka"
and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/c675aed9-a8c7-4279-ac2b-9c6753403c16)

### 10
select country.name 
from airport, game, goal_reached, goal, country
where game.location = airport.ident
and goal_reached.game_id = game.id
and goal_reached.goal_id = goal.id
and airport.iso_country = country.iso_country
and game.screen_name = "Ilkka"
and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/6b8cb32f-d5f9-40fc-974b-a7292924095e)

</details>
