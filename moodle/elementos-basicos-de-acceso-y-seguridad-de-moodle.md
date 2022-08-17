---
description: >-
  Estas notas vienen del cuarto curso en el programa Moodle Developer Basics. En
  este curso, aprenderá cómo controlar el acceso a su complemento utilizando la
  API de acceso de Moodle.
---

# Elementos básicos de acceso y seguridad de Moodle

{% hint style="info" %}
Moodle context: es un lugar donde se asignan permisos a un usuario (generalmente a través de un rol). En Moodle, los contextos se superponen en una jerarquía.
{% endhint %}

Por ejemplo un usuario que es estudiante, solo tiene este rol dentro de los cursos, fuera de ellos es solo un usuario logeado.

El administrador puede editar las capacidades de cada rol.

Un sitio de Moodle está organizado en una jerarquía de áreas denominadas contextos y los usuarios se convierten en estudiantes o profesores en contextos individuales, como cursos.

![Contextos de moodle](../.gitbook/assets/image.png)

* El nivel raíz de la jerarquía es el contexto del sistema que representa todo el sitio.
* En la parte superior hay un árbol de contextos de categorías de cursos.
* Cada curso tiene su propio contexto de curso.
* Dentro de los contextos del curso hay contextos de módulos que representan instancias de módulos de actividades particulares y contextos de bloques que representan bloques.
* La página principal del sitio se implementa internamente como un curso, por lo que el contexto de la página principal es en realidad uno de los contextos de nivel de curso para ese curso de sitio en particular.
* Finalmente, el contexto de usuario representa a un usuario determinado.

#### Ejemplo

Tengamos un rol personalizado "Spammer" que prohíba al usuario iniciar nuevas discusiones y responder a las publicaciones del foro. Si este rol está asignado a un usuario en el nivel de contexto del sistema, evita que el usuario publique en cualquier parte del sitio. Si el rol se asigna al usuario en un nivel de contexto de curso particular, el usuario no puede publicar en foros en este curso en particular, pero puede publicar en foros en otros cursos. El rol también podría asignarse en el nivel de contexto del módulo y afectar solo a un foro.

### Control de acceso

Su código nunca debe verificar qué rol tiene el usuario. Nunca debe diseñar e implementar el código con construcciones como "si el usuario es estudiante, entonces..." o "si el usuario es profesor, entonces...".

En su lugar, piense en un buen conjunto de capacidades que describan todas las funciones proporcionadas por el complemento. Declarar estas capacidades en el archivo `db/access.php` de su complemento junto con valores predeterminados sensibles para roles de arquetipo. Luego verifique si el usuario tiene la capacidad dada a través de los métodos `has_capability()` y `require_capability()`.

[Ver más sobre capacidades](https://docs.moodle.org/dev/Access\_API)
