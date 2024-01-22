# DB UNIVERSITY

## Descrizione 
Simulazione di un database per una piattaforma universitaria strutturata in tabelle. 



## QUERY CORRETTE db_university


1. SELECT
    *
FROM
    students
WHERE
    YEAR(`date_of_birth`) = 1990;
2. SELECT
    *
FROM
    courses
WHERE
    (`cfu`) > 10;
3. SELECT
    *
FROM
    students
WHERE
    YEAR(CURRENT_DATE) - YEAR(date_of_birth) = 30;