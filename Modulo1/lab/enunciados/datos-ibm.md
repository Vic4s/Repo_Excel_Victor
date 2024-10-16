<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_naranja@4x.png?raw=true" alt="esquema" />
</div>


### Descripción del conjunto de datos:

Este conjunto de datos proporciona información sobre los empleados de una empresa, incluyendo detalles demográficos, educación, rol, departamento, y otros factores relacionados con su desempeño laboral y satisfacción. A continuación, se ofrece una descripción detallada de cada columna del conjunto de datos:

1. **Attrition**: Indica si un empleado ha dejado la empresa (yes) o si continúa en ella (NO). Esta columna es esencial para los análisis de rotación de personal.
   
2. **Business Travel**: Muestra la frecuencia con la que el empleado viaja por trabajo, con categorías como "Travel_Rarely", "Travel_Frequently", y "Non-Travel".

3. **CF_age band**: Agrupa a los empleados en rangos de edad (por ejemplo, "35 - 44"). Esto es útil para analizar el comportamiento y las tendencias según la edad.

4. **CF_attrition label**: Una etiqueta que identifica si un empleado es un "Ex-Employees" o un "Current Employees". Esto permite un análisis más segmentado de los datos.

5. **Department**: Indica el departamento en el que trabaja el empleado, como "Sales", "R&D" o "HR". Es útil para analizar la rotación y el rendimiento por departamento.

6. **Education Field**: Campo de estudio del empleado, como "Life Sciences", "Medical", "Other", etc. Permite analizar la distribución de los empleados por áreas de formación.

7. **emp no**: Identificador del tipo de empleado, utilizado internamente en la organización.

8. **Employee Number**: Un número único asignado a cada empleado. Esta columna es útil para identificar empleados individualmente.

9. **Gender**: Género del empleado (FEMALE o male). Esto permite realizar análisis de rotación y otros indicadores en función del género.

10. **Job Role**: Especifica el rol del empleado dentro de la empresa, como "Research Scientist", "Sales Executive", "Laboratory Technician", etc.

11. **Marital Status**: Indica el estado civil del empleado (Single, Married, Divorced). Es útil para realizar análisis demográficos y su relación con la retención de empleados.

12. **Monthly Income**: Indica el salario mensual del empleado. Es una métrica importante para analizar la satisfacción laboral, la rotación, y la estructura salarial.

13. **Overtime**: Indica si el empleado realiza horas extras (Yes o No). Esto puede estar relacionado con otros factores como el desgaste o la satisfacción laboral.

14. **Performance Rating**: Calificación del desempeño del empleado en una escala de 1 a 4. Es clave para analizar la relación entre rendimiento y otros factores como la rotación.

15. **Relationship Satisfaction**: Una calificación que mide la satisfacción del empleado con las relaciones laborales dentro de la empresa.

16. **Stock Option Level**: Nivel de opciones de acciones que tiene el empleado. Esto puede estar relacionado con la satisfacción y retención.

17. **Total Working Years**: El total de años que el empleado ha trabajado en su carrera profesional.

18. **Work Life Balance**: Calificación del equilibrio entre el trabajo y la vida personal del empleado, en una escala de 1 a 4.

19. **Years At Company**: Los años que el empleado ha trabajado en la empresa actual. Esta columna es útil para analizar la lealtad y retención.

20. **Years In Current Role**: Indica cuántos años ha estado el empleado en su rol actual dentro de la empresa.

21. **Years Since Last Promotion**: Muestra los años que han pasado desde la última promoción del empleado.

22. **Years With Curr Manager**: Los años que el empleado ha trabajado con su gerente actual.

---

### Ideas de generación de columnas para transformación de datos:

Para mejorar el análisis y facilitar la visualización, se pueden generar nuevas columnas a partir de los datos existentes. Algunas ideas de transformación son las siguientes:


- Otra transformación interesante sería crear una columna llamada `Travel_Frequency_Level`, que asigne valores numéricos a las categorías de la columna `Business Travel` (por ejemplo, 0 para "Non-Travel", 1 para "Travel_Rarely" y 2 para "Travel_Frequently"). Esto permitirá realizar análisis numéricos más profundos sobre cómo la frecuencia de viajes afecta el rendimiento o la satisfacción laboral.

- Podemos también generar una columna llamada `Income_Band`, que clasifique a los empleados en rangos salariales (por ejemplo, "Bajo", "Medio", "Alto") basándose en la columna `Monthly Income`. Esta segmentación ayudará a identificar si existen patrones de rotación según el nivel de ingresos y a analizar cómo afecta el salario a la retención.

- Una nueva columna llamada `Promotion_Status` podría indicar si un empleado ha sido promovido recientemente (1 si `Years Since Last Promotion` es menor a 1 año, y 0 si no). Esta transformación permitirá un análisis más claro de los empleados que han recibido promociones y cómo esto afecta su satisfacción y rendimiento.

- Otra columna útil sería `Work_Tenure`, que calcule el total de años de experiencia en la empresa (`Years At Company` más `Years With Curr Manager`). Esto permitirá comparar la experiencia global de los empleados y su relación con el desempeño y la rotación.

- Una columna llamada `Job_Stability` podría calcular la relación entre los años en el rol actual (`Years In Current Role`) y los años en la empresa (`Years At Company`). Esto permitirá identificar empleados con una alta estabilidad en su puesto y analizar cómo este factor influye en su satisfacción y rendimiento.

Estas son algunas recomendaciones de columnas que puedes crear, pero recuerda que puedes crear todas las que necesites. 
---

### Ideas para el Dashboard:

El dashboard final debe presentar los insights más relevantes del análisis de datos, facilitando la toma de decisiones basadas en el rendimiento de los empleados y los patrones de rotación. A continuación se proponen algunas ideas clave para las visualizaciones:

1. **Rotación de personal a lo largo del tiempo**: Un gráfico de barras que muestre el porcentaje de empleados que han dejado la empresa cada año (`Attrition_Flag`) permitirá visualizar la evolución de la rotación a lo largo del tiempo y detectar tendencias preocupantes o mejoras en la retención.

2. **Distribución por departamentos**: Un gráfico de barras que muestre la cantidad de empleados por departamento (`Department`) será útil para identificar qué áreas de la empresa tienen mayor número de empleados y si existen departamentos con tasas de rotación más altas que otros.

3. **Análisis de ingresos mensuales por género**: Un gráfico de cajas que compare los ingresos mensuales (`Monthly Income`) entre hombres y mujeres permitirá visualizar cualquier disparidad salarial y analizar la relación entre el salario y la rotación en función del género.

4. **Relación entre horas extra y rendimiento**: Un gráfico de dispersión que muestre la relación entre los empleados que hacen horas extra (`Overtime`) y su calificación de rendimiento (`Performance Rating`) ayudará a detectar si existe una correlación entre el tiempo extra trabajado y el rendimiento.

5. **Promociones y satisfacción laboral**: Un gráfico de barras que compare la satisfacción con el equilibrio entre la vida y el trabajo (`Work Life Balance`) de empleados promovidos (`Promotion_Status`) y no promovidos mostrará si las promociones recientes están mejorando la satisfacción laboral.

6. **Análisis de estabilidad en el rol**: Un gráfico de líneas que muestre la relación entre los años en el rol actual (`Years In Current Role`) y el rendimiento (`Performance Rating`) proporcionará insights sobre cómo la estabilidad en el puesto influye en el desempeño laboral.

7. **Comparativa de rotación por nivel de educación**: Un gráfico de barras que muestre la tasa de rotación (`Attrition_Flag`) por campo de educación (`Education Field`) permitirá identificar si ciertos niveles de educación están más asociados a la retención o rotación de empleados.

