 # Converting functions samples for learning purpose

Sample SQL statements

:wrench: 
Retrieve a list of FIRST_NAME and LAST_NAME values and an expression based on the HIRE_DATE column for employees hired on a Saturday. The expression must be aliased as START_DATE and a HIRE_DATE value of 17-FEB-1996 must return the following string:
Saturday, the 17th of February, One Thousand Nine Hundred Ninety-Six.
 
    SELECT FIRST_NAME, LAST_NAME, TO_CHAR(HIRE_DATE, 'fmDay,''the ''ddth ''of ''Month, Yyyysp.' )START_DATE
    FROM HR.EMPLOYEES
    WHERE TO_CHAR (HIRE_DATE, 'fmDAY') = 'Saturday' ;
    
    -- 'fm' - trims blank spaces
