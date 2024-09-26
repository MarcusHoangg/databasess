Qes.1 select * from goal ;
![image](https://github.com/user-attachments/assets/6ab0c985-895c-49d7-85c2-36903ecc02b4)
Qes.2 select name from airport where iso_country = "FI";
![image](https://github.com/user-attachments/assets/e59e7e57-cb1f-435e-8507-2d3b67781b56)
Qes.3 select name from airport where iso_country = "FI" order by name asc;
![image](https://github.com/user-attachments/assets/1eb19bc1-a322-462f-9add-82d824767a8a)
Qes.4 select name, type from airport where iso_country = "FI" order by type, name;
![image](https://github.com/user-attachments/assets/11bfa92c-8677-4c1a-8e59-11df8d1a3abd)
Qes.5 select name from country where name like "F%";
![image](https://github.com/user-attachments/assets/5ff2bc53-df98-4ff4-a2d5-7dcd89a70cfe)
Qes.6 select name from country where name like "%F%";
![image](https://github.com/user-attachments/assets/83f2f929-2063-4bbd-9de8-d3a97de04dd5)
Qes.7 select location from game where screen_name = "Vesa";
![image](https://github.com/user-attachments/assets/35dd5845-5455-4054-aa82-1cc4aaf8d5ad)
Qes.8 select co2_consumed from game where screen_name = "Ilkka";
![image](https://github.com/user-attachments/assets/18c768ab-b311-4aa1-be23-08bc790d7949)
Qes.9 select distinct co2_budget from game;
![image](https://github.com/user-attachments/assets/974786d0-2c19-4bf9-bc0a-015dae42fbd4)
Qes.10 set @co2_left := 0; select screen_name, co2_budget, co2_consumed, (co2_budget - co2_consumed) as co2_left from game where screen_name = "Ilkka";
![image](https://github.com/user-attachments/assets/874f074d-b361-4aae-ba5c-be8cd0a90a65)

#exercise 3
Qes.1 select country.name as "country name", airport.name as "airport name" -> from country, airport -> where airport.iso_country = country.iso_country and country.name = "Iceland";
![image](https://github.com/user-attachments/assets/b133c5bf-5310-40dc-ab73-547faa23a830)
Qes.2 select airport.name as "airport name" from airport -> join country on airport.iso_country = country.iso_country -> where country.name = "France" and airport.type = "large_airport";
![image](https://github.com/user-attachments/assets/7a96297a-f022-4c76-b21c-7431b9880673)
Qes.3 select country.name as "country_name", airport.name as "airport_name" from country, airport -> where airport.iso_country = country.iso_country and country.continent = "AN";
![image](https://github.com/user-attachments/assets/e2b8e538-daa7-4e75-b97f-ddb3707b8c4f)
Qes.4 select elevation_ft from airport -> join game on airport.ident = game.location -> where screen_name = "Heini";
![image](https://github.com/user-attachments/assets/8c59f33c-e628-4bc5-a5b1-5df53bcf03a5)
Qes.5 set @elevation_m = 0; select (elevation_ft * 0.3048) as elevation_m from airport -> join game on airport.ident = game.location -> where screen_name = "Heini";
![image](https://github.com/user-attachments/assets/6992e04b-6d0a-42f1-ba1a-bc1c24833d3c)
Qes.6 select name from airport -> join game on airport.ident = game.location -> where screen_name = "Ilkka";
![image](https://github.com/user-attachments/assets/1853370d-5bce-4688-8e33-77c2563bae64)
Qes.7 select country.name from country, airport, game -> where game.location = airport.ident and airport.iso_country = country.iso_country -> and game.screen_name = "Ilkka";
![image](https://github.com/user-attachments/assets/41e3f454-145b-4016-b3ed-be42f2d1c71d)
Qes.8 select goal.name from goal, goal_reached, game -> where goal.id = goal_id and game.id = game_id and screen_name = "Heini";
![image](https://github.com/user-attachments/assets/5313a623-1987-49fe-9709-490687c5534e)
Qes.9 select airport.name from airport, game, goal_reached, goal -> where airport.ident = game.location and game.id = game_id and goal.id = goal_id -> and game.screen_name = "Ilkka" and goal.name = "clouds";
![image](https://github.com/user-attachments/assets/a6ced4e4-a333-4a29-8e88-8a620f2a082d)
Qes.10 select country.name from country, airport, game, goal_reached, goal -> where game.location = airport.ident and game.id = game_id -> and goal.id = goal_id and airport.iso_country = country.iso_country -> and game.screen_name = "Ilkka" and goal.name = "clouds";
![image](https://github.com/user-attachments/assets/07efb39f-7d94-4a7c-86a6-3a6c0f83fa40)


