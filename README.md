# 01 - Desarrollo de una Aplicación de Lista de Libros

El objetivo de esta prueba es diseñar e implementar una pequeña aplicación web de lista de libros utilizando las herramientas de tu elección (Preferiblemente React).
 
Este proyecto busca probar tus habilidades en el manejo de interacciones con el usuario, gestión del estado, filtrado de datos y la estructuración del código.
![Sin título-2023-03-24-0943 (1)](https://github.com/midudev/pruebas-tecnicas/assets/1561955/a829323d-07e6-4937-91c6-5498481148c5)

## Contexto

Somos un sello editorial de libros multinacional. Queremos ofrecer a nuestro público una forma de ver nuestro catálogo y poder guardar los libros que les interesan en una lista de lectura.

Para ello, queremos desarrollar una aplicación web que permita a los usuarios registrarse en la plataforma, loguearse y ver los libros disponibles y crear una lista de lectura. Ten en cuenta que:

- No sabemos si el framework que utilicemos ahora será el definitivo, pero querremos reutilizar el máximo de código posible.
- La aplicación debe ser fácil de usar y agradable a la vista.
- Tenemos un 80% de usuarios que vienen de navegadores de escritorio.

Usa el archivo `books.json` para obtener los datos de los libros. Puedes añadir más libros si lo deseas, siempre y cuando siga la misma estructura.
Y utiliza la siguiente ApiRest para gestionar la creación del usuario basica y el loguin del mismo utilizando JWT.

El EndPint para crear usuario es: 
POST: https://apirestmercado.azurewebsites.net/usuario/Crear
Se debe pasar como parametro el JSON:
    {
    "documento": 0,
    "nombre": "string",
    "correo": "string",
    "password": "string"
    }

Y el EndPoint para Loguearse y recibir el Token es el siguiente:
POST: https://apirestmercado.azurewebsites.net/usuario/Login
Se debe pasar como parametro el JSON:
    {
    "correo": "string",
    "password": "string"
    }
"El correo y password deberan ser de un usuario creado previo con la opción del registro de usuario"

La respuesta del Loguin es la siguiente:
Ejemplo:
    {
        "documento": 1048213956,
        "nombre": "Ronald Moreno",
        "correo": "rony@gmail.com",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJub21icmVVc3VhcmlvIjoiUm9uYWxkIE1vcmVubyIsIm5vbWJyZUNvcnJlbyI6InJvbnlAZ21haWwuY29tIiwiZW1haWwiOiJyb255QGdtYWlsLmNvbSIsIm5iZiI6MTczMDQwMzIyNiwiZXhwIjoxNzMwNDA2ODI2LCJpc3MiOiJodHRwczovL2t4NHcyNjhnLTcwMDkudXNlMi5kZXZ0dW5uZWxzLm1zLyIsImF1ZCI6Imh0dHBzOi8va3g0dzI2OGctNzAwOS51c2UyLmRldnR1bm5lbHMubXMvIn0.xfW2vkYvHlBspEtqF-p3Dh1lzv2RkiciLb0gs4GZoig"
    }
Se debe almacenar el token en el cliente y cuando se ingrese a la pagina de libros en la parte superior debe estar el nombre del usuario Logueado con la opción de cerrar sesión.

Este proyecto tambien busca probar tu alcance en la implementación de registro de cualquier formulario utilizando ApiRest y el manejo de autenticación con JWT.
https://github.com/RonyAlejandro15/pruebaFrontEnd/blob/main/1.png
https://github.com/RonyAlejandro15/pruebaFrontEnd/blob/main/2.png


## Requisitos

### Funcionalidad

0. **Gestión para registrarse un usuario nuevo y opción para iniciar sesión**: La aplicación al iniciar debe mostrar una vista de Login con su boton de registro de usuario, si no se tiene usuario debe permitir registrar un usuario nuevo.
Y posteriormente al loguearse en la parte superior de la pagina debe mostrar el nombre del usuario logueado y con la opción de desloguearse. El login debe hacerso con el Endpoint arriba socializado y con JWT.

1. **Visualización de Libros Disponibles**: La aplicación debe mostrar una lista de libros disponibles que el usuario pueda revisar.

2. **Creación de Lista de Lectura**: El usuario debe ser capaz de crear una lista de lectura a partir de los libros disponibles. En la UI debe quedar claro qué libros están en la lista de lectura y cuáles no. También debe ser posible mover un libro de la lista de lectura a la lista de disponibles.

3. **Filtrado de Libros por Género**: Los usuarios deben poder filtrar la lista de libros disponibles por género, y se mostrará un contador con el número de libros disponibles, el número de libros en la lista de lectura y el número de libros disponibles en el género seleccionado.

4. **Sincronización de Estado**: Debe haber una sincronización del estado global que refleje el número de libros en la lista de lectura y el número de libros todavía disponibles. Si un libro se mueve de la lista de disponibles a la lista de lectura, el recuento de ambos debe actualizarse en consecuencia.

5. **Persistencia de Datos**: La aplicación debe persistir los datos de la lista de lectura en el almacenamiento local del navegador. Al recargar la página, la lista de lectura debe mantenerse.

6. **Sincronización entre pestañas**: Si el usuario abre la aplicación en dos pestañas diferentes, los cambios realizados en una pestaña deben reflejarse en la otra. Sin necesidad de usar Backend.

7. **Despliegue**: La aplicación debe estar desplegada en algún servicio de hosting gratuito (Netlify, Vercel, Firebase, etc) y debe ser accesible a través de una URL pública. Indica la URL en el README.

8. **Test**: La aplicación debe tener AL MENOS un test. Haz el test que consideres más importante para tu aplicación.

## Consejos sobre el código

1. **Estructura del código**: El código debe estar bien organizado y fácil de leer.

2. **Semántica HTML**: El HTML debe ser semántico y accesible.

3. **Pensando en equipo**: Prepara tu proyecto pensando que cualquier persona de tu equipo puede tener que trabajar en él en el futuro. (scripts en el package.json, mínima documentación en el README, comentarios en el código si es necesario, etc)

4. **Formatea tu código**: Asegúrate de que tu código está formateado de forma consistente. Puedes usar Prettier o cualquier otra herramienta que te guste.

5. **Preparado para producción**: Asegúrate de que tu aplicación está lista para producción. Minimiza el código, optimiza las imágenes, etc.

## Desafíos adicionales

**¿Quieres ir más allá?** Estos son algunos desafíos adicionales que puedes intentar:

- Implementar una funcionalidad de búsqueda en la lista de libros disponibles.
- Añade un nuevo filtro para filtrar los libros por número de páginas.
- Permitir la reorganización de los libros en la lista de lectura por prioridad.
- Haz que tu diseño sea responsive.

## Entrevista

Si pasas a la siguiente fase, te pediremos que hagas una entrevista con nosotros. Durante la entrevista, te pediremos que expliques tu código y que hagas algunos cambios en el mismo.

- Nos tendrás que explicar el código que has escrito y las decisiones que has tomado.
- Haremos cambios en el JSON y tendrás que adaptar el código en vivo.
- Añadiremos un nuevo filtro a la aplicación y tendrás que implementarlo.

Buena suerte y ¡diviértete programando!


