### Zamówienie


### Product
Table creation - DDL (Data Definition Language) SQL

    CREATE TABLE ANIA.PRODUCTS 
    (
      PRODUCT_CODE  VARCHAR2(20)    NOT NULL, 
      NAME          VARCHAR2(50)    NOT NULL, 
      DESCRIPTION   VARCHAR2(300), 
      CONSTRAINT PK_PRODUCTS PRIMARY KEY(PRODUCT_CODE)
    );

Inserting - DML (Data Modification Language) SQL

    INSERT INTO ANIA.PRODUCTS (PRODUCT_CODE, NAME) VALUES ('PL/1045/TB', 'Basic Wooden Table 45');
    INSERT INTO ANIA.PRODUCTS (PRODUCT_CODE, NAME) VALUES ('PL/1560/CH', 'Hoker 13');
    INSERT INTO ANIA.PRODUCTS (PRODUCT_CODE, NAME) VALUES ('UK/6501/PC', 'Painting - industrial 002');

Querying - SQL queries

    SELECT * FROM ANIA.PRODUCTS;


### Linia zamówienia
