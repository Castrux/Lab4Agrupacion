# Uso de herramientas de IA generativa

## Declaración del uso

| Herramienta | Tipo de uso |
|---|---|
| Claude | Generación inicial de código, depuración de errores, generación de visualizaciones |


---

## Prompts utilizados

A continuación se documentan los prompts principales que influyeron directamente en el resultado entregado.

---

### Prompt 1 — Exploración inicial de datos

> "Importa los datos del archivo Datos_VuelaAlpes.csv y crea un notebook para hacer una exploración inicial de los datos."

**Contexto de uso:** Etapa 1 — Exploración de datos. Se usó para generar la estructura inicial del notebook con carga del CSV, revisión de tipos, valores nulos y estadísticas descriptivas.

---

### Prompt 2 — Depuración de error en Agglomerative Clustering

> "Ayudame a corregir este error:
>
> ```
> Cell In[53], line 7
> 1 pipeline_agglo = Pipeline([
> 2     ('prep', make_preprocessor()),
> 3     ('agglo', AgglomerativeClustering(n_clusters=best_k_ag, linkage=best_lnk))
> 4 ])
> 6 labels_ag = pipeline_agglo.fit_predict(df_model)
> ----> 7 sil_ag = silhouette_score(X_prep, labels_ag, sample_size=5000, random_state=42)
> ...
> ValueError: Number of labels is 1. Valid values are 2 to n_samples - 1 (inclusive)
> ```"

**Contexto de uso:** Etapa 3 — Modelamiento. Se usó para identificar que el error era causado por la búsqueda de hiperparámetros retornando un único clúster, y corregir el rango de parámetros evaluados.

---

### Prompt 3 — Visualizaciones para selección de hiperparámetros

> "Crea gráficos de los 3 algoritmos para poder escoger los mejores parámetros"

**Contexto de uso:** Etapa 3 — Modelamiento. Se usó para generar curvas de silueta, dendrogramas y gráficos de inercia (Elbow) que apoyaron la selección del número óptimo de clústeres para cada algoritmo.

---



## Análisis crítico del resultado

### ¿Qué partes del contenido generado fueron correctas y útiles?

[_Respuesta aquí — por ejemplo: La estructura del pipeline sugerida por la IA fue correcta y se adaptó bien al flujo de trabajo requerido. Los gráficos generados permitieron visualizar claramente los valores óptimos de k._]

### ¿Qué errores, imprecisiones o limitaciones se identificaron?

[ En el Prompt 2, la IA sugirió una solución parcial; fue necesario revisar manualmente el rango de valores del hiperparámetro `n_clusters` para que el pipeline no colapsara en un único grupo.]



---

## Aportes propios del estudiante

- **¿Qué fue desarrollado, modificado o decidido por el estudiante?**  
  [La selección final de los tres algoritmos (K-Means, Agglomerative Clustering y DBSCAN) y la justificación de su elección se realizaron con criterio propio a partir del análisis del conjunto de datos.]


