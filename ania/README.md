### Zamówienie


### Produkt
    CREATE TABLE ANIA.PRODUCTS 
    (
      PRODUCT_CODE  VARCHAR2(20)    NOT NULL, 
      NAME          VARCHAR2(50)    NOT NULL, 
      DESCRIPTION   VARCHAR2(300), 
      CONSTRAINT PK_PRODUCTS PRIMARY KEY(PRODUCT_CODE)
    );


### Linia zamówienia
