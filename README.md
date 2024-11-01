## Descripción del Dataset

En este conjunto de datos, encontrarás cinco archivos con las estadísticas al final de cada campo de batalla. Las estadísticas comunes (columnas) en todos los archivos son:

- **Code**: código del campo de batalla (no es necesario para el análisis).
- **Faction**: facción del jugador (Horda o Alianza).
- **Class**: clase del jugador (guerrero, paladín, cazador, pícaro, sacerdote, caballero de la muerte, chamán, mago, brujo, monje, druida, cazador de demonios).
- **KB**: número de muertes letales infligidas por el jugador.
- **D**: número de veces que el jugador murió.
- **HK**: número de asesinatos en los que el jugador o su grupo contribuyeron.
- **DD**: daño infligido por el jugador.
- **HD**: sanación realizada por el jugador.
- **Honor**: honor otorgado al jugador.
- **Win**: 1 si el jugador ganó.
- **Lose**: 1 si el jugador perdió.
- **Rol**: "dps" si el jugador es un repartidor de daño; "heal" si el jugador se enfoca en sanar aliados. Ten en cuenta que no todas las clases pueden ser sanadores, solo chamán, paladín, sacerdote, monje y druida, pero todas las clases pueden ser repartidores de daño.
- **BE**: algunas semanas hay un evento de bonificación, cuando el honor ganado se incrementa. 1 si el campo de batalla ocurrió durante esa semana.

Estas columnas, más la columna **battleground**, están en el archivo `wowbgs.csv`. La columna *battleground* representa el tipo de campo de batalla:

- **AB**: Cuenca de Arathi.
- **BG**: Batalla por Gilneas.
- **DG**: Grieta Aullante.
- **ES**: Ojo de la Tormenta.
- **SA**: Playa de los Ancestros.
- **SM**: Minas Lonjaplata.
- **SS**: Costa Hirviente.
- **TK**: Templo de Kotmogu.
- **TP**: Cumbres Gemelas.
- **WG**: Garganta Grito de Guerra.

