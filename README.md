# mongodbTorneo Deportivo - Futbol Sala

Este repositorio contiene la implementación de una base de datos para un torneo deportivo de fútbol sala. La base de datos utiliza MongoDB para almacenar y gestionar la información relacionada con los equipos, deportistas, entrenadores, árbitros y encuentros deportivos.

Requerimientos

Equipos con un máximo de 7 deportistas y un mínimo de 4 deportistas.

Deportistas con edad mínima de 18 años y máxima de 50 años.

Encuentros deportivos 1 contra 1 en fechas y lugares determinados.

Tabla de posiciones basada en puntos obtenidos en los encuentros.

Dos árbitros asignados por encuentro deportivo.

Entrenadores asignados a cada equipo.

Modelo de base de datos

La base de datos utiliza las siguientes colecciones:

equipos: Almacena información sobre los equipos participantes.

deportistas: Almacena información sobre los deportistas inscritos en el torneo.

entrenadores: Almacena información sobre los entrenadores asignados a los equipos.

arbitros: Almacena información sobre los árbitros disponibles para los encuentros deportivos.

encuentros: Almacena información sobre los encuentros deportivos programados.

Esquemas de las colecciones

Equipos

json

Copy code

{

"\_id": ObjectId,

"nombre": String,

"entrenador\_id": ObjectId,

"deportistas\_ids": [ObjectId, ...],

"puntos": Number

}

Deportistas

json

Copy code

{

"\_id": ObjectId,

"nombre": String,

"apellido": String,

"edad": Number,

"equipo\_id": ObjectId

}

Entrenadores

json

Copy code

{

"\_id": ObjectId,

"nombre": String,

"apellido": String,

"equipo\_id": ObjectId

}

Árbitros

json

Copy code

{

"\_id": ObjectId,

"nombre": String,

"apellido": String

}

Encuentros

json

Copy code

{

"\_id": ObjectId,

"equipo1\_id": ObjectId,

"equipo2\_id": ObjectId,

"arbitros\_ids": [ObjectId, ObjectId],

"fecha": Date,

"lugar": String,

"resultado": {

"equipo1\_puntos": Number,

"equipo2\_puntos": Number

}

}

Enlaces útiles

Video explicativo

Repositorio Git

Instrucciones para la instalación

Clonar el repositorio: git clone https://github.com/Saraycotes92/mongodb.git

Instalar MongoDB y configurarlo según las necesidades del proyecto.

Importar los datos de ejemplo y configurar las colecciones según el modelo de base de datos proporcionado.

Contribuciones y soporte

Si tienes alguna pregunta o deseas contribuir al proyecto, no dudes en abrir un issue o enviar un pull request.


