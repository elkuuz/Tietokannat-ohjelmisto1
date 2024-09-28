Koostetieto kyselyt
   1. ![image](https://github.com/user-attachments/assets/d5d85757-eae7-4a5a-989d-e700a1813c73)
      select max(elevation_ft)
      from airport;
      
   2.  ![image](https://github.com/user-attachments/assets/0cccb607-8c2c-49a4-99bc-1d7ab5b01d39)
       select continent, count(*)
       from country
       group by continent;
       
   3.  select screen_name, count(*) from game, goal_reached where id=game_id group by screen_name;
       ![image](https://github.com/user-attachments/assets/4242f6bd-f7f1-4617-9ef8-1673f1c8a888)
      
   4.  ![image](https://github.com/user-attachments/assets/feba5274-36c2-43a9-b7d4-d4eb1817c752)
       select screen_name
       from game
       where co2_consumed in(
       select min(co2_consumed)
       from game
        );
    5.  ![image](https://github.com/user-attachments/assets/1e314831-7a6a-4f34-b7ea-76ecabab88a6)
         select country.name, count(*) from airport, country
         where airport.iso_country=country.iso_country
         group by country.iso_country
         order by count(*)desc
         limit 50;

       6. ![image](https://github.com/user-attachments/assets/c3d35826-0b65-4a33-90b9-0d32e7ab8283)
          	
          select country.name
          from airport, country
          where airport.iso_country = country.iso_country
          group by country.iso_country
          having count(*) > 1000;

       7. ![image](https://github.com/user-attachments/assets/cf67051e-6b57-400d-9389-0ef9d544c27d)
          	
          select name
          from airport
          where elevation_ft in (
          select max(elevation_ft)
          from airport
          );

       8. ![image](https://github.com/user-attachments/assets/e31d7444-b6ab-45e9-bc8b-cf8bfb9432a5)
          	
         select name
         from country
        where iso_country in (
        select iso_country
          from airport
         where elevation_ft in(
         select max(elevation_ft)
            from airport
            )
            );
       9. select count(*)
          from game, goal_reached
          where id = game_id and screen_name = "Vesa"
          group by screen_name;
          ![image](https://github.com/user-attachments/assets/8392e368-dd9b-405c-ba36-b192916188c4)
       10. 	
       select name
       from airport
       where latitude_deg in(
       select min(latitude_deg)
       from airport
       );
       ![image](https://github.com/user-attachments/assets/109d6389-78cd-4d76-a83a-08dc89009c67)


Päivityskyselyt
      1. ![image](https://github.com/user-attachments/assets/b4ba020e-2b69-443c-b455-bdb5c0ca7a5a)
         update game
         set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
        where screen_name = "Vesa";
       2. goal_reached

      
   3. ![image](https://github.com/user-attachments/assets/77ff7978-f103-4e06-b8bd-e963ca63d814)
   4. delete from game;


       





