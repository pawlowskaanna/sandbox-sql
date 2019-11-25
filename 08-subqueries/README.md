# Subqueries - examples for learning purpose
 
:pushpin: 3 level subquery

    -- Query all employees who work in departments located in the United Kingdom </br>
    
    select E.last_name from hr.employees E where department_id in
            (select D.department_id from hr.departments D 
                 where location_id in
                      (select L.location_id from hr.locations L
                            where country_id =
                                (select C.country_id from hr.countries C where C.country_name= 'United Kingdom' )
    ) );
    
<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/08-subqueries/pictures/ch08-sub01.png" width="600">

___
