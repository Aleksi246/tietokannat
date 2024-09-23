tehtävä merkintä tyyliä 1234 missä 1 on moduuli 2 on moduulin tehtävä 3 ja 4 on tehtävän kysymyksen numero

kurssi yleisraportti: https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/kurssiazrviointi.PNG



2101
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2101.PNG

2102
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2102.PNG

2103
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2103.PNG

2104
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2104.PNG

2105
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2105.PNG

2106
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2106.PNG

2107
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2107.PNG

2108
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2108.PNG

2109
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2109.PNG



2201
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2201.PNG

select country.name as "country name", airport.name as "airport name"
from country, airport
where country.iso_country = airport.iso_country and country.name = "Iceland";

2202
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2202.PNG

select airport.name as "airport name"
from airport, country
where airport.type = "large_airport" and country.name = "France" and 
country.iso_country = airport.iso_country;

2203
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2203.PNG

select  country.name as "country_name",airport.name as "airport_name"
from airport, country
where country.iso_country = airport.iso_country and country.continent = "AN";

2204
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2204.PNG

select elevation_ft
from airport, game
where screen_name = "Heini" and game.location = airport.ident;

2205
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2205.PNG

select elevation_ft*0.3048 as "elevation_m"
from airport, game
where screen_name = "Heini" and game.location = airport.ident;

2206
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2206.PNG

select airport.name
from airport, game
where screen_name = "Ilkka" and game.location = airport.ident;

2207
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2207.PNG

select country.name
from airport, game,country
where screen_name = "Ilkka" and game.location = airport.ident and airport.iso_country = country.iso_country;

2208
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2208.PNG

select goal.name
from goal, goal_reached, game
where goal.id = goal_reached.goal_id and goal_reached.game_id = game.id and game.screen_name = "Heini";

2209
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2209.PNG

select airport.name
from airport, game, goal_reached,goal
where airport.ident = game.location and game.id = goal_reached.game_id and goal_reached.goal_id = goal.id 
and goal.description = "Cloudy" and screen_name = "Ilkka";

2210
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/2210.PNG

select country.name
from airport, game, goal_reached,goal, country
where airport.iso_country = country.iso_country and airport.ident = game.location and game.id = goal_reached.game_id and goal_reached.goal_id = goal.id 
and goal.description = "Cloudy" and screen_name = "Ilkka";



3101
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3101.PNG

select country.name as "country name", airport.name as "airport name"
from country
inner join airport on country.iso_country = airport.iso_country
where scheduled_service = "yes" and country.name = "Finland";

3102
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3102.PNG

select screen_name, airport.name
from game
inner join airport on airport.ident = game. location;

3103
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3103.PNG

select screen_name, country.name
from game
inner join airport on airport.ident = game. location
inner join country on airport.iso_country = country.iso_country;

3104
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3104.PNG

select airport.name, screen_name
from airport
left join game on airport.ident = game.location
where airport.name like "%Hels%";

3105
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3105.PNG

select goal.name, screen_name
from goal
left join goal_reached on goal.id = goal_reached.goal_id
left join game on goal_reached.game_id = game.id;



3201
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3201.PNG

select country.name
from country
where iso_country in (
select airport.iso_country
from airport
where airport.name like "Satsuma%"
);

3202
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3202.PNG

select airport.name
from airport
where airport.iso_country in(
select country.iso_country
from country
where country.name = "Monaco"
);

3203
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3203.PNG

select screen_name
from game
where game.id in(
select game_id
from goal_reached
where goal_id in(
select id
from goal
where description ="Cloudy"
)
);

3204
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3204.PNG

select country.name
from country
where country.iso_country not in (
select airport.iso_country
from airport);

3205
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/3205.PNG


select goal.name
from goal
where goal.id not in(
select goal_id
from goal_reached
where goal_reached.game_id in (
select game.id
from game
where screen_name = "Heini"
)
);



4101
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4101.PNG

select max(elevation_ft)
from airport
;

4102
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4102.PNG

select continent,count(*)
from country
group by continent;

4103
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4103.PNG

select screen_name, count(*)
from game, goal_reached
where goal_reached.game_id = game.id
group by game_id
order by count(*) desc, screen_name;

4104
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4104.PNG

select screen_name
from game
where id in(
select min(id) 
from game);

4105
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4105.PNG

select country.name, count(*)
from country, airport 
where airport.iso_country = country.iso_country 
group by airport.iso_country 
order by count(*) desc limit 50;

4106
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4106.PNG

select country.name
from country, airport 
where airport.iso_country = country.iso_country
group by airport.iso_country 
having count(airport.iso_country) > 1000;

4107
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4107.PNG

select airport.name from airport 
order by elevation_ft desc limit 1;

4108
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4108.PNG

select country.name from country, airport
where airport.iso_country = country.iso_country
order by elevation_ft desc limit 1;

4109
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4109.PNG

select count(*) from game, goal_reached
where goal_reached.game_id = game.id and screen_name = "Vesa";

4110
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4110.PNG

select airport.name from airport 
order by latitude_deg limit 1;



4201
https://github.com/Aleksi246/tietokannat/blob/kuvankaapaukset/4201.PNG

update game
set co2_consumed = (select co2_consumed from game where screen_name = "Vesa") + 500,
location = (select ident from airport where name = "Nottingham Airport")
where screen_name = "Vesa";




