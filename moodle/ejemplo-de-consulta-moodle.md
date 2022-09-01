# Ejemplo de consulta moodle

```php
/*

mysql -u moodle_pruebas_db_user -p
MOODLE_PRUEBAS_estudia_lidera_trasciendedb
USE moodle_pruebas_db;

La fecha de finalización del curso está en la tabla  mdl_course en el campo enddate, el id del curso está en el atributo id
Tabla de user enrolments -> mdl_user_enrolments;
Tabla mdl_enrol
fontjoy.com
coolors.co
CONSULTA PARA VER USUARIOS ACTIVO - CONSULTA COMPLETA
Select mdl_enrol.courseid, mdl_course.fullname, mdl_course.enddate, mdl_user_enrolments.userid FROM mdl_enrol, mdl_course, mdl_user_enrolments WHERE mdl_enrol.courseid = mdl_course.id AND mdl_user_enrolments.enrolid = mdl_enrol.id;
CONSULTA ESPECÍFICA
Select mdl_course.fullname, mdl_course.enddate, mdl_user_enrolments.userid FROM mdl_enrol, mdl_course, mdl_user_enrolments WHERE mdl_enrol.courseid = mdl_course.id AND mdl_user_enrolments.enrolid = mdl_enrol.id;

*/

//

```
