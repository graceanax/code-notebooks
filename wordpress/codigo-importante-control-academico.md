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

{% embed url="https://www.sitepoint.com/using-wp-list-table-to-create-wordpress-admin-tables/" %}

{% embed url="https://clearintelligence.mx/wp-list-table-una-guia-paso-a-paso/" %}

{% embed url="https://supporthost.com/wp-list-table-tutorial/#connect_table_to_data_and_columns" %}

Otros sin revisar

{% embed url="https://www.smashingmagazine.com/2011/11/native-admin-tables-wordpress/" %}

{% embed url="https://www.folkstalk.com/2022/10/how-to-untab-highlighed-code-in-vscode-with-code-examples.html" %}
