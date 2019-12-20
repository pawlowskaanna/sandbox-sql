<img src="https://github.com/pawlowskaanna/sandbox-sql/blob/master/exercises/zielnik/pictures/tresc-zadania.png" width="700">

-- Creating tables

    CREATE TABLE ANIA.KOLEKCJE 
    (
        KOD_KOLEKCJI      VARCHAR2(20 CHAR),
        DONATOR           VARCHAR2(100 CHAR),
        DZIAL             VARCHAR2(20 CHAR),

        CONSTRAINT PK_KOLEKCJE PRIMARY KEY(KOD_KOLEKCJI)
    );
