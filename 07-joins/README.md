 # Join - types, examples for learning purpose
 
:pushpin: Use NATURAL JOIN </br> 

    --There are 3 identically named columns in EMPLOYEES table: EMPLOYEE_ID, JOB_ID, DEPARTMENT_ID. </br>
    --Fetch the EMPLOYEE_ID, JOB_ID, DEPARTMENT_ID, LAST_NAME, HIRE_DATE, END_DATE values for all rows </br>
    --Alias the EMPLOYEES table as EMP and the JOB_HISTORY table as JH.

    SELECT EMPLOYEE_ID, JOB_ID, DEPARTMENT_ID,
    EMP.LAST_NAME,
    EMP.HIRE_DATE,
    JH.END_DATE
    FROM HR.employees EMP NATURAL JOIN HR.job_history JH 

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/07-joins/pictures/ch07-natural-join.png" 
width="650">

---

:pushpin: Use LEFT OUTER JOIN </br> 

    SELECT D.DEPARTMENT_NAME , E.DEPARTMENT_ID
    FROM HR.DEPARTMENTS D 
    LEFT OUTER JOIN HR.EMPLOYEES E ON (E.DEPARTMENT_ID = D.DEPARTMENT_ID)
    WHERE E.DEPARTMENT_ID IS NULL ; 

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/07-joins/pictures/cho7-left-outer-join.png" width="1500">
