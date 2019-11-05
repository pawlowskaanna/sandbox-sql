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
