 # Join - types, examples for learning purpose
 
:wrench: 
</br>There are 3 identically named columns with the EMPLOYEES table: EMPLOYEE_ID, JOB_ID, and DEPARTMENT_ID. </br>
   Fetch the EMPLOYEE_ID, JOB_ID, DEPARTMENT_ID, LAST_NAME, HIRE_DATE, and END_DATE values for all rows retrieved using a pure natural join. </br>
Alias the EMPLOYEES table as EMP and the JOB_HISTORY table as JH.

    SELECT EMPLOYEE_ID, JOB_ID, DEPARTMENT_ID,
    EMP.LAST_NAME,
    EMP.HIRE_DATE,
    JH.END_DATE
    FROM HR.employees EMP NATURAL JOIN HR.job_history JH 

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/07-joins/pictures/ch07-natural-join.png" 
width="400">
