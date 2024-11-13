# Análisis del Dataset de Campos de Batalla

![Portada de World of Warcraft]()

En este proyecto, se realiza una exhaustiva limpieza y modificación del dataset, añadiendo nuevas variables que enriquecen la información disponible. La primera etapa consiste en un análisis exploratorio del dataset para comprender las distribuciones de las diferentes clases y facciones en los campos de batalla. Este análisis permite identificar patrones y tendencias importantes, y establecer conclusiones preliminares.

![Radar Plot](https://github.com/Arnaud-Chafai/wow-bgs-eda-predictive-analysis/blob/main/Screenshots/RadarPlot.png)

---

Posteriormente, el dataset se prepara para la implementación de modelos de machine learning. En esta fase, se eliminan variables altamente correlacionadas, como la variable de "Honor", para evitar el overfitting. Además, se aplican técnicas como el one-hot encoding y el mean encoding, junto con filtrado y otras transformaciones, para asegurar que el modelo aprenda de forma efectiva y robusta.

El análisis predictivo se realiza utilizando cinco modelos diferentes:

1. **Regresión Logística**
2. **KNN (K-Nearest Neighbors)**
3. **Árbol de Decisión**
4. **Random Forest**
5. **XGBoost**

El modelo con peor desempeño fue **KNN**, con los siguientes resultados:
- Accuracy: 0.681
- AUC en entrenamiento: 0.817
- AUC en prueba: 0.735
- Sensibilidad: 0.663
- Especificidad: 0.701
- F1 Score: 0.686

El modelo con los mejores resultados en precisión y balance entre métricas fue **XGBoost**, optimizado mediante un ajuste bayesiano de hiperparámetros.

![Historia de Optimización](https://github.com/Arnaud-Chafai/wow-bgs-eda-predictive-analysis/blob/main/Screenshots/Optimizacion.png)

---

## Reporte del Modelo XGBoost:

### 1. Métricas Básicas:
- **Accuracy Train**: 0.849
- **Accuracy Test**: 0.791
- **AUC en Train**: 0.932
- **AUC en Test**: 0.884
- **Sensibilidad**: 0.811
- **Especificidad**: 0.768
- **F1 Score**: 0.803

### 2. Validación Cruzada:
- **Media CV Score**: 0.866
- **Scores por fold**: [0.8626, 0.8735, 0.8311, 0.8660, 0.8975]
- **Desviación estándar**: 0.021

### 3. Tasas de Error:
- **Error en Train**: 0.151
- **Error en Test**: 0.209
- **Diferencia (Test - Train)**: 0.058

![Curva ROC](https://github.com/Arnaud-Chafai/wow-bgs-eda-predictive-analysis/blob/main/Screenshots/AUC.png)

---

## Conclusiones
La variable más importante en el modelo final fue **HK** (número de asesinatos en los que el jugador o su grupo contribuyeron), seguida de la facción (Horda) y la variable **D** (número de veces que el jugador murió). Estos resultados proporcionan una visión profunda sobre los factores más decisivos en el éxito de los jugadores en los campos de batalla.

---
![Feature](https://github.com/Arnaud-Chafai/wow-bgs-eda-predictive-analysis/blob/main/Screenshots/Features.png)
-----------------------------------


## Descripción del Dataset

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

