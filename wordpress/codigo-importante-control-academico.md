# Código importante control académico

```php
//lista usuarios por rol
$wp_roles = wp_roles();
$result   = count_users();

foreach ( $result['avail_roles'] as $role => $count ) {
    if ( 0 == $count )
        continue; //pass role none

    $args = array(
        'role' => $role
    );

    $users = get_users( $args );
    $user  = array();
    for ( $i = 0; $i < $count ; $i++ )
        $user[] = esc_html( $users[ $i ]->display_name ); //show display name

    //output
    echo wp_sprintf( '<h2>%1$s</h2><ul><li>%2$s</li></ul>',
        esc_html( $wp_roles->role_names[ $role ] ),
        implode( '</li><li>', $user )
    );
}


//lista todos los usuarios de un rol
  $args1 = array(
  'role' => 'bba_inicial',
  'orderby' => 'user_nicename',
  'order' => 'ASC'
  );
  $students = get_users($args1);
  echo '<ul>';
  foreach ($students as $user) {
  echo '<li>' . $student->display_name.'['.$student->user_email . ']</li>';
  }
  echo '</ul>';
```
