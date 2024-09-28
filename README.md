# Tietokanta

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
select country.name as "country name", airport.name as "airport name" <br>
from country, airport <br>
where country.name = "Iceland" <br>
and airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/92664947-9985-4e55-82d5-cc461b0a9e6e)

### 2
select airport.name as "airport name" <br>
from airport, country <br>
where country.name = "France" <br>
and airport.iso_country = country.iso_country <br>
and airport.type = "large_airport";

![image](https://github.com/user-attachments/assets/68f856de-2bd6-49b9-a3aa-18a2089ea303)

### 3
select country.name as country_name, airport.name as airport_name <br>
from country, airport <br>
where country.continent = "AN" <br>
and airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/c62ac0cb-1e96-4695-a6c6-dd5f46146c87)

### 4
select airport.elevation_ft <br>
from airport, game <br>
where game.screen_name = "Heini" <br>
and airport.ident = game.location;

![image](https://github.com/user-attachments/assets/5f9f1696-0d8a-4555-b743-176ded6d0660)

### 5
select airport.elevation_ft * 0.3048 as elevation_m <br>
from airport, game <br>
where game.screen_name = "Heini" <br>
and airport.ident = game.location;

![image](https://github.com/user-attachments/assets/7b19a3e0-1203-4522-a8f5-45db43095041)

### 6
select airport.name <br>
from airport, game <br>
where game.screen_name = "Ilkka" <br>
and game.location = airport.ident;

![image](https://github.com/user-attachments/assets/9c0e73d8-a532-4122-86ae-772cf8cdd48d)

### 7
select country.name <br>
from airport, game, country <br>
where game.screen_name = "Ilkka" <br>
and game.location = airport.ident <br>
and airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/bf7595f8-8df5-4484-88ed-fdcbfde2431b)

### 8
select goal.name <br>
from goal, goal_reached, game <br>
where game.screen_name = "Heini" <br>
and game.id = goal_reached.game_id <br>
and goal_reached.goal_id = goal.id;

![image](https://github.com/user-attachments/assets/7662f587-0bf2-45f3-88be-ad195391b958)

### 9
select airport.name <br>
from airport, game, goal_reached, goal <br>
where game.location = airport.ident <br>
and goal_reached.game_id = game.id <br>
and goal_reached.goal_id = goal.id <br>
and game.screen_name = "Ilkka" <br>
and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/c675aed9-a8c7-4279-ac2b-9c6753403c16)

### 10
select country.name <br>
from airport, game, goal_reached, goal, country <br>
where game.location = airport.ident <br>
and goal_reached.game_id = game.id <br>
and goal_reached.goal_id = goal.id <br>
and airport.iso_country = country.iso_country <br>
and game.screen_name = "Ilkka" <br>
and goal.name = "CLOUDS";

![image](https://github.com/user-attachments/assets/6b8cb32f-d5f9-40fc-974b-a7292924095e)

</details>
<details>
<summary>Tentti 3, Join harjoitukset</summary>

### 1
select country.name as "country name", airport.name as "airport name" <br>
from airport <br>
inner join country on country.iso_country = airport.iso_country <br>
where airport.scheduled_service = "yes" <br>
and country.name = "Finland";

![image](https://github.com/user-attachments/assets/e9505386-f7dd-4584-8c41-beed02909e82)

### 2
select game.screen_name, airport.name <br>
from airport <br>
inner join game on game.location = airport.ident; 

![image](https://github.com/user-attachments/assets/fa56350b-6b1d-4924-a85c-4f00b282a11f)

### 3
select game.screen_name, country.name <br>
from country <br>
inner join airport on airport.iso_country = country.iso_country <br>
inner join game on game.location = airport.ident;

![image](https://github.com/user-attachments/assets/5e2bc227-9479-487b-86b9-9df7ceccd685)

### 4
select airport.name, game.screen_name <br>
from airport <br>
left join game on game.location = airport.ident <br>
where airport.name like "%Hels%"; 

![image](https://github.com/user-attachments/assets/8891665f-9eed-4813-bd75-7e5d98dc9874)

### 5
select goal.name, game.screen_name <br>
from goal <br>
left join goal_reached on goal_reached.goal_id = goal.id <br>
left join game on game.id = goal_reached.game_id;

![image](https://github.com/user-attachments/assets/b663a785-5945-4de5-bedb-b958096de7dd)

</details>

<details>
<summary>Tentti 4, Sisäkysely harjoitukset</summary>

### 1
select name 
from country <br>
where iso_country in( <br>
	select iso_country <br>
	from airport <br>
	where name like "Satsuma%" <br>
	);

![image](https://github.com/user-attachments/assets/3dd2e7a6-7b36-4f77-8660-20432c1a5897)

### 2
select name <br>
from airport <br>
where iso_country in( <br>
	select iso_country <br>
	from country <br>
	where name = "Monaco" <br>
	);

![image](https://github.com/user-attachments/assets/d4bf2b84-6bda-4a83-9e32-37d51de39dc1)

### 3
select screen_name <br>
from game <br>
where id in( <br>
	select game_id <br>
	from goal_reached <br>
	where goal_id in( <br>
		select id <br>
		from goal <br>
		where name = "CLOUDS" <br>
		) <br>
	);

![image](https://github.com/user-attachments/assets/caee9529-c0e2-437a-a863-3faa9cf63908)

### 4
select name <br>
from country <br>
where iso_country not in( <br>
	select iso_country <br>
	from airport <br>
	where name like "%" <br>
	);

![image](https://github.com/user-attachments/assets/784fc59f-d267-4b7c-8ad4-0032c0eed8b3)

### 5
select name <br>
from goal <br>
where id not in( <br>
	select goal_id <br>
	from goal_reached <br>
	where game_id in ( <br>
		select id <br>
		from game <br>
		where screen_name = "Heini" <br>
		) <br>
	);

![image](https://github.com/user-attachments/assets/1474fba2-0ddc-4406-a189-ed1f748ce040)

</details>

<details>
<summary>Tentti 5, Koostetieto kyselyt harjoitukset</summary>

### 1
select max(elevation_ft)
from airport;

![image](https://github.com/user-attachments/assets/3aa705bc-e1ba-46a4-9f0e-7aebbce9def6)

### 2
select distinct continent, count(*)
from country
group by continent;

![image](https://github.com/user-attachments/assets/a1aab61b-38c2-4a6e-a187-e1c52fa9c98f)

### 3
select screen_name, count(*)
from game
inner join goal_reached on game_id = game.id
inner join goal on goal.id = goal_reached.goal_id
group by screen_name;

![image](https://github.com/user-attachments/assets/813bacc3-97bf-45d7-a969-dc40527e2c40)

### 4
select screen_name
from game
where co2_consumed in (
	select min(co2_consumed)
	from game
	);

![image](https://github.com/user-attachments/assets/1a1d29ac-601f-4f02-829d-ef1245257ca5)

### 5
select country.name, count(*)
from country
inner join airport on airport.iso_country = country.iso_country
group by country.name
order by count(airport.ident) desc, country.name asc
limit 50;

![image](https://github.com/user-attachments/assets/15d306bc-7218-4929-92cd-cf74d689d0a1)

### 6
select country.name
from country
inner join airport on airport.iso_country = country.iso_country
group by airport.iso_country
having count(*) > 1000;

![image](https://github.com/user-attachments/assets/08510bf6-3257-45af-8ba3-44c44946cf6e)

### 7 
select name 
from airport 
where elevation_ft = (
	select max(elevation_ft) 
	from airport);

![image](https://github.com/user-attachments/assets/5e9d804b-d657-4250-b90c-3d208bcedbb5)

### 8
select country.name 
from country
join airport on airport.iso_country = country.iso_country 
where elevation_ft = (
	select max(elevation_ft) 
	from airport);

![image](https://github.com/user-attachments/assets/3eb1976d-51ac-4661-a3eb-6955854ba61f)

### 9 
select count(*)
from goal
join goal_reached on goal_reached.goal_id = goal.id
join game on game.id = goal_reached.game_id
where goal.target = "TEMP" 
and game.screen_name = (
	select screen_name
	from game
	where screen_name like "Vesa");

![image](https://github.com/user-attachments/assets/6f42106c-56df-46c2-94ca-cbf38533144a)

### 10
select name 
from airport 
where latitude_deg = (
	select min(latitude_deg) 
	from airport);

![image](https://github.com/user-attachments/assets/b714b1d8-d2a7-410a-86b3-8a256565643a)

</details>

<details>
<summary>Tentti 6, Päivityskyselyt harjoitukset</summary>

### 1 
update game
set location =(
	select ident
	from airport 
	where name like "Nottingham airport")
where screen_name = "Vesa";

update game
set co2_consumed = co2_consumed + 500
where screen_name = "Vesa";

![image](https://github.com/user-attachments/assets/d0f63d1c-ed11-46ca-aff0-3d70074d55e1)

### 2

![image](https://github.com/user-attachments/assets/dcce7f32-b7d0-4415-bc62-84dbeaeb7eaa)

### 3 
delete from goal_reached

![image](https://github.com/user-attachments/assets/0704c01a-c266-4030-ab16-312cb702b8ed)

### 4
delete from game

![image](https://github.com/user-attachments/assets/968c2942-ec50-4165-9932-21593c54b9ab)

</details>

# Lopputulos 

![image](https://github.com/user-attachments/assets/ec0a6789-e768-49ff-ae51-e094b0eb8e25)

![image](https://github.com/user-attachments/assets/7eb99ee4-2e69-45a7-8ae4-1fa6e2355c22)

![image](https://github.com/user-attachments/assets/26e0c5af-2792-4ffa-adb0-b8b6cab253ad)

