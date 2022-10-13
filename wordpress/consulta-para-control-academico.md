# Consulta para control académico

11 días inactivo

```sql
SELECT ecampus_users.user_login, 
ecampus_users.user_email, ecampus_users.display_name,
lws_user.activity_status,
lws_user.activity_type,
eposts.post_title, DATE_FORMAT(FROM_UNIXTIME(lws_user.activity_completed),'%d %M %Y')AS Fecha
FROM ecampusnbs_users as ecampus_users
INNER JOIN ecampusnbs_learndash_user_activity as lws_user
ON ecampus_users.ID = lws_user.user_id
INNER JOIN ecampusnbs_posts as eposts 
ON eposts.ID = lws_user.post_id
INNER JOIN (
	SELECT lws_user.user_id, MAX(lws_user.activity_completed) as max_date
	FROM ecampusnbs_learndash_user_activity as lws_user 
	INNER JOIN ecampusnbs_posts as eposts 
	ON eposts.ID = lws_user.post_id
	WHERE lws_user.activity_type IN ('course', 'quiz')
	GROUP BY lws_user.user_id
) AS ecampus_max_date
ON ecampus_users.ID = ecampus_max_date.user_id
INNER JOIN ecampusnbs_usermeta as usermeta
ON usermeta.user_id = ecampus_users.ID 
WHERE lws_user.activity_completed = ecampus_max_date.max_date
AND usermeta.meta_key = 'ecampusnbs_capabilities' 
AND ( 
usermeta.meta_value LIKE '%subscriber%'
OR usermeta.meta_value LIKE '%customer%'
OR usermeta.meta_value LIKE '%libre%')
GROUP BY ecampus_users.ID
ORDER BY Fecha asc;
```
