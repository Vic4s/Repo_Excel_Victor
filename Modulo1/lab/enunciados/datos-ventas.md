<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_naranja@4x.png?raw=true" alt="esquema" />
</div>



### Descripción del conjunto de datos:

Este conjunto de datos proporciona información detallada sobre las transacciones de ventas realizadas por una empresa, incluyendo detalles de los pedidos, productos, clientes y datos financieros como precios y beneficios. ALa descripción de las columnas la tienes a continuación:

1. **Row ID**: Un identificador único para cada fila o transacción registrada. Esta columna es útil para identificar transacciones específicas y evitar duplicados.
   
2. **Order ID**: Un identificador único para cada pedido realizado. Esta columna permite agrupar múltiples filas que forman parte de un mismo pedido.

3. **Order Date**: La fecha en que se realizó el pedido, almacenada en un formato numérico (número de serie de Excel). Es necesario convertirla a un formato de fecha legible.

4. **Ship Date**: La fecha en que se envió el pedido, también almacenada en formato numérico.

5. **Ship Mode**: El modo de envío utilizado para el pedido, como "Second Class", "Standard Class", etc. Esta columna es útil para analizar los costos y tiempos de envío.

6. **Customer ID**: Un identificador único para cada cliente. Permite agrupar las compras realizadas por el mismo cliente.

7. **Customer Name**: El nombre del cliente que realizó el pedido.

8. **Segment**: Segmento al que pertenece el cliente, como "Consumer", "Corporate", o "Home Office". Esta clasificación permite analizar las ventas por tipo de cliente.

9. **Country**: El país desde el que se realizó el pedido.

10. **City**: La ciudad desde la que se realizó el pedido. Algunas filas pueden tener valores faltantes en esta columna.

11. **State**: El estado o región del pedido, útil para realizar análisis de ventas regionales.

12. **Postal Code**: El código postal del lugar donde se realizó el pedido.

13. **Region**: Región geográfica a la que pertenece la transacción, como "East", "West", etc.

14. **Category**: La categoría a la que pertenece el producto vendido, como "Furniture", "Technology", o "Office Supplies".

15. **Sub-Category**: La subcategoría del producto, proporcionando un nivel adicional de detalle (por ejemplo, "Chairs", "Tables", etc.).

16. **Product Name**: El nombre completo del producto vendido.

17. **Sales**: El monto total de la venta para ese producto, basado en la cantidad vendida y el precio unitario.

18. **Quantity**: La cantidad de productos vendidos en la transacción.

19. **Discount**: El porcentaje de descuento aplicado a la venta.

20. **Discount value**: El valor monetario del descuento aplicado a la venta.

21. **Profit**: La ganancia generada por la venta, calculada como la diferencia entre el ingreso por ventas y el costo del producto.

22. **COGS**: El costo de los bienes vendidos, es decir, cuánto costó la producción o adquisición del producto vendido.

23. **Shipping time range**: El rango de tiempo de envío del producto en días.

24. **Year sales**: El año en que se realizó la venta.

---

### Ideas de generación de columnas para transformación de datos:

- **`formatted_order_date`**: Convertir la columna `Order Date` a un formato de fecha legible (DD/MM/AAAA). Esto permitirá realizar análisis de tendencias temporales sobre las ventas.

- **`formatted_ship_date`**: Convertir la columna `Ship Date` a un formato de fecha legible. Esto facilitará el análisis del tiempo de envío y permitirá evaluar la eficiencia logística.

- **`order_processing_time`**: Calcular la diferencia entre `Ship Date` y `Order Date` para medir el tiempo de procesamiento de cada pedido. Esta métrica es clave para entender la eficiencia operativa.

- **`total_discount`**: Multiplicar el porcentaje de descuento (`Discount`) por el valor de la venta (`Sales`) para obtener el valor total del descuento aplicado. Esto ayudará a analizar el impacto de los descuentos en las ventas y beneficios.

- **`total_profit_margin`**: Calcular el margen de beneficio como la relación entre `Profit` y `Sales`. Este indicador permitirá identificar qué transacciones o productos tienen los márgenes más altos.

- **`order_size_category`**: Clasificar los pedidos en categorías como "Pequeños", "Medios" y "Grandes" según la cantidad de productos vendidos (`Quantity`). Esto permitirá segmentar los análisis de ventas por tamaño de pedido.

- **`shipping_delay`**: Crear una columna que indique si el envío de un pedido se retrasó, comparando el tiempo de envío real (`Shipping time range`) con el tiempo estimado. Esto proporcionará información clave sobre la puntualidad en la entrega de pedidos.

---

### Ideas para el Dashboard:

El dashboard debe proporcionar una vista clara y concisa de los aspectos clave de las ventas y el desempeño de la empresa. Aquí hay algunas ideas para las visualizaciones que se pueden incluir en el dashboard:

1. **Tendencias de ventas por fecha**: Un gráfico de líneas que muestre las ventas totales (`Sales`) a lo largo del tiempo, basado en la columna `formatted_order_date`, será útil para identificar picos y caídas en las ventas. Este análisis permitirá detectar patrones estacionales o eventos que influyen en el comportamiento de compra.

2. **Distribución de ventas por categoría**: Un gráfico de barras o un gráfico de pastel que muestre la distribución de ventas por `Category` y `Sub-Category` proporcionará una visión clara de qué tipos de productos están generando la mayor parte de los ingresos. Esto ayudará a identificar las categorías más rentables y posibles áreas de crecimiento.

3. **Tiempo de procesamiento de pedidos**: Un gráfico de barras que visualice el tiempo promedio que toma procesar los pedidos (`order_processing_time`) para cada categoría o por región permitirá evaluar la eficiencia del proceso de cumplimiento de pedidos y detectar dónde se pueden realizar mejoras.

4. **Impacto de los descuentos en las ventas**: Un gráfico de dispersión que compare el valor de `total_discount` con las ventas totales (`Sales`) permitirá analizar el impacto de los descuentos en los ingresos. Esto ayudará a evaluar si las promociones están impulsando las ventas o reduciendo el margen de beneficio.

5. **Análisis de margen de beneficio**: Un gráfico de barras que muestre el margen de beneficio (`total_profit_margin`) por categoría de producto o por cliente será útil para identificar qué productos o segmentos de clientes están generando mayores ganancias.

6. **Ventas por región**: Un gráfico de mapa o de barras que muestre las ventas por `Region` permitirá visualizar la distribución geográfica de las ventas y detectar áreas de oportunidad. Esta visualización ayudará a comprender dónde la empresa está teniendo mayor éxito y dónde puede mejorar su presencia.

7. **Pedidos retrasados vs entregados a tiempo**: Un gráfico de barras o de pastel que compare los pedidos enviados a tiempo con los pedidos retrasados (`shipping_delay`) proporcionará información clave sobre la eficiencia en la entrega de productos y ayudará a identificar problemas logísticos.

