<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/exercises/zielnik/pictures/tresc-zadania.png" width="700">

Diagram ERD

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/exercises/zielnik/pictures/zielnik-ERD.png" width="300">

---

Encje

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/exercises/zielnik/pictures/zielnik-encje.png" width="600">

---
Tabele

<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/exercises/zielnik/pictures/zielnik-tabele.png" width="600">

---

DDL

    CREATE TABLE ANIA.KOLEKCJE 
    (
        KOD_KOLEKCJI      VARCHAR2(20 CHAR)         NOT NULL,
        DONATOR           VARCHAR2(100 CHAR)        NOT NULL,
        DZIAL             VARCHAR2(20 CHAR)         NOT NULL,

        CONSTRAINT PK_KOLEKCJE PRIMARY KEY(KOD_KOLEKCJI)
    );

</br>

    CREATE TABLE ANIA.HERBARIA
    (
        KOD_HERBARIUM        VARCHAR2(20 CHAR)        NOT NULL,
        NAZWA_HERBARIUM      VARCHAR (100)            NOT NULL,

        CONSTRAINT PK_HERBARIA PRIMARY KEY(KOD_HERBARIUM)
    );
    
</br>

    CREATE TABLE ANIA.KARTY_ZIELNIKA 
    (	
        KOD_KARTY       VARCHAR2(20 CHAR)           NOT NULL, 
        OPIS            VARCHAR2(500 CHAR)          NOT NULL,
        OBRAZ           BLOB,
        KOD_KOLEKCJI    VARCHAR2(20 CHAR)           NOT NULL,
        
        CONSTRAINT PK_KARTY_ZIELNIKA PRIMARY KEY(KOD_KARTY),
        CONSTRAINT FK_KOLEKCJE FOREIGN KEY(KOD_KOLEKCJI) REFERENCES ANIA.KOLEKCJE(KOD_KOLEKCJI)
    );
    
</br>

    CREATE TABLE ANIA.KARTY_ZIELNIKÓW_W_HERBARIACH
    (
        KOD_KARTY           VARCHAR2 (20 CHAR)      NOT NULL,
        KOD_HERBARIUM       VARCHAR2(20 CHAR)       NOT NULL,

        CONSTRAINT PK_KARTY_ZIELNIKÓW_W_HERBARIACH PRIMARY KEY(KOD_KARTY , KOD_HERBARIUM),
        CONSTRAINT FK_KODY_KART_ZIELNIKÓW_W_HERBARIACH FOREIGN KEY(KOD_KARTY) REFERENCES ANIA.KARTY_ZIELNIKA(KOD_KARTY),
        CONSTRAINT FK_KODY_HERBARIOW FOREIGN KEY(KOD_HERBARIUM) REFERENCES ANIA.HERBARIA(KOD_HERBARIUM)
    );
   
</br>

    ALTER TABLE ANIA.KARTY_ZIELNIKÓW_W_HERBARIACH MODIFY
    (
        KOD_KARTY           NOT NULL,
        KOD_HERBARIUM       NOT NULL
    );
