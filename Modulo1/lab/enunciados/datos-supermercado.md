<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_naranja@4x.png?raw=true" alt="esquema" />
</div>

### Descripción del conjunto de datos:

Este conjunto de datos contiene información sobre las ventas realizadas en un supermercado, con detalles sobre las fechas, tipos de ventas, métodos de pago, productos vendidos y sus respectivos precios, entre otros. A continuación, se describen cada una de las columnas en detalle:

1. **DATE**: La fecha de la transacción, almacenada en formato numérico (número de serie de Excel). Esta columna debe convertirse a un formato de fecha legible para su análisis.

2. **PRODUCT ID**: Un identificador único para cada producto vendido. Permite rastrear las ventas por producto.

3. **QUANTITY**: La cantidad de unidades vendidas del producto en cada transacción. Es útil para calcular el volumen de ventas y analizar la demanda.

4. **SALE TYPE**: Tipo de venta, que puede ser "WHOLESALER" (mayorista) o "DIRECT SALES" (venta directa). Esta columna permite analizar el tipo de transacción realizada.

5. **PAYMENT MODE**: El método de pago utilizado por el cliente, como "ONLINE" o "cash". Es útil para analizar las preferencias de pago de los clientes.

6. **DISCOUNT %**: El porcentaje de descuento aplicado a la venta. Es útil para analizar el impacto de los descuentos en las ventas y en la rentabilidad.

7. **PRODUCT**: El nombre del producto vendido.

8. **CATEGORY**: La categoría a la que pertenece el producto (como "Category03" o "Category05"). Es útil para realizar análisis de ventas por categorías.

9. **UOM (Unidad de Medida)**: La unidad de medida del producto, como "Ft" (pies), "Kg" (kilogramos), "Lt" (litros), etc.

10. **BUYING PRIZE**: El costo de compra del producto, es decir, cuánto pagó el supermercado por adquirir el producto.

11. **SELLING PRICE**: El precio al que se vendió el producto al cliente.

12. **Total Buying Value**: El valor total del costo de compra, calculado como `BUYING PRIZE` multiplicado por `QUANTITY`.

13. **Total Selling Value**: El valor total de la venta, calculado como `SELLING PRICE` multiplicado por `QUANTITY`.

14. **Day**: El día en que se realizó la transacción.

15. **Month**: El mes en que se realizó la transacción.

16. **Year**: El año en que se realizó la transacción.

---

### Ideas de generación de columnas para transformación de datos:

- **`formatted_date`**: Convertir la columna `DATE` a un formato de fecha legible (DD/MM/AAAA). Esto permitirá realizar análisis temporales y estudiar las tendencias de ventas a lo largo del tiempo.

- **`total_discount_value`**: Crear una columna que calcule el valor total del descuento aplicado a la venta. Esto se puede obtener multiplicando `DISCOUNT %` por `Total Selling Value`. Esta métrica ayudará a entender el impacto de los descuentos en los ingresos.

- **`profit_per_product`**: Calcular el beneficio por producto como la diferencia entre `SELLING PRICE` y `BUYING PRIZE`. Esto permitirá medir la rentabilidad de cada producto.

- **`total_profit`**: Crear una columna que calcule el beneficio total por transacción, multiplicando `profit_per_product` por `QUANTITY`. Esta métrica es clave para analizar las ganancias generadas por cada transacción.

- **`profit_margin`**: Calcular el margen de beneficio como la relación entre `total_profit` y `Total Selling Value`. Esto ayudará a identificar productos y transacciones con los márgenes más altos.

- **`sales_category`**: Crear una columna que clasifique las transacciones en categorías de ventas, como "Pequeña", "Mediana" o "Grande", según el valor de `Total Selling Value`. Esto facilitará el análisis de ventas por tamaño de transacción.

- **`payment_type_indicator`**: Crear una columna binaria que indique si el pago fue realizado en efectivo (`PAYMENT MODE` = "cash") o no. Esto ayudará a comparar las ventas por métodos de pago.

- **`month_year`**: Crear una columna que combine el mes y el año (`Month` y `Year`), facilitando el análisis de ventas mensuales.

---

### Ideas para el Dashboard:

El dashboard debe proporcionar una visión clara de los resultados de las ventas, los márgenes de beneficio y otros indicadores clave de rendimiento. Aquí algunas ideas para las visualizaciones que se pueden incluir:

1. **Tendencias de ventas por fecha**: Un gráfico de líneas que muestre las ventas totales a lo largo del tiempo, usando la columna `formatted_date`, para identificar picos y caídas en las ventas. Esto permitirá detectar patrones estacionales y períodos de alta demanda.

2. **Distribución de ventas por categoría de producto**: Un gráfico de barras o un gráfico de pastel que muestre la distribución de las ventas por `CATEGORY`. Esto permitirá identificar las categorías de productos más vendidas y las menos populares.

3. **Análisis de márgenes de beneficio**: Un gráfico de barras que muestre el margen de beneficio (`profit_margin`) por categoría o por producto. Esto ayudará a visualizar qué productos están generando más ganancias y cuáles tienen márgenes más ajustados.

4. **Impacto de los descuentos en las ventas**: Un gráfico de dispersión que muestre la relación entre los descuentos (`DISCOUNT %`) y el valor total de las ventas. Esto permitirá evaluar si los descuentos están generando más ingresos o si están afectando negativamente a los márgenes de beneficio.

5. **Ventas por método de pago**: Un gráfico de barras que compare las ventas realizadas en efectivo contra las ventas realizadas en línea, usando la columna `payment_type_indicator`. Esto permitirá identificar las preferencias de pago de los clientes.

6. **Beneficio total por mes**: Un gráfico de barras que muestre los beneficios totales por mes usando la columna `month_year` para visualizar la rentabilidad mes a mes. Esto ayudará a identificar los meses más rentables.

7. **Comparativa de ventas entre mayoristas y ventas directas**: Un gráfico de barras que compare el volumen de ventas entre los dos tipos de venta (`SALE TYPE`: "WHOLESALER" vs. "DIRECT SALES"). Esto ayudará a entender cuál de los dos segmentos está generando más ingresos.

