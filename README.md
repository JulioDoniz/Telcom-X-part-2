# Análisis de Factores de Cancelación de Clientes (Churn) y Estrategias de Retención

Este proyecto realiza un análisis exhaustivo de los datos de clientes de una empresa de telecomunicaciones para identificar los factores clave que influyen en la cancelación de servicios (Churn). Utilizando técnicas de machine learning, específicamente modelos de Árbol de Decisión y Random Forest, se busca predecir qué clientes son más propensos a cancelar y proponer estrategias de retención basadas en estos hallazgos.

## Objetivos del Proyecto

*   Identificar las variables con mayor influencia en la decisión de un cliente de cancelar su servicio.
*   Entrenar y evaluar modelos de clasificación para predecir la cancelación de clientes.
*   Proponer estrategias de retención de clientes basadas en los factores de mayor impacto identificados.

## Metodología

1.  **Carga y Exploración de Datos:**
    *   Los datos se cargaron desde un archivo CSV.
    *   Se realizó una exploración inicial para entender la estructura de los datos, identificar tipos de variables y detectar valores nulos.

2.  **Preparación de Datos:**
    *   Se manejaron los valores nulos eliminando las filas correspondientes.
    *   Se eliminó la columna 'CustomerID' por no ser relevante para el modelado.
    *   La variable objetivo ('Churn') se transformó a formato numérico (0 y 1).
    *   Las variables categóricas se codificaron utilizando One-Hot Encoding para hacerlas compatibles con los algoritmos de machine learning.

3.  **Análisis de Correlación:**
    *   Se generó una matriz de correlación para visualizar las relaciones entre las variables.

4.  **Balanceo de Datos:**
    *   Dado que el conjunto de datos de 'Churn' estaba desbalanceado, se aplicó la técnica NearMiss para equilibrar las clases en el conjunto de entrenamiento.

5.  **Separación de Datos:**
    *   El conjunto de datos se dividió en conjuntos de entrenamiento y prueba.

6.  **Modelado:**
    *   Se entrenaron modelos de **Árbol de Decisión** y **Random Forest**.
    *   Se realizó un ajuste de hiperparámetros utilizando **GridSearchCV** con validación cruzada (StratifiedKFold) para optimizar el rendimiento, priorizando la métrica **Recall** debido a la importancia de identificar correctamente a los clientes que cancelarán.

7.  **Evaluación de Modelos:**
    *   Se evaluó el rendimiento de los modelos utilizando métricas clave como **Accuracy**, **Precision**, **Recall** y **F1-score** a través de informes de clasificación.
    *   Se analizó la **importancia de las características** obtenida de los modelos de árbol para identificar los factores más influyentes en la cancelación.

## Factores Clave que Influyen en la Cancelación

Basado en el análisis de importancia de características, los principales factores que afectan la cancelación de clientes son:

*   **Tipo de Servicio de Internet (especialmente Fibra Óptica):** Los clientes con fibra óptica muestran una mayor propensión a la cancelación.
*   **Costo de los Servicios:** Los cargos totales y mensuales elevados son un predictor significativo de la cancelación.
*   **Antigüedad del Cliente (Tenure):** Los clientes con menor antigüedad son más propensos a cancelar.
*   **Tipo de Contrato (Mes a Mes):** Los contratos mes a mes están asociados con una mayor probabilidad de cancelación en comparación con contratos a largo plazo.
*   **Método de Pago (Cheque Electrónico):** Este método de pago se asocia con una mayor importancia en la predicción de la cancelación.
*   **Servicios Adicionales (Seguridad en Línea, Streaming TV, Soporte Técnico):** La presencia o ausencia de estos servicios también influye en la decisión de cancelar.

## Rendimiento de los Modelos

Se comparó el rendimiento de varios modelos de Árbol de Decisión y Random Forest. El modelo **RandomForestClassifier ajustado con hiperparámetros y utilizando todas las características** demostró ser el más efectivo en el conjunto de prueba, logrando la mejor Accuracy general y un buen equilibrio entre Precision y Recall para la clase minoritaria 'Churn'.

## Estrategias de Retención Propuestas

Basado en los hallazgos, se proponen las siguientes estrategias para reducir la tasa de cancelación:

*   **Mejorar la experiencia del servicio de Fibra Óptica:** Abordar proactivamente los problemas de calidad o satisfacción percibida por los usuarios de fibra óptica.
*   **Optimizar la estructura de precios y ofrecer incentivos:** Considerar descuentos o paquetes especiales para clientes con cargos elevados o para incentivar la permanencia.
*   **Implementar programas de retención temprana:** Enfocarse en los clientes nuevos para asegurar una integración positiva y construir lealtad desde el principio.
*   **Promover contratos a largo plazo:** Ofrecer beneficios atractivos para que los clientes cambien de contratos mes a mes a contratos de uno o dos años.
*   **Evaluar y mejorar los métodos de pago:** Investigar las razones detrás de la importancia del cheque electrónico en la cancelación y optimizar este proceso o promover alternativas.
*   **Destacar el valor de los servicios adicionales:** Comunicar de manera efectiva los beneficios de servicios como seguridad en línea, streaming y soporte técnico.

## Estructura del Repositorio

*   `nombre_del_notebook.ipynb`: El notebook de Google Colab que contiene todo el código y análisis.
*   `datos_tratados.csv`: Archivo de datos utilizado (enlazado desde la URL proporcionada).
*   `README.md`: Este archivo.

## Cómo Ejecutar el Código

1.  Abrir el notebook `nombre_del_notebook.ipynb` en Google Colab.
2.  Ejecutar las celdas secuencialmente. Asegúrate de tener acceso a la URL de los datos.

## Dependencias

Las principales bibliotecas utilizadas incluyen:

*   pandas
*   matplotlib
*   seaborn
*   numpy
*   sklearn
*   imblearn
*   statsmodels

Estas dependencias se instalan automáticamente en el entorno de Google Colab.

## Contribuciones

Las contribuciones son bienvenidas. Si encuentras algún problema o tienes sugerencias, por favor abre un issue o envía un pull request.
