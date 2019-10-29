# Restricting and sorting data samples for learning purpose
Sample SQL statements

:wrench: Restricting returned rows to those which contain a "3" in the REGION_ID column

    SELECT country_name
    FROM HR.countries
    WHERE region_id=3;

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/03-restricting-and-storing-data/images/ch03-where-clause.PNG )

---

:wrench: ENG: The WHERE clause can be also used to compare the arithmetic expressions
           
     SELECT last_name, salary
     FROM HR.employees
     WHERE salary/10 = department_id*10;
![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/03-restricting-and-storing-data/images/ch03-comparing-expressions.PNG )

---
:pencil2:
Reusable query, input: tax rate, EMPLOYEE_ID </br>
Raturned values: EMPLOYEE_ID, FIRST_NAME, SALARY, ANNUAL SALARY(SALARY * 12), TAX_RATE, TAX (TAX_RATE * 12) 

           select employee_id, first_name, salary, salary * 12 AS "Annual salary", 
           &&tax_rate, (&TAX_RATE * (salary * 12))AS "TAX"
           FROM HR.employees
           where employee_id = &employee_id;
           
1 - SELECT command ; "Annual salary" defined </br>
2 - '&&' because once given tax value isn't changed , "TAX" defined </br>
3 - FROM clause </br>
4 - restraining rows to wanted employee </br>
