# Informes configurables

### Reporte de inasistencia

```sql
SELECT u.firstname AS "Nombre", u.lastname AS "Apellido", u.email AS "Email", c.fullname AS "Curso", attst.acronym, DATE_FORMAT(FROM_UNIXTIME(att.sessdate),'%d %M %Y')AS Fecha
FROM prefix_attendance_sessions AS att
JOIN prefix_attendance_log AS attlog ON att.id = attlog.sessionid
JOIN prefix_attendance_statuses AS attst ON attlog.statusid = attst.id
JOIN prefix_attendance AS a ON att.attendanceid = a.id
JOIN prefix_course AS c ON a.course = c.id
JOIN prefix_user AS u ON attlog.studentid = u.id
WHERE attst.acronym = "I"
%%FILTER_STARTTIME:att.sessdate:>%% 
%%FILTER_ENDTIME:att.sessdate:<%%
ORDER BY att.sessdate DESC
```

### Reporte de notas finales

```sql
SELECT 
c.shortname AS 'Cod curso', 
c.fullname AS 'Curso',
DATE_FORMAT(FROM_UNIXTIME(c.enddate), '%Y-%m-%d') AS 'Fin de curso',
u.lastname AS 'Apellido',
u.firstname AS 'Nombre',
u.username AS 'Usuario',
u.email AS 'Email',
ROUND(gg.finalgrade,2)
AS Calificacion,
DATE_ADD('1970-01-01',
INTERVAL gi.timemodified SECOND) AS FecCalif
FROM prefix_course AS c 
JOIN prefix_context AS ctx ON c.id = ctx.instanceid 
JOIN prefix_role_assignments AS ra ON ra.contextid = ctx.id 
JOIN prefix_user AS u ON u.id = ra.userid 
JOIN prefix_grade_grades AS gg ON gg.userid = u.id 
JOIN prefix_grade_items AS gi ON gi.id = gg.itemid 
JOIN prefix_course_categories AS cc ON cc.id = c.category  
WHERE
gi.courseid = c.id 
AND
gi.itemtype = 'course'
AND
ra.roleid=5
%%FILTER_USERS:u.username%%
ORDER
BY c.enddate DESC, u.lastname
```
