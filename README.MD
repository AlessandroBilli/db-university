# DB UNIVERSITY

## Descrizione 
Simulazione di un database per una piattaforma universitaria strutturata in tabelle. 



## QUERY CORRETTE db_university


1. SELECT
    *
FROM
    `students`
WHERE
    YEAR(`date_of_birth`) = 1990;
2. SELECT
    *
FROM
    `courses`
WHERE
    (`cfu`) > 10;
3. SELECT
    *
FROM
    `students`
WHERE
    YEAR(CURRENT_DATE) - YEAR(date_of_birth) = 30;

4. SELECT
    *
FROM
    `courses`
WHERE
    `period` = "I semestre" AND `year` = 1;

5. SELECT
    *
FROM
    `exams`
WHERE
    DATE(`date`) = '2020-06-20' AND TIME(`hour`) > '14:00:00';

6. SELECT
    *
FROM
    `degrees`
WHERE
    `level` = 'magistrale';


7. SELECT
    *
FROM
    `departments`;



8. SELECT
    `phone`,
    `name`,
    `surname`
FROM
    `teachers`
WHERE
    `phone` IS NULL;