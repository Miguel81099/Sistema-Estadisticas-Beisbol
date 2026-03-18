# Sistema-Estadisticas-Beisbol
## Descripcion
Desarrollo de una base de datos relacional para gestionar estadísticas de bateo en una liga de beisbol. Se organiza mediante 4 entidades:  Equipo, Posición, Jugador y Promedio. 
## Motivacion
La motivación de este proyecto es aplicar los conceptos de normalización de datos en un escenario deportivo real que en mi caso es beisbol, ya que al finalizar un toreno no se premia al mejor bateador por perdida de score, que en este caso son los libros que llevan en el registro de cada turno al bat de bateador. por lo tanto quiero tener una solucion a esta problematica mediante este proyecto.

## Proceso de Normalización Aplicado

Se actualizaron los diagramas E-R y UML aplicando las reglas de normalización para asegurar la integridad de los datos:

1. **Primera Forma Normal (1FN):** Se aplicó la **atomicidad** en los atributos. El cambio principal fue en la tabla `Bateador`, dividiendo el campo `Nombre` en `Nombre` y `Apellido`. También se separó el periodo de tiempo en `Año` y `Mes` en la tabla `Temporada`.
2. **Segunda Forma Normal (2FN):** Se eliminaron dependencias parciales. Las estadísticas (como `hits` o `home_runs`) ahora dependen de la combinación de `id_bateador` e `id_temporada` mediante llaves foráneas (FK), asegurando que cada dato pertenezca a un jugador y un momento específico.
3. **Tercera Forma Normal (3FN):** Se eliminaron dependencias transitivas. En la tabla `Equipo`, los datos como `Ciudad` y `Liga` dependen únicamente de la llave primaria `id_equipo`, evitando redundancias.

### Diagramas del Sistema
* [Ver Diagrama Entidad-Relación (DER)](DER-EstadisticasDeBateador)
* [Ver Diagrama de Clases UML](UML.pdf.pdf)
