## Ejercicio 1
Atributos a analizar del dataset Obesity
- Gender  CN
- Age     CD
- Height  CC
- Weight  CC
- Family_history_with_overweight CO
- FAVC  CO
- FCVC  CC
- NCP   CD
- CAEC  CN
- SMOKE CO
- CH2O  CC
- SCC   CO
- FAF   CC
- TUE   CC
- CALC  CN
- MTRANS CN
- NObesity(target)

Tipo de atributo         | Cantidad
------------------------ | --------
cuantitativo discreto CD |    2
cuantitativo continuo CC |    6
cualitativo nominal   CN |    4
cualitativo ordinal   CO |    4

## Ejercicio 2
#### Proponga una tarea de clasificación y una tarea de regresión que puedan realizarse a partir de los datos del dataset de obesidad.
En este ejercicio lo que se busca es elegir el tipo de variable objetivo.
- Clasificación → La salida del modelo es una variable cualitativa
- Regresión → La salida del modelo es una variable cuantitativa

Una tarea de Clasificación puede ser clasificar a las personas segun su nivel de obesidad (alto, medio, bajo) a partir de los distintos atributos que tenemos.
Una tarea de Regresión puede ser predecir el indice de masa corporal (IMC) o el peso exacto de una persona a partir de los distintos atributos que tenemos.  

## Ejercicio 3
#### Indique qué tipo de información brindan las siguientes representaciones gráficas: 
- **a. Diagrama de Barras**  
  - <u>Funcionamiento:</u>
    - Cada categoría (variable cualitativa) se representa con una barra.
    - La altura o longitud de la barra indica la frecuencia absoluta, relativa o un valor agregado (ejemplo: promedio de ingresos por categoría).
  - <u>Características clave:</u>
    - El eje X (horizontal) suele mostrar las categorías.
    - El eje Y (vertical) muestra la magnitud o frecuencia.
  - <u>Cuándo usarlo:</u> Para comparar fácilmente grupos o categorías.
    - Ejemplo: comparar la cantidad de hombres y mujeres en un estudio de obesidad.

- **b. Histograma** 
  - <u>Funcionamiento:</u>
    - Divide el rango de valores de una variable numérica en intervalos o "bins".
    - Cada barra representa la cantidad de observaciones que caen dentro de ese intervalo.
  - <u>Características clave:</u>
    - Se parece a un diagrama de barras, pero aquí los datos son continuos.
    - No hay espacios entre las barras porque representan un rango de valores contiguos.
    - Permite ver la forma de la distribución (simétrica, sesgada, uniforme, con colas largas).
  - <u>Cuándo usarlo:</u> Para analizar la distribución de una variable cuantitativa.
    - Ejemplo: distribución de IMC en una población.

- **c. Diagrama de caja**  
  - <u>Funcionamiento:</u>
    - Resume los datos numéricos mostrando sus cuartiles:
      - Caja → va del Q1 (25%) al Q3 (75%).
      - Línea dentro de la caja → mediana (Q2, 50%).
      - "Bigotes" → valores mínimo y máximo sin ser atípicos.
      - Puntos fuera de los bigotes → outliers (valores atípicos).
  - <u>Características clave:</u>
    - Excelente para comparar la variabilidad de varios grupos.
    - Ayuda a detectar asimetría y outliers rápidamente.
  - <u>Cuándo usarlo:</u> Para ver la dispersión y los valores extremos en una variable.
    - Ejemplo: comparar la distribución de pesos entre hombres y mujeres.

- **d. Diagrama de dispersión** 
  - <u>Funcionamiento:</u>
    - Cada observación se representa como un punto en un plano cartesiano, donde el eje X es una variable y el eje Y otra.
  - <u>Características clave:</u>
    - Muestra tendencias lineales o no lineales.
    - Permite detectar correlación: positiva (suben juntas), negativa (una sube y la otra baja), o ausencia de relación.
    - También revela agrupamientos (clusters) o valores atípicos.
  - <u>Cuándo usarlo:</u> Para estudiar la relación entre dos variables cuantitativas.
    - Ejemplo: ver cómo varía el peso en función de la altura.

Luego, genere al menos un ejemplo de cada representación usando el dataset de obesidad y explique cómo interpretar cada uno. 

## Ejercicio 4
#### Complete el siguiente cuadro y dibuje el diagrama de caja del atributo “weight” 
Medida                                    | Valor
----------------------------------------- | -------- 
Mínimo                                    |   39
Máximo                                    |   173
Q1                                        |   65.47
Q2 o mediana                              |   83
Q3                                        |   107.43
RIC                                       |   41.96
Bigote superior                           |   170.37
Bigote inferior                           |   2.54
Intervalos de valores atípicos leves      |  [-60.40 ; 2.54) o (170.37 ; 233.30] 
Valores atípicos leves                    |  173 
Intervalos de valores atípicos extremos   |  weight < -60.40 ó weight > 233.30
Valores atípicos extremos                 |   no existen


## Ejercicio 5
#### Los valores del atributo peso (“weight”) fueron agrupados según el atributo de antecedente de obesidad familiar (“family_history_with_overweight”). La figura muestra los diagramas de caja correspondientes. 
![ejercicio5](ejercicio-5.png)
Complete el siguiente cuadro y responda verdadero o falso justificando cada afirmación según los valores obtenidos:

Medida              |   yes   |   no   |
------------------- | ------- | ------ | 
Mínimo              |   ~40   |  ~40   |
Máximo              |   ~175  |  ~115  |
Q1                  |   ~78   |  ~49   |
Q2                  |   ~90   |  ~56   |
Q3                  |  ~115   |  ~57   |
RIC                 |  Q3-Q1  |  Q3-Q1 |
Bigote Inferior     |   40    |   40   |
Bigote Superior     |  ~165   |  ~100  |
 
- a. Al menos el 25% de las personas con antecedentes familiares de obesidad pesan más de 100 kg.
  - VERDADERO, acá vemos que Q3 ~115 y de esto podemos deducir que el ultimo cuartil corresponde completamente a personas que pesan más de 100kg
- b. Es atípico que una persona sin antecedentes familiares de obesidad (no) pese más de 115 kg.
  - VERDADERO, acá vemos que el máximo se da por un valor atípico de ~115
- c. La mediana del peso de las personas sin antecedentes familiares (no) es menor que 60 kg. 
  - VERDADERO, la mediana (Q2) de peso de las personas sin antecedentes familiares es menor a 60kg (~56)
- d. Todos los valores atípicos para personas con antecedentes familiares de obesidad son leves.
  - VERDADERO, para esto verificamos en este caso con la fórmula para encontrar valores atípicos extremos, (Q3+3*RIC) = 115+3*37 = 226, y como el valor máximo es 173 no se considera un valor atípico extremo  
  ![ejercicio5d](ejercicio5.d.png)



## Ejercicio 6 
#### Discretice el atributo del consumo de agua diario en litros (“CH2O”) en tres intervalos: Bajo, Medio y Alto. Indique en la tabla los intervalos utilizados y la cantidad respectivas de ejemplos de cada uno al discretizar por rango y por intervalo. Luego, explique porque los ejemplos no quedaron divididos en intervalos con la misma cantidad de valores. 

##### Discretizacion por rango
Divide los datos en intervalos que contienen aproximadamente la misma cantidad de observaciones (basado en cuantiles). Ideal cuando los datos no están distribuidos uniformemente  
CH20          |  frecuencia |	valor
------------- |	----------- | ------	
(0.999, 1.92]	| 704         |	Bajo
(1.92, 2.185]	| 703	        | Medio
(2.185, 3.0]	| 704	        | Alto

##### Discretizacion por intervalo
Divide los datos en intervalos de igual tamaño (ancho constante), basándose en el valor mínimo y máximo de la variable. Se puede especificar el número de intervalos con `bins=n`  
CH2O           | frecuencia |	valor
-------------- | ---------- | ------
(0.998, 1.667] |	576       |	Bajo
(1.667, 2.333] |	910	      | Medio
(2.333, 3.0]   |	625       |	Alto

- Con rango (quantiles) → se equilibran las cantidades de ejemplos en cada intervalo.
- Con intervalo (ancho fijo) → los cortes son uniformes en valores, pero como la distribución de datos no es uniforme, las frecuencias de ejemplos en cada intervalo quedan desiguales.



## Ejercicio 7
#### Realice las siguientes tareas para preparar el dataset para que pueda ser utilizado para entrenar modelos de redes neuronales. 
- a) Visualice las primeras 5 filas y el resumen estadístico. 
- b) Identifique los atributos (columnas) con valores nulos y su porcentaje. 
- c) Analizar los valores faltantes y discutir cuales serían las alternativas posibles para tratarlos. 
- d) Los nombres de los pasajeros van acompañados de títulos que pueden ser importantes para la interpretación de los datos o para completar información faltante: 
  - i. Extrae el título (como Mr, Miss, Mrs, Master, etc.) del nombre de cada pasajero y crea una nueva columna llamada Title. 
  - ii. Unifica los valores para que queden Mr, Miss (Mlle, Ms), Mrs (Mme), Master, Others (resto). 
  - iii. Computa las edades faltantes utilizando la edad promedio por categoría. 
- e) Complete los valores faltantes utilizando las estrategias planteadas en los puntos anteriores. 
- f) Cree un nuevo atributo FamilySize que contabiliza los integrantes de familia a partir de los atributos SibSp (hermanos y esposo) y Parch (padres e hijos). No olvidar contar a la persona. 
- g) Numerice los atributos categóricos: Sex, Embarked, y Title. 
- h) Discuta y responda ¿Por qué one-hot encoding podría ser preferible a label encoding para el atributo Pclass? 
- i) Visualiza distribuciones: Histograma de Age, gráfico de barras para Survived por Sex y Pclass.

Como la práctica la dan echa y cualquier cosa se puede ver la documentacion de pandas que esta buena considero importante responder el punto h

En el caso de Pclass, sería mejor "one-hot encoding" en lugar de "label encoding" ya que la relacion entre las clases a las que pertenecian las personas que abordaron el titanic no necesariamente tienen una relacion lineal.  
Si nosotros dejamos las clases como estan (1, 2, 3) se puede interpretar que la relacion entre 1ra y 2da clase es la misma que entre 2da y 3ra, lo cual no es cierto ya que habia mucha mas probabilidad en 1ra y 2da clase que en 3ra.  
Por esto es que al hacer "one-hot encoding" dejamos tablas binarias, en este caso cada pasjero tendra un atributo "Pclass1", "Pclass2" y "Pclass3" donde se va a dejar constancia con un "1" la clase a la que pertenecio realmente y un "0" en las otras 2.  
Si dejaramos el "label encoding" habría una relacion matematica artificial segun el amigo gpt  


## Ejercicio 8
#### Calcule la correlación lineal entre los atributos “Fare” (Tarifa) y “PClass” (clase del ticket). Indique la intensidad de la correlación (no hay correlación/débil/fuerte) y el tipo (positiva/negativa). Explique el significado del valor de correlación obtenido. 
La correlacion entre los atributo `Fare` y `Pclass` es de `-0.55` entonces la consideramos moderada, como es < 0 podemos también interpretar  que es negativa, por lo tanto cuando una sube, la otra baja.

**El valor que puede tomar la corelacion es un número entre -1 y 1:**
- +1 → correlación perfecta positiva (si una sube, la otra sube).
- 0 → sin correlación lineal.
- -1 → correlación perfecta negativa (si una sube, la otra baja).

**Guía práctica de intensidad (puede variar según autores):**
- 0.00 – 0.19 → Correlación muy débil / despreciable.
- 0.20 – 0.39 → Débil.
- 0.40 – 0.59 → Moderada.
- 0.60 – 0.79 → Fuerte.
- 0.80 – 1.00 → Muy fuerte.


## Ejercicio 9
#### Realice un análisis sobre los valores de los atributos del dataset  automobile.csv. Para cada atributo que no pueda ser procesado directamente, indique que problema tiene (valores nulos o vacíos, valores categóricos, valores atípicos o outliers, etc.) y como solucionarlo.


## Ejercicio 10
#### Dada la siguiente tabla con mediciones de 2 características correspondientes a mediciones de altura y peso de personas: 

|                | 1     | 2     | 3     | 4     | 5     | 6     | 7     | 8     | 9     |
|----------------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| **Altura (m)** | 1.65  | 1.81  | 1.70  | 1.62  | 1.74  | 1.70  | 1.80  | 1.73  | 1.68  |
| **Peso (kg)**  | 75    | 86    | 82    | 78    | 77    | 87    | 90    | 83    | 80    |

 
- a) Aplique las siguientes normalizaciones y grafíquelas con un diagrama de caja: 
  - MinMax:   𝑥𝑖−𝑚𝑖𝑛(𝑥) / 𝑚𝑎𝑥(𝑥)−𝑚𝑖𝑛(𝑥) 
  - Standard: 𝑥𝑖−𝑚𝑒𝑑𝑖𝑎(𝑥) / 𝑠𝑡𝑑𝑑𝑒𝑣(𝑥)  
  - Robust:  𝑥𝑖−𝑄1(𝑥) / 𝑄3(𝑥)−𝑄1(𝑥) 
- b) Agregue la siguiente medición (2.20, 120) y repita el punto a
- c) Compare los diagramas de caja entre las normalizaciones de los puntos a y b y comente las diferencias. 


```python
plt.figure(figsize=(12, 4))
sns.boxplot(data=df, x='Title', y='Age')
plt.title('Distribución de edad por título (después de imputar)')
plt.ylabel('Edad')
plt.xlabel('Título')
plt.show()
```  