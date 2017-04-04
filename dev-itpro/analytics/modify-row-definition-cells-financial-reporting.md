---
title: "Modifique las celdas de definición de filas"
description: "En este artículo se describe la información que se requiere para cada celda de una definición de fila en un informe financiero y se explica cómo escribir esa información."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-07 16 - 09 - 06
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Management Reporter, Core
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: b61364c9055e5c5a63592c7f05551d0c145924b9
ms.lasthandoff: 03/29/2017


---

# <a name="modify-row-definition-cells"></a>Modifique las celdas de definición de filas

En este artículo se describe la información que se requiere para cada celda de una definición de fila en un informe financiero y se explica cómo escribir esa información. 

# <a name="specify-a-row-code-in-a-row-definition"></a>Especifique un código de fila en una definición de filas

En las definiciones de filas, los números o las etiquetas en la celda **Código de la fila** identifican cada línea en la definición de filas. Puede especificar el código de la fila para hacer referencia a datos en los cálculos y los totales.

### <a name="row-code-requirements"></a>Requisitos de código de fila

Se requiere un código de fila para todas las filas. Puede mezclar códigos de filas numéricos, alfanuméricos y no establecidos (vacíos) en una definición de fila. El código de fila puede ser cualquier número entero positivo (menor de 100.000.000) o una etiqueta descriptiva que identifique esa fila. Una etiqueta descriptiva debe seguir estas reglas:

-   La etiqueta debe comenzar por un carácter alfabético (de la a a la z o de la A a la Z) y puede ser cualquier combinación de números y de letras hasta 16 caracteres. ** Nota: ** Una etiqueta puede incluir el carácter de subrayado (\_), pero no se permiten más caracteres especiales.
-   La etiqueta no puede usar ninguna de las siguientes palabras reservadas: AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO o RPO.

Los siguientes ejemplos son códigos válidos de fila:

-   320
-   INGRESO de TL NET\_\_
-   NET TL\_\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Cambiar un código de fila en una definición de filas

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  En la fila correspondiente, especifique el nuevo valor en la celda en la columna **Código de la fila**.

### <a name="reset-numeric-row-codes"></a>Restablecer los códigos numéricos de la fila

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  En el menú **Editar**, haga clic en **Renumerar filas**.
3.  En el cuadro de diálogo **Renumerar filas**, especifique los nuevos valores para el código de la fila de inicio y el incremento del código de la fila. Puede restablecer los códigos numéricos de la fila a valores equidistantes. Sin embargo, el diseñador de informes renumera solo los códigos de fila que empiecen por números (por ejemplo 130 o 246). No vuelve a numerar los códigos de la fila que empiezan con las letras (por ejemplo, INGRESO\_93 o TP0693). **Nota:** cuando se renumeran códigos de la fila, el diseñador de informes automáticamente las referencias **TOT** y **CAL**. Por ejemplo, si una fila **TOT** hace referencia a un intervalo que empiece por el código 100 de la fila y se renumeran las filas, empezando por 90, la referencia **TOT** cambia del 100 al 90.

## <a name="add-a-description"></a>Agregar una descripción
La celda de la descripción ofrece una visión general de los datos financieros en la fila del informe, como “ingresos” o “ingresos netos.” El texto en la celda **Descripción** aparece en el informe exactamente como se ha especificado en la definición de filas. **Nota:** la anchura de la columna de la descripción en el informe se establece en la definición de la columna. Si el texto en la columna de **Descripción** en la definición de filas es largo, compruebe la anchura de la columna **DESC**. Cuando se usa el cuadro de diálogo **Insertar filas desde**, los valores en la columna **Descripción** son los valores de segmento o los valores de dimensión de los datos financieros. Puede insertar filas para agregar texto descriptivo, como un título de sección o un total de sección, y para agregar formato, como una línea antes de una fila de total. Si el informe incluye un organigrama, puede incluir el texto adicional que está definido para las unidades de notificación en el organigrama. También puede limitar el texto adicional a una unidad de notificación específica.

### <a name="add-the-description-for-a-line-on-a-report"></a>Agregar la descripción de una línea en un informe

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Seleccione la celda **Descripción** y especifique el nombre de la fila del informe.
3.  Aplique el formato.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Agregue el texto adicional de un organigrama en la visión general

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Especifique el código de texto adicional y cualquier otro texto en la celda **Descripción** apropiada.
3.  Aplique el formato.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Limitar el texto adicional a una unidad de notificación específica

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Localice la fila donde el texto adicional debe ser creado, y después haga doble clic en la celda en la columna **Fórmulas, filas o unidades relacionadas**.
3.  En el cuadro de diálogo **Selección de la unidad de notificación**, en el campo **Organigrama**, seleccione un organigrama.
4.  En el campo **Selección de organigrama para restricción**, expanda o contraiga el organigrama y seleccione un organigrama.

## <a name="add-a-format-code"></a>Agregar un código de formato
La celda **Código de formato** ofrece una selección de opciones preformateadas para el contenido de la fila. Si la celda **Código de formato** está en blanco, se interpreta la fila como una fila de datos financieros. **Nota:** si un informe contiene filas de formato sin importe que no están relacionadas con las filas de importe que se han eliminado (por ejemplo debido al saldo cero), puede usar la columna **Fórmulas, filas o unidades relacionadas** para evitar que las filas de cabecera y de formato se impriman.

### <a name="add-a-format-code-to-a-report-row"></a>Agregar un código de formato a una fila del informe

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después seleccione una definición de fila para modificarla.
2.  Haga doble clic en la celda **Código del formato**.
3.  Seleccione un código de formato en la lista. La tabla siguiente describe los códigos de formato y sus acciones.
    | Código de formato                   | Interpretación del código del formato | Acción|
    |---|---|---|
    | (Ninguno)                        |                                    | Borra la celda **Código de formato**.                                                                                                                                                                               |
    | TOT                           | Total                              | Identifica una fila que usa operadores matemáticos en la columna **Fórmulas, filas o unidades relacionadas**. Los totales contienen operadores simples, por ejemplo ** **+o-** **.                                                      |
    | CAL                           | Cálculo                        | Identifica una fila que usa operadores matemáticos en la columna **Fórmulas, filas o unidades relacionadas**. Los cálculos contienen operadores complejos, por ejemplo+** **, ** **-,\*** **, ** **/, y ** IF/THEN/ELSE ** las instrucciones. |
    | DES                           | Descripción                        | Identificar una línea de encabezado o una línea en blanco en un informe.                                                                                                                                                        |
    | LFT RGT CEN                   | Izquierda Derecha Centro                  | Alínea el texto de la descripción de la fila en la página del informe, independientemente de la colocación del texto en la definición de la columna.                                                                                               |
    | CBR                           | Cambiar la fila de base                    | Identifica una fila que define la fila de base para los cálculos de la columna.                                                                                                                                               |
    | COLUMNA                        | Salto de columna                       | Inicia una nueva columna en el informe.                                                                                                                                                                             |
    | PÁGINA                          | Salto de página                         | Inicia una nueva página en el informe.                                                                                                                                                                               |
    | ---                           | Subrayado simple                   | Pone una única línea debajo de todas las columnas de importe en el informe.                                                                                                                                                     |
    | ===                           | Subrayado doble                   | Pone dos líneas debajo de todas las columnas de importe en el informe.                                                                                                                                                     |
    | LINE1                         | Línea fina                          | Dibuja una única línea fina en la página.                                                                                                                                                                      |
    | LINE2                         | Línea gruesa                         | Dibuja una única línea gruesa en la página.                                                                                                                                                                     |
    | LINE3                         | Línea de puntos                        | Dibuja una única línea de puntos en la página.                                                                                                                                                                    |
    | LINE4                         | Línea gruesa y línea fina           | Dibuja una línea doble en la página. La línea superior es gruesa y la de abajo es fina.                                                                                                                       |
    | LINE5                         | Línea fina y línea gruesa           | Dibuja una línea doble en la página. La línea superior es fina y la de abajo es gruesa.                                                                                                                       |
    | BXB BXC                       | Fila encajonada                          | Dibuja una caja alrededor de las filas del informe que empiezan por la fila **BXB** y acaban por la fila **BXC**.                                                                                                               |
    | REM                           | Comentario                             | Identifica una fila que es una fila de comentarios y no se debe imprimir en el informe. Por ejemplo, una fila de observación puede explicar sus técnicas de formato.                                                            |
    | SORT ASORT SORTDESC ASORTDESC | Ordenar                               | Ordena gastos o ingresos, ordena un informe de desviación del presupuesto real por desviación mayor u ordena las descripciones de fila alfabéticamente.                                                                   |

## <a name="specify-related-formulasrowsunits"></a>Especificar fórmulas, filas o unidades relacionadas
La celda **Fórmulas, filas o unidades relacionadas** tiene varios objetivos. En función del tipo de fila, una celda de **Fórmulas, filas o unidades relacionadas** puede realizar una de las funciones siguientes:

-   Defina las filas que desea incluir en un cálculo cuando usa un código de formato **TOT** o **CAL**.
-   Vincule una fila de formato a una fila de importe, de forma que se imprima el formato solo cuando se imprime el importe relacionado.
-   Limita una fila a una unidad de notificación específica.
-   Defina la fila de base para los cálculos cuando use el código de formato **BASEROW**.
-   Defina las filas que desea clasificar cuando usa alguno de los códigos de formato de ordenación.

### <a name="use-a-row-total-in-a-row-definition"></a>Usar un total de filas en una definición de filas

Use una fórmula de totales de fila para agregar o restar importes en otras filas. Una fórmula para crear un total de fila puede incluir los operadores + y - para combinar códigos e intervalos de fila individuales. Los intervalos se indican con dos puntos (:). La fórmula puede contener hasta 1.024 caracteres. Aquí hay un ejemplo de una fórmula estándar de balance: 400+420+430+450+460LIABILITIES+EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>Componentes de una fórmula total de la fila

Cuando se crea una fórmula total de la fila, se deben usar códigos de fila para especificar las filas que se agregan o se restan en la definición de filas actual, y se deben usar operadores para especificar cómo se combinan las filas. Las filas del total y las filas de importe se pueden usar en cualquier combinación. **Nota:** se excluyen todas las filas del total que se encuentran en un intervalo. Para crear un total general, puede especificar el intervalo de filas. Si la primera fila de un intervalo es una fila del total, esa fila se incluye en el nuevo total. La siguiente tabla describe cómo se usan los operadores en fórmulas de total de las filas.

| Operador | Fórmula de ejemplo | Descripción                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Agrega el importe de la fila 100 al importe de la fila 330.        |
| :        | 100:330         | Agrega los totales de todas las filas entre la fila 100 y la fila 330.    |
| -        | 100-330         | Resta el importe de la fila 100 del importe de la fila 330. |

### <a name="create-a-row-total"></a>Crear un total de fila

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Haga doble clic en la celda **Código de formato** en la definición de filas y seleccione **TOT**.
3.  En la celda **Fórmulas, filas o unidades relacionadas**, especifique la fórmula total.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relacionar una fila de formato a una fila de importe

En ** código de formato ** la definición de la columna en una fila, ** DES **, ** LFT **, ** RGT **, ** CEN **, ** **---,===y ** ** códigos de formato aplica de filas de formato el importe no. Para evitar que el formato se imprima cuando se eliminan las filas del importe relacionado (por ejemplo porque las filas del importe contienen valores cero o ninguna actividad del período), debe relacionar las filas de formato a las filas de importe correspondientes. Esta función es útil si desea evitar que se impriman encabezados o formato relacionados con subtotales cuando no hay detalles a imprimir para el período. **Nota:** también puede evitar que se impriman las filas de importe detalladas desactivando la opción de mostrar filas sin importes. Esta opción se encuentra en la pestaña **Configuración** de la definición del importe. De forma predeterminada, las cuentas de detalle de transacción con saldo cero o ninguna actividad del período se eliminan en los informes. Para mostrar estas cuentas de detalle de transacción, active la casilla **Mostrar filas sin importes** en la pestaña **Configuración** de la definición del informe.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relacionar una fila de formato a una fila de importe

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después seleccione una definición de fila para modificarla.
2.  En la fila de formato, en la celda **Fórmulas, filas o unidades relacionadas**, especifique el código de fila de la fila de importe que se desea eliminar. **Nota:** para eliminar una fila de importe, el saldo de la fila debe ser 0 (cero). Una fila de importe que tiene un saldo no se elimina.
3.  En el menú **Archivo**, haga clic en **Guardar**.

### <a name="example-of-preventing-printing-of-rows"></a>Ejemplo de cómo evitar la impresión de filas

En el siguiente ejemplo, Fernanda quiere evitar que se imprima el encabezado y los subrayados en la fila **Efectivo total** del informe porque no ha habido actividad en ninguna de las cuentas de efectivo. Por tanto, en la fila 220 (que, mientras que **---** el código de formato indica, es una fila del formato), en ** las fórmulas o las filas o las unidades relacionadas ** la celda ella, especifica 250 ** **, que es el código de la fila del importe de la fila que ella desea suprimir. ![RelatedRowsRowDefinition [] (. /media/relatedrowsrowdefinition-1024x144.png])(. /media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Seleccionar la fila de base para el cálculo de una columna
En los informes relacionales, se asignan una o varias filas de base en la definición de filas usando el código de formato **CBR** (fila de la base de cambio). ULuego se hace referencia a una fila de base en la definición de la columna. Algunos ejemplos típicos de cálculos de CBR:

-   Porcentaje de los ingresos totales según están relacionados a elementos individuales de ingresos
-   Porcentaje de los gastos totales según están relacionados a elementos individuales de gastos
-   Porcentaje del margen bruto según está relacionado a los detalles de la división o del departamento.

Una o varias filas de base se definen en la definición de filas y luego la definición de columnas determina la relación en la que se notifica la fila base. El código que se usa en la fórmula de la columna es **BASEROW**. Se usan las siguientes operaciones matemáticas básicas con **BASEROW**: división, multiplicación, suma o resta. La operación que se usa más es a menudo dividir entre **BASEROW**, donde el resultado se muestra como porcentaje. Los cálculos de columna que usan **BASEROW** en la fórmula, usan la definición de filas para los códigos de fila de base relacionados. Las filas de **CBR** tienen las siguientes características:

-   Las filas de **CBR** no se imprimirán en el informe completado.
-   El código de formato de **CBR** y su código de fila relacionado se colocan encima de la fila o la sección que muestra los cálculos relacionados.

En una definición de columna, el tipo de columna **CALC** indica una columna que especifique una fórmula en la fila **Fórmula**. Esta fórmula trabaja con los datos para esta columna del informe y usa la palabra clave de Baserow para basar los cálculos en los códigos de formato de **CBR** de la fila. En la definición de filas, el código de formato **CBR** define la fila base de las columnas que calculan un porcentaje o se multiplican por la fila de base de cada fila en el informe. Puede tener varios códigos de formato **CBR** en el formato de fila, por ejemplo uno para las ventas netas, uno para las ventas brutas y otro para los gastos totales. Normalmente, el código de formato **CBR** se usa para crear un porcentaje para cuentas que se comparan con una línea de totales. Una fila de base se usa para todos los nuevos cálculos hasta que se defina otra fila de base. Debe definir un código de formato **CBR** inicial y un código de formato **CBR **final. Por ejemplo, para determinar los gastos como porcentaje de ventas netas, puede dividir el valor de cada fila de gastos entre el valor de la fila de ventas netas. En este caso, la fila de ventas netas es la fila base. Puede definir una definición de columna que notifica resultados actuales y del ejercicio a fecha, junto con un porcentaje de la base de cada resultado, como se muestra en el ejemplo que se incluye a continuación. Comience con un informe detallado de ingresos.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Seleccione la fila base en una definición de filas para un cálculo de la columna

1.  En el diseñador del informe, haga clic en **Definiciones de columna** y, a continuación, abra la definición de columna para un informe de ingresos.
2.  Agregue una nueva columna a la definición de columna y defina el tipo de columna en **CALC**.
3.  En la celda **Fórmula** de la nueva columna, especifique la fórmula **X/BASEROW**, donde **X** es el tipo de columna **FD** para considerar un porcentaje.
4.  Haga doble clic en la celda **Reemplazo de formato o divisa**.
5.  En la caja de diálogo **Reemplazo de formato**, en la lista **Categoría de formato**, seleccione **Porcentaje** y luego haga clic en **Aceptar**.
6.  En el menú **Archivo**, haga clic en **Guardar como** para guardar la definición de la columna con un nombre nuevo. Anexan ** CBR ** en el nombre de archivo actual (por ejemplo, ** CUR\_YTD\_CBR **). Esta definición de la columna es su definición de columna de la fila base.
7.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila usando el cálculo de la fila base.
8.  Inserte una nueva fila sobre la fila en la que debe comenzar el cálculo de la fila de base.
9.  Haga doble clic en la celda **Código de formato** en la definición de filas y luego seleccione **CBR**.
10. En la celda **Fórmulas, filas o unidades relacionadas**, especifique el número de código de la fila para la fila base.

### <a name="example-of-base-row-calculation"></a>Ejemplo del cálculo de la fila base

En el siguiente ejemplo de una definición de fila, la fila 100 muestra que la fila base para los cálculos es la fila 280. [ejemplo![del cálculo base de la fila.] (. /media/cbrrowdefinition.png])(. /media/cbrrowdefinition.png) En el siguiente ejemplo de una definición de columna, los cálculos usan el código de formato **CBR**. El cálculo en la columna C divide el valor de la columna B del informe entre el valor de la fila 280 de la columna B. La anulación de formato en la columna B imprime el resultado del cálculo como porcentaje. Del mismo modo, cada importe en la columna E es el importe en la columna D como un porcentaje de ventas netas. [ejemplo de la definición de columna de![.] (. /media/cbrcolumndefinition2.png])(. /media/cbrcolumndefinition2.png) En el ejemplo siguiente se muestra un informe que se puede generar en función de los cálculos anteriores. [informe![basado en los cálculos del ejemplo anterior.] (. /media/cbrreport-1024x272.png])(. /media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Seleccione un código de ordenación para una definición de fila
Los códigos de ordenación ordenan cuentas o valores, ordenan un informe de desviación del presupuesto real por desviación mayor y ordenan las descripciones de fila alfabéticamente. Los siguientes códigos de ordenación están disponibles:

-   **SORT**: ordena el informe en orden ascendente, en función de los valores en la columna especificada.
-   **ASORT**: ordena el informe en orden ascendente, en función del valor absoluto de los valores en la columna especificada. Es decir, el signo de cada valor se omite cuando se ordenan los valores. Este código de formato secuencia los valores por la magnitud de la desviación, independientemente de si la desviación es positiva o negativa.
-   **SORTDESC**: ordena el informe en orden descendente, en función de los valores en la columna especificada.
-   **ASORTDESC**: ordena el informe en orden descendente, en función del valor absoluto de los valores en la columna especificada.

### <a name="select-a-sorting-code"></a>Seleccionar un código de ordenación

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Haga doble clic en la celda **Código de formato** y seleccione un código de ordenación.
3.  En la celda **Fórmulas, filas o unidades relacionadas**, especifique el intervalo de códigos de fila que desea ordenar. Para especificar un intervalo, especifique el primer código de fila, dos puntos (:) y, a continuación, el código de la última fila. Por ejemplo, escriba **160:490** para especificar que el intervalo es de la fila 160 a la fila 490.
4.  En la celda **Restricción de columnas**, especifique la letra de la columna de informe para usar en la ordenación. **Nota:** incluya solo las filas de importe en un cálculo de ordenación.

### <a name="examples-of-ascending-and-descending-column-values"></a>Ejemplos de valores ascendentes y descendentes de columna

En el siguiente ejemplo, los valores de la columna D del informe se clasifican en orden ascendente para las filas 160 a 490. Además, los valores absolutos en la G de columnas del informe se clasifican en orden descendente para las filas 610 a 940.

| Código de fila | Descripción                                         | Código de formato | Fórmulas, filas o unidades relacionadas | Saldo de comprobación | Restricción de columna | Vínculo a dimensiones financieras |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Clasificado por la desviación mensual en orden ascendente       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | Ventas                                               |             |                             | C              |                    | 4100                         |
| 190      | Devoluciones de ventas                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Ingresos de interés                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Clasificado por la desviación del ejercicio a fecha en orden descendente | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | G (Verde)                  |                              |
| 610      | Ventas                                               |             |                             | C              |                    | 4100                         |
| 640      | Devoluciones de ventas                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Ingresos de interés                                     |             |                             | C              |                    | 7000                         |

Ejemplo del informe que se genera.

**Análisis de desviación (ordenado por desviación)**

**Regiones de Pekín y Atlanta**

**Para los siete meses que finalizan el 31 de julio de 2013**

**Julio**

**Ejercicio a fecha**

**Real**

**Presupuesto**

**Desviación**

**Real**

**Presupuesto**

**Desviación**

**Clasificado por la desviación mensual en orden ascendente**

COGS

873,872

236,144

(637,728)

4,864,274

1,590,315

(3,273,959)

Sueldos y salarios

97,624

65,573

(32,051)

653,884

441,664

(212,220)

Descuentos de ventas

36,383

24,152

(12,231)

241,562

162,670

(78,892)

Devoluciones de ventas

10,917

7,246

(3,671)

62,809

48,803

(14,006)

Gasto de alquiler

12,052

9,019

(3,033)

80,444

60,748

(19,696)

Gastos de oficina

5,023

3,291

(1,732)

33,420

22,098

(11,322)

Gastos de viajes

7,656

7,641

(15)

51,062

51,469

407

Ventas

1,240,119

410,389

829,730

7,139,288

2,764,549

4,374,739

**Clasificado por la desviación del ejercicio a fecha en orden descendente**

Ventas

1,240,119

410,389

829,730

7,139,288

2,764,549

4,374,739

Gastos de viajes

7,656

7,641

(15)

51,062

51,469

407

Gastos de oficina

5,023

3,291

(1,732)

33,420

22,098

(11,322)

Devoluciones de ventas

10,917

7,246

(3,671)

62,809

48,803

(14,006)

Gasto de alquiler

12,052

9,019

(3,033)

80,444

60,748

(19,696)

Descuentos de ventas

36,383

24,152

(12,231)

241,562

162,670

(78,892)

Sueldos y salarios

97,624

65,573

(32,051)

653,884

441,664

(212,220)

COGS

873,872

236,144

(637,728)

4,864,274

1,590,315

(3,273,959)

## <a name="specify-a-format-override-cell"></a>Especificar una celda de anulación de formato
La celda **Anulación de formato** especifica el formato que se usa para la fila cuando se imprime el informe. Este formato reemplaza el formato que se especifica en la definición de la columna y la definición del informe. De forma predeterminada, el formato que se especifica en esas definiciones es divisa. Si una fila del informe muestra el número de activos, como el número de edificios, y otra fila muestra el valor monetario de dichos activos, puede anular el formato de divisa y especificar el formato numérico para la fila que especifica el número de edificios. Especifique esta información en el cuadro de diálogo **Anulación de formato**. Las opciones disponibles dependen de la categoría del formato que se selecciona. El área **Ejemplo** del cuadro de diálogo muestra formatos de ejemplo. Están disponibles las siguientes categorías:

-   Formato de divisa
-   Formato numérico
-   Formato de porcentaje
-   Formato personalizado

### <a name="override-cell-formatting"></a>Anulación del formato de celda

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  En la fila que desea anular el formato, haga doble clic en la celda en la columna **Anulación de formato**.
3.  En el cuadro de diálogo **Anulación de formato**, seleccione las opciones de formato que se usarán para dicha fila en el informe.
4.  Haga clic en **Aceptar**.

### <a name="currency-formatting"></a>Formato de divisa

El formato de divisa se aplica a un importe fiscal e incluye el símbolo de la divisa. Están disponibles las siguientes opciones:

-   **Símbolo de la divisa**: el símbolo de la divisa para el informe. Este valor anula la configuración **Opciones regionales** para la información de la empresa.
-   **Números negativos**: los números negativos pueden tener un signo menos (-), pueden aparecer entre paréntesis o pueden tener un triángulo (∆).
-   **Decimales**: el número de dígitos a mostrar después del separador decimal.
-   **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**. **Nota:** si la impresión se elimina para los valores cero o ninguna actividad en el período, se eliminará este texto.

### <a name="numeric-formatting"></a>Formato numérico

El formato numérico se aplica a cualquier importe y no incluye un símbolo de divisa. Están disponibles las siguientes opciones:

-   **Números negativos**: los números negativos pueden tener un signo menos (-), pueden aparecer entre paréntesis o pueden tener un triángulo (∆).
-   **Decimales**: el número de dígitos a mostrar después del separador decimal.
-   **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**. **Nota:** si la impresión se elimina para los valores cero o ninguna actividad en el período, se eliminará este texto.

### <a name="percentage-formatting"></a>Formato de porcentaje

El formato de porcentaje incluye el signo de porcentaje (%). Están disponibles las siguientes opciones:

-   **Números negativos**: los números negativos pueden tener un signo menos (-), pueden aparecer entre paréntesis o pueden tener un triángulo (∆).
-   **Decimales**: el número de dígitos a mostrar después del separador decimal.
-   **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**. **Nota:** si la impresión se elimina para los valores cero o ninguna actividad en el período, se eliminará este texto.

### <a name="custom-formatting"></a>Formato personalizado

Use la categoría de formato personalizado para crear una anulación de formato personalizado. Están disponibles las siguientes opciones:

-   **Tipo**: el formato personalizado.
-   **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**. **Nota:** si la impresión se elimina para los valores cero o ninguna actividad en el período, se eliminará este texto.

El tipo debe representar el valor positivo y después el valor negativo. Normalmente, se especifica un formato similar que distinga valores negativos y positivos. Por ejemplo, especificar que el positivo y los valores negativos tienen dos posiciones decimales, pero los valores negativos se producen entre paréntesis, especifique 0.00; **(0.00) **. En la tabla siguiente se muestran los formatos personalizados que puede usar para controlar el formato de sus valores. Todos los ejemplos empiezan con el valor 1234.56.

| Formato                         | Positivo   | Negativo     | Cero    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);“”       | 1,235      | (1,235)      | (En blanco) |
| \#,\#\#0.00;\#(\#,\#0.00;)cero | 1,234.56   | (1,234.56)   | cero    |
| 0.00%;(0.00%)                  | 123456.00% | (123456.00%) | 0.00%   |

## <a name="specify-a-normal-balance-cell"></a>Especificar una celda de saldo normal
La celda **Saldo normal** en una definición de fila controla el signo de los importes de una fila. Para invertir el signo de una fila, o si el saldo normal de una cuenta es un crédito, especifique **C** en la celda **Saldo normal** para dicha fila. El diseñador de informes invertir el signo en todas las cuentas con saldos de crédito en esa fila. Cuando el diseñador de informes convierte estas cuentas, quita la característica de débito o crédito de todos los importes y por tanto realiza el balance directo. Por ejemplo, para calcular los ingresos netos, tiene que restar los gastos de los ingresos. Normalmente, las filas sumadas y calculadas no se ven afectadas por un código **C**. Sin embargo, el control de impresión **XCR** en la definición de la columna invierte el signo de cualquier fila que contenga una **C** en la columna **Saldo normal**. Este formato es especialmente importante cuando desea mostrar todas las desviaciones desfavorables como importes negativos. Si un número sumado o calculado tiene el signo incorrecto, escriba una **C** en la celda **Saldo normal** para que la fila invierta el signo.

## <a name="specify-a-row-modifier-cell"></a>Especificar una celda modificadora de fila
El contenido de la celda **Modificador de fila** en una definición de fila reemplaza los ejercicios, los períodos y otra información especificada en la definición de columna para dicha fila. El modificador seleccionado se aplica a cada cuenta en la fila. Puede modificar cada fila mediante uno o más de los siguientes tipos de modificadores:

-   Modificadores de cuenta
-   Modificadores de código de libro
-   Atributos de cuentas y de transacciones

### <a name="override-a-column-definition"></a>Anular una definición de columna

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  En la fila que desea anular la definición de la columna, haga doble clic en la celda **Modificador de fila**.
3.  En el cuadro de diálogo **Modificador de fila**, seleccione una opción en el campo **Modificador de cuenta**. Para obtener una descripción de las opciones, vea la sección “Modificadores de cuenta”.
4.  En el campo **Modificador del código del libro**, seleccione el código del libro que se usará para la fila.
5.  En **Atributos**, siga estos pasos para agregar una entrada para cada atributo que se debe incluir con el código de la fila:
    1.  Haga doble clic en la celda **Atributo** y seleccione un nombre de atributo. ** Precaución: ** Reemplazar el signo de número (\#) con un valor numérico.
    2.  Haga doble clic en la celda **Desde** y especifique el primer valor para el intervalo.
    3.  Haga doble clic en la celda **Hasta** y especifique el último valor para el intervalo.

6.  Haga clic en **Aceptar**.

### <a name="account-modifiers"></a>Modificadores de cuenta

Cuando selecciona una cuenta concreta, el diseñador de informes combina normalmente la cuenta y los ejercicios, los períodos y otra información que especifique en la definición de la columna. Puede usar información distinta, como diferentes períodos fiscales, para filas específicas. La tabla siguiente muestra los modificadores de cuenta que están disponibles. Reemplazar el signo de número (\#) con un valor al que está igual o menor que el número de períodos de un año fiscal.

| Modificador de cuenta | ¿Qué se imprime?                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Los saldos iniciales para una cuenta.                                                     |
| /\#              | El saldo del período fiscal especificado.                                                     |
| /-\#             | El saldo del período que \# los períodos anteriores del período actual.                  |
| /+\#             | El saldo del período que \# los períodos posteriores después del período actual.                   |
| /C               | El saldo del período fiscal actual.                                                       |
| /C-\#            | El saldo del período que \# los períodos anteriores del período actual.                  |
| /C\#+            | El saldo del período que \# los períodos posteriores después del período actual.                   |
| /Y               | Los saldos del proyecto a la fecha en el período actual.                                      |
| /Y-\#            | La año-a- fecha que se equilibre con el período que \# los períodos anteriores del período actual. |
| /Y\#+            | La año-a- fecha que se equilibre con el período que \# los períodos posteriores después del período actual.  |

### <a name="book-code-modifiers"></a>Modificadores de código de libro

Puede limitar una fila a un código existente del libro. La definición de la columna debe incluir al menos una columna **FD** que tenga el código del libro. **Nota:** la restricción del código del libro para una fila anula las restricciones del código del libro en la definición de columna para dicha fila.

### <a name="account-and-transaction-attributes"></a>Atributos de cuentas y de transacciones

Algunos sistemas contables admiten atributos de cuentas y atributos de transacción en los datos financieros. Estos atributos actúan como segmentos virtuales de la cuenta y pueden contener información adicional sobre la cuenta o la transacción. Esta información adicional podría ser identificadores de la cuenta, identificadores de lote, códigos postales u otro atributos. Si su sistema contable admite atributos, puede usar atributos de cuenta o atributos de transacción como modificadores de la fila en la definición de filas. Para obtener información sobre cómo anular la información de la fila, consulte la sección “Anulación de la definición de la columna” mendionada anteriormente en este artículo.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Especificar un vínculo a la celda de las dimensiones financieras
La celda **Vincular a las dimensiones financieras** contiene vínculos a los datos financieros que se deben incluir en cada fila del informe. Esta celda contiene valores de dimensión, pero se pueden especificar celdas en una hoja de cálculo de Microsoft Excel o, además de eso, valores de segmento o valores de dimensión. Para abrir el cuadro de diálogo **Dimensiones**, haga doble clic en la celda **Vínculo a las dimensiones financieras**. ** Nota: ** El Diseñador de informes no puede seleccionar cuentas, dimensiones, los campos o desde el sistema ERP de Microsoft Dynamics que incluyen cualquiera de las reservas caracteres: y, \*, \[, \], {, o}. Para especificar información para una fila que ya esté en la definición de filas, agregue la información en la celda **Vínculo a las dimensiones financieras**. Para agregar nuevas filas que vinculan a los datos financieros, use el cuadro de diálogo **Insertar filas desde** para crear nuevas filas en la definición del informe. El título de la columna cambia, en función de cómo se configura la columna, tal y como se muestra en la siguiente tabla.

| Tipo de vínculo que se selecciona       | La descripción de la columna de vínculo cambia a esto |
|----------------------------------|----------------------------------------------------|
| Dimensiones financieras             | Vínculo a dimensiones financieras                       |
| Hoja de cálculo externa               | Vincular a la hoja de cálculo                                  |
| Dimensiones financieras + Hoja de cálculo | Vincular a dimensiones financieras + Hojas de cálculo           |
| Informe de Management Reporter       | Informe de Management Reporter                         |

### <a name="specify-a-dimension-or-range"></a>Especificar una dimensión o un intervalo

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  Haga doble clic en una celda en la columna **Víncular a las dimensiones financieras**.
3.  En el cuadro de diálogo **Dimensiones**, haga doble clic en una celda bajo el nombre de la dimensión.
4.  En el cuadro de diálogo para la dimensión, seleccione **Individual o intervalo**.
5.  En ** ¡de ** el campo, especifique la dimensión inicial, o en! [] (Exploración “https://i-technet.sec.s-msft.com/dynimg/IC679490.gif”) exploración buscar las dimensiones disponibles. Para especificar un intervalo de dimensiones, escriba la dimensión final en el campo **Hasta**.
6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo de la dimensión. El cuadro de diálogo **Dimensiones** muestra la dimensión o el intervalo actualizados.
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Dimensiones**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Mostrar las cuentas de saldo cero en una definición de filas
De forma predeterminada, el diseñador de informes no imprime ninguna fila que no tenga un saldo correspondiente en los datos financieros. Por lo tanto, puede crear una definición de fila que incluya todos los valores de segmento o todos los valores de dimensión naturales y después usar dicha definición de filas para cualquiera de los departamentos.

### <a name="modify-zero-balance-settings"></a>Modificar la configuración de saldo cero

1.  En el diseñador de informes, abra la definición del informe para modificarla.
2.  En la pestaña **Parámetros**, en **Otro formato**, seleccione las opciones para la definición de filas que se usa en la definición del informe.
3.  En el menú **Archivo**, haga clic en **Guardar** para guardar los cambios.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Usar intervalos y caracteres comodín en una definición de filas
¿Cuándo especifica un valor natural de segmento en ** las dimensiones ** el cuadro de diálogo, puede establecer un carácter comodín (? \*) o en cualquier puesto de un segmento. El diseñador de informes extrae todos los valores para puestos definido sin tener de caracteres comodín. Por ejemplo, la definición de filas solo contiene valores naturales de segmentos y los segmentos naturales tienen cuatro caracteres. ¿A ** 6??? ** en una fila, se indique al diseñador de informes para incluir todas las cuentas con un valor natural del segmento que empiece por 6. Si especifica 6 ** **\*, se devuelven los mismos resultados, pero los resultados también incluyen valores de configuración anchura, por ejemplo ** ** 60 y 600000 ** **. El diseñador de informes reemplaza cada carácter comodín (?) por la gama completa de valores posibles, que incluyen letras y caracteres especiales. Por ejemplo, en el intervalo de **12?0** a **12?4**, el carácter comodín en **12?0** se reemplaza con el valor más bajo del conjunto de caracteres, y el carácter comodín en **12?4** se reemplazan con el valor más alto del conjunto de caracteres. **Nota:** debe evitar usar caracteres comodín para las cuentas de inicio y fin en intervalos. Si usa los caracteres comodín en la cuenta de inicio o la cuenta de fin, puede obtener resultados inesperados.

### <a name="single-segment-or-single-dimension-ranges"></a>intervalos de un único segmento o de una única dimensión

Puede especificar un intervalo de valores de segmento o valores de dimensión. La ventaja de especificar un intervalo es que no tiene que actualizar la definición de filas cada vez que un nuevo valor de segmento o valor de dimensión se agrega a los datos financieros. Por ejemplo, el intervalo ** 6100:6900 de +Account=\]\[** extracciones los valores de las cuentas 6100 al 6900 en el importe de la fila. Cuando un intervalo incluye un carácter comodín (?), el diseñador de informes no evalúa el intervalo según cada carácter. En su lugar, se determinan los puntos bajos y altos del intervalo y luego se incluyen los valores de fin y todos los valores entre ellos. ** Nota: ** El Diseñador de informes no puede seleccionar cuentas, dimensiones, los campos o desde el sistema ERP de Microsoft Dynamics que incluyen cualquiera de las reservas caracteres: y, \*, \[, \], {, o}. Puede agregar el signo & si está creando automáticamente definiciones de filas usando el cuadro de diálogo **Insertar filas desde dimensiones**.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Intervalos de varios segmentos o varias dimensiones

Cuando se especifica un intervalo mediante combinaciones de valores de la dimensión varias, la comparación de intervalo se realiza en el. A. \ \ dimensiones financieras de la base dimensión-por- dimensión. La comparación del intervalo no se puede realizar carácter por carácter o o por segmento parcial. Por ejemplo, el intervalo ** 5000:6000\], 1000:2000 center=\],\[00\]de +Account= de\[\[Department= de coste ** incluye sólo las cuentas que coinciden cada segmento. En este escenario, la primera dimensión debe estar dentro del intervalo entre 5000 y 6000, la segunda dimensión debe estar dentro del intervalo a partir del 1000 hasta el 2000, y la última dimensión debe ser 00. Por ejemplo, +Account= **\[5100 Department=\],\[1100\],\[center= 01\]de coste ** no se incluye en el informe, ya que el último segmento está fuera del intervalo específico. Si un valor del segmento incluye espacios, agregue ese valor en van encerrados entre corchetes\[ ( \]). Los valores siguientes son válidos para un segmento de cuatro caracteres: **\[ 234\], \[123 \], \[1 34 **\]. Los valores de dimensión se deben incluir entre corchetes los\[ ( \]), y el diseñador de estos informes agrega corchetes para usted. ¿Cuándo un intervalo de múltiple- segmento o varias de la dimensión incluye los caracteres comodín (? o se determinan \*), el punto y en las partes altos de múltiple- segmento o del intervalo entero de la dimensión varias y, a continuación los valores finales y todos los valores entre ellos se incluyen. Si tiene un intervalo de gran tamaño, como todo el intervalo de cuentas de 40000 a 99999, debe especificar una cuenta de inicio válida y una cuenta de fin válida siempre que sea posible. ** Nota: ** El Diseñador de informes no puede seleccionar cuentas, dimensiones, los campos o desde el sistema ERP de Microsoft Dynamics que incluyen cualquiera de las reservas caracteres: y, \*, \[, \], {, o}. Puede agregar el signo & si está creando automáticamente definiciones de filas usando el cuadro de diálogo **Insertar filas desde dimensiones**.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Agregar o quitar de otras cuentas en una definición de filas
Para agregar o quitar los importes monetarios en una cuenta de importes monetarios a otra cuenta, puede usar el símbolo más (+) y el símbolo menos (-) en la celda **Vincular a dimensiones financieras**. La tabla siguiente muestra los formatos aceptables para agregar y quitar vínculos a los datos financieros.

| Operación                                                                               | Use este formato                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Agregar dos cuentas completas cualificadas.                                                       | +Division=\[000 Account=\],\[1205\],\[Department= 00\]+Division=\[100\],\[Account= 1205\], Department=\[00\] |
| Agregar dos valores de segmento.                                                                 | +Account=\[\]1205 +Account=\[\]1210                                                                           |
| Agregar valores de segmento que incluyen caracteres comodín.                                    | ¿+Account=\[120? ¿+Account=\[11??\]                                                                             |
| Agregar un intervalo de cuentas completas cualificadas.                                                | 000:100 Account=\],\[, 1205\]Department=\[00\]de +Division=\[                                                   |
| Agregar un intervalo de valores de segmento.                                                          | 1200:1205 de +Account=\]\[                                                                                       |
| Agregar un intervalo de valores de segmento que incluyen caracteres comodín.                         | +Account=\[: 120? ¿130?\]                                                                                       |
| Quitar una cuenta completamente calificada de otra cuenta completamente calificada.              | +Division=\[000\],\[Account= 1205\], Department=\[00\]-\[Division= 100\],\[Account= 1205 Department=\],\[00\] |
| Quitar un valor del segmento de otro valor del segmento.                                  | +Account=\[\]1205 - Account=\[\]1210                                                                           |
| Quitar un valor del segmento que incluya un carácter comodín de otro valor del segmento. | ¿+Account=\[\]1200 - Account=\[11??\]                                                                           |
| Quitar un intervalo de cuentas completas cualificadas.                                           | 000:100 -\], 1200:1205,\]00:01\]Division= de\[de Account= de\[\[Department=                                           |
| Quitar un intervalo de valores de segmento.                                                     | 1200:1205 -\]de Account=\[                                                                                       |
| Quitar un intervalo de valores de segmento que incluyen caracteres comodín.                    | - Account=\[: 120? ¿130?\]                                                                                       |

Aunque puede modificar las cuentas directamente, también puede usar el cuadro de diálogo **Dimensiones** para aplicar el formato adecuado a sus vínculos de datos financieros. ¿Los valores cualquiera de los pueden incluir caracteres comodín (? \*o). Sin embargo, el Diseñador de informes no puede seleccionar cuentas, dimensiones, los campos o desde el sistema ERP de Microsoft Dynamics que incluyen cualquiera de las reservas caracteres: y, \*, \[, \], {, o}. **Nota:** para quitar valores, debe ponerle paréntesis a estos valores. ¿Por ejemplo, si especifica 450 **? ¿- (4509) ha **, mostrado como ** +Account=\[4509 -\]Account=\[450? **\], y está da instrucciones al diseñador de informes para restar el importe para el segmento 4509 de la cuenta del importe para cualquier segmento de la cuenta que empiece por 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Agregar o quitar cuentas de otras cuentas

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  En la fila apropiada, haga doble clic en la celda de la columna **Víncular a las dimensiones financieras**.
3.  En la primera fila del cuadro de diálogo **Dimensiones**, siga estos pasos:
    1.  En el primer campo, seleccione todas las dimensiones (predeterminado) o haga clic para abrir el cuadro de diálogo **Gestionar los conjuntos de dimensiones**, donde puede crear, modificar, copiar o eliminar un conjunto.
    2.  Haga doble clic ** operador +/- ** a la celda, y seleccione el más (**+**) o (**-** el operador) menos que se aplican a uno o varios valores de dimensión o conjuntos de la fila.
    3.  En la columna correspondiente del valor de dimensión, haga doble clic en la celda para abrir el cuadro de diálogo **Dimensiones** y seleccione si este valor de dimensión es individual o para un intervalo, un conjunto de valores de dimensión o las cuentas de balance. Para las descripciones de los campos en el cuadro de diálogo **Dimensiones**, consulte la sección “Cuadro de diálogo Descripción de la dimensión”.
    4.  Especifique los valores de segmento en la columna **Desde** y en la columna **Hasta**.

4.  Repita los pasos del 2 al 3 para agregar más operaciones.

**Nota:** el operador se aplica a todas las dimensiones en la fila.

## <a name="description-of-the-dimensions-dialog-box"></a>Descripción del cuaro de diálogo Dimensiones
En la tabla siguiente se describen los campos del cuadro de diálogo **Dimensiones**.

| Artículo                | Descripción                                                                                                                                                                                                                                                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Individual o intervalo | En ** ¡de ** el campo, especifique el nombre de una cuenta, o haga clic en ** exploración ** el botón! [] (Exploración “https://i-technet.sec.s-msft.com/dynimg/IC679490.gif”) exploración examinar para la cuenta. Para seleccionar un intervalo, escriba o busque un valor en el campo **Hasta**.                                             |
| Conjunto de valores de dimensión | En el campo **Nombre**, especifique el nombre de un conjunto de valores de dimensión. Para crear, modificar, copiar o eliminar un conjunto, haga clic en **Administrar los conjuntos de valores de dimensión**. ** Fórmula ** el campo se rellena con la fórmula ** vínculo a las dimensiones financieras ** de la celda de este valor de dimensión establecido en la definición de filas. |
| Cuentas totales   | En el campo **Nombre**, escriba o busque una dimensión de las cuentas de balance. El campo **Fórmula** se rellena con la fórmula en la celda **Vínculo a las dimensiones financieras** para esta cuenta de balance en la definición del informe.                                                                       |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Agregar conjuntos de valores de dimensión en una definición de filas
Un conjunto de valores de dimensión es un grupo con nombre de valores de dimensión. Un conjunto de valores de dimensión puede contener valores en una sola dimensión únicamente, pero puede usar un valor de dimensión establecido en las definiciones de varias filas, definiciones de columna, definiciones de organigrama y definiciones de informe. También puede combinar conjuntos de valores de dimensión en una definición del informe. Cuando un cambio en los datos financieros requiere que cambie el conjunto de valores de dimensión, puede actualizar la definición del conjunto de valores de dimensión, y esa actualización se aplicará a todas las áreas que usan el conjunto de valores de dimensión. Por ejemplo, si se indica a menudo un intervalo de valores para vincular a los datos financieros, como los valores de 5100 a 5600, puede asignar este intervalo a un conjunto de cuentas que se denomina Ventas. Después de crear un conjunto de valores de dimensión, puede seleccionar que se establecerá como el vínculo de datos financiero. Como otro ejemplo, si el intervalo de valor de 5100 a 5600 se asigna a las ventas, y 4175 se asigna a los descuentos, puede determinar ventas totales restando descuentos de ventas. Esta operación se indica como ** (5100:5600 - 4175) **.

### <a name="create-a-set-of-dimension-values"></a>Crear un conjunto de valores de dimensión

1.  En el diseñador de informes, abra la definición de la fila, la columna o el organigrama para modificarlas.
2.  En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3.  En el cuadro de diálogo **Administrar los conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de conjunto de valores de dimensión que quiere crear y haga clic en **Nuevo**.
4.  En el cuadro de diálogo **Nuevo**, especifique un nombre y una descripción del conjunto.
5.  En la columna **Desde**, haga doble clic en una celda.
6.  En el cuadro de diálogo **Cuenta**, seleccione el nombre de la cuenta en la lista, o busque la entrada en el campo **Buscar**. A continuación, haga clic en **Aceptar**.
7.  Repita los pasos 5 a 6 en la columna **Hasta** para diseñar una fórmula para dicho operador.
8.  Cuando la fórmula se completa, haga clic en **Aceptar**.
9.  En el cuadro de diálogo **Gestionar los conjuntos de dimensiones**, haga clic en **Cerrar**.

### <a name="update-a-set-of-dimension-values"></a>Actualizar un conjunto de valores de dimensión

1.  En el diseñador de informes, abra la definición de la fila, la columna o el organigrama para modificarlas.
2.  En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3.  En el cuadro de diálogo **Gestionar conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de dimensión.
4.  En la lista, seleccione el conjunto de valores de dimensión para actualizarlo, y haga clic en **Modificar**.
5.  En el cuadro de diálogo **Modificar**, modifique los valores de la fórmula para incluir en el conjunto. **Nota:** si agrega nuevas cuentas o dimensiones, asegúrese de modificar los conjuntos existentes del conjunto de valores de dimensión para incorporar los cambios.
6.  Haga doble clic en la celda y seleccione el operador apropiado, la cuenta **Desde** y la cuenta **Hasta**.
7.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Modificar** y guardar los cambios.

### <a name="copy-a-dimension-set"></a>Copiar un conjunto de dimensiones

1.  En el diseñador de informes, abra la definición de la fila, la columna o el organigrama para modificarlas.
2.  En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3.  En el cuadro de diálogo **Gestionar conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de dimensión.
4.  En la lista, elija el conjunto que quiere copiar y haga clic en **Guardar como**.
5.  Especifique un nombre nuevo para el conjunto copiado y después haga clic en **Aceptar**.

### <a name="delete-a-dimension-set"></a>Eliminar un conjunto de dimensiones

1.  En el diseñador de informes, abra la definición de la fila, la columna o el organigrama para modificarlas.
2.  En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3.  En el cuadro de diálogo **Gestionar conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de dimensión.
4.  Seleccione el conjunto que desee eliminar y, a continuación, haga clic en **Eliminar**. Haga clic en **Sí** para eliminar permanentemente el conjunto de valores de dimensión.


<a name="see-also"></a>Consulte también
--------

[Informe financiero para Microsoft Dynamics 365 para las operaciones (financial-reporting-intro.md])


