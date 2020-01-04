## Data Retrieval samples for learning purpose

### Data dictionary query

    select * from all_tables;
    
    select owner, table_name from user_tables;

---

Sample SQL statements

:wrench: PL: Konkatenacja tekstu i danych jako nazwana kolumna  
           ENG: Concatenation of text and data as a named column

    SELECT 
        'The Job ID for the ' || JOB_TITLE || '''s' || ' job is: ' || JOB_ID AS "Job description" 
    FROM HR.JOBS;

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/02-data-retrieval/images/ch02q2.PNG )

---

:wrench: PL: Obliczanie pola koła, przy uzyciu tabeli DUAL ; r=6000, pi=22/7  
         ENG: Calculating the area of a circle, using the DUAL table ; r=6000, pi=22/7
         
         
    SELECT (22/7) * (6000 * 6000 ) "Area"
    FROM SYS.dual

![alt text](https://github.com/pawlowskaanna/sandbox-sql/blob/master/02-data-retrieval/images/ch02q3.PNG )

---
How can we use the NVL:

    select first_name, last_name, salary, commission_pct, salary+(NVL(commission_pct,0))
    from hr.employees;
  
</br>  

---

    -- Znajdź pracowników, którzy mają więcej niż jeden okres zatrudnienia.

    select employee_id, count(*)
    from hr.job_history
    group by employee_id
    having count(*)>1 ;
    
---

    -- Sprawdź, którzy pracownicy “są bliżej niż dalej” pensji maksymalnej dla swojego stanowiska 
    (tzn. przekroczyli próg połowy sumy będącej różnicą między płacą minimalną a maksymalną).
   
           select E.first_name, E.last_name, J.job_title,  E.salary, J.max_salary, J.min_salary, 
           (J.max_salary -    J.min_salary)/2
           from hr.employees E join hr.jobs J on (E.job_id = J.job_id)
           where E.salary > (( (J.max_salary - J.min_salary)/2 )+ J.min_salary);



