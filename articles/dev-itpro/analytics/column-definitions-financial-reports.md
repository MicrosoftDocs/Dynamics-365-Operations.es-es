---
title: Definiciones de columna en los informes financieros
description: "Este artículo proporciona información acerca de las definiciones de columnas. Una definición de columna es un componente de informe, o bloque de creación, que define el contenido de las columnas de un informe. Como definiciones de filas, las definiciones de columna básicas se pueden usar en varios informes."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8c877a4ad6d4c29607159da52bf1cedae1476f92
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="column-definitions-in-financial-reports"></a>Definiciones de columna en los informes financieros

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de las definiciones de columnas. Una definición de columna es un componente de informe, o bloque de creación, que define el contenido de las columnas de un informe. Como definiciones de filas, las definiciones de columna básicas se pueden usar en varios informes.

<a name="create-and-modify-a-column-definition"></a>Crear y modificar una definición de columna
-------------------------------------

Una definición de columna puede contener de dos a 255 columnas.

### <a name="create-a-column-definition"></a>Permite crear una definición de columna

1.  En el diseñador de informes, en el panel de navegación, haga clic en **Definiciones de columnas**.
2.  En el menú **Archivo**, haga clic en **Nueva** y, a continuación, haga clic en **Definición de columna**.
3.  Agregar el contenido de la definición de la columna.

### <a name="open-a-column-definition"></a>Abrir una definición de columna

1.  En el diseñador de informes, en el panel de navegación, haga clic en **Definiciones de columnas**.
2.  Haga doble clic en una definición de columna para abrirla.

### <a name="add-a-column-to-a-column-definition"></a>Agregar una columna a una definición de columna

1.  En el diseñador del informes, haga clic en **Definiciones de columnas** y después abra la definición de columna para modificarla.
2.  Seleccione la columna donde una nueva columna debe ser insertada.
3.  En el menú **Editar**, haga clic en **Insertar columna**. La nueva columna aparece a la izquierda de la columna seleccionada.

### <a name="delete-a-column-from-a-column-definition"></a>Eliminar una columna de una definición de columna

1.  En el Diseñador de informes, haga clic en **Definiciones de columnas** y abra la definición de columna que desee modificar.
2.  Seleccione la columna que se debe eliminar.
3.  En el menú **Editar**, haga clic en **Eliminar columna**.

## <a name="contents-of-a-column-definition"></a>Contenido de una definición de columna
Una definición de columna incluye la información siguiente:

-   Una columna de las descripciones para la definición de filas
-   Columnas de importe que muestran datos de los datos financieros, una hoja de cálculo de Microsoft Excel, o los cálculos que se basan en otros datos en la definición de la columna
-   Formato de columnas
-   Atribuir columnas

Esta información aparece en las siguientes áreas en la definición de la columna:

-   El área de los encabezados de la definición de la columna contiene el texto y el formato de encabezado que aparece en el informe. Un encabezado puede aplicarse a una sola columna de datos, puede extenderse en varias columnas o puede aplicarse a columnas de manera condicional. La definición de columna puede incluir el número de filas de encabezado de columna según sea necesario. **Nota:** Los encabezados de columna se aplican a cada columna de datos del informe. Los encabezados de informes se aplican a todo el informe. Defina los encabezados de informes en la pestaña **Encabezados y pies de página** de la definición del informe.
-   Las filas de detalle de la columna son las filas debajo de las filas de encabezado en la definición de la columna. Las filas de detalle de la columna definen la información que se incluyen en el informe. En la siguiente tabla se muestran y describen las filas de detalle de la columna.

    | Nombre de la fila de detalle de la columna                                                | Descripción                                                                                            |
    |-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
    | Tipo de columna                                                           | (Requerido) Especifique el tipo de datos en la columna.                                                     |
    | Código de libro/Categoría de atributo                                          | Especifique la información de los datos financieros de las columnas de tipo **FD** y **ATTR**.                       |
    | Períodos del período del ejercicio cubiertos                                    | Especifique la información de los datos financieros de las columnas de tipo **FD**.                                     |
    | Fórmula                                                               | Especifique una fórmula de cálculo para las columnas de tipo **CALC**.                                        |
    | Los espacios adicionales de la anchura de columna antes del control de impresión de anulación del formato de la columna | Especifique las opciones especiales de formato.                                                                        |
    | Restricciones de columna                                                   | Restrinja los datos.                                                                                         |
    | Unidad de notificación                                                        | Restrinja la columna, de modo que muestre solo los datos para la unidad de notificación especificada.                      |
    | Filtro de la divisa de la visualización de la divisa                                      | Formato de divisa.                                                                                       |
    | Filtro de dimensiones                                                      | Especifique un filtro para restringir datos a determinadas unidades de notificación de datos financieros.                           |
    | Filtro de atributo                                                      | Especifique un filtro para restringir los datos financieros.                                                       |
    | Fecha inicial Fecha final                                                   | Restrinja los datos financieros a fechas específicas.                                                         |
    | Justificación                                                         | Alínee a la izquierda, al centro o a la derecha la descripción especificada en la definición de filas. |

## <a name="column-restrictions-in-a-column-definition"></a>Restricción de la columna en una definición de columna
Puede usar las restricciones de columna para especificar cómo una definición de columna usa datos o calcula la información. También puede restringir una columna de informe a una unidad específica o para fechas específicas. **Nota:** Un código de **Restricción de la columna** reemplaza cualquier ajuste en conflicto que se asigne en la definición de filas.

### <a name="column-restrictions-cell"></a>Celda de restricciones de columna

La celda **Restricciones de columna** puede incluir los códigos que restringen o eliminan información, como formato de la fila, los detalles, y los importes para dicha columna.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Añadir una restricción de columna en una definición de columna

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en la celda **Restricciones de la columna** para la columna que se va a restringir.
3.  En el cuadro de diálogo **Restricciones de la columna**, seleccione uno o más códigos que figuran en la lista, y haga clic en **Aceptar**.

### <a name="column-restriction-codes"></a>Códigos de restricción de columna

En la tabla siguiente se describen los códigos de restricción de la columna.

| Código de restricción de columna | Descripción                                                                                                                                                                                                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SU                      | Eliminar subrayado para una columna en la que un comando de subrayado (**---**) o un comando de doble subrayado (**===**) se especifica en la definición de filas. Por ejemplo, puede que no desee subrayar los importes que son producidos por un cálculo porcentual.                                                                        |
| ST                      | Eliminar los totales, de forma que solo se muestren los detalles en la columna (por ejemplo, una columna estadística).                                                                                                                                                                                                                                      |
| SD                      | Eliminar los detalles, de forma que solo las filas **TOT** y **CAL** (de la definición de filas) aparezcan en la columna.                                                                                                                                                                                                                              |
| DR                      | Restringir los importes en una columna **FD** a los importes de débito.                                                                                                                                                                                                                                                                              |
| CR                      | Restringir los importes en una columna **FD** a los importes de crédito.                                                                                                                                                                                                                                                                             |
| ADJ                     | Restringir los importes en la columna a los importes de ajuste del período, si estos importes están disponibles.                                                                                                                                                                                                                                        |
| XAD                     | Restringir los importes en la columna para que los importes de ajuste del período se excluyan.                                                                                                                                                                                                                                                     |
| TP                      | Restringir los importes en la columna, de manera que solo las transacciones registradas se incluyen, si estas transacciones están disponibles.                                                                                                                                                                                                                 |
| UPT                     | Restringir los importes en la columna, de manera que solo las transacciones no registradas se incluyen, si estas transacciones están disponibles. **Nota:** No todos los proveedores de los datos admiten transacciones no registradas. Para obtener más información, consulte [guía de la integración de datos](http://go.microsoft.com/fwlink/?LinkID=162565) para su sistema de Microsoft Dynamics ERP. |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Restringir una columna a una unidad de notificación

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en la celda **Unidad de notificación** para la columna que se va a restringir.
3.  En el cuadro de diálogo **Selección de la unidad de notificación**, en la lista **Organigrama**, seleccione un organigrama.
4.  Expanda o contraiga la lista de unidades, seleccione una unidad de notificación, y haga clic en **Aceptar**.

## <a name="format-column-headers"></a>Dar formato a encabezados de columna
Puede agregar, modificar y eliminar los encabezados que aparecen en la parte superior de las columnas en un informe. También puede configurar encabezados de columna de extensión condicional, según el campo **Período** de definiciones de la columna y el campo **Período de base** de definiciones de informe. La característica del período de base ayuda a ahorrar tiempo cuando crea informes de previsión de acumulación.

### <a name="create-and-manage-column-headers"></a>Crear y administrar los encabezados de columna

Puede usar la caja de diálogo **Encabezado de columna** para agregar, modificar y eliminar los encabezados que aparecen en la parte superior de las columnas en un informe. En la tabla siguiente se describen los campos del cuadro de diálogo **Encabezado de columna**.

| Campo                 | Descripción                                                                                                                                                                                                                                                                                                              |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Texto del encabezado de columna    | Este texto aparece en el encabezado de columna. Puede escribir texto directamente en este campo, o hacer clic en **Insertar AutoTexto** para seleccionar una opción que permite actualizar el encabezado de columna cada vez que se genera el informe. Para incluir varios códigos de autotexto, haga clic en **Insertar AutoTexto** otra vez, y haga clic en otro código en la lista. |
| Aplicar formato a las opciones        | Aplique el formato a un encabezado de columna, como cuadro o subrayado.                                                                                                                                                                                                                                                           |
| Extensión desde y extensión hasta | Defina la columna o las columnas en las que se aplica el texto de encabezado.                                                                                                                                                                                                                                                            |
| Justificación         | Especifique cómo se debe alinear el texto del encabezado de columna se para la columna o el intervalo de columnas especificadas en los campos **Extensión desde** y **Extensión hasta**.                                                                                                                                                               |

### <a name="create-a-column-header"></a>Crear un encabezado de columna

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en una celda de encabezado.
3.  En el cuadro de diálogo **Encabezado de columna**, escriba el texto del encabezado de columna. De forma alternativa, haga clic en **Inserta AutoTexto** y seleccione una opción.
4.  En el campo **Opciones de formato**, especifique un formato para el encabezado.
5.  En el campo **Extensión desde**, especifique la letra de la columna desde la que el encabezado de columna debe comenzar. En el campo **Extensión hasta**, especifique la letra de la columna desde la que el encabezado de columna debe acabar.
6.  En **Justificación**, seleccione si el texto del encabezado de columna debe estar justificado a la izquierda, al centro o a la derecha.
7.  Haga clic en **Aceptar**.

### <a name="add-a-column-header-row"></a>Agregar una fila del encabezado de columna

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Seleccione una celda en la fila de cabecera.
3.  En el menú **Editar**, haga clic en **Insertar fila**. La nueva fila se inserta encima de la fila que seleccionó en el paso 2. **Nota:** Si tiene cuatro o más filas de los encabezados de informes en un informe, los encabezados se superpondrán cuando el informe se exporta a una hoja de cálculo de Excel. Para ver todos los encabezados en el informe, aumente el margen superior de la definición del informe.

### <a name="delete-a-column-header-row"></a>Eliminar una fila del encabezado de columna

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  En la fila de cabecera, seleccione la celda para eliminar.
3.  En el menú **Editar**, haga clic en **Eliminar fila**.

### <a name="create-an-automatically-generated-header"></a>Crear un encabezado generado automáticamente

El diseñador de informes puede generar automáticamente encabezados de columna, en función de códigos de autotexto. Los códigos de Autotexto son variables que se actualizan cada vez que un informe se genera. Cualquier encabezado de columna puede incluir estos códigos para especificar la información de informe que puede variar, como fechas o números de período. Por lo tanto, puede usar una definición de columna para las definiciones de varios informes, períodos de tiempo y organigramas. Dado que los códigos de autotexto confían en la información del calendario de las filas de detalle de la definición de la columna, se admiten solo para las columnas **CALC****FD** y **WKS**. La forma en que un código de autotexto aparece en la celda de encabezado de columna afecta a cómo dicha información aparece en el informe. En el cuadro de diálogo **Encabezado de columna**, los códigos de autotexto aparecen en mayúscula y minúscula. Por lo tanto, el texto aparece en mayúsculas y minúsculas en el informe. Por ejemplo, en un año natural estándar, **@CalMonthLong** resuelve el mes **7** en **julio**. Si el nombre del mes está en mayúscula (por ejemplo **JULIO**), escriba el código de autotexto en caracteres en mayúscula en el campo **Texto del encabezado de columna**. Por ejemplo, escriba **@CALMONTHLONG**. Puede mezclar códigos y el texto. Por ejemplo, puede especificar el texto de encabezado siguiente: **Período @FiscalPeriod-@FiscalYear del @StartDate al @EndDate**. El encabezado del informe que se genera se asemeja al texto siguiente: **Período 1-02 desde 01/01/02 a 01/31/02**. **Nota:** El formato de parte del texto, como la fecha larga, depende de la configuración regional en el servidor de Finance and Operations. Para cambiar estos ajustes, haga clic en el botón **Iniciar**, haga clic en **Panel de control** y luego en **Región y idioma**. En la tabla siguiente se enumeran las opciones disponibles de autotexto para encabezados de columna.

| Opción y código de Autotexto                | Descripción                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre del mes (@CalMonthLong)              | Imprimir el nombre del mes actual en el encabezado de columna. Si decide redondear los importes del informe en millares, millones o billones, o si establece la anchura de columna en el informe a menos de nueve caracteres, el nombre del mes se abrevia a los primeros tres caracteres. |
| Nombre abreviado del mes (@CalMonthShort) | Imprimir el nombre abreviado del mes para el período fiscal seleccionado.                                                                                                                                                                                                                          |
| Número de período (@FiscalPeriod)           | Imprimir el formulario numérico del período fiscal que se identifica para dicha columna. Si la columna abarca varios períodos, el último período del intervalo es el que se imprime.                                                                                                                                   |
| Descripción del período (@FiscalPeriodName)  | Imprima la descripción del período fiscal que se identifica en los datos financieros.                                                                                                                                                                                                                    |
| Ejercicio (@FiscalYear)               | Imprimir el ejercicio para la columna en forma numérica.                                                                                                                                                                                                                                            |
| Año natural (@CalYear)                | Imprimir el calendario para la columna en forma numérica.                                                                                                                                                                                                                                          |
| Fecha inicial (@StartDate)                 | Imprimir la fecha inicial para la columna.                                                                                                                                                                                                                                                             |
| Fecha final (@EndDate)                     | Imprimir la fecha final para la columna.                                                                                                                                                                                                                                                               |
| Nombre de la unidad de organigrama (@UnitName)         | Si se restringe una columna a una unidad concreta del organigrama, imprima el nombre de la unidad en el encabezado de columna.                                                                                                                                                                                     |
| Descripción de la unidad (@UnitDesc)            | Si se restringe una columna a una unidad concreta del organigrama, imprima la descripción de la unidad en el encabezado de columna.                                                                                                                                                                              |
| Código de libro (@BookCode)                   | Imprima el código de libro que se especifica en la columna.                                                                                                                                                                                                                                             |
| Espacio en blanco (@Blank)                     | Inserte una línea en blanco en el encabezado de columna.                                                                                                                                                                                                                                                       |

### <a name="create-a-conditional-spanning-header"></a>Crear un encabezado de extensión condicional

Los encabezados de extensión condicionales pueden incluir varias columnas que se basan en datos específicos del período. Por ejemplo, si tiene un informe de presupuesto para el ejercicio y desea mostrar los presupuestos reales de pasados meses junto con los presupuestos proyectados de los meses futuros, puede usar un encabezado de extensión condicional para actualizar automáticamente el encabezado del informe. Tenga en cuenta las situaciones siguientes al crear un encabezado de expansión condicional:

-   Cualquier condición de detención (campo **Extensión hasta**) que coincida antes de que comience una condición de inicio (campo **Extensión desde**). Por ejemplo, la columna B tiene la condición de la extensión definida como BASE+1 a BASE, BASE se encuentra en la columna C, y BASE+1 se encuentra en la columna D. En este caso, la condición de detención en la columna C se ignora, y la impresión del encabezado comienza en la columna D.
-   Si especifica los encabezados de columna que se superponen, se superponen cuando se imprimen en el informe. Se genera el informe, pero la advertencia siguiente aparece en el campo **Estado de la cola del informe**: “Los encabezados de columna que usan Base se entrecruzan con otros encabezados de columna y pueden provocar texto entrecruzado.” Por ejemplo, la definición de cabecera en la columna B es B a BASE+1, y la definición de cabecera en la columna D es BASE+1 a F. En este caso, los encabezados se imprimen uno encima de otro y son ilegibles. Siempre que BASE se use en una definición **Extensión desde/Extensión hasta**, asegúrese de ver el informe que se genera, para ver si los encabezados se superponen.
-   Si especifica BASE en la definición de la extensión en una columna Sin impresión (**NP**), se ignora, independientemente de lo que se define en la definición de la columna. Esencialmente, este escenario es el mismo que no crear una definición del encabezado de columna.
-   Para las columnas condicionales de impresión (**P&lt;B**, **P&gt;=B**), los encabezados de extensión condicional se comportan como cualquier definición regular de encabezado de columna. Por ejemplo, si la condición es falsa, cualquier columna posterior coincidente para la condición de extensión inicia la impresión de cabecera.

#### <a name="create-a-conditional-spanning-header"></a>Crear un encabezado de extensión condicional

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en una celda de encabezado.
3.  En el cuadro de diálogo **Encabezado de columna**, escriba el texto del encabezado de columna. De forma alternativa, haga clic en **Inserta AutoTexto** y seleccione una opción.
4.   En el campo **Opciones de formato**, especifique un estilo de formato para el encabezado.
5.  Especifique un período en relación con el período de la base especificada cuando se genera el informe. En los campos **Extensión desde** y **Extensión hasta**, especifique uno de los siguientes valores: **BASE**, **BASE-X** o **BASE+X**, donde X es el número de períodos desde el período de la base. Por ejemplo, si especifica **BASE** en el campo **Extensión desde**, el texto de encabezado extensión adicional de columna empieza en el encabezado de columna donde el valor de **Período base** de la definición del informe es igual al valor de la definición **Período**. Finaliza en la columna que se indica en el campo **Extensión hasta**. Por lo tanto, si la extensión es BASE a M, y el valor de **Período de base** es **4**, el encabezado comienza en la columna en el período establecido en **4** y finaliza en la columna M. Los encabezados se detienen y comienzan en columnas de impresión solo.
6.  En **Justificación**, seleccione si el texto del encabezado de columna debe estar justificado a la izquierda, al centro o a la derecha.
7.  Haga clic en **Aceptar**.

#### <a name="example-of-a-conditional-spanning-header"></a>Ejemplo de un encabezado de extensión condicional

Fátima está creando un informe para una previsión de seis meses dinámica. Ella desea que la palabra “Real” se imprima encima de las columnas que contengan datos reales, y que la palabra “Presupuesto” se imprima encima de las columnas que contienen las previsiones de presupuesto. Cada mes que el informe se ejecuta, hay un columna más de real y una columna menos de presupuesto. Aunque Fátima puede modificar la definición de la columna manualmente cada vez que se genera el informe para ajustar los encabezados, para ahorrar tiempo y esfuerzo, decide crear encabezados de extensión condicional que van a crear automáticamente encabezados de las columnas adecuadas cada vez que el informe se ejecuta. Fátima abre al diseñador del informe, hace clic en **Definición de la columna** en el panel de navegación, y abre la definición de columna del informe. Luego, especifica información siguiente. El período de la base de la definición del informe es 4.

|                     | A    | mil millones             | C             | D             | E             | F             | G (Verde)             | H             | I             | J             | mil             | L             | M             |
|---------------------|------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|
| Encabezado 1            |      | Real        | Presupuesto        |               |               |               |               |               |               |               |               |               |               |
| Encabezado 2            |      | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong |
| Encabezado 3            |      |               |               |               |               |               |               |               |               |               |               |               |               |
| Tipo de columna         | DESC | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            |
| Código de libro/Atributo |      | REAL        | PRESUPUESTO2012    | REAL        | PRESUPUESTO2012    | REAL        | PRESUPUESTO2012    | REAL        | PRESUPUESTO2012    | REAL        | PRESUPUESTO2012    | REAL        | PRESUPUESTO2012    |
| Año fiscal         |      | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          |
| Período              |      | 1             | 1             | 2             | 2             | 3             | 3             | 4             | 4             | 5             | 5             | 6             | 6             |
| Períodos cubiertos     |      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      |
| Ancho de columna        | 30   | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            |
| Control de impresión       |      | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        |

Fátima hace clic en una celda de encabezado de columna para abrir el cuadro de diálogo **Encabezado de columna**, donde escribe la información siguiente.

| Campo              | Valor                 |
|--------------------|-----------------------|
| Texto del encabezado de columna | Real                |
| Insertar AutoTexto    | No se realiza ninguna selección. |
| Aplicar formato a las opciones     | Cuadro                   |
| Justificación      | No se realiza ninguna selección. |
| Extensión desde        | mil millones                     |
| Extensión hasta          | BASE                  |
| Encabezado del presupuesto      | BASE+1 para acabar columna  |

Después de que haya terminado de especificar la información, Fátima hace clic en **Aceptar**. Luego hace doble clic en la celda de encabezado de columna en la columna C para abrir el cuadro de diálogo **Encabezado de columna**, donde escribe la información siguiente.

| Campo              | Valor                 |
|--------------------|-----------------------|
| Texto del encabezado de columna | Presupuesto                |
| Insertar AutoTexto    | No se realiza ninguna selección. |
| Aplicar formato a las opciones     | Cuadro                   |
| Justificación      | No se realiza ninguna selección. |
| Extensión desde        | C                     |
| Extensión hasta          | BASE+2                |

Ahora, cada vez que se genere este informa, la palabra “Real” se imprimirá encima de las columnas que contengan datos reales, y la palabra “Presupuesto” se imprimirá encima de las columnas que contienen las previsiones de presupuesto. Además, el número de columnas se ajustará cada mes.

## <a name="apply-column-justification"></a>Aplicar justificación de columna.
La celda **Justificación** se usa para aplicar formato de justificación a una columna de la descripción en un informe. Esta opción solo afecta a las descripciones de la columna, no a los valores reales.

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en la celda **Justificación**.
3.  Seleccione uno de los siguientes valores en la lista:
    -   **Ninguno**: no se aplica justificación.
    -   **Izquierda**: las descripciones de la columna se alínean a la izquierda.
    -   **Centro**: las descripciones de la columna se ajustan al centro.
    -   **Derecha**: las descripciones de la columna se alínean a la derecha.

## <a name="add-special-formatting-options"></a>Agregar las opciones de formato especiales
En la definición de la columna, las filas de detalle de la columna de formato aplican formato especial en las columnas seleccionadas. Aunque algunas de las opciones de **Control de impresión** y **Restricciones de la columna** son específicas a las columnas **FD**, la mayoría de las opciones se aplican a todos los tipos de columna. El formato que se especifica en la definición de la columna anula el formato que se especifica en la definición del informe. Sin embargo, el formato que se especifica en la definición de la fila anula el formato que se especifica en la definición de la columna. Las filas siguientes se consideran filas de formato:

-   Ancho de columna
-   Espacios adicionales antes de la columna
-   Anulación de formato o de divisa
-   Control de impresión

### <a name="changing-the-column-width"></a>Cambio de la anchura de columna

La celda **Anchura de columna** especifica el número de caracteres que se usará para la anchura de esta columna en el informe impreso. La anchura de columna es importante para las columnas que contienen importes (columnas de tipo **CALC**, **WKS** o **FD**), descripciones (columnas de tipo **DESC**) o relleno (columnas de tipo **FILL**). De forma predeterminada, la opción **Ajustar automáticamente** está seleccionada, para ajustar la anchura de cada columna automáticamente para que se adapte al contenido.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>Especificar la anchura de una columna en un informe

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  En la celda **Anchura de columna**, especifique el número de espacios para la anchura de la columna. La anchura máxima de cualquier columna es de 255 caracteres (este número incluye céntimos, comas y paréntesis). También puede habilitar el diseñador de informes para seleccionar la anchura adecuada para la columna, en función del contenido de la celda, haga doble clic en la celda **Anchura de columna** y haga clic en **Ajustar automáticamente**.

### <a name="add-space-between-columns"></a>Agregar espacio entre columnas

La celda **Espacios adicionales antes de la columna** especifica la anchura del separador entre una columna y las columnas adyacentes en la definición de la columna. La configuración **Espacios adicionales antes de la columna** afecta a todas las filas de detalle de columna para la columna, pero no a las filas de cabecera de la columna. Use esta opción para separar los grupos de columnas o agregar algunos espacios antes de la descripción, para aplicar sangría a la columna de descripción de los encabezados alineados a la izquierda en el informe. El número predeterminado de espacios entre cada columna es dos. Puede cambiar este ajuste en la pestaña **Parámetros** de la definición del informe.

#### <a name="specify-the-space-between-columns"></a>Especificar el espacio entre las columnas

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  En la celda **Espacios adicionales antes de la columna**, especifique el número de espacios para insertar entre las columnas.

### <a name="specify-a-currency"></a>Especificar una divisa

La celda **Anulación de formato o de divisa** especifica el formato de decimal, divisa e importes de porcentaje de la columna. Este formato reemplaza el formato que se especifica en la definición del informe o valores predeterminados del sistema.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Asignar un reemplazo de divisa de formato a una columna de informe

1.  En el Diseñador de informes, abra la definición de columna que desee modificar.
2.  Haga doble clic en una celda **Reemplazo de formato o de divisa** en una columna de importe.
3.  En el cuadro de diálogo **Anulación de formato**, seleccione las opciones de formato.

### <a name="add-a-print-control-code"></a>Agregar un código de control de impresión

La celda **Control de impresión** puede contener los códigos que ajustan la visualización o las características de impresión de una columna. Existen dos tipos de códigos de control de impresión: códigos de control normales de impresión y códigos de control condicionales de impresión.

#### <a name="regular-print-control-codes"></a>Códigos de control regulares de impresión

| Código de control de impresión | Traducción                                     | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|--------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | No se imprime                                     | Excluir los importes en esta columna del informe que se imprime y de los cálculos. Para incluir una columna de no impresión en un cálculo, vaya a la columna directamente en la fórmula de cálculo. Por ejemplo, la columna C sin impresión se incluye en el cálculo siguiente: **B+C+D**. Sin embargo, la columna C sin impresión no se incluye en el cálculo siguiente: **B:D**.                                                                                                                                          |
| XCR                | Cambiar el signo si el saldos típico de la fila es crédito | Cree un presupuesto o informe comparativo donde cualquier variación desfavorable (como un déficit de ingresos o un gasto de saturación) es siempre negativo. Aplique este código a una columna **CALC** para invertir el signo del importe de la columna si el saldo típico de una fila en una determinada es un crédito (según se identifica por una **C** en la columna **Saldo normal** de la definición de filas). **Nota:** Para las filas **TOT** y **CAL** que mantienen normalmente saldos de crédito, asegúrese de especificar una **C** en la columna **Saldo normal** en la definición de filas. |
| X0                 | Eliminar la columna si son todos ceros o espacios en blanco          | Excluya una columna **FD** del informe si todas las celdas en la columna están en blanco o contienen ceros.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| SR                 | Eliminar redondeo                               | Evitar que los importes en esta columna se redondeen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| XR                 | Eliminar acumulación                                 | Eliminar una acumulación. Si el informe usa un organigrama, los importes en esta columna no se agrupan en nodos principales posteriores.                                                                                                                                                                                                                                                                                                                                                                                                   |
| RP                 | Repetir columna en cada página                      | Repita una columna especificada en cada página de un informe. Por ejemplo, puede usar el código de control de impresión **RP** para incluir a una columna de tipo **FILA** que tira en de códigos de fila en cada página.                                                                                                                                                                                                                                                                                                                                           |
| WT                 |  Encapsular texto                                      |  Si el texto en una columna es demasiado largo para ajustarse al espacio, encapsule todo el texto en la columna.                                                                                                                                                                                                                                                                                                                                                                                                                            |

#### <a name="conditional-print-control-codes"></a>Códigos de control de impresión condicionales

| Código de control de impresión condicionales | Descripción                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (ninguno)                         | Borre la selección condicional de impresión.                                                  |
| P&lt;B                         | Muestre una columna especificada solo si el período es menor que el período de la base.             |
| P&gt;B                         | Muestre una columna especificada solo si el período es mayor que el período de la base.             |
| P=B                            | Muestre una columna especificada solo si el período es igual al período de la base.              |
| P&lt;=B                        | Muestre una columna especificada solo si el período es menor o igual al período de la base. |
| P&gt;=B                        | Muestre una columna especificada solo si el período es mayor o igual al período de la base. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Agregar los códigos de control de impresión a una columna del informe

1.  En el Diseñador de informes, abra la definición de columna que desee modificar.
2.  Haga doble clic en la celda **Control de impresión**.
3.  En el cuadro de diálogo **Control de impresión** seleccione un código de la lista **Seleccionar las opciones de control de impresión**. Para seleccionar más de un código, mantenga presionada la tecla Ctrl mientras selecciona los códigos.
4.  Seleccione una opción en el campo **Opciones de impresión condicional**. De forma predeterminada, la opción **(ninguno)** está seleccionada. Solo puede seleccionar un código de impresión condicional cada vez.
5.  Haga clic en **Aceptar**.

> [!TIP]
> También puede escribir los códigos de impresión directamente en la celda **Control de impresión**. Separe varios códigos de control de impresión con una coma.


## <a name="column-types"></a>Tipos de columna
El tipo de información que cada columna en un informe incluye se especifica con el valor en la fila **Tipo de columna** en la definición de la columna. Cada definición de la columna debe contener el menos una columna de descripción (**DESC**) y una columna de importe (**FD**, **WKS** o **CALC**). **Nota:** Los códigos del tipo columna no se aplican a todos los sistemas contables. Si selecciona un tipo que no sea válido para su sistema contable, esa columna está en blanco en el informe.

### <a name="specify-a-column-type"></a>Seleccione un tipo de columna

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  En la columna correspondiente, haga doble clic en una celda en la fila **Tipo de columna**.
3.  Seleccione un tipo de columna en la lista. En la tabla siguiente se proporciona una descripción de los diferentes tipos de columnas.
    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Código de tipo de columna</th>
    <th>Descripción</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>FD</td>
    <td>Muestra datos financieros o de una hoja de cálculo de Excel cuando usa una columna <strong>Vínculo a dimensiones financieras</strong> o <strong>Vínculo a hoja de cálculo</strong> en la definición de fila. Si selecciona el tipo de columna <strong>FD</strong>, se especifica automáticamente la configuración predeterminada para las filas siguientes: <ul>
    <li><strong>Código del libro/Categoría de atributo:</strong> REAL</li>
    <li><strong>Código del libro/Categoría de atributo:</strong> REAL</li>
    <li><strong>Año fiscal:</strong> BASE</li>
    <li><strong>Período:</strong> BASE</li>
    <li><strong>Períodos cubiertos:</strong> PERIODIC</li>
    <li><strong>Ancho de columna:</strong> 14</li>
    </ul>
Es posible cambiar estos ajustes predeterminados.</td>
    </tr>
    <tr class="even">
    <td>CALC</td>
    <td>Muestre el resultado del cálculo simple o complejo que se especifique en la celda <strong>Fórmula</strong>. Para obtener más información, consulte <a href="advanced-formatting-options-financial-reporting.md">Opciones de formato avanzadas en informes financieros</a>.</td>
    </tr>
    <tr class="odd">
    <td>DESC</td>
    <td>Mostrar la descripción de la fila de la definición de filas. Aunque la columna de la descripción es a menudo la primera columna en el informe, puede estar en cualquier puesto.</td>
    </tr>
    <tr class="even">
    <td>FILA</td>
    <td>Mostrar los códigos individuales de la fila para las filas financieras de la columna <strong>Código de la fila</strong> de la definición de filas. Para obtener más información, consulte <a href="row-definitions-financial-reporting.md">Definiciones de filas en informes financieros</a>.</td>
    </tr>
    <tr class="odd">
    <td>ACCT (Códigos de cuenta)</td>
    <td>Mostrar los valores de dimensión o los valores del segmento de datos financieros que se aplican a cada fila. Para los informes detallados de cuentas y transacciones, se imprimirá la cuenta completa (por ejemplo, <strong>110140-070-0101</strong>). Si se especificaron intervalos en la columna <strong>Vínculo a dimensiones financieras</strong> de una definición de fila asociada, el intervalo se encierra en corchetes y se trata como un solo valor (por ejemplo, <strong>[110140:110700]-070-[0101:0200]</strong>). Para los informes financieros y de alto nivel que son una combinación de varias cuentas, se imprime el vínculo de datos financieros de la definición de fila (por ejemplo, <strong>1100:1200</strong>).</td>
    </tr>
    <tr class="even">
    <td>RELLENO</td>
    <td>Rellene la celda con un carácter que se va a incluir entre comillas simples. Si no especifica un carácter, la columna está vacía. Por ejemplo, para rellenar una columna con puntos suspensivos (...), escriba. <strong>RELLENAR</strong> <strong>'.'</strong>.</td>
    </tr>
    <tr class="odd">
    <td>PÁGINA</td>
    <td>Insertar un salto de página vertical en el informe. Las columnas que están a la derecha de la columna <strong>PAG</strong> aparecen en una página diferente.</td>
    </tr>
    <tr class="even">
    <td>WKS</td>
    <td>Visualizar datos que se tiran de una hoja de cálculo de Excel. Si selecciona el tipo de columna <strong>HOJ</strong>, se especifica automáticamente la configuración predeterminada para las filas siguientes: <ul>
    <li><strong>Año fiscal:</strong> PERIODIC</li>
    <li><strong>Período:</strong> BASE</li>
    </ul>
Es posible cambiar estos ajustes predeterminados.</td>
    </tr>
    <tr class="odd">
    <td>ATTR</td>
    <td>Si su sistema contable admite atributos, se muestra una cuenta o un atributo de la transacción en la columna. Un atributo, que se debe aplicar a una única cuenta completa, extrae información de transacciones o de la cuenta subyacente de los datos financieros. Los atributos de nivel de cuenta muestran los datos de la cuenta y los atributos de nivel de transacción muestran los datos que se produjeron en el momento de registrar la transacción. Si selecciona <strong>ATR</strong> como tipo de columna, especifique la categoría de atributo en la fila de detalle <strong>Categoría de código del libro o atributo</strong> de la definición de columna.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Columna de dimensiones financieras

Las siguiente definiciones de fila **Definición de la columna** se aplican a las columnas que tengan un tipo de columna **FD** (Importes de dimensiones financieras).

#### <a name="book-codeattribute-category-cell"></a>Celda de Código de libro/Categoría de atributo

La celda **Código de libro/Categoría de atributo** identifica el código de libro para los datos en la columna **FD**. Una definición de la columna puede incluir varias columnas reales, el presupuesto y columnas estadísticas. Una definición de la columna puede mostrar también diferentes períodos, como actual o a la fecha, y distintos importes. La lista de códigos del libro refleja las opciones reales, de presupuesto y estadísticas (no financieras) que se han establecido en sus datos financieros.

#### <a name="fiscal-year-cell"></a>Celda de ejercicio

La celda **Ejercicio** identifica el ejercicio que la columna debe incluir. El año puede ser en relación con el año de la base especificada cuando se genera el informe. Están disponibles las siguientes opciones.

| Opción  | Descripción                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| BASE    | Use el año de la base especificada en el momento del informe.                                                                          |
| BASE+\# | Use el año que es \# años después del año de la base. Por ejemplo, para usar el tercer año después del año base, escriba **BASE+3**. |
| BASE-\# | Use el año que es \# años antes del año de la base. Por ejemplo, para usar el último año, escriba **BASE-1**.                 |
| \#      | Especifique el ejercicio real.                                                                                                |

#### <a name="period-cell"></a>Celda del período

La celda **Período** identifica los períodos fiscales que la columna debe incluir. El período puede ser relativo al período de la base especificada cuando se genera el informe. Están disponibles las siguientes opciones.

| Opción          | Descripción                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BASE            | Use el período de la base.                                                                                                                                                                                                                 |
| BASE+\#         | Use el período que es \# períodos después del período de la base. Por ejemplo, para usar el tercer período después del período base, escriba **BASE+3**.                                                                                               |
| BASE-\#         | Use el período que es \# períodos antes del período de la base. Por ejemplo, para usar el último período, escriba **BASE-1**.                                                                                                                 |
| BASE-\#:BASE    | Use varios períodos, a partir de varios períodos anteriores al período de base hasta el período de la base. Por ejemplo, para usar los tres períodos anteriores y el período de base, escriba **BASE-3:BASE**.                                                |
| BASE:BASE+\#    | Use varios períodos, a partir del período de la base hasta varios períodos después del período de base. Por ejemplo, para usar el período de base y los siguientes dos períodos, escriba **BASE:BASE+2**.                                                  |
| BASE-\#:BASE+\# | Use varios períodos, a partir de varios períodos anteriores al período de base hasta varios períodos después del período de la base. Por ejemplo, para usar los tres períodos previos, el período de la base y los siguientes dos períodos, escriba **BASE-3:BASE+2**. |
| 1:BASE          | Use varios períodos, a partir del primer período hasta el período de base.                                                                                                                                                                 |
| \#              | Use siempre un número específico del período. No se recomienda que use esta opción, ya que reduce la flexibilidad de la definición de la columna.                                                                                       |
| \#:\#           | Use siempre un intervalo específico de períodos. No se recomienda que use esta opción, ya que reduce la flexibilidad de la definición de la columna.                                                                                    |

Puede ir más allá de los límites del ejercicio en cualquiera de las especificaciones de período, y puede mezclar años en un intervalo de períodos. Poor ejemplo, se especifican los períodos como **BASE-5** (para representar los últimos seis períodos) y se ejecuta un informe que tenga un período de base de 2. En este caso, el informe muestra los datos para los dos primeros períodos del ejercicio especificado y los cuatro últimos períodos del ejercicio anterior.

### <a name="specify-the-periods-for-an-fd-column"></a>Especificar los períodos de una columna FD

1.  En el Diseñador de informes, abra la definición de columna que desee modificar.
2.  En la columna **FD**, haga doble clic en la celda en la fila **Período**, y seleccione una opción en la lista.
3.  En la barra de fórmula encima del panel de navegación, o en la celda **Período**, complete la fórmula. Sustituya cualquier signo de número (\#) por el valor adecuado.

#### <a name="periods-covered-cell"></a>Celda de Período de cobertura

La celda **Períodos cubiertos** identifica lo importe que la columna debe mostrar. Este importe se encuentra en relación con el valor en las celdas **Ejercicio** y **Período** de la columna. Están disponibles las siguientes opciones.

| Opción      | Descripción                                                                 |
|-------------|-----------------------------------------------------------------------------|
| PERIÓDICO    | Muestra la suma de la actividad para el período actual o el intervalo de períodos. |
| PERIÓDICO/BB | Muestra el saldo inicial para el período actual o el intervalo de períodos.   |
| Ejercicio a fecha         | Visualice la suma de la actividad a fecha.                               |
| YTD/BB      | Muestra los saldos iniciales del año.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Especifique los períodos que están cubiertos para una columna de FD

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  En la columna **FD**, haga doble clic en la celda en la fila **Períodos cubiertos** y luego seleccione una opción en la lista.

### <a name="attribute-filter-in-a-column-definition"></a>El filtro del atributo en una definición de la columna

Los atributos son valores de los datos que definen más aún una cuenta o una transacción. Los atributos de la cuenta incluyen **Activo**, **Pasivo**, **Ingresos** y **Gastos**. Los atributos de transacción incluyen **Descripción de la transacción** y **Fecha de aplicación de la transacción**. La compatibilidad del atributo puede diferir entre los sistemas ERP de Microsoft Dynamics AX. La celda **Filtro del atributo** restringe los datos en las columnas **FD** a los valores o a los intervalos específicos para las categorías del atributo. Aunque esta característica se pueda usar junto con la columna **ATTR**, la columna **ATTR** no se requiere. En la columna **FD**, hay un límite en las cuentas o las transacciones que el informe incluirá del filtro del atributo. **Nota:** Para ver qué atributos son compatibles con el sistema ERP, consulte la guía de integración para su sistema.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Aplicar un filtro de atributos para una columna de FD en un informe

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en la celda **Filtro de atributos** de una columna **FD**.
3.  En el cuadro de diálogo **Filtro de atributos**, haga doble clic en la celda de la columna **Atributo** y seleccione el tipo de filtro.
4.  Para limitar más los resultados, especifique un intervalo en las columnas **Desde** y **Hasta**. La celda **Desde** debe contener un valor.
5.  Haga clic en **Aceptar**.

#### <a name="example-of-an-attribute-filter"></a>Ejemplo de un atributo de filtro

En el ejemplo siguiente se muestra parte de una descripción de la columna que tiene un atributo de la cuenta en la fila **Código del libro/categoría del atributo**. El filtro de atributos para esta columna especifica el intervalo de valores para incluir en el informe.

|                              | A    | B                    |
|------------------------------|------|----------------------|
| Tipo de columna                  | DESC | FD                   |
| Código del libro/Categoría de atributo |      | REAL               |
| Año fiscal                  |      | BASE                 |
| Período                       |      | 1:BASE               |
| Períodos cubiertos              |      | PERIÓDICO             |
| ...                          |      |                      |
| Ancho de columna                 | 30   |                      |
| ...                          |      |                      |
| Filtro de atributo             |      |  Referencia=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>El filtro de la dimensión en una definición de la columna

Un filtro de la dimensión se usa para restringir la columna **FD** a los valores de dimensión específicos. El filtro puede incluir una sola dimensión, un intervalo de dimensiones o un grupo de dimensiones. El filtro también puede incluir sistemas del valor de dimensión. Dado que los valores de dimensión pueden variar, un sistema basado en la dimensión..\financial-dimensions\ no tiene que corresponder con una duración exacta. El filtro se aplica, independientemente de si el informe incluye un organigrama. Puede usar un carácter comodín (\* o ?) en cualquier puesto. Cuando especifique varias cuentas, ponga una coma entre las cuentas, como en el ejemplo siguiente: +Cuenta=\[1200\], +Cuenta=\[1100\], Departamento=\[01?\] Para recibir todos los departamentos para una cuenta específica, puede excluir la dimensión de departamento del filtro de la dimensión. Por ejemplo, los dos filtros siguientes de la dimensión se gestionan de la misma manera:

-   +Cuenta=\[1100\],Departamento
-   +Cuenta=\[1100\]

También puede usar cualquier combinación de caracteres alfanuméricos para una coincidencia exacta y puede definir dimensiones parciales. Por ejemplo, **Ubicación = \[10\*\]** incluye todos los valores de dimensión de la ubicación que comiencen por 10.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Aplicar un filtro de la dimensión para una columna de un informe

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en la celda **Filtro de la dimensión** para una columna **FD**.
3.  En el cuadro de diálogo **Dimensiones**, especifique los filtros para aplicar.
4.  Haga clic en **Aceptar**.

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Aplicar formato a un informe de varias divisas en una definición de la columna

Un informe de varias divisas puede mostrar importes en la divisa natural (local), la divisa funcional (predeterminada) o la divisa de notificación. La divisa funcional de una empresa se define en el sistema de Microsoft Dynamics ERP. No confunda esta configuración de ERP con las opciones de configuración regionales del sistema operativo, donde puede configurar los símbolos de la divisa predeterminada que se usan en los informes. Las siguientes celdas relacionadas con la divisa están disponibles en la definición de la columna:

-   **Visualización de divisa**: especificar el tipo de divisa (natural, funcional o de notificación) en que muestran las transacciones. Esta función se denomina a veces traducción de la divisa. La traducción de la divisa es la capacidad de notificar importes de la contabilidad general en una divisa que puede no ser la divisa funcional de la empresa o la divisa en que se registró la transacción.
-   **Filtro de la divisa**: especifique un filtro de la divisa. Solo las transacciones que se especifican en la divisa seleccionada se muestran en el informe.

> [!NOTE]
> Para crear informes que usan varias divisas, debe seleccionar la casilla de verificación **Incluir todas las divisas de notificación** en la pestaña **Informe** de la definición del informe. Para determinar la divisa funcional de una empresa, siga estos pasos.

1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Empresas**.
2.  En el cuadro de diálogo **Empresas**, seleccione una empresa, y haga clic en **Ver**.
3.  En el cuadro de diálogo **Ver empresa**, en **Opciones regionales**, puede ver la divisa que se define para la empresa seleccionada.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Especificar la divisa en un informe de varias divisas

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  Haga doble clic en la celda **Visualización de divisa** en a columna **FD** correspondiente, y seleccione la opción para mostrar la información de divisa: **Divisa natural/originaria**, **Divisa funcional de la información de empresa** o divisa de notificación.
3.  Haga doble clic en la celda **Filtro de la divisa** en la columna **FD** correspondiente, y seleccione el código de divisa correspondiente en la lista. Solo las transacciones que se especifican en esta divisa se muestran en el informe.

> [!NOTE]
> Las opciones que se describen aquí pueden variar, en función del sistema ERP. Para obtener más información, consulte [Documentación del sistema de ERP de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=5916).

### <a name="example-for-currency-display-and-currency-filter-cells"></a>Ejemplo para las celdas de visualización de la divisa y filtro de la divisa

Fátima ha realizado las siguientes selecciones de divisa en la definición de la columna:

-   **Filtro de la divisa:** Yen
-   **Visualización de divisa:** Funcional (dólares estadounidenses).

Debido al filtro de la divisa que Fátima ha seleccionado, el informe incluye solo las transacciones especificadas en yenes japoneses (JPY). Debido a la visualización de la divisa que ha seleccionado, el informe muestra las transacciones en la divisa funcional, dólares estadounidenses (USD).

#### <a name="currency-filter-and-currency-display-combinations"></a>Combinaciones del filtro de la divisa y la visualización de la divisa

En la tabla siguiente se muestran los resultados del informe en los que se puede producir diferentes combinaciones de las opciones en las celdas **Visualización de divisa** y **Filtro de la divisa** debido a las selecciones que Fátima ha realizado. La divisa funcional es USD.

| Celda de visualización de divisa                        | Celda de filtro de la divisa | Resultado del informe                                                                                                                                                                                    |
|----------------------------------------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Divisa natural u originaria                 | **YEN**              | **Y6.000**: el resultado muestra solo las transacciones especificadas en JPY.                                                                                                                        |
| Divisa funcional de la información de empresa | **YEN**              | **$60**: el resultado muestra solo las transacciones especificadas en JPY y muestra esas transacciones en USD. **Nota:** el índice de conversión es aproximadamente 100 JPY por USD.                    |
| Divisa funcional de la información de empresa | Vacía                | **$2.310\*\***: el resultado muestra todos los datos en la divisa funcional que se especifica en la información de empresa. **Nota:** este importe es la suma de todas las transacciones en divisa funcional. |
| Divisa natural u originaria                 | Vacía                | **$2.250**: el resultado muestra todos los importes en la divisa en la que se ha realizado la transacción.                                                                                                 |

### <a name="calculation-column-in-a-column-definition"></a>Columna de cálculo en una definición de columna

Un tipo de columna de **CALC** en una definición de la columna admite cálculos complejos en la celda **Fórmula**, y puede incluir los operadores **+**, **-**, **\*** y **/**, y también las expresiones **IF/THEN/ELSE**. Una columna de cálculo también puede hacer referencia a cualquier otra columna, incluso a columnas posteriores. Además, una columna de cálculo también puede incluir el ejercicio y el período para admitir los encabezados de la columna. La fórmula de cáculo puede tener hasta 1.024 caracteres. Para expresar el resultado del cálculo como porcentaje, use una anulación especial del formato. **Nota:** los resultados de fórmulas de cálculo no incluyen los valores en intervalos sin impresión de la columna. Por ejemplo, **A:D** imprime **0** (cero), mientras que **A+B+C** para valores sin impresión calcula el valor.

#### <a name="operators-in-calculation-columns"></a>Operadores en columnas de cálculo

Para sumar, restar, multiplicar o dividir columnas, especifique las letras de la columna en el orden de cómputo, y después use el operador adecuado para separar cada letra de columna. La siguiente tabla explica los operadores que puede usar en una columna de cálculo.

| Operador | Ejemplo de cálculo | Descripción                                                                                                                                                                                                                                    |
|----------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| +        | A+C                 | Sume el importe en la columna A al importe en la columna C.                                                                                                                                                                                          |
| :        | A:C A:C-D           | Sume un intervalo de columnas consecutivas. Por ejemplo, la fórmula **A:C** agrega las sumas de las columnas A a la C, y la fórmula **A:C-D** agrega las sumas de las columnas A a la C, y después resta el importe en la columna D.                          |
| -        | A-C                 | Resta el importe en la columna A al importe en la columna C. **Nota:** También puede usar el signo menos (-) para invertir los signos en una columna. Por ejemplo, use **- A+B** para sumar el contrario del importe en la columna A all importe en la columna B. |
| \*       | A\*C                | Multiplique el importe en la columna A por importe en la columna C.                                                                                                                                                                                     |
| /        | A/C                 | Divida el importe en la columna A por importe en la columna C.                                                                                                                                                                                       |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Usar una fórmula de cálculo en una definición de columnas

1.  En el diseñador de informes, abra la definición de la columna para modificarla.
2.  En la columna **CALC** correspondiente, especifique una fórmula en la celda **Fórmula**.

#### <a name="complex-calculations"></a>Cálculos complejos

Un cálculo complejo puede incluir cualquier combinación de referencias, operadores, valores y niveles de paréntesis jerarquizados de celdas Por ejemplo, para computar la media de las columnas A y B, use la fórmula **((A+B)/2)** de cálculo.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Especificar celdas de informe en el cálculo de la columna

Puede hacer referencia a una celda específica del informe introduciendo una letra de la columna y un código de la fila. Por ejemplo, **B.100** hace referencia al código 100 de la fila en la columna B. Puede dividir una columna completa por un importe específico de la celda de informe que se encuentre en la misma columna. Por ejemplo, el cálculo **B/B.100** significa que el importe en la columna B se debe dividir por el valor del código 100 de la fila en la columna B. Si el cálculo hace referencia a una columna que dependa de otra columna, la columna dependiente se resuelve primero. Si refiere una columna a otra columna que hace referencia a la primera columna, se producirá un error de referencia circular. **Nota:** el cálculo puede ser erróneo si cambia la prioridad de cálculo para el informe. Puede establecer la prioridad de cálculo en la pestaña **Parámetros** de la definición del informe.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Multiplicar o dividir una columna por una fila de base

Puede crear una columna que muestre todos los valores en una columna especificada como un porcentaje de un número de la base. Por lo tanto, puede mostrar relaciones entre las filas, como un porcentaje de una fila de ventas o un porcentaje de una fila de los gastos totales. Para multiplicar o dividir cada fila en una columna específica por una fila base, especifique la columna para usar en el cálculo y, a continuación, escriba **\*BASEROW** o **/BASEROW**. Por ejemplo, escriba **C\*BASEROW** o **C/BASEROW**. **Nota:** cuando usa un cálculo de la fila base en una definición de la columna, asegúrese de que cada definición de fila que se usa con esta definición de columna contiene el menos una fila de la base para los cálculos.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Dividir el importe en una columna por el número de períodos

Puede dividir el importe en una columna por un número de períodos específico. Por ejemplo, la fórmula **B/Períodos** divide el valor de la columna B por el número de períodos en la columna B. Si el cálculo abarca varias columnas, especifique el número de períodos para usar en el cálculo. Por ejemplo, la fórmula **(B+C)/Períodos** suma los importes en la columna B y la columna C, y después divide el resultado por el valor de período.

<a name="see-also"></a>Consulte también
--------

[Definiciones de filas en informes financieros](row-definitions-financial-reporting.md)

[Opciones de formato avanzadas en informes financieros](advanced-formatting-options-financial-reporting.md)




