 # Converting functions samples for learning purpose

Sample SQL statements

:wrench: 
Retrieve a list of FIRST_NAME and LAST_NAME values and an expression based on the HIRE_DATE column for employees hired on a Saturday. The expression must be aliased as START_DATE and a HIRE_DATE value of 17-FEB-1996 must return the following string:
Saturday, the 17th of February, One Thousand Nine Hundred Ninety-Six.
 
    SELECT FIRST_NAME, LAST_NAME, TO_CHAR(HIRE_DATE, 'fmDay,''the ''ddth ''of ''Month, Yyyysp.' )START_DATE
    FROM HR.EMPLOYEES
    WHERE TO_CHAR (HIRE_DATE, 'fmDAY') = 'Saturday' ;
    
    -- 'fm' - trims blank spaces
---
:wrench: Comparing values with the use of NVL2 function 

    SELECT FIRST_NAME, LAST_NAME, JOB_ID,
    NVL2(NULLIF( Length(first_name), Length(last_name)), 'Different length' , 'Same length') NAME_LENGTHS
    FROM HR.EMPLOYEES
    WHERE DEPARTMENT_ID = 100;
    
<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/05-conversion-functions/pictures/ch05-nvl2-clause.png" width="400">

---
:wrench: Using the DECODE clause - comparing values 

    SELECT state_province, DECODE(STATE_PROVINCE, 'Washington', 'Headquarters', 
        'Texas' , 'Oil Wells',
        'California' , city,
        'New Jersey' , street_address
        ) "LOCATION_INFO",
        COUNTRY_ID, CITY
    FROM HR.LOCATIONS
    WHERE COUNTRY_ID LIKE 'US'
    ORDER BY LOCATION_INFO;

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/05-conversion-functions/pictures/ch05-decode-clause.png" width="550">


---
:wrench:
Using SQL Developer or SQL*Plus, connect to the OE schema and complete the following tasks.
As part of a new marketing initiative, you are asked to prepare a list of customer birthdays that occur
between two days ago and seven days from now. The list should retrieve rows from the CUSTOMERS table which include the CUST_FIRST_NAME, CUST_LAST_NAME, CUST_EMAIL, and DATE_ OF_BIRTH columns in ascending order based on the day and month components of the DATE_OF_ BIRTH value. An additional expression aliased as BIRTHDAY is required to return a descriptive mes- sage based on the following table.


---
:wrench:

Create a report containing the number of employees who left their jobs, grouped by the year in which they left. The jobs they performed are also required. The results must be sorted in descending order based on the number of employees in each group. The report must list the year, the JOB_ID, and the number of employees who left a particular job in that year

    -- The JOB_ID is tricky, ts must be added to GROUP BY clause as otherwise it is impossible to propperly analyse data. It is not said in the exercise but it has to be added to the GROUP BY clause to get a proper query result
    
    SELECT TO_CHAR(END_DATE, 'YYYY') "LAST_YEAR" , JOB_ID,
    COUNT (EMPLOYEE_ID) "NUMBER_OF_EMP"
    FROM HR.JOB_HISTORY
    WHERE END_DATE IS NOT NULL
    GROUP BY TO_CHAR(END_DATE, 'YYYY'), JOB_ID
    ORDER BY 2 DESC;

---
:wrench: The HAVING clause - simple query

    SELECT TO_CHAR(HIRE_DATE, 'DAY')HIRE_DAY , COUNT(*) 
    FROM HR.EMPLOYEES 
    GROUP BY TO_CHAR(HIRE_DATE,'DAY')
    HAVING COUNT(*) >15
    ORDER BY 1;

---
:wrench: Chapter 6 - summing up

    -- Listing all statuses
    SELECT DISTINCT PRODUCT_STATUS FROM OE.PRODUCT_INFORMATION;

    -- report
    SELECT PRODUCT_STATUS, COUNT(PRODUCT_STATUS), SUM(LIST_PRICE)
    FROM OE.PRODUCT_INFORMATION
    -- WHERE PRODUCT_STATUS <> 'orderable'
    WHERE NOT(PRODUCT_STATUS = 'orderable')
    GROUP BY PRODUCT_STATUS 
    HAVING SUM(LIST_PRICE) > 4000;             
