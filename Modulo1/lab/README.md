<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_naranja@4x.png?raw=true" alt="esquema" />
</div>


# Ejercicio Integral: Análisis Exploratorio de Datos, Limpieza, Transformación y Creación de un Dashboard

**Objetivo del ejercicio:**  

El objetivo de este proyecto apliques los conocimientos adquiridos sobre análisis de datos para realizar un proceso completo que incluya el análisis exploratorio, la limpieza, transformación de los datos, la creación de nuevas columnas y la presentación de resultados mediante un dashboard interactivo. Este ejercicio te permitirá enfrentarte a un caso realista donde deberás resolver problemas de calidad de datos y obtener información valiosa para la toma de decisiones.

**Elección del conjunto de datos:**

Para realizar este ejercicio, pueden elegir cualquiera de los cuatro conjuntos de datos que os hemos proporcionado:

1. Datos de ventas de un café. 

2.	Datos de recursos humanos.

3.	Datos de ventas.

4.	Datos de ventas en supermercados.

Cada uno de estos conjuntos de datos contiene diferentes tipos de información (ventas, productos, empleados, etc.), por lo que puedes elegir el que consideres más adecuado o interesante para trabajar en este ejercicio. La descripción de cada uno de estos conjuntos de datos la tenéis en los archivos que tenemos aparte. 


### Nota importante:  

Este proyecto se desarrollará de manera progresiva a lo largo de las próximas semanas. A medida que avancemos con los conceptos clave en las clases, se espera que vayas aplicando esos conocimientos para completar cada uno de los pasos descritos a continuación. No es necesario tener todo listo de inmediato; irás resolviendo cada fase en función de los temas que vayamos cubriendo.

### Instrucciones detalladas del laboratorio:

#### 1. **Análisis Exploratorio de Datos (EDA):**  

   - **Carga del conjunto de datos:** Carga el archivo de datos proporcionado y realiza una primera exploración.

   - **Estadísticas descriptivas:** Calcula las estadísticas básicas para todas las columnas.

   - **Visualizaciones iniciales:** Utiliza gráficos para explorar la distribución de los datos:

     - Histogramas para analizar la distribución de variables numéricas (como precios o cantidades).

     - Gráficos de barras para entender la distribución de categorías (como productos, clientes, métodos de pago).

     - Gráficos de dispersión para detectar correlaciones entre variables numéricas.

   - **Detección de valores atípicos (*outliers*):** Detecta valores que se salgan del rango esperado en las variables numéricas y marquen estos posibles *outliers*.

#### 2. **Limpieza de Datos:**  

   - **Identificación y tratamiento de valores nulos:** Revisa las columnas donde haya valores faltantes. Decide si es más adecuado eliminar esos registros o imputar los valores (por ejemplo, usando la media o la mediana).

   - **Detección y eliminación de duplicados:** Aseguráte de que no existan filas repetidas en el conjunto de datos. Si encuentra duplicados, debes decidir como gestionarlos y explicar el motivo de tu decisión. 

   - **Estandarización de formatos:** Revisa que las columnas que contienen texto sigan un formato consistente (por ejemplo, asegurar que todos los nombres de productos o categorías estén en mayúsculas o minúsculas, según el caso).

   - **Corrección de tipos de datos:** Verifica que cada columna tenga el tipo de dato correcto (fechas como fechas, números como enteros o decimales, texto como cadenas).

#### 3. **Transformación de Datos:**  

   - **Creación de nuevas columnas:** Basándose en los datos existentes, genera nuevas columnas que puedan ser útiles para el análisis. Algunos ejemplos incluyen:

     - Crear una columna de “Año de Venta” o “Mes de Venta” a partir de una columna de fecha.

     - Crear una columna que clasifique los productos o servicios en categorías como "Alta demanda", "Media demanda" o "Baja demanda" dependiendo de la cantidad vendida.

     - Crear una columna de "Rango de Precios" (Ej. bajo, medio, alto) si la columna de precio lo permite.

   - **Conversión de unidades:** Si es aplicable, convierte las unidades de medida de acuerdo a la necesidad del análisis (por ejemplo, convertir precios de una moneda a otra, o cantidades de una unidad de medida a otra).

#### 4. **Creación de un Dashboard:**

   - **Herramienta de visualización:** Utliza Excel para diseñar un dashboard que resuma los *insights* más relevantes del análisis.

   - **Algunas ideas de visualizaciones:**

     - Un gráfico de líneas o área para mostrar las tendencias temporales (ventas, ingresos, compras, etc.) si el conjunto de datos lo permite.

     - Un gráfico de barras o pastel que muestre la distribución de las principales categorías (productos, clientes, métodos de pago, etc.).

     - Una tabla resumen que contenga las estadísticas clave de los datos, como el total de ventas, número de transacciones o valor promedio por cliente.

     - Un gráfico de dispersión o correlación para mostrar las relaciones entre las variables numéricas más importantes.

   - **Interactividad:** Agrega filtros en el dashboard para que se puedan visualizar los resultados por segmentos, periodos de tiempo, o categorías de productos.

#### 5. **Conclusiones del Análisis:**

   - Al final del ejercicio, deberás entregar un resumen escrito (en markdown) donde expliques los principales hallazgos del análisis. Este resumen deberá incluir:

     - Las tendencias observadas en los datos.

     - Las correlaciones más relevantes.

     - Un análisis de las categorías con mejor y peor desempeño (si es aplicable).

     - Recomendaciones basadas en los resultados obtenidos.

