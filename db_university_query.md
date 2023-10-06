### 1. Selezionare tutti gli studenti nati nel 1990 (160)

    SELECT `id`,`name`,`surname`,`date_of_birth` AS `year_birth` FROM `students` WHERE YEAR(`date_of_birth`) = 1990;

### 2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT `id`,`name`,`cfu`,`website` FROM `courses` WHERE `cfu` > 10 ORDER BY `courses`.`cfu` DESC;
{{ ho lasciato DESC per visualizzare prima i cfu più alti }}

### 3. Selezionare tutti gli studenti che hanno più di 30 anni

SELECT `id`,`name`,`surname`,`date_of_birth` FROM `students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURRENT_DATE) > 30  
ORDER BY `students`.`date_of_birth` ASC

### 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di

laurea (286)
SELECT `id`,`name`,`period`,`year` FROM `courses` WHERE `period` LIKE "I %" AND `year` = 1 ORDER BY `courses`.`year` ASC;

### 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del

20/06/2020 (21)

SELECT `id`,`date`,`hour`,`location`,`address` FROM `exams` WHERE `date` LIKE '2020-06-20' AND TIME(`hour`) > '14%';

{{DA TORNARCI}} -
