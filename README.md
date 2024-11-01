# Análisis del Dataset de Campos de Batalla

En este proyecto, se realiza una exhaustiva limpieza y modificación del dataset, añadiendo nuevas variables que enriquecen la información disponible. La primera etapa consiste en llevar a cabo un análisis exploratorio del dataset para comprender las distribuciones de las diferentes clases y facciones presentes en los campos de batalla. Este análisis inicial nos permite identificar patrones y tendencias, y llegar a las primeras conclusiones sobre el comportamiento de los jugadores en distintos escenarios.

---

Posteriormente, se prepara el dataset para la implementación de modelos de machine learning. Durante este proceso, se eliminan variables altamente correlacionadas, como la variable de "Honor", que pueden inducir al overfitting en los modelos. Además, se aplican técnicas como el one-hot encoding y el mean encoding, junto con filtrado y otras transformaciones, para asegurar que el modelo pueda aprender de manera efectiva.

Se lleva a cabo el análisis predictivo utilizando tres modelos diferentes:
1. **Regresión Logística**: 
2. **KNN (K-Nearest Neighbors)**
3. **Árbol de Decisión**:
Los resultados obtenidos con el **DecisionTreeClassifier** son prometedores:
- **Precisión**: 0.783
- **AUC en entrenamiento**: 0.865
- **AUC en prueba**: 0.856
- **Sensibilidad**: 0.783
- **Especificidad**: 0.782
- **F1 Score**: 0.791

Estas métricas indican que el modelo es capaz de clasificar correctamente una buena parte de las instancias. 

Finalmente, se alcanzan conclusiones interesantes, donde se identifican condiciones clave que afectan el rendimiento de los jugadores. Entre estas condiciones destacan aspectos como la contribución a las muertes en el campo de batalla y la facción a la que pertenece el jugador. Estas observaciones no solo enriquecen nuestra comprensión del juego, sino que también pueden guiar futuras estrategias de mejora y optimización del rendimiento de los jugadores.



-----------------------------------
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

