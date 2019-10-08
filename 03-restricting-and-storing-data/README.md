# Restricting and sorting data samples for learning purpose
Sample SQL statements

:wrench: PL: Ograniczenie wyświetlonych COUNTRY_NAME do tych wersów, któr mają wartość "3" w kolumnie REGION_ID    
           ENG: Restricting returned rows to those which contain a "3" in the REGION_ID column

    SELECT country_name
    FROM HR.countries
    WHERE region_id=3;

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/02-data-retrieval/images/ch02q2.PNG )

---
