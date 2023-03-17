# Torneo Deportivo - Futbol Sala

Este repositorio contiene la implementación de una base de datos para un torneo deportivo de fútbol sala. La base de datos utiliza MongoDB para almacenar y gestionar la información relacionada con los equipos, deportistas, entrenadores, árbitros y encuentros deportivos.

## Requerimientos

- Equipos con un máximo de 7 deportistas y un mínimo de 4 deportistas.
- Deportistas con edad mínima de 18 años y máxima de 50 años.
- Encuentros deportivos 1 contra 1 en fechas y lugares determinados.
- Tabla de posiciones basada en puntos obtenidos en los encuentros.
- Dos árbitros asignados por encuentro deportivo.
- Entrenadores asignados a cada equipo.

## Modelo de base de datos

La base de datos utiliza las siguientes colecciones:

1. `equipos`: Almacena información sobre los equipos participantes.
2. `deportistas`: Almacena información sobre los deportistas inscritos en el torneo.
3. `entrenadores`: Almacena información sobre los entrenadores asignados a los equipos.
4. `arbitros`: Almacena información sobre los árbitros disponibles para los encuentros deportivos.
5. `encuentros`: Almacena información sobre los encuentros deportivos programados.

### Esquemas de las colecciones

#### Equipos

```json
{
  "_id": ObjectId,
  "nombre": String,
  "entrenador_id": ObjectId,
  "deportistas_ids": [ObjectId, ...],
  "puntos": Number
}

#### Deportistas

{
  "_id": ObjectId,
  "nombre": String,
  "apellido": String,
  "edad": Number,
  "equipo_id": ObjectId
}

#### Entrenadores


  "_id": ObjectId,
  "nombre": String,
  "apellido": String,
  "equipo_id": ObjectId
}

#### Árbitros

{
  "_id": ObjectId,
  "nombre": String,
  "apellido": String
}

#### Encuentros
{
  "_id": ObjectId,
  "equipo1_id": ObjectId,
  "equipo2_id": ObjectId,
  "arbitros_ids": [ObjectId, ObjectId],
  "fecha": Date,
  "lugar": String,
  "resultado": {
    "equipo1_puntos": Number,
    "equipo2_puntos": Number
  }
}


