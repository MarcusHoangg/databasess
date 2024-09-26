Qes.1 select country.name as "country name ", airport.name as "airport name" from country inner join airport on country.iso_country = airport.iso_country where country.name = "Finland";
![image](https://github.com/user-attachments/assets/d1be9f61-6bf0-46d0-8dc1-c16123363cf4)
Qes.2 select screen_name, name from game inner join airport on game.location = airport.ident;
![image](https://github.com/user-attachments/assets/8476d7d9-d9b3-4fbd-8531-948f14f446cd)
Qes.3 select game.screen_name, country.name from game inner join airport on game.location = airport.ident inner join country on airport.iso_country = country.iso_country;
![image](https://github.com/user-attachments/assets/1737da8a-f125-46a9-b56c-857cab8c0db7)
Qes.4 select name, screen_name from airport left join game on game.location = airport.ident where name like "%Hels%" order by screen_name desc;
![image](https://github.com/user-attachments/assets/3dbb0f67-2e37-4f62-b83a-61ca69348b26)
Ques.5 select name, screen_name from goal left join goal_reached on goal.id = goal_id left join game on game.id = game_id;
![image](https://github.com/user-attachments/assets/0f1dab90-a88b-40bb-87d6-ab5e92a2eb08)

#ex5
Qes.1 select name from country where iso_country in (select iso_country from airport where name like "Satsuma%");
![image](https://github.com/user-attachments/assets/95ad233e-65da-4274-9510-070dedd3d6af)
Qes.2 select name from airport where iso_country in ( select iso_country from country where name = "Monaco");
![image](https://github.com/user-attachments/assets/ee7320cc-65fb-4061-9f64-c603f5c8bf43)
Qes.3 select screen_name from game where id in (select game_id from goal_reached where goal_id in (select id from goal where name = "clouds"));
![image](https://github.com/user-attachments/assets/57140944-d6b1-48f1-a12a-615e608554d2)
Qes.4 select name from country where iso_country not in ( select iso_country from airport);
![image](https://github.com/user-attachments/assets/a6624012-4d35-4989-9b99-9d09eba662d1)
Qes.5 select name from goal where id not in (select goal_id from goal_reached where game_id not in (select id from game where name = "Heini"));
![image](https://github.com/user-attachments/assets/7bbaf857-6b1c-4fc8-99fd-63cd0d06dcdb)


