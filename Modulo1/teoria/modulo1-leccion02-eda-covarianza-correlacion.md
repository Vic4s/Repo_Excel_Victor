<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_amarillo@4x.png?raw=true" alt="logo" />
</div>


# Covarianza

La **covarianza** mide el grado en que dos variables aleatorias varían juntas. Específicamente, cuantifica la **dirección** de la relación lineal entre dos variables. Si la covarianza es positiva, significa que cuando una variable aumenta, la otra tiende a aumentar. Si es negativa, significa que cuando una variable aumenta, la otra tiende a disminuir. Pongamos un ejemplo para entenderlo mejor. Supongamos que una tienda online quiere analizar cómo varían las ventas en función de la cantidad de dinero que invierte en publicidad digital. Los datos recolectados por la tienda online son: 

- **Inversión en Publicidad (en miles de dólares)**: Esta variable mide cuánto dinero está invirtiendo la tienda en anuncios cada mes.

- **Ventas (en miles de unidades)**: Esta variable mide cuántos productos se han vendido cada mes.


Como hemos dicho, vamos a analizar si existe una relación entre estas dos variables: la inversión en publicidad y las ventas.

- Si el valor de la covarianza es alto y positivo, significa que hay una relación directa entre la inversión y las ventas: cuando se invierte más en publicidad, las ventas también aumentan.
   
- Ahora, si hipotéticamente los datos fueran inversos (es decir, que cuando se invierte más en publicidad, las ventas disminuyen), obtendríamos una **covarianza negativa**. Esto indicaría que cuando una variable aumenta, la otra disminuye, lo cual podría ser un indicio de un problema en la estrategia de marketing.


Matemáticamente, la covarianza se define como:

$\text{Cov}(X, Y) = \frac{\sum_{i=1}^{n}(X_i - \bar{X})(Y_i - \bar{Y})}{n}$

Donde:

- $X_i$ y $Y_i$: Son los valores de las variables.

- $\bar{X}$ y $\bar{Y}$: Son las medias de las variables $X$ y $Y$.

- $n$: Es el número de pares de datos.

**¿Cómo interpretamos entonces la covarianza?**

- **Covarianza positiva**: Indica que ambas variables tienden a moverse en la misma dirección. Ejemplo: el ingreso de una persona y su nivel de gasto.

- **Covarianza negativa**: Indica que las variables se mueven en direcciones opuestas. Ejemplo: la velocidad de un automóvil y el tiempo para llegar a un destino.

- **Covarianza cercana a cero**: Indica que no existe una relación lineal evidente entre las variables. Ejemplo: El consumo de café y la estatura de una persona no muestran relación alguna, covarianza cercana a cero.



**Limitaciones de la Covarianza**

- La covarianza depende de las unidades de las variables, lo que puede dificultar la comparación entre conjuntos de datos con diferentes escalas.
   
- Si las variables tienen una relación no lineal, la covarianza puede ser cero incluso si existe una fuerte dependencia no lineal.

- Al igual que muchas medidas de dependencia, la covarianza es sensible a outliers, que pueden distorsionar los resultados.


**Aplicaciones en Data Analytics**


- **Relación entre gastos de marketing y ventas**: Analizar la covarianza entre el gasto en publicidad y el aumento en las ventas para ver si ambos crecen o disminuyen juntos.

- **Análisis de riesgo en portafolios financieros**: Utilizar la covarianza entre los retornos de diferentes activos financieros para entender cómo varían en conjunto y así gestionar mejor el riesgo.

- **Selección de variables en modelos predictivos**: Evaluar la covarianza entre varias variables independientes para evitar incluir aquellas que tienen relaciones redundantes, ayudando a mejorar la eficiencia del modelo.



# Correlación

La **correlación** mide la **fuerza** y la **dirección** de la relación lineal entre dos variables. A diferencia de la covarianza, la correlación está **normalizada**, lo que significa que su valor siempre se encuentra entre -1 y 1, facilitando la interpretación. Este valor describe si las dos variables aumentan o disminuyen juntas, y la intensidad de esa relación.

Vamos a usar el mismo ejemplo de la tienda online que analizamos con la covarianza. La tienda quiere evaluar si existe una relación entre la **inversión en publicidad** y las **ventas** utilizando correlación. Los datos recolectaos por la tienda serán los mismos: 

- **Inversión en Publicidad (en miles de dólares)**: Esta variable mide cuánto dinero está invirtiendo la tienda en anuncios cada mes.

- **Ventas (en miles de unidades)**: Esta variable mide cuántos productos se han vendido cada mes.

Ahora, calculamos la **correlación** entre ambas variables.

- Si la correlación es cercana a **1**, significa que hay una relación lineal positiva fuerte entre la inversión en publicidad y las ventas. En este caso, las ventas aumentan de forma proporcional cuando la tienda invierte más en publicidad.
  
- Si la correlación es cercana a **-1**, significa que hay una relación lineal negativa fuerte. Esto indicaría que cuando aumenta la inversión en publicidad, las ventas disminuyen, lo que podría sugerir un mal uso de los recursos publicitarios.

- Si la correlación es cercana a **0**, indica que no existe una relación lineal evidente entre la inversión en publicidad y las ventas. En este caso, invertir más en publicidad no tendría un impacto claro en las ventas.

Matemáticamente, la **correlación de Pearson** se define como:

$\rho_{X,Y} = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y}$

Donde:

- $\text{Cov}(X, Y)$: Es la covarianza entre las variables $X$ y $Y$.

- $\sigma_X$ y $\sigma_Y$: Son las desviaciones estándar de $X$ y $Y$, respectivamente.

**¿Cómo interpretamos la correlación?**

- **Correlación positiva fuerte (+1)**: Indica que ambas variables se mueven en la misma dirección de manera proporcional. Ejemplo: el ingreso de una persona y su gasto suelen estar fuertemente correlacionados.
  
- **Correlación negativa fuerte (-1)**: Indica que una variable aumenta mientras la otra disminuye de manera proporcional. Ejemplo: la velocidad de un automóvil y el tiempo para llegar a un destino.
  
- **Correlación cercana a cero (0)**: Indica que no existe una relación lineal clara entre las variables. Ejemplo: el consumo de helado y las calificaciones académicas de los estudiantes no suelen estar correlacionados.


**Limitaciones de la Correlación**

- **Relaciones no lineales**: La correlación solo mide relaciones **lineales**. Si las variables están relacionadas de manera no lineal, la correlación puede ser cercana a cero, incluso si existe una fuerte dependencia entre ellas.
  
- **Sensibilidad a outliers**: Valores extremos o atípicos pueden distorsionar el valor de la correlación, influyendo significativamente en el resultado.

- **No implica causalidad**: Una correlación alta no implica que una variable cause cambios en la otra. Puede haber otros factores influyendo en ambas variables.

**Aplicaciones en Data Analytics**

- **Satisfacción del cliente**: Relación entre el tiempo de respuesta y las puntuaciones de satisfacción.

- **Predicción de demanda**: Correlación entre factores como el clima y las ventas de productos.

- **Estudios de salud pública**: Relación entre hábitos como el consumo de tabaco y la incidencia de enfermedades.

- **Optimización de manufactura**: Correlación entre parámetros de producción, como la temperatura, y la calidad del producto.

- **Marketing en redes sociales**: Relación entre la actividad en redes y el tráfico web generado.

