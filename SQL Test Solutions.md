1. SELECT AVG(grade) AS average_grade
FROM Enrollments;


![image](https://github.com/user-attachments/assets/0397ae4a-f717-4fdd-9a33-80d4d05e62ff)

2. SELECT Students.name AS student_name, Courses.course_name
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;


![image](https://github.com/user-attachments/assets/3e177a06-2ad4-4bf0-ac91-de42657051c9)

3. SELECT grade_level, COUNT(student_id) AS student_count
FROM Students
GROUP BY grade_level;


![image](https://github.com/user-attachments/assets/cad2f803-a600-4385-a4c6-bc8ffb7eeed5)

4. SELECT Courses.course_name, MAX(Enrollments.grade) AS max_grade
FROM Enrollments
JOIN Courses ON Enrollments.course_id = Courses.course_id
GROUP BY Courses.course_name;

![image](https://github.com/user-attachments/assets/7e0ed84a-0e8b-4103-8647-528094911616)

5. SELECT AVG(Enrollments.grade) AS average_grade
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
WHERE Students.grade_level = 3;


![image](https://github.com/user-attachments/assets/dce44790-e305-458f-8c58-1b72486b7201)

6. SELECT Students.name AS student_name, Courses.course_name, Courses.credits
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;

![image](https://github.com/user-attachments/assets/b8f2c2f0-c118-4b19-bb46-06ef59a9c00c)


7. SELECT 
    c.course_id, 
    c.course_name, 
    AVG(e.grade) AS average_grade
FROM 
    Courses c
JOIN 
    Enrollments e ON c.course_id = e.course_id
GROUP BY 
    c.course_id, c.course_name
HAVING 
    AVG(e.grade) > 3.0;

![image](https://github.com/user-attachments/assets/96ed66fd-53bf-43b3-b772-f7f1ad7dae59)

8.
SELECT 
    s.student_id, 
    s.name, 
    s.age, 
    s.grade_level
FROM 
    Students s
WHERE 
    s.student_id NOT IN (
        SELECT 
            e.student_id
        FROM 
            Enrollments e
        WHERE 
            e.grade = 4.0
    );

 ![image](https://github.com/user-attachments/assets/35c5070b-8769-45f8-b36f-834b2f108155)

9. SELECT 
    s.name
FROM 
    Students s
JOIN 
    Enrollments e ON s.student_id = e.student_id
GROUP BY 
    s.student_id, s.name
HAVING 
    AVG(e.grade) > (
        SELECT 
            AVG(grade)
        FROM 
            Enrollments
    );

![image](https://github.com/user-attachments/assets/a84956b8-c886-4a07-a08c-30fdc9e3bd0c)

10. SELECT 
    s.name,
    COUNT(e.course_id) AS total_courses,
    AVG(e.grade) AS average_grade
FROM 
    Students s
LEFT JOIN 
    Enrollments e ON s.student_id = e.student_id
GROUP BY 
    s.student_id, s.name;

![image](https://github.com/user-attachments/assets/e0ab808e-bb09-4b1a-98cd-0f6df723c113)












