# RegresionCuantilica

**Aplicación de regresión cuantílica con aplicación regularización con  Elastic Net**

<br>

**Objetivo**
Demostrar la aplicación de una regresión cuantílica con regulación usando Elastic Net


**Alumno: Marcelo Silva Ibarra**

<br>
<br>

**1.- Carga de datos y análisis exploratorio**

Los dataset usados fueron:

- California Housing: con 9 atributos y 20640 registros, Este dataset contiene datos sobre el valor mediano de las casas en California, recopilados durante el censo de 1990

- Adult Income: Es un dataset clásico para problemas de clasificación. La tarea principal es predecir si el ingreso anual de una persona supera los $50,000, posee 15 atributos, incluyendo la variable objetivo y 45222 registros

- Macroeconomic Dataset:  dataset de valores de indicadores económicos trimestrales de USA, desde 1959 a 2009, con 5 atributos, y 203 registros, sin embargo, solo se trabajó con los atributos realgdp ( Producto Interno Bruto (PIB) real), realcons (Gasto de consumo personal real) y realinv (Inversión interna privada bruta real)

Los datos fueron explorados para identificar el comportamiento de los atributos y valores atípicos, como es posible de apreciar los resultados de ejecución del código.

<br><br>

**2.- Aplicación de Elastic Net**

Se aplicó Elastic Net a los tres Dataset todos con los siguientes parámetros

-	Separación del conjunto de entrenamiento el 80%, y 20% para test
-	Alpha = 0.1, con bajo aporte a la regularización al modelo
-	L1_ratio = 0.5, equilibrio entre L1 y L2. (Lasso y Ridge)

<br><br>

Las variables por predecir por dataset fueron las siguiente:
- California Housing: MedHouseVal (valor medio de una casa)
- Adult Income: fnlwgt (es un número que indica cuántas personas en el censo nacional representa esa fila)
- Macro Data: realgdp (PIB real)

<br>

Los datos obtenidos de ejecución del algoritmo fueron

| Dataset            | R²     | RMSE        |
|--------------------|--------|-------------|
| California Housing | 0.5148 | 0.7974      |
| Adult Income       | 0.0541 | 102499.4969 |
| Macroeconomic Dataset| 0.9927 | 263.7982    |

<br>

Los mejores resultados fueron para los datos de macroeconomía, este resultado era esperable dada la naturaleza de los datos, el Macroeconomic Dataset corresponde a una serie de tiempo donde las variables tienen una alta correlación, eso explica que el RMSE es bajo en comparación con su media

<br>

**3.- Regresión Cuantílica**

Se aplicó Regresión Cuantílica a los dataset con los cuantiles de interés al 10%, 50%, y 90% (valores bajos, medio y alto)

<br>

Los resultados fueron los siguientes:

<br>

| Dataset            | 10%        | 50%        | 90%        |
|--------------------|------------|------------|------------|
| California Housing | 0.1418     | 0.3143     | 0.2095     |
| Adult Income       | 14861.8896 | 38652.0923 | 21769.9180 |
| Macroeconomic Data | 20.0170    | 60.3085    | 27.3174    |








