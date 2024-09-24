1. SELECT * 
FROM crime_scene_report;

2. SELECT *
FROM crime_scene_report
WHERE type = "murder";

3. SELECT *
FROM crime_scene_report
WHERE type = "murder"
	AND date = "20180115"
	AND city = "SQL City";

4. SELECT *
FROM person;

5. SELECT *
FROM person
WHERE address_street_name = "Northwestern Dr"
ORDER BY address_number DESC;

6. SELECT *
FROM person
WHERE name LIKE '%Annabel%'
AND address_street_name = "Franklin Ave"; 

7. SELECT *
FROM interview
WHERE person_id IN ("14887", "16371");

8. SELECT *
FROM get_fit_now_check_in
WHERE membership_id LIKE '48Z%'
	AND check_in_date = "20180109";

9. SELECT *
FROM drivers_license
WHERE gender = "male"
	AND plate_number LIKE '%H42W%'; 

10. SELECT *
FROM person
WHERE license_id IN ("423327", "664760"); 

11. SELECT *
FROM get_fit_now_member
WHERE person_id IN ("51739", "67318");

12. INSERT INTO solution VALUES (1, 'Jeremy Bowers'); 
SELECT value FROM solution; 




