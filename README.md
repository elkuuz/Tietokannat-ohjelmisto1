05. Join
  1. select country.name as "country name", airport.name as "airport name"
      from country inner join airport on airport.iso_country = country.iso_country
      where country.name = "Finland" and scheduled_service = "yes";
      ![image](https://github.com/user-attachments/assets/3c1c1bbf-8080-4044-81aa-e472081d160f)

  2. ![image](https://github.com/user-attachments/assets/717ec3b4-bc00-41a0-bd28-51a22901c787)
      select screen_name, airport.name
      from game inner join airport on location = ident;
      
  3. ![image](https://github.com/user-attachments/assets/7973c949-8327-4ce4-a591-ca027cc63b53)
     select screen_name, country.name from game inner join airport on location=ident inner join country on  airport.iso_country=country.iso_country;
     
  4. ![image](https://github.com/user-attachments/assets/b7553ca3-83f3-4ac0-8198-af81ec281297)
     select airport.name as "name", screen_name
    -> from airport left join game on ident=location where name like "%Hels%";
     
  5. ![image](https://github.com/user-attachments/assets/84c4f606-5a7f-4ff5-9703-81dc90050617)
     select name, screen_name
     from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;





06 sisäkyselyt.
   1. ![image](https://github.com/user-attachments/assets/7bc80909-2508-4990-bd6b-ed5b85ba0502)
      select name from country where iso_country in(
    -> select iso_country from airport where name like "Satsuma%");
    
   2.  ![image](https://github.com/user-attachments/assets/d24f762e-1d36-41d9-8092-6c11842e4604)
        select name from airport where iso_country in(
    -> select iso_country from country where name="Monaco");

   3. ![image](https://github.com/user-attachments/assets/5a603139-2450-4ea9-8137-c8baed4de767)'
      select screen_name
      from game
      where id in (
      select game_id
      from goal_reached
      where goal_id in(
      select id
      from goal
      where name = "CLOUDS"
      )
      );
      
   4. ![image](https://github.com/user-attachments/assets/e8cc0578-caf5-4ec4-88a6-b040d02afaf6)
       select name from country where iso_country not in(
    -> select iso_country from airport);

   5. ![image](https://github.com/user-attachments/assets/7630864e-9ca7-4765-b9ee-d507d92df20d)
      select name
      from goal
      where id not in(
      select goal.id
      from goal, goal_reached, game
      where game.id = game_id and goal.id = goal_id and screen_name = "Heini"
      );







