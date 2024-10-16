
<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_naranja@4x.png?raw=true" alt="esquema" />
</div>


### **Descripción del conjunto de datos:**

Este conjunto de datos registra información sobre las transacciones realizadas en una cadena de cafeterías. Cada fila representa una transacción individual, con detalles como la fecha y hora de la compra, la cantidad de productos adquiridos, la ubicación de la tienda, el tipo de producto, y más. Las columnas de este conjunto de datos son:

1. **transaction_id**: Un identificador único que asigna un número a cada transacción realizada. Es útil para identificar y rastrear transacciones específicas.
   
2. **transaction_date**: Representa la fecha en que se realizó la transacción, almacenada como un número de serie de Excel (por ejemplo, 44927). Esta columna deberá ser convertida a un formato de fecha legible para facilitar su análisis.

3. **transaction_time**: Muestra el tiempo de la transacción como una fracción decimal del día. Este valor deberá transformarse a un formato legible de horas (por ejemplo, "10:45 AM").

4. **transaction_qty**: Indica la cantidad de productos comprados en una transacción específica. Es útil para calcular métricas como el total de productos vendidos o el tamaño promedio de un pedido.

5. **store_id**: Un número de identificación único para cada tienda donde se realiza la transacción. Permite analizar los datos de ventas por ubicación específica.

6. **store_location**: Proporciona información sobre la ubicación geográfica de la tienda (por ejemplo, "Lower Manhattan"). Esta columna es útil para segmentar las ventas por región o ciudad.

7. **product_id**: Un identificador único para cada producto en el catálogo. Esto permite rastrear las ventas por productos específicos.

8. **unit_price**: Indica el precio unitario de los productos en la transacción. Esta columna es fundamental para calcular el ingreso total por cada transacción.

9. **product_category**: Agrupa los productos en categorías generales (por ejemplo, "COFFEE", "tea", "Drinking Chocolate"). Permite realizar análisis de ventas por categoría de producto.

10. **product_type**: Proporciona más detalles sobre el tipo de producto, como "Gourmet brewed coffee" o "Brewed Chai tea". Esta columna es útil para segmentar las ventas por tipos de productos más específicos dentro de una categoría.

11. **product_detail**: Ofrece información adicional sobre el producto (por ejemplo, "Ethiopia Rg", "Dark chocolate Lg"). Esta columna puede ser usada para realizar análisis de preferencias de los clientes sobre productos específicos.

---

### Ideas de generación de columnas para transformación de datos:

A lo largo de este ejercicio, será necesario generar nuevas columnas que ayuden a mejorar el análisis y la visualización de los datos. Algunas ideas para crear nuevas columnas y realizar transformaciones en los datos:

- Realizar una conversión de la columna `transaction_date` para crear una nueva columna llamada `formatted_transaction_date`, donde el valor numérico de la fecha se convierta a un formato de fecha legible (DD/MM/AAAA).

- Transformar la columna `transaction_time` en una nueva columna llamada `formatted_transaction_time`, donde se convierta el valor decimal de la hora a un formato más comprensible (HH:MM:SS). Esta conversión ayudará a visualizar y analizar las ventas en diferentes horas del día, permitiendo identificar periodos de mayor actividad.

- Una columna importante para calcular es `total_revenue`, que representa el ingreso total generado por cada transacción. Esta columna se obtiene multiplicando la cantidad de productos comprados (`transaction_qty`) por el precio unitario (`unit_price`). Esta métrica es esencial para calcular los ingresos generados por cada transacción y para entender el comportamiento de compra de los clientes.

- Una idea interesante es crear una columna llamada `price_range`, donde se clasifiquen los productos en rangos de precio (por ejemplo, "Bajo", "Medio" y "Alto") en función de `unit_price`. Esta clasificación ayudará a entender mejor cómo se distribuyen las ventas entre productos de diferentes precios, permitiendo realizar un análisis del comportamiento del consumidor en términos de gasto.

- Crear una columna llamada `day_time`, que clasifique las transacciones en franjas horarias como "Mañana", "Tarde" y "Noche", basándose en la hora de la transacción (`formatted_transaction_time`). Esto permitirá realizar análisis sobre cuándo ocurren más ventas a lo largo del día y ajustar estrategias de operación o marketing en consecuencia.

- También se pueden extraer los componentes de fecha como el año y el mes de la columna `formatted_transaction_date` para generar dos nuevas columnas, `transaction_year` y `transaction_month`. Estas columnas facilitarán el análisis agregado de ventas por períodos, permitiendo estudiar el comportamiento de las ventas en diferentes meses o años.

- Para entender mejor qué productos se están vendiendo en cada transacción, se puede crear una columna llamada `products_sold_category`, que cuente el número total de productos vendidos en cada transacción, agrupados por la categoría del producto (`product_category`). Esta nueva columna puede ser clave para identificar qué categorías son más populares en cada tienda.

- Otra columna útil sería `average_transaction_size`, que calcule el tamaño promedio de las transacciones, es decir, la cantidad de productos vendidos por transacción. Esta métrica es crucial para entender el comportamiento de compra y ajustar las estrategias de venta para aumentar el tamaño promedio de los pedidos.

- Finalmente, una columna o KPI importante es `store_total_revenue`, que representa los ingresos totales generados por cada tienda. Esto ayudará a comparar el rendimiento entre las diferentes ubicaciones y a identificar oportunidades para mejorar el desempeño en tiendas con menores ventas.

Estos son solo algunos ejemplos, pero puedes crear todas las columnas que consideres. 
---

### Ideas para el Dashboard:

El dashboard final debe presentar una vista clara y concisa de los *insights* más importantes obtenidos del análisis de datos. Algunas ideas clave para las visualizaciones son:

1. **Tendencia de ventas a lo largo del tiempo**: Un gráfico de líneas que muestre cómo evolucionan las ventas totales (`total_revenue`) a lo largo del tiempo, ya sea diario, semanal, o mensual, puede ofrecer una perspectiva clara sobre patrones de crecimiento o estacionalidad. Este tipo de visualización permite identificar en qué periodos las ventas aumentan o disminuyen, y se pueden correlacionar con eventos o temporadas del año para tomar decisiones estratégicas.

2. **Ventas por ubicación**: Un gráfico de barras o un mapa de calor que visualice los ingresos totales generados por cada tienda (`store_total_revenue`) es fundamental para entender el rendimiento geográfico. Esta representación gráfica ayudará a identificar qué tiendas están teniendo un mejor desempeño, permitiendo comparar el éxito relativo entre ubicaciones, así como identificar áreas donde podría haber oportunidades de mejora.

3. **Distribución de ventas por categoría de producto**: Un gráfico de pastel o de barras que muestre la proporción de ventas de cada categoría de producto (`product_category`) será útil para determinar qué categorías generan más ingresos. Este análisis ayudará a priorizar el inventario y las campañas de marketing, al entender cuáles son las categorías de productos más populares entre los clientes.

4. **Ventas por hora del día**: Un gráfico de barras que muestre los ingresos generados en diferentes momentos del día, divididos en franjas horarias como "Mañana", "Tarde" y "Noche", permitirá identificar los periodos de mayor actividad. Con esta información, se pueden ajustar las operaciones, como la asignación de personal, o realizar promociones dirigidas a incrementar las ventas en horas más tranquilas.

5. **Ranking de productos más vendidos**: Un gráfico de barras verticales que muestre los productos más vendidos, ya sea por cantidad (`transaction_qty`) o por ingresos (`total_revenue`), será clave para visualizar qué productos son los más populares y cuáles están generando más valor. Este ranking permitirá a los administradores enfocarse en productos de alta demanda o crear estrategias para mejorar las ventas de productos menos vendidos.

6. **Promedio de ticket por transacción**: Un KPI que muestre el valor promedio de cada transacción (`total_revenue` dividido entre el número de transacciones) será útil para evaluar la eficiencia en las ventas. Este indicador permitirá identificar el ticket promedio de los clientes, ofreciendo una métrica clara para estrategias de venta que busquen aumentarlo, ya sea mediante promociones, upselling o cross-selling.

7. **Análisis de márgenes de beneficio**: Si el conjunto de datos incluye información sobre los costos de los productos, un gráfico de barras o un indicador que muestre los márgenes de beneficio por tienda o por categoría de producto puede ser muy valioso. Este análisis permitirá a los gestores optimizar los márgenes y mejorar la rentabilidad general del negocio, identificando productos o categorías con alto rendimiento o aquellas que podrían requerir ajustes en precios o costos.
