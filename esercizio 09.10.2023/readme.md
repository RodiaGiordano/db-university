### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `students`.`name`, `students`.`surname`, `degrees`.`name` FROM `students` INNER JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` WHERE `degrees`.`name` LIKE "%economia";
```

<br>
<br>

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql

SELECT * FROM `departments` INNER JOIN `degrees` ON `departments`.`id`= `degrees`.`department_id` WHERE `departments`.`name` LIKE "%neuroscienze" AND `degrees`.`level` LIKE "%magistrale";
```

<br>
<br>

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT * FROM `courses` INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id` INNER JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id` WHERE `teachers`.`id` LIKE 44;
```

<br>
<br>

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT * FROM `students` INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` ORDER BY `students`.`surname` ASC, `students`.`surname`;

```

<br>
<br>

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT * FROM `degrees` INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id` INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id` INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`;
```

<br>
<br>

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql

```

<br>
<br>

### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18

```sql

```

<br>
<br>

---

### 1. Contare quanti iscritti ci sono stati ogni anno

<br>
<br>

```sql
SELECT COUNT(*), YEAR(`enrolment_date`) FROM `students` GROUP BY YEAR(`enrolment_date`);
```

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

<br>
<br>

```sql
SELECT COUNT(*), `office_address` FROM `teachers` GROUP BY `office_address`;

```

### 3. Calcolare la media dei voti di ogni appello d'esame

<br>
<br>

```sql
SELECT AVG(`vote`) FROM `exam_student` GROUP BY `exam_id`;
```

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(\*) FROM `degrees` GROUP BY `department_id`;
