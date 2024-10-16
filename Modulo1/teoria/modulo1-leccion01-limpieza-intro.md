<div style="text-align: center;">
  <img src="https://github.com/Hack-io-Data/Imagenes/blob/main/01-LogosHackio/logo_amarillo@4x.png?raw=true" alt="logo" />
</div>

# Tabla de Contenidos

1. [¿Qué es *Power Query*?](#qué-es-power-query)
   - [Ventajas e Inconvenientes de Power Query](#ventajas-e-inconvenientes-de-power-query)

2. [Importar datos en Power Query desde diversas fuentes](#importar-datos-en-power-query-desde-diversas-fuentes)
   - [Archivos locales (Excel, CSV, Text, JSON, XML)](#archivos-locales-excel-csv-text-json-xml)
   - [Bases de datos relacionales (SQL Server, MySQL, PostgreSQL, Oracle, etc.)](#bases-de-datos-relacionales-sql-server-mysql-postgresql-oracle-etc)
   - [Fuentes web (API, Web scraping)](#fuentes-web-api-web-scraping)
   - [Fuentes en la nube (Azure, SharePoint, Google BigQuery, etc.)](#fuentes-en-la-nube-azure-sharepoint-google-bigquery-etc)
   - [Consideraciones avanzadas de rendimiento](#consideraciones-avanzadas-de-rendimiento)

3. [El flujo de trabajo en Power Query](#el-flujo-de-trabajo-en-power-query)

4. [¿Dónde se encuentra Power Query en Excel?](#dónde-se-encuentra-power-query-en-excel)
   - [Power Query en Excel 2016 y versiones posteriores](#power-query-en-excel-2016-y-versiones-posteriores)
   - [Power Query en Excel 2010 y 2013](#power-query-en-excel-2010-y-2013)

5. [Componentes principales de Power Query](#componentes-principales-de-power-query)

6. [Limpieza y Transformación de Datos](#limpieza-y-transformación-de-datos)
   - [Eliminación de datos irrelevantes](#eliminación-de-datos-irrelevantes)
   - [Establecimiento de tipos de datos](#establecimiento-de-tipos-de-datos)
   - [Normalizar los datos](#normalizar-los-datos)
   - [Manejo de datos duplicados](#manejo-de-datos-duplicados)
   - [Tratamiento de valores nulos](#tratamiento-de-valores-nulos)
   - [Transformaciones de datos](#transformaciones-de-datos)
   - [Filtrado de datos relevantes](#filtrado-de-datos-relevantes)

7. [¿Qué es lo que vamos a hacer en esta clase?](#qué-es-lo-que-vamos-a-hacer-en-esta-clase)

# ¿Qué es *Power Query*?

*Power Query* es una herramienta de Excel diseñada para extraer, transformar y cargar datos (ETL) de una variedad de fuentes. Fue introducida por Microsoft para facilitar la manipulación y análisis de datos, permitiendo a los usuarios realizar complejas transformaciones de datos sin necesidad de escribir código. Es especialmente útil cuando trabajamos con grandes volúmenes de datos y necesitamos realizar transformaciones complejas de manera eficiente.

Sus principales usos son: 

- *Power Query* permite importar datos desde diversas fuentes, como archivos de Excel, CSV, bases de datos SQL, servicios web, entre otros.

- Con *Power Query*, se pueden limpiar, transformar y preparar los datos de manera visual, aplicando filtros, agregaciones, pivotes y otras transformaciones sin necesidad de código.

- Los datos transformados pueden cargarse de vuelta en Excel para su análisis, ya sea en forma de tablas, gráficos, o modelos de datos.

Sus principales carácteristicas, y por lo que para nosotros es tan importante son: 

- Cuenta con una interfaz gráfica amigable que facilita la aplicación de transformaciones.

- Las transformaciones aplicadas se registran en un flujo de trabajo, permitiendo su reutilización y actualización con nuevos datos.

- Se integra perfectamente con Excel y Power BI, permitiendo utilizar las mismas consultas en ambos entornos.

- Es capaz de conectarse a una amplia variedad de fuentes de datos, tanto locales como en la nube.

- Facilita la eliminación de duplicados, el filtrado de datos y la corrección de errores comunes en los conjuntos de datos.

**Ventajas e Inconvenientes de Power Query**

- **Ventajas**

    -  Power Query permite automatizar la limpieza y transformación de datos, lo que ahorra tiempo al evitar tareas repetitivas.

    - Las consultas se pueden actualizar fácilmente con nuevos datos sin necesidad de rehacer todo el proceso de transformación.

    - Su interfaz gráfica permite a los usuarios aplicar transformaciones de datos sin necesidad de conocimientos de programación.

    - El editor visual de consultas facilita la comprensión y el ajuste de las transformaciones aplicadas.

    - Power Query puede conectarse a una amplia variedad de fuentes de datos, como archivos, bases de datos, servicios web, y más.

    - Permite realizar transformaciones complejas de datos de manera visual, lo que es difícil o imposible con funciones tradicionales de Excel.

    - Las transformaciones realizadas se pueden guardar y reutilizar, asegurando consistencia en el tratamiento de datos.

    - Las acciones realizadas en Power Query quedan registradas, proporcionando una documentación implícita de las transformaciones aplicadas.

    - Se integra perfectamente con Excel y Power BI, facilitando el análisis y la visualización de datos en ambos entornos.

    - Power Query puede ser utilizado junto con Power Automate para crear flujos de trabajo automatizados.

- **Inconvenientes**

    - Aunque es intuitivo, los usuarios deben aprender nuevos conceptos y la interfaz de Power Query, lo que puede llevar tiempo.

    - Para realizar transformaciones más avanzadas, es útil conocer el lenguaje M, lo cual añade un nivel de complejidad.


    - Aunque Power Query es poderoso, puede tener limitaciones de rendimiento con conjuntos de datos extremadamente grandes, especialmente en hardware menos potente.

    - Las consultas complejas pueden tardar en actualizarse, lo que afecta la experiencia del usuario.

    - Power Query está diseñado principalmente para trabajar dentro de Excel y Power BI, lo que puede ser una limitación si se necesita utilizar otras plataformas.

    - Puede haber desafíos al intentar integrar Power Query con sistemas no Microsoft.

    - Algunas características de Power Query pueden no estar disponibles en todas las versiones de Excel, especialmente en versiones más antiguas.

    - Las actualizaciones de Power Query y Excel pueden cambiar o eliminar características, lo que puede afectar las consultas existentes.


# Importar datos en Power Query desde diversas fuentes

Power Query nos permite conectar y extraer datos desde una amplia variedad de fuentes, y lo hace de manera muy eficiente. Vamos a abordar cómo se realiza esta importación y las particularidades avanzadas que debemos tener en cuenta según la fuente de datos que estemos utilizando. Sin mebargo, antes de empezar, veamos como debe ser el proceso general para importar los datos:

- **Conectar**: Seleccionamos la fuente de datos desde la cual queremos extraer información.

- **Previsualizar**: Power Query nos permite ver una muestra de los datos para que podamos verificar si se ha conectado correctamente.

- **Transformar**: Una vez cargados, podemos aplicar una serie de transformaciones antes de importarlos a nuestro modelo de datos final.

- **Cargar o cerrar**: Podemos cargar los datos directamente en Excel o Power BI, o simplemente cerrar la consulta si preferimos continuar trabajando más tarde.

Veamos ahora desde que fuentes de datos podemos importar datos a Power Query: 

- **Archivos locales (Excel, CSV, Text, JSON, XML)**

   - **Excel**: Cuando importamos desde un archivo Excel, podemos elegir entre distintas hojas de cálculo o incluso tablas definidas dentro del archivo. Power Query nos permite cargar los datos en su formato tabular directamente y trabajar con ellos en su estado bruto. En Excel, una mejor práctica es definir tablas estructuradas (con la opción de "Insertar tabla") en lugar de importar un rango de celdas. Esto mejora la flexibilidad y consistencia en futuras consultas y automatizaciones.

   - **CSV y archivos de texto**: Estos son formatos comunes para la transferencia de datos entre sistemas. Al importar CSVs, Power Query detecta automáticamente el delimitador (coma, punto y coma, tabulador, etc.), pero podemos personalizar esta opción si trabajamos con formatos personalizados. Si trabajamos con grandes volúmenes de datos en archivos CSV, Power Query tiene la capacidad de procesar datos de manera eficiente, pero también podemos considerar usar métodos de carga incremental para evitar problemas de rendimiento.

   - **JSON y XML**: Estos formatos, más estructurados, suelen utilizarse en la transferencia de datos entre aplicaciones web. Al importar un archivo JSON o XML, Power Query nos presenta los datos en una estructura jerárquica que podemos expandir según las necesidades de nuestro análisis. Estos formatos suelen tener estructuras complejas. Power Query ofrece herramientas para convertirlos en tablas llanas a través de la función "Expandir", pero puede ser necesario un manejo cuidadoso de los datos anidados y relaciones entre entidades.

- **Bases de datos relacionales (SQL Server, MySQL, PostgreSQL, Oracle, etc.)**

   - Importar desde bases de datos es una de las funciones más potentes de Power Query. Podemos conectarnos directamente a una base de datos relacional (como SQL Server o MySQL), escribir consultas SQL personalizadas, o simplemente seleccionar tablas y vistas existentes. A la hora de trabajar con bases de datos debemos tener en cuenta un par de aspectos: 

     - En lugar de extraer grandes cantidades de datos y luego aplicar transformaciones en Power Query, es recomendable delegar el procesamiento a la base de datos. Podemos hacerlo escribiendo consultas SQL directamente dentro del diálogo de conexión. De esta manera, reducimos la carga en Power Query y trabajamos de forma más eficiente.

     - Cuando trabajamos con grandes conjuntos de datos en bases de datos, es importante aplicar filtros en la fuente de datos antes de cargar los datos en Power Query. Esto se conoce como **push-down** de consultas, lo que mejora considerablemente el rendimiento.

- **Fuentes web (API, Web scraping)**

   - **APIs web**: Power Query puede conectarse a APIs RESTful, que son una fuente cada vez más común de datos dinámicos. Al hacerlo, podemos importar datos en formato JSON o XML desde la web. Aspectos que debemos tener en cuenta:

     - Al conectar con APIs, generalmente es necesario manejar autenticación (tokens, claves API, OAuth). Además, las APIs suelen tener paginación, lo que significa que los datos se entregan en varias partes. En estos casos, deberemos construir consultas en Power Query que iteren sobre las páginas para cargar el conjunto completo de datos.

   - Power Query también tiene la capacidad de extraer datos de páginas web HTML. Esto es útil cuando los datos están disponibles públicamente pero no hay una API disponible.

- **Fuentes en la nube (Azure, SharePoint, Google BigQuery, etc.)**

   - **Azure y SharePoint**: Si trabajamos en un entorno corporativo, es probable que nuestros datos estén almacenados en servicios de la nube como Azure SQL Database o SharePoint. Power Query tiene integraciones directas con estos servicios. Sin emmbargo, las conexiones a fuentes en la nube pueden requerir autenticación mediante credenciales empresariales o tokens de acceso. También es importante manejar los permisos y accesos de lectura/escritura de manera adecuada para garantizar la seguridad y el acceso correcto a los datos.


**Consideraciones avanzadas de rendimiento**

- **Cargar los datos eficientemente**: En situaciones donde los volúmenes de datos son muy grandes, Power Query permite realizar cargas diferidas, es decir, cargar solo un subconjunto de datos a la vista previa y aplicar transformaciones sin importar el conjunto completo. Esto mejora considerablemente la velocidad y rendimiento en la manipulación de datos.

- **Carga incremental**: Si estamos trabajando en un entorno de Power BI, podemos configurar la **carga incremental** para que Power Query solo procese los nuevos datos o aquellos que han cambiado, en lugar de cargar todo el conjunto de datos cada vez.


# El flujo de trabajo

```mermaid
graph LR
    A[Conectar] --> B[Transformar]
    B --> C[Combinar]
    C --> D[Cargar]
    D --> E[Consulta guardada]
    E --> F[Actualización automática]
    F --> A
```

El flujo de trabajo en Power Query sigue un ciclo bastante simple y lógico:

1. **Conectar**: Cargar datos desde la fuente de nuestra elección.

2. **Transformar**: Aplicamos todas las transformaciones necesarias para preparar los datos.

3. **Combinar** (si es necesario): Si estás trabajando con múltiples fuentes de datos, podemos combinar tablas, realizar uniones y consolidar la información.

4. **Cargar**: Exportar los datos transformados nuevamente a Excel o a otro destino.

Una vez que completemos la transformación y carguemos los datos en Excel, Power Query guarda todo el proceso en la consulta. Esto significa que, cuando necesitemos actualizar los datos en el futuro, solo necesitamos volver a cargar la fuente y la consulta ejecutará automáticamente todas las transformaciones anteriores.

# ¿Dónde se encuentra Power Query en Excel?

Power Query está disponible en diferentes versiones de Excel, pero la forma de acceder a esta herramienta depende de la versión que estemos utilizando. En las versiones más recientes, está completamente integrado, mientras que en versiones anteriores se requiere la instalación de un complemento.

## Power Query en Excel 2016 y versiones posteriores

En Excel 2016, Excel 2019, y Microsoft 365, Power Query ya está integrado de manera predeterminada. Esto significa que no necesitamos realizar ninguna instalación adicional para utilizar esta herramienta de manipulación de datos. A continuación, explicamos cómo acceder a Power Query y cómo empezar a utilizarlo:

### Acceso a Power Query

- **Paso 1: Ubicación del menú**: Power Query está integrado en la pestaña **Datos** de la cinta de opciones de Excel. Al abrir Excel, debes dirigirte a la barra de herramientas en la parte superior y seleccionar la pestaña **Datos**. Aquí encontraremos una sección denominada **Obtener y transformar datos**.

- **Paso 2: Botón "Obtener datos"**: Dentro de esta sección, veremos el botón **Obtener datos**. Este botón es el punto de partida para todas las operaciones de Power Query. Al hacer clic en él, se desplegará una lista con varias opciones para importar datos desde distintas fuentes. Las fuentes comunes incluyen:

  - **Desde archivo**: Aquí puedes importar datos desde archivos locales como Excel, CSV, XML, y archivos de texto.

  - **Desde bases de datos**: Esta opción te permite conectar bases de datos como SQL Server, Access, y otras.

  - **Desde la web**: Power Query también permite importar datos desde fuentes online, como una tabla HTML en una página web.

  - **Desde otras fuentes**: Aquí puedes conectarte a servicios en la nube, como Azure, o realizar consultas avanzadas con OData o servicios de API.

### Vista del Editor de Power Query

Una vez que hayamos seleccionado e importado los datos, Excel abrirá automáticamente el **Editor de Power Query** en una ventana separada. Aquí es donde comenzaremos a aplicar transformaciones y a preparar los datos para su análisis. Las principales partes del editor de Power Query son: 

  - **Panel de Consultas**: A la izquierda, puedes ver una lista de todas las consultas que has creado. Si estás trabajando con múltiples conjuntos de datos, puedes navegar fácilmente entre ellos.

  - **Vista previa de los datos**: En el centro, puedes ver cómo se ven tus datos en su forma actual, lo que te permite verificar los cambios en tiempo real.

  - **Pasos aplicados**: A la derecha, se muestra un registro detallado de todos los pasos que has aplicado a los datos. Cada vez que realices una acción (como eliminar una columna o cambiar un tipo de dato), se añadirá como un paso. Puedes modificar o eliminar cualquier paso en cualquier momento.



## Power Query en Excel 2010 y 2013

En las versiones de Excel 2010 y 2013, Power Query no está disponible de manera predeterminada. En lugar de eso, necesitas descargar e instalar un **complemento** proporcionado por Microsoft.

### Cómo instalar Power Query en Excel 2010 y 2013

- **Paso 1: Descargar el complemento**: Debemos ir al [sitio web oficial de Microsoft Power Query](https://www.microsoft.com/es-es/download/details.aspx?id=39379) y descargar el complemento para la versión específica de Excel que estás utilizando. Asegúrate de elegir la versión correcta para tu sistema operativo (32-bit o 64-bit).
  


- **Paso 2: Instalar el complemento**: Una vez descargado el archivo de instalación, debes ejecutarlo y seguir las instrucciones en pantalla para instalar Power Query. Este proceso es rápido y no requiere configuraciones complicadas.

- **Paso 3: Acceder a Power Query**:  Después de instalar el complemento, abre Excel. Notarás que aparece una nueva pestaña en la cinta de opciones llamada **Power Query**. Aquí tendrás acceso a las mismas funciones de obtención y transformación de datos que en las versiones más recientes.

### Funcionalidad de Power Query en Excel 2010/2013

Aunque el acceso es ligeramente diferente, la funcionalidad de Power Query en Excel 2010 y 2013 es prácticamente la misma que en las versiones más recientes. Una vez que haces clic en la pestaña **Power Query**, podemos:

- Obtener datos desde diversas fuentes, como archivos, bases de datos y servicios en línea.

- Aplicar transformaciones de datos dentro del Editor de Power Query.

- Guardar y cargar los datos transformados en Excel.

El flujo de trabajo es el mismo, aunque la interfaz puede variar un poco.


# Componentes principales de Power Query

El editor de Power Query es el núcleo de todas las transformaciones de datos. Aquí es donde se realizan y registran los cambios que hacemos a los datos, y es una parte fundamental del flujo de trabajo de Power Query. La interfaz del editor está diseñada para ser fácil de usar, y te proporciona todas las herramientas que necesitas para limpiar, transformar y preparar datos de manera eficiente. Los principales componentes son:

- **Cinta de opciones (Ribbon)**: Está situada en la parte superior de la ventana de Power Query. Aquí encontraremos las acciones principales que podemos ejecutar sobre nuestros datos. La cinta está dividida en varias pestañas:

   - **Inicio (Home)**: Aquí es donde encontraremos las herramientas más utilizadas, como cargar, cerrar, aplicar cambios, ordenar y filtrar datos, reducir filas, dividir columnas, etc.

   - **Transformar (Transform)**: En esta pestaña tenemos todas las funciones que nos permiten modificar los datos. Esto incluye cambiar tipos de datos, agrupar filas, pivotar columnas, entre otros.

   - **Agregar columna (Add Column)**: Esta pestaña se usa para agregar nuevas columnas derivadas de otras mediante fórmulas, cálculos, o transformaciones basadas en texto, números o fechas.

   - **Vista/Ver (View)**: Nos permite cambiar el modo en que se visualizan los datos, habilitar el lenguaje M en el editor avanzado, o visualizar las consultas y su dependencias en forma gráfica.

- **Panel de consultas (Queries pane)**: A la izquierda de la pantalla encontraremos el **Panel de consultas**. Aquí se listan todas las consultas que hemos creado o importado en nuestro proyecto actual. Este panel nos permite gestionar las diferentes consultas, renombrarlas, duplicarlas, o eliminarlas.

- **Editor de pasos aplicados (Applied Steps)**: A la derecha, veremos el **panel de Pasos Aplicados**. Aquí se registra cada transformación que aplicamos a los datos en forma de "pasos". Estos pasos se guardan como un registro secuencial, lo que nos permite retroceder, eliminar o modificar cualquier transformación previa sin perder el historial de tu trabajo. Cada paso se escribe en el lenguaje M de Power Query, y podemos editar manualmente cada uno desde este panel si deseas un mayor control sobre las transformaciones.

- **Vista previa de datos (Data Preview)**: En el centro de la ventana se encuentra la **Vista previa de datos**, donde podemos ver una muestra de los datos en los que estamos trabajando. No se trata de todos los datos, sino de una representación parcial (generalmente las primeras mil filas), que nos permite verificar si las transformaciones que aplicamos están funcionando correctamente. Podemos interactuar directamente con la vista previa: al hacer clic derecho en una columna o fila, veremos un menú contextual que ofrece diversas opciones de transformación. Además, cualquier operación que realices en esta vista se traduce automáticamente en un nuevo paso en el panel de Pasos Aplicados.

- **Barra de fórmulas (Formula Bar)**: Justo encima de la vista previa de datos, encontraremos la **Barra de fórmulas**. Esta barra muestra la fórmula M correspondiente al paso seleccionado actualmente. Es una herramienta esencial cuando necesitamos ajustar manualmente las transformaciones o escribir fórmulas personalizadas. 

- **Editor avanzado (Advanced Editor)**: Si prefieres tener un control total o necesitas realizar ajustes muy específicos, el **Editor avanzado** se pueden convertir en nuestro mejor aliado. Este editor nos permite escribir o modificar directamente el código en lenguaje M que define la consulta. Para acceder, debemos dirigirnos a la pestaña **Vista** y selecciona "Editor avanzado". Aquí podremos ver el script completo que Power Query está generando en segundo plano a medida que aplicamos pasos en la consulta.

- **Pestañas de consultas**: En la parte superior de la ventana de Power Query, veremos **pestañas** si tenemos múltiples consultas abiertas a la vez. Esto nos permite alternar rápidamente entre diferentes consultas sin necesidad de cerrar o perder el contexto de la consulta actual.

Algunos consejos para usar de forma eficiente Power Query son: 

- **Organización de pasos**: El panel de pasos aplicados es clave para revisar y gestionar el flujo de trabajo. El orden de los pasos importa, así que asegúrate de que las transformaciones ocurran en la secuencia correcta.

- **Uso de la barra de fórmulas**: A medida que avanzamos en tus conocimientos de Power Query, notaremos que muchas transformaciones pueden simplificarse ajustando las fórmulas directamente en la barra. Esto nos ahorra tiempo al no tener que buscar las opciones en el menú.

- **Vista previa de datos**: Siempre debemos revisar la vista previa después de aplicar cada paso para asegurarnos de que los resultados son los esperados.




# Limpieza y Transformación de Datos 

Para realizar el **proceso de limpieza y transformación de datos** como analistas, es importante seguir un enfoque sistemático que garantice que los datos estén en el formato correcto para su análisis. A continuación detallamos los pasos clave que deberías seguir, incluyendo los puntos mencionados en la imagen sobre **eliminación de datos irrelevantes** y **tratamiento de valores nulos**.

```mermaid
graph LR
    A[Eliminación de datos irrelevantes] --> B[Establecimiento de tipos de datos]
    B --> C[Normalizar los datos]
    C --> D[Manejo de datos duplicados]
    D --> E[Tratamiento de valores nulos]
    E --> F[Transformaciones de datos]
    F --> G[Filtrado de datos relevantes]
```


## Eliminación de datos irrelevantes

Este es el primer paso y consiste en identificar y eliminar columnas o filas que no contribuyen al análisis. El objetivo es reducir el "ruido" en los datos, eliminando aquellos elementos que no agregan valor para nuestro análisis. Las acciones que debemos realizar en este primer paso son: 

- **Eliminar columnas irrelevantes**: Para ello debemos: 

   - Identificar las columnas que no son necesarias para el análisis. Esto puede incluir identificadores como "Customer ID" o campos redundantes.

   - Ejemplo: En un análisis de clientes, campos como "Notas internas" o "Número de grupo" pueden no ser relevantes si no contribuyen a los KPIs del análisis.
   
- **Eliminar filas innecesarias**: Para ello debemos: 

   - Eliminar filas duplicadas que no proporcionen información adicional.

   - Filtrar filas que contengan valores irrelevantes o fuera de rango (outliers) que no sean útiles para el análisis.


## Establecimiento de tipos de datos

El **establecimiento de tipos de datos** es uno de los pasos más importantes en la preparación y limpieza de datos. Garantizar que cada columna tenga el tipo de dato correcto es esencial para evitar errores y asegurar que las operaciones de análisis funcionen correctamente. Un tipo de dato incorrecto puede distorsionar los resultados, generar errores en los cálculos y dificultar la visualización o manipulación de los datos. Por lo tanto, corregir y ajustar los tipos de datos al inicio del proceso de análisis es crucial para obtener conclusiones precisas y confiables.

Cada columna en un conjunto de datos debe tener un tipo de dato que se ajuste a la naturaleza de la información contenida en ella. Los tipos de datos más comunes incluyen:

- **Numérico**: Para columnas que contienen cantidades o medidas, como precios, totales de ventas o métricas financieras.

- **Texto**: Para información alfanumérica, como nombres de productos, nombres de clientes o descripciones.

- **Fecha**: Para columnas que contienen información de fechas, como la fecha de transacción o la fecha de registro de un cliente.

- **Booleano**: Para columnas que solo contienen valores de "sí/no", "verdadero/falso" o similares.

Si no se asigna el tipo de dato correcto a cada columna, pueden surgir varios problemas durante el análisis. Por ejemplo, si una columna de fechas se almacena como texto, las herramientas de análisis no podrán realizar operaciones de comparación o cálculos de intervalos de tiempo correctamente. Lo mismo sucede con columnas numéricas que se guardan como texto, ya que no se podrán sumar, promediar o aplicar funciones matemáticas.

Las principales acciones que deberemos hacer en esta fase de la limpieza y transformación son: 

- `Detectar y corregir tipos de datos incorrectos`: En la mayoría de los conjuntos de datos, es común encontrar columnas cuyo tipo de dato no es el adecuado, especialmente cuando los datos provienen de múltiples fuentes o se introducen de manera manual. Uno de los errores más frecuentes es cuando los números o fechas se almacenan como texto. En estos casos, es necesario realizar un ajuste para que el sistema reconozca los datos correctamente.

- `Cambiar tipo de dato para columnas numéricas`: Para las columnas numéricas, es importante asegurarse de que se almacenen como números, no como texto. En **Excel**, puedes detectar fácilmente si una columna de números está almacenada como texto porque los números aparecerán alineados a la izquierda, en lugar de a la derecha. Para corregirlo, se puede convertir el formato de la celda a "Número" o "Moneda", dependiendo del tipo de información que contenga.

    En **Power Query**, también podemos cambiar fácilmente el tipo de dato de una columna seleccionando la opción de "Cambiar tipo" en el menú de transformación, donde se puede especificar si los datos deben ser numéricos enteros, decimales o de otro tipo.

- `Cambiar tipo de dato para columnas de fechas`: Las fechas son otro tipo de dato que con frecuencia está en el formato incorrecto. Si una columna de fechas se guarda como texto, los análisis basados en tiempo no funcionarán correctamente, ya que Excel o Power BI no podrán interpretar esos datos como fechas.

    Para corregir esto en **Excel**, podemos convertir las celdas en el formato de "Fecha" y asegurarnos de que las fechas estén en un formato consistente, como "dd/mm/aaaa". En **Power Query**, también podemos usar la función de "Detectar tipo de datos" o cambiar manualmente el tipo de columna a "Fecha".

    Una vez que las fechas estén en el formato correcto, podremos realizar análisis basados en series temporales, como calcular la duración entre dos eventos o agrupar datos por año o mes.

- `Cambiar tipo de dato para columnas booleanas`: Las columnas booleanas (verdadero/falso, sí/no) son útiles para identificar la presencia o ausencia de una condición. Si una columna está en formato incorrecto, es posible que el análisis no sea capaz de realizar comparaciones o filtros correctos. En estos casos, debemos asegurarnos de que los valores booleanos estén en el formato adecuado.

    En **Excel**, podemos transformar las columnas de "Sí" y "No" en valores booleanos (VERDADERO/FALSO) o números (1/0), lo que facilita las comparaciones y cálculos. En **Power Query**, también podemos definir el tipo de columna como "Verdadero/Falso" para asegurar que las herramientas de análisis lo interpreten correctamente.


## Normalizar los datos

La normalización de los datos es un paso fundamental en el proceso de limpieza y transformación. Mantener la consistencia en el formato de los datos es esencial para garantizar que los análisis y las visualizaciones posteriores se realicen de manera efectiva y sin errores. Inconsistencias en el formato pueden generar discrepancias, afectar la precisión de los resultados o complicar la integración de los datos con otras fuentes. Por lo tanto, establecer un formato estándar ayuda a prevenir estos problemas y a mejorar la calidad de los datos.

- Uno de los aspectos clave en el proceso de normalización es la **uniformidad del texto**. Cuando los datos provienen de diferentes fuentes o han sido introducidos por varias personas, es común encontrar variaciones en el uso de mayúsculas y minúsculas. Esto puede afectar la manera en que los datos son interpretados y utilizados en el análisis.

    Por ejemplo, si en una columna que contiene nombres de ciudades aparece "Madrid", "madrid" o "MADRID", los análisis que dependan de agrupar o contar la frecuencia de aparición de estas ciudades podrían fallar, ya que el sistema podría considerarlas como tres entradas diferentes. Para evitar este problema, es necesario **normalizar el texto**, lo que implica convertir todas las entradas de una columna de texto en un formato consistente, ya sea todo en **mayúsculas** o en **minúsculas**.

    Existen diferentes herramientas en Excel y Power Query que permiten hacer esta transformación de manera sencilla. Por ejemplo, usando la fórmula `UPPER()` en Excel podemos convertir todo el texto a mayúsculas, y con `LOWER()` a minúsculas. En Power Query, se puede hacer una transformación similar de manera automatizada al seleccionar la opción correspondiente en el menú de transformación de texto.

- Otro problema común en los conjuntos de datos es la presencia de **espacios en blanco** innecesarios, especialmente en columnas de texto. Estos espacios pueden ser difíciles de detectar visualmente, pero pueden causar problemas cuando se intenta comparar, filtrar o hacer análisis de datos. Por ejemplo, si tienes una columna con nombres de clientes y algunos de esos nombres incluyen espacios adicionales al principio o al final, como " Juan" en lugar de "Juan", las comparaciones y filtros pueden no funcionar correctamente, ya que el sistema los considera como dos valores diferentes.

    La eliminación de espacios en blanco es una tarea simple pero crucial. En Excel, puedes usar la fórmula `TRIM()` para eliminar los espacios innecesarios, incluidos los que se encuentran al principio, en el medio o al final del texto. En Power Query, existe una transformación específica para **recortar** los espacios en blanco que también puede automatizar esta tarea en todo un conjunto de datos de manera rápida y eficiente.


# ¿Qué es lo que vamos a hacer en esta clase?

En esta clase, nos enfocaremos en entender cómo podemos aplicar **Power Query** para limpiar y transformar nuestros datos de forma efectiva, eliminando información irrelevante y preparando los datos para un análisis más preciso.

El objetivo principal de la clase es que aprendamos a identificar **qué datos son útiles y cuáles no lo son** para el análisis de abandono de clientes (churn) y cómo **eliminarlos** de manera eficiente utilizando Power Query. A continuación, desglosamos en pasos claros lo que haremos:

1. **Exploraremos el conjunto de datos**: 

   - Vamos a cargar los datos en Power Query y observar sus columnas. 

   - Identificaremos qué columnas son importantes para nuestro análisis y cuáles pueden considerarse "ruido" o irrelevantes.

2. **Eliminación de datos irrelevantes**: 

   - Aprenderemos a eliminar columnas que no contribuyen al análisis, como identificadores que no aportan valor, o datos extra como "Hobby" y "Favorite TV Show".

   - Practicaremos cómo seleccionar y eliminar columnas directamente en el editor de Power Query.

3. **Aplicaremos transformaciones básicas**:

   - Veremos cómo ajustar los tipos de datos y limpiar el formato de las columnas que son relevantes.

   - También aprenderemos cómo guardar estas transformaciones para que puedan reutilizarse en futuras actualizaciones de los datos.

Este proceso no solo nos ayudará a limpiar los datos, sino que también nos dará una comprensión clara de cómo preparar un conjunto de datos para un análisis de abandono de clientes y facilitar la toma de decisiones basadas en los factores que realmente importan. 


## Eliminación de Datos Irrelevantes

Basándonos en el problema definido previamente sobre el análisis de abandono de clientes, el objetivo es identificar los factores clave que influyen en la decisión de los clientes de abandonar el servicio. Algunos de estos factores incluyen el tiempo que el cliente lleva con la empresa, la frecuencia de quejas, el método de pago, el tipo de contrato y otros aspectos directamente relacionados con el comportamiento de los clientes.

Enumeremos las columnas que podrían considerarse **irrelevantes** para este análisis de abandono, ya que no aportan información relevante para comprender el comportamiento del cliente respecto al abandono del servicio:

1. **Phone Number**: Es un identificador de contacto que no aporta valor analítico para el análisis del comportamiento del cliente.

2. **Hobby**: Esta columna contiene información sobre pasatiempos que no influye en la decisión de un cliente de abandonar o no el servicio.

3. **Favorite TV Show**: Similar a "Hobby", esta información no está relacionada con el comportamiento de abandono de los clientes.

4. **Internal Notes**: Suele contener información administrativa o interna que no tiene impacto directo en el análisis del abandono.

5. **Group**: A menos que la segmentación por grupos sea relevante para el análisis del churn, esta columna puede ser irrelevante.

6. **Number of Customers in Group**: Si no es relevante analizar la dinámica entre clientes dentro de grupos, esta columna puede considerarse irrelevante para el análisis de abandono.

7. **Churned**: Es una columna redundante, ya que tenemos la misma información en la columna "Churn Label". 

Estas columnas pueden eliminarse para simplificar el conjunto de datos y enfocarse en las variables que tienen mayor relación con el comportamiento de abandono. Eliminar estos datos irrelevantes ayudará a concentrarse en los factores clave del análisis, como la duración de la cuenta, el número de quejas, el método de pago, y los patrones de uso de servicios, que son más indicativos del comportamiento de abandono.


## Normalización de Datos

Para garantizar la coherencia y la facilidad de análisis en el conjunto de datos, es esencial aplicar ciertos procesos de normalización. A continuación, vamos a describir las transformaciones realizadas para unificar el formato de las distintas columnas y asegurar que todas las variables sean fácilmente comparables.

1. **Formato de fechas unificado**: Hemos observado que las columnas de fechas están en diferentes formatos. Una columna está en el formato día-mes-año y otra en año-mes-día. Para estandarizar las fechas, vamos a utilizar el formato **día-mes-año** en todas las columnas relacionadas con fechas, facilitando así su manejo y comprensión.

2. **Separador decimal**: La columna **Intl Min** utiliza un punto (".") como separador de decimales, lo cual es inconsistente con otros datos que usan coma (","). Vamos a corregir este formato para que todos los decimales usen coma en lugar de punto, adaptando así el formato a las convenciones estándar utilizadas en este conjunto de datos.

3. **Consistencia en los valores numéricos**: Vamos a ajustar todas las columnas numéricas para mostrar los valores con **dos decimales**. Esto garantiza una mayor precisión y coherencia en los cálculos y análisis posteriores.

4. **Unificación de nombres de columnas**: Para mejorar la comprensión y la coherencia del conjunto de datos, vamos a unificar el nombre de todas las columnas en inglés. Esto evita posibles confusiones al tener una mezcla de idiomas en los encabezados de las columnas. 

5. **Valores en la columna "Unlimited Data"**: La columna que indica si un cliente tiene **datos ilimitados** estaba codificada como 0 (No) y 1 (Sí), lo que puede ser confuso. Vamos a reemplazar los valores por **'No'** y **'Yes'** para facilitar su interpretación y asegurar la consistencia con otros valores categóricos.

6. **Unificación de género**: En la columna de **Gender**, los valores están mezclados entre español e inglés, con entradas como "Femenino/Female" y "Masculino/Male". Unificaremos el idioma de esta columna, utilizando **'Male'** y **'Female'** para todas las entradas.

7. **Consistencia en la columna "Monthly Charges"**: La columna de **Monthly Charges** contiene una mezcla de valores numéricos puros y valores numéricos acompañados por "USD". Eliminaremos "USD" para que todos los valores en esta columna sean puramente numéricos, facilitando el análisis cuantitativo.

8. **Normalización de la columna "Payment Method"**: Los valores en la columna **Payment Method** están en una mezcla de mayúsculas y minúsculas. Todos los valores los convertiremos a **minúsculas** para asegurar la consistencia en la representación de los diferentes métodos de pago.



# Cambios en los Tipos de Datos

Basado en la inspección de los datos proporcionados, aquí te detallo algunas **normalizaciones de datos** que se pueden aplicar al conjunto de datos para mejorar la consistencia y facilitar el análisis:

1. **Formato de números**: Cambiar los valores numéricos a un formato consistente con dos decimales para columnas relacionadas con cantidades monetarias o tiempo, como **Monthly Charges** y **Total Charges**. Esto garantizará la coherencia a lo largo de los datos y facilitará el análisis cuantitativo.

2. **Fecha de ingreso**: La columna **Date of Joining** (si está presente) debería estar en formato de fecha (dd/mm/yyyy o yyyy-mm-dd), dependiendo de la convención regional utilizada. Asegúrate de que todas las columnas de fecha estén en el mismo formato para evitar confusiones y errores en los cálculos de antigüedad o segmentación temporal.

3. **Normalización de la columna de quejas**: Si hay una columna relacionada con el número de quejas, revisa que no existan valores atípicos o errores. Las quejas que aparecen con un formato no numérico (como texto) deben corregirse. Convierte esta columna a un **tipo numérico** y asegura que los valores estén dentro de un rango lógico.

4. **Uso de servicios internacionales**: La columna de **International Usage** o **Uso de servicios internacionales** debe ser categórica (Sí/No). Los valores deben ser uniformes, sin diferencias en mayúsculas o abreviaturas. Esto ayudará a crear segmentaciones más precisas.

5. **Conversión de género a binario**: Para análisis estadísticos, puedes transformar la columna de **Gender** a valores binarios (0 = Male, 1 = Female), o mantenerla como categorías textuales si eso aporta más valor a tu análisis.

