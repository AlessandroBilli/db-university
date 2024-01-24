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
    YEAR(CURRENT_DATE) - YEAR(date_of_birth) > 30;

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

  ## QUERY JOIN

  1.  

SELECT `students`.* ,  `degrees`.`name`
FROM `students`
INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = "Corso di Laurea in Economia"

2. 
  
SELECT
    *
FROM
    `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE  `degrees`.`level` = "magistrale" AND `departments`.`name` = "Dipartimento di Neuroscienze"

3. 


SELECT `teachers`.*, `courses`.*
FROM `teachers`
INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `teachers`.`id` = 44

4. 

SELECT
`students`.`surname`, `students`.`name`, `degrees`.`name` AS `corso_di_laurea`, `departments`.`name` AS `dipartimento`
FROM
    `students`
INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname`, `students`.`name`


5. 

SELECT *
FROM `degrees`
LEFT JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`


6. 

SELECT DISTINCT `teachers`.`id`, `teachers`.`surname`, `teachers`.`name`, `departments`.`name`
FROM `teachers`
INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
INNER JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = "Dipartimento di Matematica"
ORDER BY `teachers`.`surname`, `teachers`.`name`;

  
