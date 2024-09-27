Qes.1 select max(elevation_ft) from airport;
![image](https://github.com/user-attachments/assets/ea15b7b3-0677-42ca-9f4a-e1d3e2cb5b69)
Qes.2 select continent, count(*) from country group by continent;
![image](https://github.com/user-attachments/assets/bf363a84-83ba-4520-a664-2db5f34a0686)
Qes.3 select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;
![image](https://github.com/user-attachments/assets/df913deb-cdc0-4460-8c81-3764ed168efd)
Qes.4 select screen_name from game where co2_consumed in (select min(co2_consumed) from game);
![image](https://github.com/user-attachments/assets/1ad14e93-8c23-4504-bff6-81b9e1a5ad19)
Qes.5 select country.name, count(*) from country inner join airport on airport.iso_country = country.iso_country group by country.name order by count(airport.id) desc limit 50;
![image](https://github.com/user-attachments/assets/27e7bc1c-af16-4a2a-9ea6-c347e1013a7f)
Qes.6 select country.name from country inner join airport on airport.iso_country = country.iso_country group by country.name having count(airport.id) > 1000;
![image](https://github.com/user-attachments/assets/45a07d35-aa1f-4213-ae78-da16f56509f3)
Qes.7 select name from airport where elevation_ft in (select max(elevation_ft) from airport);
![image](https://github.com/user-attachments/assets/94ed596f-bee9-49a7-a6ec-3a36103de698)
Qes.8 select country.name from country inner join airport on airport.iso_country = country.iso_country where elevation_ft in (select max(elevation_ft) from airport);
![image](https://github.com/user-attachments/assets/a320e4bf-7726-4a86-b3c3-52d16030f635)
Qes.9 select count(*) from goal_reached, game where id = game_id and screen_name = "Vesa";
![image](https://github.com/user-attachments/assets/7b01dbdb-57b6-4462-8b9b-b10ebee91507)
Qes.10 select name from airport where latitude_deg in (select min(latitude_deg) from airport);
![image](https://github.com/user-attachments/assets/87e11df4-df90-4697-b3cd-e113047dcf08)

#ex7
Qes.1 update game set co2_consumed = co2_consumed + 500, location = (select ident from airport where name = "Nottingham Airport") where screen_name = "Vesa";
![image](https://github.com/user-attachments/assets/eec06124-1731-4127-8ee3-e2f2dd93935e)
Qes.3 delete from goal_reached; select * from goal_reached;
![image](https://github.com/user-attachments/assets/670c14a5-749c-45fd-95e5-e4da71aaec84)
Qes.4 delete from game; select * from game;
![image](https://github.com/user-attachments/assets/7a4728a0-6cf6-4cf7-b5fe-4da8925c417b)
