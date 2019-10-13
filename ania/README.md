### Order
Table creation - DDL (Data Definition Language) SQL


    -- DROP TABLE ANIA.ORDERS;
    CREATE TABLE "ANIA"."ORDERS" 
    (	
    "ORDER_NR" VARCHAR2(25 CHAR), 
    "ORDER_SUB" DATE, 
    "ORDER_EXE" DATE,
    CONSTRAINT PK_ORDERS PRIMARY KEY(ORDER_NR)
    );

Inserting - DML (Data Modification Language) SQL

    INSERT INTO ANIA.ORDERS (ORDER_NR, ORDER_SUB) VALUES ('PL/001', TO_DATE('13-10-2019', 'DD-MM-YYYY'));
    INSERT INTO ANIA.ORDERS (ORDER_NR, ORDER_SUB) VALUES ('PL/023', TO_DATE('14-10-2019', 'DD-MM-YYYY'));
    INSERT INTO ANIA.ORDERS (ORDER_NR, ORDER_SUB) VALUES ('PL/013', TO_DATE('15-10-2019', 'DD-MM-YYYY'));


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

Querying - select all

    SELECT * FROM ANIA.PRODUCTS;

Querying - select custom name from PL products

    SELECT NAME || ' [ ' || PRODUCT_CODE || ' ]' "PRODUCT_LINE"
    FROM ANIA.PRODUCTS
    WHERE PRODUCT_CODE LIKE 'PL%';


<img src="./pictures/ania01q2.png" width="300" >

### Linia zamówienia
