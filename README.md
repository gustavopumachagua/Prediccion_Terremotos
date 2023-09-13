# **Prediccion Terremotos**

---

## **Temario**

| **Indice**                                                    |
| ------------------------------------------------------------- |
| [Inicio](#introduccion)                                       |
| [Data](./data/Data_Limpio.csv)                                |
| [Estadisticas y Visualizacion](./Estadisticas_graficos.ipynb) |
| [Prediccion](./Prediccion.ipynb)                              |

---

### **Introduccion**

| **Abreviatura**     | **Significado**                                                                                                                                                                                                                                                                                                    |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Time**            | Se refiere al tiempo o la marca de tiempo en la que ocurrió un terremoto específico.                                                                                                                                                                                                                               |
| **Place**           | Se refiere al lugar o ubicación geográfica en la que ocurrió un terremoto específico.                                                                                                                                                                                                                              |
| **Latitude**        | Se refiere a la latitud geográfica en la que ocurrió un terremoto específico. La latitud es una medida angular que indica la posición norte-sur de un punto en la superficie de la Tierra.                                                                                                                         |
| **Longitude**       | Se refiere a la longitud geográfica en la que ocurrió un terremoto específico. La longitud es una medida angular que indica la posición este-oeste de un punto en la superficie de la Tierra.                                                                                                                      |
| **Depth**           | Se refiere a la profundidad del hipocentro o foco del terremoto. La profundidad indica la distancia vertical desde la superficie de la Tierra hasta el punto donde se origina el terremoto.                                                                                                                        |
| **Mag**             | Se refiere a la magnitud del terremoto. La magnitud es una medida que cuantifica la energía liberada por un terremoto en su fuente sísmica.                                                                                                                                                                        |
| **MagType**         | Se refiere al tipo de escala o método utilizado para medir la magnitud del terremoto. Md (Magnitud de duración), Mb (Magnitud de cuerpo ondulatorio), Ms (Magnitud de superficie), Mw (Magnitud de momento).                                                                                                       |
| **nst**             | Se refiere al número de estaciones sísmicas utilizadas para determinar la ubicación y los parámetros del terremoto.                                                                                                                                                                                                |
| **gap**             | El campo "gap" en los datos de terremotos indica la brecha angular en grados entre las estaciones sísmicas que registraron el terremoto. Esta medida se utiliza para evaluar la distribución espacial de las estaciones sísmicas y proporciona información sobre las áreas donde la cobertura sísmica es limitada. |
| **dmin**            | Se refiere a la distancia mínima entre la estación sísmica más cercana y el epicentro del terremoto.                                                                                                                                                                                                               |
| **rms**             | Se refiere a la amplitud de la onda sísmica medida en términos del valor eficaz (root mean square en inglés).                                                                                                                                                                                                      |
| **net**             | Se refiere a la red sísmica utilizada para la detección, registro y monitoreo de los eventos sísmicos. Una red sísmica es un conjunto de estaciones sísmicas distribuidas geográficamente que se utilizan para registrar y analizar los terremotos.                                                                |
| **ID**              | Se refiere al identificador o identificación única asignada a cada evento sísmico registrado en una base de datos o catálogo de terremotos.                                                                                                                                                                        |
| **Updated**         | Se refiere a la fecha y hora en la que se realizó la última actualización de la información relacionada con un evento sísmico específico en un catálogo o base de datos.                                                                                                                                           |
| **Type**            | Se refiere al tipo de terremoto o evento sísmico registrado.                                                                                                                                                                                                                                                       |
| **horizontalError** | Se refiere al error horizontal asociado con la ubicación geográfica del epicentro de un terremoto.                                                                                                                                                                                                                 |
| **depthError**      | Se refiere al error o incertidumbre asociada con la determinación de la profundidad del hipocentro de un terremoto.                                                                                                                                                                                                |
| **magError**        | Se refiere al error o incertidumbre asociada con la determinación de la magnitud de un terremoto.                                                                                                                                                                                                                  |
| **magNst**          | Se refiere al número de estaciones utilizadas para determinar la magnitud de un terremoto.                                                                                                                                                                                                                         |
| **status**          | Se refiere al estado o condición de un evento sísmico en relación con su procesamiento o informe.                                                                                                                                                                                                                  |
| **locationSource**  | Se refiere a la fuente o la entidad responsable de la determinación de la ubicación geográfica de un terremoto.                                                                                                                                                                                                    |
| **magSource**       | Se refiere a la fuente o entidad responsable de la determinación de la magnitud de un terremoto.                                                                                                                                                                                                                   |

---

## **Tipos de Magnitud**

Aquí tienes una descripción de los diferentes tipos de escalas utilizados para medir la magnitud de un terremoto:

- **mww:** Magnitud de Momento (Moment Magnitude). Es una escala moderna y ampliamente utilizada que se basa en la cantidad total de energía liberada por un terremoto. Es especialmente efectiva para terremotos de gran magnitud.

- **mb:** Magnitud de Onda Corporal (Body Wave Magnitude). Es una medida de la amplitud de las ondas P (ondas primarias) registradas en las estaciones sísmicas. Se utiliza principalmente para terremotos de menor magnitud y distancias moderadas a largas desde las estaciones sísmicas.

- **Mi:** Magnitud Imax (Imax Magnitude). Es una medida de la amplitud máxima del movimiento del suelo registrada en una estación sísmica específica.

- **mwc:** Cálculo de Magnitud de Momento (Moment Magnitude Calculation). Indica que la magnitud de momento ha sido calculada, pero no especifica si se basa en ondas superficiales o en el análisis de ondas corporales.

- **mw:** Magnitud de Momento (Moment Magnitude). Similar a 'mww', indica que la magnitud ha sido calculada mediante el análisis de ondas sísmicas y la cantidad total de energía liberada.

- **mwb:** Magnitud de Onda Corporal (Body Wave Magnitude). Similar a 'mb', indica que la magnitud ha sido calculada utilizando ondas corporales.

- **mwr:** Magnitud de Momento Regional (Regional Moment Magnitude). Similar a 'mww', pero utilizado específicamente para terremotos regionales.

- **ml:** Magnitud Local (Local Magnitude). Es una medida de la amplitud de las ondas sísmicas registradas en una estación cercana al epicentro del terremoto. También se conoce como "Magnitud de Richter".

- **ms_20:** Magnitud de Onda Superficial (Surface Wave Magnitude). Es una medida de la amplitud de las ondas superficiales registradas en las estaciones sísmicas.

- **mwp:** Magnitud de Onda P (P Wave Magnitude). Es una medida de la amplitud de las ondas P (ondas primarias) registradas en las estaciones sísmicas.

- **Ml:** Magnitud Local (Local Magnitude). Similar a 'ml', indica que la magnitud ha sido calculada a nivel local.

- **ms:** Magnitud de Onda Superficial (Surface Wave Magnitude). Similar a 'ms_20', indica que la magnitud ha sido calculada utilizando ondas superficiales.

- **md:** Magnitud de Duración (Duration Magnitude). Es una medida de la duración del terremoto y se utiliza para evaluar la energía total liberada.

- **mh:** Magnitud de Alta Frecuencia (High Frequency Magnitude). Indica que la magnitud se ha calculado utilizando datos de alta frecuencia.

- **uk:** Desconocido (Unknown). Indica que el tipo de escala de magnitud no se ha especificado o no se conoce.

- **fa:** Área Sentida (Felt Area). Indica que la información se refiere al área geográfica donde el terremoto fue sentido por las personas.

- **lg:** Magnitud Local (Local Magnitude). Es una medida de la amplitud de las ondas sísmicas registradas en una estación cercana al epicentro del terremoto. También se conoce como "Magnitud de Richter".

- **mint:** Magnitud Instrumental (Instrumental Magnitude). Es una medida de la amplitud del movimiento del suelo registrada por instrumentos sísmicos.

---

## **Bar Chart Race**

- **Magnitudes Acumuladas por País por Año**

![img](./video/bar_chart_race.gif)

[🔼](#temario)

---
