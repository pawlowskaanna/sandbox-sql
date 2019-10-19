### Zadania

#### Zadanie 1
:wrench: Zaprojektuj bazę danych do ewidencji produkcyjnej dla firmy konstrukcyjnej.  

Firma produkuje **elementy konstrukcyjne**. Każdy z nich jest identyfikowany 10 znakowym, alfanumerycznym (zawsze 10 znaków) *kodem elementu*. Dodatkowo każdy z nich ma unikalną *nazwę* i *opis*. Poza tym, zapisywana jest w bazie zawsze *data wprowadzenia (elementu) na rynek* i w przypadku elementów archiwalnych, które nie są już produkowane, *data archiwizacji*. Wymagane jest zapisanie *wagi* każdego z elementów w dokładności do grama.

Element konstrukcyjny może składać się z wielu **komponentów**. Komponent jest unikalnie identyfikowany numerycznym (minimalnie 5, maksymalnie 10 cyfr) *kodem komponentu*, a także zawiera *nazwę*, *wagę* w dokładności do grama i *oznaczenie dostępności* mogącą przybierać trzy wartości (dostępny, niedostępny, na wyczerpaniu). Jeden komponent może być zastosowany w wielu elementach konstrukcyjnych.

:dart: Polecenia szczegółowe:

1. Zaprojektuj ERD (entity-relationship diagram)
2. Zaprojektuj model fizyczny (tabele)
3. Stwórz SQL DDL dla każdej tabeli
4. Stwórz SQL DML (3 elementy i 12 komponentów)
5. Stwórz następujące zapytania (SQL Queries):
   - *TO BE ADDED*
