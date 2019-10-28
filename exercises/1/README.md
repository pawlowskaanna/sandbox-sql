### Zadanie 1

#### Model ERD
:pencil: TODO: diagram

#### Model fizyczny

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/exercises/1/pictures/z1.png" width="800" >
#### SQL DDL

    -- SQL DDL
    
    
    -- Creating COMPONENTS table with primary key: COMPONENT_CODE with additional CONSTRAINT CHECK (CONSTRAINT col_name CHECK (col IN (...)))

    CREATE TABLE Z1.COMPONENTS 
    (	
    "COMPONENT_CODE" number(10,0) NOT NULL,
    "NAME"      VARCHAR2(50 char) NOT NULL,
    "WEIGHT"    NUMBER(7,3) NOT NULL,
    "AVAILABILITY"  VARCHAR2(20), 
    CONSTRAINT PK_COMPONENTS PRIMARY KEY(COMPONENT_CODE),
    CONSTRAINT CHK_AVAILABILITY CHECK (AVAILABILITY IN ('avaliable', 'unavaliable', 'running out'))
    );
    
     -- Creating STRUCTURAL_ELEMENTS table with primary key: ELEMENT_CODE
     
    CREATE TABLE Z1.STRUCTURAL_ELEMENTS 
    (	
    "ELEMENT_CODE"  nchar(10) NOT NULL,
    "NAME"          varchar(20) NOT NULL,
    "ELEMENT_DESCRIPTION"          varchar(20),
    "ENTRY"         date NOT NULL,
    "ARCH"          date,
    "WEIGHT"        number(7,3) NOT NULL,
    CONSTRAINT PK_STRUCTURAL_ELEMENTS PRIMARY KEY(ELEMENT_CODE)
    );
    
    
     -- Creating ELEMENT_COMPONENTS table with primary key: COMPONENT_KODE, ELEMENT_CODE

    CREATE TABLE Z1.ELEMENT_COMPONENTS 
    (	
    "ELEMENT_CODE"  nchar(10) NOT NULL,
    "COMPONENT_CODE" number(10,0) NOT NULL,
    CONSTRAINT FK_COMPONENTS FOREIGN KEY(COMPONENT_CODE) REFERENCES Z1.COMPONENTS(COMPONENT_CODE),
    CONSTRAINT FK_STRUCTURAL_ELEMENTS FOREIGN KEY(ELEMENT_CODE) REFERENCES Z1.STRUCTURAL_ELEMENTS(ELEMENT_CODE),
    CONSTRAINT PK_ELEMENT_COMPONENTS PRIMARY KEY(COMPONENT_CODE, ELEMENT_CODE)
    );

#### SQL DML
:pencil: TODO

:x: Delete unproper rows

    DELETE
    FROM structural_elements;

:rocket: COMPONENTS    

:one:
    
    INSERT INTO Z1.COMPONENTS 
    (COMPONENT_CODE, NAME, WEIGHT, AVAILABILITY) 
    VALUES ('6101010001', 'E10x10', '0000,015', 'avaliable');

 :two:
 
    INSERT INTO Z1.COMPONENTS 
    (COMPONENT_CODE, NAME, WEIGHT, AVAILABILITY) 
    VALUES ('6201510001', 'F15x10', '0000,025', 'unavaliable');

:three:

    INSERT INTO Z1.STRUCTURAL_ELEMENTS 
    (ELEMENT_CODE , name, ELEMENT_DESCRIPTION, ENTRY, WEIGHT) 
    VALUES ('ISKF010/35', 'ISKF10x35', 'Sliding element', TO_DATE('13-03-2019', 'DD-MM-YYYY'), '0000,040');
    
:four:

    INSERT INTO Z1.COMPONENTS 
    (COMPONENT_CODE, NAME, WEIGHT, AVAILABILITY) 
    VALUES ('990014035', 'ISKF14x35', '0000,045', 'avaliable');

:five:

    INSERT INTO Z1.COMPONENTS 
    (COMPONENT_CODE, NAME, WEIGHT, AVAILABILITY) 
    VALUES ('6000000022', 'GL22standard', '0000,020', 'running out');
    
:six:

    INSERT INTO Z1.COMPONENTS 
    (COMPONENT_CODE, NAME, WEIGHT, AVAILABILITY) 
    VALUES ('6000000032', 'GL32standard', '0000,030', 'avaliable');
    
:seven:

:eight:

:nine:

:ten:

:eleven:

:twelfe:

