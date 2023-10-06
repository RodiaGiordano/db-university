### 1. Selezionare tutti gli studenti nati nel 1990 (160)

    SELECT `id`,`name`,`surname`,`date_of_birth` AS `year_birth` FROM `students` WHERE YEAR(`date_of_birth`) = 1990;

### 2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT `id`,`name`,`cfu`,`website` FROM `courses` WHERE `cfu` > 10 ORDER BY `courses`.`cfu` DESC;
{{ ho lasciato DESC per visualizzare prima i cfu più alti }}
