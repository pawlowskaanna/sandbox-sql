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

___

</br>
TASK: </br>
A customer requires a hard disk drive and a graphics card for her personal computer. She is willing to spend between $500 and $800 on the disk drive but is unsure about the cost of a graphics card. Her only requirement is that the resolution supported by the graphics card should be either 1024×768 or 1280×1024. As the sales representative, you have been tasked to write one query that searches the PRODUCT_INFORMATION table where the PRODUCT_NAME value begins with HD (hard disk) or GP (graphics processor) and their list prices. Remember the hard disk list prices must be between $500 and $800 and the graphics processors need to support either 1024×768 or 1280×1024. Sort the results in descending LIST_PRICE order.

    SELECT PRODUCT_NAME, LIST_PRICE
    FROM PRODUCT_INFORMATION
    WHERE PRODUCT_NAME LIKE "HD%" 
    AND LIST_PRICE BETWEEN 500 AND 800
    OR PRODUCT_NAME LIKE 'GP%1024%';
