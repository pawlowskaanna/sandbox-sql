# Restricting and sorting data samples for learning purpose
Sample SQL statements

:wrench: PL: Ograniczenie wyświetlonych COUNTRY_NAME do tych wersów, któr mają wartość "3" w kolumnie REGION_ID    
           ENG: Restricting returned rows to those which contain a "3" in the REGION_ID column

    SELECT country_name
    FROM HR.countries
    WHERE region_id=3;

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/03-restricting-and-storing-data/images/ch03-where-clause.PNG )

---

:wrench: PL: WHERE można używać także w celu porównywania wyrażeń algebraicznych  
           ENG: The WHERE clause can be also used to compare the arithmetic expressions
           
     SELECT last_name, salary
     FROM HR.employees
     WHERE salary/10 = department_id*10;
![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/03-restricting-and-storing-data/images/ch03-comparing-expressions.PNG )
