---
title: Modificar celdas de definición de filas
description: En este tema se describe la información que se requiere para cada celda de una definición de fila en un informe financiero y se explica cómo escribir esa información.
author: ShylaThompson
ms.date: 02/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e0bab0c9ecff1161612a6654209735b23a40aa6d085c6e83cdd44d3bf41e8b5e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734729"
---
# <a name="modify-row-definition-cells"></a>Modificar celdas de definición de filas

[!include [banner](../includes/banner.md)]

En este tema se describe la información que se requiere para cada celda de una definición de fila en un informe financiero y se explica cómo escribir esa información.

## <a name="specify-a-row-code-in-a-row-definition"></a>Especifique un código de fila en una definición de filas

En las definiciones de filas, los números o las etiquetas en la celda **Código de la fila** identifican cada línea en la definición de filas. Puede especificar el código de fila para hacer referencia a los datos en los cálculos y totales.

### <a name="row-code-requirements"></a>Requisitos de código de fila

Se requiere un código de fila para todas las filas. Puede mezclar códigos de filas numéricos, alfanuméricos y no establecidos (vacíos) en una definición de fila. El código de fila puede ser cualquier número entero positivo (menor de 100.000.000) o una etiqueta descriptiva que identifique esa fila. Una etiqueta descriptiva debe seguir estas reglas:

- La etiqueta debe comenzar por un carácter alfabético (de la a a la z o de la A a la Z) y puede ser cualquier combinación de números y de letras hasta 16 caracteres.

    > [!NOTE]
    > Una etiqueta puede incluir el guión bajo (\_), pero no se permiten otros caracteres especiales.

- La etiqueta no puede usar ninguna de las siguientes palabras reservadas: AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO o RPO.

Los siguientes ejemplos son códigos válidos de fila:

- 320
- TL\_NET\_INCOME
- TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Cambiar un código de fila en una definición de filas

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2. En la fila correspondiente, especifique el nuevo valor en la celda en la columna **Código de la fila**.

### <a name="reset-numeric-row-codes"></a>Restablecer los códigos numéricos de la fila

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2. En el menú **Editar**, haga clic en **Renumerar filas**.
3. En el cuadro de diálogo **Renumerar filas**, especifique los nuevos valores para el código de la fila de inicio y el incremento del código de la fila. Puede restablecer los códigos numéricos de la fila a valores equidistantes. Sin embargo, el diseñador de informes renumera solo los códigos de fila que empiecen por números (por ejemplo 130 o 246). No renumera los códigos de fila que empiecen por letras (por ejemplo INCOME\_93 o TP0693).

> [!NOTE]
> Cuando se reenumeran los códigos de la fila, el diseñador de informes actualiza automáticamente las referencias **TOT** y **CAL**. Por ejemplo, si una fila **TOT** hace referencia a un intervalo que empiece por el código 100 de la fila y se renumeran las filas, empezando por 90, la referencia **TOT** cambia del 100 al 90.

## <a name="add-a-description"></a>Agregar una descripción
La celda de la descripción ofrece una visión general de los datos financieros en la fila del informe, como “ingresos” o “ingresos netos.” El texto en la celda **Descripción** aparece en el informe exactamente como se ha especificado en la definición de filas.

> [!NOTE]
> La anchura de la columna de la descripción del informe se establece en la definición de la columna. Si el texto en la columna de **Descripción** en la definición de filas es largo, compruebe la anchura de la columna **DESC**. Cuando se usa el cuadro de diálogo **Insertar filas desde**, los valores en la columna **Descripción** son los valores de segmento o los valores de dimensión de los datos financieros. Puede insertar filas para agregar texto descriptivo, tal como un encabezado de sección o un total de sección, y para agregar formato, por ejemplo una línea antes de una fila de total. Si el informe incluye un organigrama, puede incluir el texto adicional que está definido para las unidades de notificación en el organigrama. También puede limitar el texto adicional a una unidad de notificación específica.

### <a name="add-the-description-for-a-line-on-a-report"></a>Agregar la descripción de una línea en un informe

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2. Seleccione la celda **Descripción** y especifique el nombre de la fila del informe.
3. Aplique el formato.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Agregue el texto adicional de un organigrama en la visión general

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2. Especifique el código de texto adicional y cualquier otro texto en la celda **Descripción** apropiada.
3. Aplique el formato.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Limitar el texto adicional a una unidad de notificación específica

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2. Localice la fila donde el texto adicional debe ser creado, y después haga doble clic en la celda en la columna **Fórmulas, filas o unidades relacionadas**.
3. En el cuadro de diálogo **Selección de la unidad de notificación**, en el campo **Organigrama**, seleccione un organigrama.
4. En el campo **Selección de organigrama para restricción**, expanda o contraiga el organigrama y seleccione un organigrama.

## <a name="add-a-format-code"></a>Agregar un código de formato
La celda **Código de formato** ofrece una selección de opciones preformateadas para el contenido de la fila. Si la celda **Código de formato** está en blanco, se interpreta la fila como una fila de datos financieros.

> [!NOTE]
> Si un informe contiene filas de formato sin importe que no están relacionadas con las filas de importe que se han eliminado (por ejemplo debido al saldo cero), puede usar la columna **Fórmulas, filas o unidades relacionadas** para evitar que las filas de cabecera y de formato se impriman.

### <a name="add-a-format-code-to-a-report-row"></a>Agregar un código de formato a una fila del informe

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después seleccione una definición de fila para modificarla.
2. Haga doble clic en la celda **Código del formato**.
3. Seleccione un código de formato en la lista. La tabla siguiente describe los códigos de formato y sus acciones.

    | Código de formato                   | Interpretación del código de formato | Acción |
    |-------------------------------|-----------------------------------|--------|
    | (Ninguno)                        |                                   | Borra la celda **Código de formato**. |
    | TOT                           | Total                             | Identifica una fila que usa operadores matemáticos en la columna **Fórmulas, filas o unidades relacionadas**. Los totales incluyen operadores simples, como **+** o **-**. |
    | CAL                           | Cálculo                       | Identifica una fila que usa operadores matemáticos en la columna **Fórmulas, filas o unidades relacionadas**. Los cálculos contienen operadores complejos, como las instrucciones **+**, **-**, **\**_, _*/** y **IF/THEN/ELSE**. |
    | DES                           | Descripción                       | Identificar una línea de encabezado o una línea en blanco en un informe. |
    | LFT RGT CEN                   | Izquierda Derecha Centro                 | Alínea el texto de la descripción de la fila en la página del informe, independientemente de la colocación del texto en la definición de la columna. |
    | CBR                           | Cambiar la fila de base                   | Identifica una fila que define la fila de base para los cálculos de la columna. |
    | COLUMNA                        | Salto de columna                      | Inicia una nueva columna en el informe. |
    | PÁGINA                          | Salto de página                        | Inicia una nueva página en el informe. |
    | \---                          | Subrayado simple                  | Pone una única línea debajo de todas las columnas de importe en el informe. |
    | ===                           | Subrayado doble                  | Pone dos líneas debajo de todas las columnas de importe en el informe. |
    | LINE1                         | Línea fina                         | Dibuja una única línea fina en la página. |
    | LIN2                         | Línea gruesa                        | Dibuja una línea gruesa única a lo largo de la página. |
    | LIN3                         | Línea de puntos                       | Dibuja una única línea de puntos en la página. |
    | LINE4                         | Línea gruesa y línea fina          | Dibuja una línea doble en la página. La línea superior es gruesa y la de abajo es fina. |
    | LINE5                         | Línea fina y línea gruesa          | Dibuja una línea doble en la página. La línea superior es fina y la de abajo es gruesa. |
    | BXB BXC                       | Fila encajonada                         | Dibuja una caja alrededor de las filas del informe que empiezan por la fila **BXB** y acaban por la fila **BXC**. |
    | NOT                           | Comentario                            | Identifica una fila que es una fila de comentario y no debería imprimirse en el informe. Por ejemplo, una fila de comentario podría explicar técnicas de formato. |
    | SORT ASORT SORTDESC ASORTDESC | Ordenar                              | Ordena gastos o ingresos, ordena un informe de desviación del presupuesto real por desviación mayor u ordena las descripciones de fila alfabéticamente. |

## <a name="specify-related-formulasrowsunits"></a>Especificar fórmulas, filas o unidades relacionadas
La celda **Fórmulas, filas o unidades relacionadas** tiene varios objetivos. En función del tipo de fila, una celda de **Fórmulas, filas o unidades relacionadas** puede realizar una de las funciones siguientes:

- Defina las filas que desea incluir en un cálculo cuando usa un código de formato **TOT** o **CAL**.
- Vincule una fila de formato a una fila de importe, de forma que se imprima el formato solo cuando se imprime el importe relacionado.
- Limita una fila a una unidad de notificación específica.
- Defina la fila de base para los cálculos cuando use el código de formato **BASEROW**.
- Defina las filas que desea clasificar cuando usa alguno de los códigos de formato de ordenación.

### <a name="use-a-row-total-in-a-row-definition"></a>Usar un total de filas en una definición de filas

Use una fórmula de totales de fila para agregar o restar importes en otras filas. Una fórmula para crear un total de fila puede incluir los operadores + y - para combinar códigos e intervalos de fila individuales. Los intervalos se indican con dos puntos (:). La fórmula puede contener hasta 1.024 caracteres. Aquí hay un ejemplo de una fórmula estándar de balance: 400+420+430+450+460LIABILITIES+EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>Componentes de una fórmula de total de fila

Al crear una fórmula total de filas, deberá usar códigos de fila para especificar las filas que se deben sumar o restar en la definición de fila actual y usar operadores para especificar cómo se combinan las filas. Se puede usar cualquier combinación de filas de total y filas de importe.

> [!NOTE]
> Se excluyen todas las filas totales que se encuentran dentro de un intervalo. Para crear un total general, puede especificar el intervalo de filas. Si la primera fila de un intervalo es una fila del total, esa fila se incluye en el nuevo total. La siguiente tabla describe cómo se usan los operadores en fórmulas de total de las filas.

| Operador | Fórmula de ejemplo | Descripción                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Agrega el importe de la fila 100 al importe de la fila 330.        |
| :        | 100:330         | Agrega los totales de todas las filas entre la fila 100 y la fila 330.    |
| -        | 100-330         | Resta el importe de la fila 100 del importe de la fila 330. |

### <a name="create-a-row-total"></a>Crear un total de fila

1. En el Diseñador de informes, haga clic en **Definiciones de filas** y abra la definición de fila que desee modificar.
2. Haga doble clic en la celda **Código de formato** en la definición de filas y seleccione **TOT**.
3. En la celda **Fórmulas, filas o unidades relacionadas**, especifique la fórmula total.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relacionar una fila de formato a una fila de importe

En la columna **Código de formato** en una definición de fila, se aplican los códigos de formato **DES**, **LFT**, **RGT**, **CEN**, **---** y **===** a filas sin importe. Para evitar que el formato se imprima cuando se eliminan las filas del importe relacionado (por ejemplo porque las filas del importe contienen valores cero o ninguna actividad del período), debe relacionar las filas de formato a las filas de importe correspondientes. Esta función es útil si desea evitar que se impriman encabezados o formato relacionados con subtotales cuando no hay detalles a imprimir para el período.

> [!NOTE]
> También puede evitar que se impriman las filas de importe detalladas desactivando la opción de mostrar filas sin importes. Esta opción se encuentra en la pestaña **Configuración** de la definición del importe. De forma predeterminada, las cuentas de detalle de transacción con saldo cero o ninguna actividad del período se eliminan en los informes. Para mostrar estas cuentas de detalle de transacción, active la casilla **Mostrar filas sin importes** en la pestaña **Configuración** de la definición del informe.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relacionar una fila de formato a una fila de importe

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después seleccione una definición de fila para modificarla.
2. En la fila de formato, en la celda **Fórmulas, filas o unidades relacionadas**, especifique el código de fila de la fila de importe que se desea eliminar.

    > [!NOTE]
    > Para eliminar una fila de importe, el saldo de la fila debe ser igual que 0 (cero). Una fila de importe que tiene un saldo no se elimina.

3. En el menú **Archivo**, haga clic en **Guardar**.

### <a name="example-of-preventing-printing-of-rows"></a>Ejemplo de cómo evitar la impresión de filas

En el siguiente ejemplo, un usuario quiere evitar que se imprima el encabezado y los subrayados en la fila **Efectivo total** del informe porque no ha habido actividad en ninguna de las cuentas de efectivo. Por lo tanto, en la fila 220 (que, como el código de formato **---** indica, es una fila de formato), en la celda **Fórmulas, filas o unidades relacionadas**, escribe **250**, que es el código de fila de la fila de importe que desea eliminar.

[![RelatedRowsRowDefinition.](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Seleccionar la fila de base para el cálculo de una columna
En los informes relacionales, se asignan una o varias filas de base en la definición de filas usando el código de formato **CBR** (fila de la base de cambio). ULuego se hace referencia a una fila de base en la definición de la columna. Algunos ejemplos típicos de cálculos de CBR:

- Porcentaje de los ingresos totales según están relacionados a elementos individuales de ingresos
- Porcentaje de los gastos totales según están relacionados a elementos individuales de gastos
- Porcentaje del margen bruto según está relacionado a los detalles de la división o del departamento.

Una o varias filas de base se definen en la definición de filas y luego la definición de columnas determina la relación en la que se notifica la fila base. El código que se usa en la fórmula de la columna es **BASEROW**. Se usan las siguientes operaciones matemáticas básicas con **BASEROW**: división, multiplicación, suma o resta. La operación que se usa más es a menudo dividir entre **BASEROW**, donde el resultado se muestra como porcentaje. Los cálculos de columna que usan **BASEROW** en la fórmula, usan la definición de filas para los códigos de fila de base relacionados. Las filas de **CBR** tienen las siguientes características:

- Las filas de **CBR** no se imprimirán en el informe completado.
- El código de formato de **CBR** y su código de fila relacionado se colocan encima de la fila o la sección que muestra los cálculos relacionados.

En una definición de columna, el tipo de columna **CALC** indica una columna que especifica una fórmula en la fila **Fórmula**. Esta fórmula trabaja con los datos para esta columna del informe y usa la palabra clave de Baserow para basar los cálculos en los códigos de formato de **CBR** de la fila. En la definición de filas, el código de formato **CBR** define la fila base de las columnas que calculan un porcentaje o se multiplican por la fila de base de cada fila en el informe. Puede tener varios códigos de formato **CBR** en el formato de fila, por ejemplo uno para las ventas netas, uno para las ventas brutas y otro para los gastos totales. Normalmente, el código de formato **CBR** se usa para crear un porcentaje para cuentas que se comparan con una línea de totales. Una fila de base se usa para todos los nuevos cálculos hasta que se defina otra fila de base. Debe definir un código de formato **CBR** inicial y un código de formato **CBR** final. Por ejemplo, para determinar los gastos como porcentaje de ventas netas, puede dividir el valor de cada fila de gastos entre el valor de la fila de ventas netas. En este caso, la fila de ventas netas es la fila base. Puede definir una definición de columna que notifica resultados actuales y del ejercicio a fecha, junto con un porcentaje de la base de cada resultado, como se muestra en el ejemplo que se incluye a continuación. Comience con un informe detallado de ingresos.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Seleccione la fila base en una definición de filas para un cálculo de la columna

1. En el diseñador del informe, haga clic en **Definiciones de columna** y, a continuación, abra la definición de columna para un informe de ingresos.
2. Agregue una nueva columna a la definición de columna y defina el tipo de columna en **CALC**.
3. En la celda **Fórmula** de la nueva columna, especifique la fórmula **X/BASEROW**, donde **X** es el tipo de columna **FD** para considerar un porcentaje.
4. Haga doble clic en la celda **Reemplazo de formato o divisa**.
5. En la caja de diálogo **Reemplazo de formato**, en la lista **Categoría de formato**, seleccione **Porcentaje** y luego haga clic en **Aceptar**.
6. En el menú **Archivo**, haga clic en **Guardar como** para guardar la definición de la columna con un nombre nuevo. Agregue **CBR** al nombre de archivo actual (por ejemplo, **CUR\_YTD\_CBR**). Esta definición de la columna es su definición de columna de la fila base.
7. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila usando el cálculo de la fila base.
8. Inserte una nueva fila sobre la fila en la que debe comenzar el cálculo de la fila de base.
9. Haga doble clic en la celda **Código de formato** en la definición de filas y luego seleccione **CBR**.
10. En la celda **Fórmulas, filas o unidades relacionadas**, especifique el número de código de la fila para la fila base.

### <a name="example-of-base-row-calculation"></a>Ejemplo del cálculo de la fila base

En el siguiente ejemplo de una definición de fila, la fila 100 muestra que la fila base para los cálculos es la fila 280.

[![Ejemplo del cálculo de la fila base.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png)

En el siguiente ejemplo de una definición de columna, los cálculos usan el código de formato **CBR**. El cálculo en la columna C divide el valor de la columna B del informe entre el valor de la fila 280 de la columna B. La anulación de formato en la columna B imprime el resultado del cálculo como porcentaje. Del mismo modo, cada importe en la columna E es el importe en la columna D como un porcentaje de ventas netas.

[![Ejemplo de definición de columnas.](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png)

En el ejemplo siguiente se muestra un informe que se puede generar en función de los cálculos anteriores.

[![Ejemplo de informe basado en los cálculos del ejemplo anterior.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Seleccione un código de ordenación para una definición de fila
Los códigos de ordenación ordenan cuentas o valores, ordenan un informe de desviación del presupuesto real por desviación mayor y ordenan las descripciones de fila alfabéticamente. Están disponibles los siguientes códigos de ordenación:

- **SORT**: ordena el informe en orden ascendente, en función de los valores en la columna especificada.
- **ASORT**: ordena el informe en orden ascendente, en función del valor absoluto de los valores en la columna especificada. Es decir, el signo de cada valor se omite cuando se ordenan los valores. Este código de formato secuencia los valores por la magnitud de la desviación, independientemente de si la desviación es positiva o negativa.
- **SORTDESC**: ordena el informe en orden descendente, en función de los valores en la columna especificada.
- **ASORTDESC**: ordena el informe en orden descendente, en función del valor absoluto de los valores en la columna especificada.

### <a name="select-a-sorting-code"></a>Seleccionar un código de ordenación

1. En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2. Haga doble clic en la celda **Código de formato** y seleccione un código de ordenación.
3. En la celda **Fórmulas, filas o unidades relacionadas**, especifique el intervalo de códigos de fila que desea ordenar. Para especificar un intervalo, especifique el primer código de fila, dos puntos (:) y, a continuación, el código de la última fila. Por ejemplo, escriba **160:490** para especificar que el intervalo es de la fila 160 a la fila 490.
4. En la celda **Restricción de columnas**, especifique la letra de la columna de informe para usar en la ordenación.

    > [!NOTE]
    > Incluya solo las filas de importe en un cálculo de ordenación.

### <a name="examples-of-ascending-and-descending-column-values"></a>Ejemplos de valores ascendentes y descendentes de columna

En el siguiente ejemplo, los valores de la columna D del informe se ordenarán en orden ascendente desde la fila 160 hasta la 490. Además, los valores absolutos en la columna G del informe se ordenarán en orden descendente desde la fila 610 hasta la 940.

| Código de fila | Descripción                                         | Código de formato | Fórmulas, filas o unidades relacionadas | Saldo normal | Restricción de columnas | Vínculo a dimensiones financieras |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Clasificado por la desviación mensual en orden ascendente       | DES         |                             |                |                    |                              |
| 130      |                                                     | ORD        | 160:490                     |                | D                  |                              |
| 160      | Ventas                                               |             |                             | C              |                    | 4100                         |
| 190      | Devoluciones de ventas                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Ingresos por intereses                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Ordenado por la varianza absoluta del año hasta la fecha en orden descendente | DES         |                             |                |                    |                              |
| 580      |                                                     | ORDESCABS   | 610:940                     |                | G                  |                              |
| 610      | Ventas                                               |             |                             | C              |                    | 4100                         |
| 640      | Devoluciones de ventas                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Ingresos por intereses                                     |             |                             | C              |                    | 7000                         |


## <a name="specify-a-format-override-cell"></a>Especificar una celda de anulación de formato
La celda **Anulación de formato** especifica el formato que se usa para la fila cuando se imprime el informe. Este formato reemplaza el formato que se especifica en la definición de la columna y la definición del informe. De forma predeterminada, el formato que se especifica en esas definiciones es divisa. Si una fila del informe muestra el número de activos, como el número de edificios, y otra fila muestra el valor monetario de dichos activos, puede anular el formato de divisa y especificar el formato numérico para la fila que especifica el número de edificios. Especifique esta información en el cuadro de diálogo **Anulación de formato**. Las opciones disponibles dependen de la categoría del formato que se selecciona. El área **Ejemplo** del cuadro de diálogo muestra formatos de ejemplo. Están disponibles las siguientes categorías:

- Formato de divisa
- Formato numérico
- Formato de porcentaje
- Formato personalizado

### <a name="override-cell-formatting"></a>Anulación del formato de celda

1. En el diseñador de informes, abra la definición de filas para modificarla.
2. En la fila que desea anular el formato, haga doble clic en la celda en la columna **Anulación de formato**.
3. En el cuadro de diálogo **Anulación de formato**, seleccione las opciones de formato que se usarán para dicha fila en el informe.
4. Haga clic en **Aceptar**.

### <a name="currency-formatting"></a>Formato de divisa

El formato de divisa se aplica a un importe fiscal e incluye el símbolo de la divisa. Las opciones siguientes están disponibles:

- **Símbolo de divisa**: el símbolo de divisa del informe. Este valor anula la configuración **Opciones regionales** para la información de la empresa.
- **Números negativos**: los números negativos pueden tener un signo menos (-), pueden aparecer entre paréntesis o pueden tener un triángulo (∆).
- **Decimales**: el número de dígitos a mostrar después del separador decimal.
- **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**.

    > [!NOTE]
    > Si la impresión se elimina si no hay valores ni actividad de período, se eliminará este texto.

### <a name="numeric-formatting"></a>Formato numérico

El formato numérico se aplica a cualquier importe y no incluye un símbolo de divisa. Están disponibles las siguientes opciones:

- **Números negativos**: los números negativos pueden tener un signo menos (-), pueden aparecer entre paréntesis o pueden tener un triángulo (∆).
- **Decimales**: el número de dígitos a mostrar después del separador decimal.
- **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**.

    > [!NOTE]
    > Si la impresión se elimina si no hay valores ni actividad de período, se eliminará este texto.

### <a name="percentage-formatting"></a>Formato de porcentaje

El formato de porcentaje incluye el signo de porcentaje (%). Están disponibles las siguientes opciones:

- **Números negativos**: los números negativos pueden tener un signo menos (-), pueden aparecer entre paréntesis o pueden tener un triángulo (∆).
- **Decimales**: el número de dígitos a mostrar después del separador decimal.
- **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**.

    > [!NOTE]
    > Si la impresión se elimina si no hay valores ni actividad de período, se eliminará este texto.

### <a name="custom-formatting"></a>Formato personalizado

Use la categoría de formato personalizado para crear una anulación de formato personalizado. Están disponibles las siguientes opciones:

- **Tipo**: el formato personalizado.
- **Texto de anulación del valor cero**: el texto a incluir en el informe cuando el importe es 0 (cero). Este texto aparece como la última línea en el área **Ejemplo**.

    > [!NOTE]
    > Si la impresión se elimina si no hay valores ni actividad de período, se eliminará este texto.

El tipo debe representar el valor positivo y después el valor negativo. Normalmente, se especifica un formato similar que distinga valores negativos y positivos. Por ejemplo, para especificar que los valores negativos y positivos tienen dos decimales, pero los valores negativos aparecen entre paréntesis, escriba **0.00; (0.00)**. En la tabla siguiente se muestran los formatos personalizados que puede usar para controlar el formato de sus valores. Todos los ejemplos empiezan con el valor 1234.56.

| Formato                         | Positivo   | Negativo     | Cero    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);""       | 1,235      | (1,235)      | (En blanco) |
| \#,\#\#0.00;(\#,\#\#0.00);cero | 1,234.56   | (1,234.56)   | cero    |
| 0.00%;(0.00%)                  | 123456.00% | (123456.00%) | 0.00%   |

## <a name="specify-a-normal-balance-cell"></a>Especificar una celda de saldo normal
La celda **Saldo normal** en una definición de fila controla el signo de los importes de una fila. Para invertir el signo de una fila, o si el saldo normal de una cuenta es un crédito, especifique **C** en la celda **Saldo normal** para dicha fila. El diseñador de informes invierte el signo en todas las cuentas de saldo de crédito en esa fila. Cuando el diseñador de informes convierte estas cuentas, quita la característica de débito o crédito de todos los importes y por tanto realiza el balance directo. Por ejemplo, para calcular los ingresos netos, tiene que restar los gastos de los ingresos. Normalmente, las filas sumadas y calculadas no se ven afectadas por un código **C**. Sin embargo, el control de impresión **XCR** en la definición de la columna invierte el signo de cualquier fila que contenga una **C** en la columna **Saldo normal**. Este formato es especialmente importante cuando desea mostrar todas las desviaciones desfavorables como importes negativos. Si un número sumado o calculado tiene el signo incorrecto, escriba una **C** en la celda **Saldo normal** para que la fila invierta el signo.

## <a name="specify-a-row-modifier-cell"></a>Especificar una celda modificadora de fila
El contenido de la celda **Modificador de fila** en una definición de fila reemplaza los ejercicios, los períodos y otra información especificada en la definición de columna para dicha fila. El modificador seleccionado se aplica a cada cuenta en la fila. Puede modificar cada fila mediante uno o más de los siguientes tipos de modificadores:

- Modificadores de cuenta
- Modificadores de código de libro
- Atributos de cuentas y de transacciones

### <a name="override-a-column-definition"></a>Anular una definición de columna

1. En el diseñador de informes, abra la definición de filas para modificarla.
2. En la fila que desea anular la definición de la columna, haga doble clic en la celda **Modificador de fila**.
3. En el cuadro de diálogo **Modificador de fila**, seleccione una opción en el campo **Modificador de cuenta**. Para obtener una descripción de las opciones, vea la sección “Modificadores de cuenta”.
4. En el campo **Modificador del código del libro**, seleccione el código del libro que se usará para la fila.
5. En **Atributos**, siga estos pasos para agregar una entrada para cada atributo que se debe incluir con el código de la fila:

    1. Haga doble clic en la celda **Atributo** y seleccione el nombre del atributo.

        > [!IMPORTANT]
        > Reemplace el signo de almohadilla (\#) por un valor numérico.

    2. Haga doble clic en la celda **Desde** y especifique el primer valor para el intervalo.
    3. Haga doble clic en la celda **Hasta** y especifique el último valor para el intervalo.

6. Haga clic en **Aceptar**.

### <a name="account-modifiers"></a>Modificadores de cuenta

Cuando selecciona una cuenta concreta, el diseñador de informes combina normalmente la cuenta y los ejercicios, los períodos y otra información que especifique en la definición de la columna. Puede usar información distinta, como diferentes períodos fiscales, para filas específicas. La tabla siguiente muestra los modificadores de cuenta que están disponibles. Sustituya el signo de número (\#) por un valor que sea igual o menor que el número de períodos de un ejercicio.

| Modificador de cuenta | ¿Qué se imprime?                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Los saldos iniciales para una cuenta.                                                     |
| /\#              | El saldo del período fiscal especificado.                                                     |
| /-\#             | El saldo del período que es \# períodos anteriores al período actual.                  |
| /+\#             | El saldo del período que es \# períodos posteriores al período actual.                   |
| /C               | El saldo del período fiscal actual.                                                       |
| /C-\#            | El saldo del período que es \# períodos anteriores al período actual.                  |
| /C+\#            | El saldo del período que es \# períodos posteriores al período actual.                   |
| /Y               | Los saldos del proyecto a la fecha en el período actual.                                      |
| /Y-\#            | El saldo a la fecha del período que es \# períodos anteriores al período actual. |
| /Y+\#            | El saldo a la fecha del período que es \# períodos posteriores al período actual.  |

### <a name="book-code-modifiers"></a>Modificadores de código de libro

Puede limitar una fila a un código existente del libro. La definición de la columna debe incluir al menos una columna **FD** que tenga el código del libro.

> [!NOTE]
> La restricción del código del libro para una fila anula las restricciones del código del libro en la definición de columna para dicha fila.

### <a name="account-and-transaction-attributes"></a>Atributos de cuenta y transacción

Algunos sistemas contables admiten atributos de cuentas y atributos de transacción en los datos financieros. Estos atributos actúan como segmentos virtuales de la cuenta y pueden contener información adicional sobre la cuenta o la transacción. Esta información adicional podría ser identificadores de la cuenta, identificadores de lote, códigos postales u otro atributos. Si su sistema contable admite atributos, puede usar atributos de cuenta o atributos de transacción como modificadores de la fila en la definición de filas. Para obtener información sobre cómo anular la información de la fila, consulte la sección “Anulación de la definición de la columna” mendionada anteriormente en este artículo.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Especificar un vínculo a la celda de las dimensiones financieras
La celda **Vincular a las dimensiones financieras** contiene vínculos a los datos financieros que se deben incluir en cada fila del informe. Esta celda contiene valores de dimensión. Para abrir el cuadro de diálogo **Dimensiones**, haga doble clic en la celda **Vínculo a las dimensiones financieras**.

> [!NOTE]
> El diseñador de informes no puede seleccionar cuentas, dimensiones ni campos del sistema de Microsoft Dynamics ERP que incluyan los siguientes caracteres reservados: &, \*, \[, \], { o }. Para especificar información de una fila que ya se encuentra en la definición de fila, agregue la información a la celda **Vínculo a dimensiones financieras**. Para agregar nuevas filas que vinculan a los datos financieros, use el cuadro de diálogo **Insertar filas desde** para crear nuevas filas en la definición del informe. El título de la columna cambia, en función de cómo se configura la columna, tal y como se muestra en la siguiente tabla.

| Tipo de vínculo que se selecciona       | La descripción de la columna de vínculo cambia a esto |
|----------------------------------|----------------------------------------------------|
| Dimensiones financieras             | Vínculo a dimensiones financieras                       |
| Hoja de cálculo de informe                 | Informe de de informes financieros                         |

### <a name="specify-a-dimension-or-range"></a>Especificar una dimensión o un intervalo

1. En el Diseñador de informes, abra la definición de fila que desee modificar.
2. Haga doble clic en una celda de la columna **Vínculo a dimensiones financieras**.
3. En el cuadro de diálogo **Dimensiones**, haga doble clic en una celda situada bajo el nombre de la dimensión.
4. En el cuadro de diálogo para la dimensión, seleccione **Individual o intervalo**.
5. En el campo **Desde**, especifique la dimensión de inicio o haga clic en ![Examinar.](media/browse.gif "Examinar") para buscar dimensiones disponibles. Para especificar un intervalo de dimensiones, escriba la dimensión final en el campo **Hasta**.
6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo de la dimensión. El cuadro de diálogo **Dimensiones** muestra la dimensión o el intervalo actualizados.
7. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Dimensiones**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Mostrar las cuentas de saldo cero en una definición de filas
De forma predeterminada, el diseñador de informes no imprime ninguna fila que no tenga un saldo correspondiente en los datos financieros. Por lo tanto, puede crear una definición de fila que incluya todos los valores de segmento o todos los valores de dimensión naturales y después usar dicha definición de filas para cualquiera de los departamentos.

### <a name="modify-zero-balance-settings"></a>Modificar la configuración de saldo cero

1. En el diseñador de informes, abra la definición del informe para modificarla.
2. En la pestaña **Parámetros**, en **Otro formato**, seleccione las opciones para la definición de filas que se usa en la definición del informe.
3. En el menú **Archivo**, haga clic en **Guardar** para guardar los cambios.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Usar intervalos y caracteres comodín en una definición de filas
Cuando se especifica un valor natural de segmento en el cuadro de diálogo **Dimensiones**, puede poner un carácter comodín (? o \*) en cualquier posición de un segmento. El diseñador de informes extrae todos los valores de las posiciones definidas sin tener en cuenta los caracteres comodín. Por ejemplo, la definición de filas solo contiene valores naturales de segmentos y los segmentos naturales tienen cuatro caracteres. Si escribe **6???** en una fila, le está pidiendo al diseñador de informes que incluya todas las cuentas con un valor natural de segmento que empiece por 6. Si escribe **6\**_, se devuelven los mismos resultados, pero los resultados también incluyen valores de la variable anchura, como _* 60** y **600000**. El diseñador de informes reemplaza cada carácter comodín (?) por la gama completa de valores posibles, que incluyen letras y caracteres especiales. Por ejemplo, en el intervalo de **12?0** a **12?4**, el carácter comodín en **12?0** se reemplaza con el valor más bajo del conjunto de caracteres, y el carácter comodín en **12?4** se reemplazan con el valor más alto del conjunto de caracteres.

> [!NOTE]
> Debe evitar usar caracteres comodín para las cuentas de inicio y fin en intervalos. Si usa los caracteres comodín en la cuenta de inicio o la cuenta de fin, puede obtener resultados inesperados.

### <a name="single-segment-or-single-dimension-ranges"></a>intervalos de un único segmento o de una única dimensión

Puede especificar un intervalo de valores de segmento o valores de dimensión. La ventaja de especificar un intervalo es que no tiene que actualizar la definición de filas cada vez que un nuevo valor de segmento o valor de dimensión se agrega a los datos financieros. Por ejemplo, el intervalo **+Cuenta=\[6100:6900\]** extrae los valores de las cuentas de la 6100 a la 6900 para el importe de fila. Cuando un intervalo incluye un carácter comodín (?), el diseñador de informes no evalúa el intervalo según cada carácter. En su lugar, se determinan los puntos bajos y altos del intervalo y luego se incluyen los valores de fin y todos los valores entre ellos.

> [!NOTE]
> El diseñador de informes no puede seleccionar cuentas, dimensiones ni campos del sistema de Microsoft Dynamics ERP que incluyan los siguientes caracteres reservados: &, \*, \[, \], { o }. Puede agregar el signo & si está creando automáticamente definiciones de filas usando el cuadro de diálogo **Insertar filas desde dimensiones**.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Intervalos de varios segmentos o varias dimensiones

Cuando se especifica un intervalo mediante combinaciones de varios valores de dimensión, la comparación del intervalo se hace ..\\financial-dimensions\\dimensión por dimensión. La comparación del intervalo no se puede realizar carácter por carácter o o por segmento parcial. Por ejemplo, el intervalo **+Cuenta=\[5000:6000\], Departamento=\[1000:2000\], Centro de coste=\[00\]** incluye únicamente las cuentas que coinciden con cada segmento. En este escenario, la primera dimensión debe estar en el intervalo de 5000 a 6000, la segunda dimensión debe estar en el intervalo de 1000 a 2000 y la última dimensión debe ser 00. Por ejemplo, **+Cuenta=\[5100\], Departamento=\[1100\], Centro de coste=\[01\]** no se incluye en el informe, ya que el segmento último se encuentra fuera del intervalo específico. Si un valor del segmento contiene espacios, incluya ese valor en corchetes (\[ \]). Los siguientes valores son válidos para un segmento de cuatro caracteres: **\[ 234\], \[123 \], \[1 34\]**. Los valores de dimensión se deben incluir entre corchetes (\[ \]) y el diseñador de informes agrega estos corchetes para el usuario. Cuando un intervalo de varios segmentos o de varias dimensiones incluye caracteres comodín (? o \*), se determina el punto bajo y alto de todo el intervalo de varios segmentos o varias dimensiones y luego se incluyen los valores de fin y todos los valores entre ellos. Si tiene un intervalo de gran tamaño, como todo el intervalo de cuentas de 40000 a 99999, debe especificar una cuenta de inicio válida y una cuenta de fin válida siempre que sea posible.

> [!NOTE] 
> El diseñador de informes no puede seleccionar cuentas, dimensiones ni campos del sistema de Microsoft Dynamics ERP que incluyan los siguientes caracteres reservados: &, \*, \[, \], { o }. Puede agregar el signo & si está creando automáticamente definiciones de filas usando el cuadro de diálogo **Insertar filas desde dimensiones**.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Agregar o quitar de otras cuentas en una definición de filas
Para agregar o quitar los importes monetarios en una cuenta de importes monetarios a otra cuenta, puede usar el símbolo más (+) y el símbolo menos (-) en la celda **Vincular a dimensiones financieras**. La tabla siguiente muestra los formatos aceptables para agregar y quitar vínculos a los datos financieros.

| Operación                                                                               | Use este formato                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Agregar dos cuentas completas cualificadas.                                                       | +División=\[000\], Cuenta=\[1205\], Departamento=\[00\]+División=\[100\], Cuenta=\[1205\], Departamento=\[00\] |
| Agregar dos valores de segmento.                                                                 | +Cuenta=\[1205\]+Cuenta=\[1210\]                                                                           |
| Agregar valores de segmento que incluyen caracteres comodín.                                    | +Cuenta=\[120?+Cuenta=\[11??\]                                                                             |
| Agregar un intervalo de cuentas completas cualificadas.                                                | +División=\[000:100\], Cuenta=\[1205\], Departamento=\[00\]                                                   |
| Agregar un intervalo de valores de segmento.                                                          | +Cuenta=\[1200:1205\]                                                                                       |
| Agregar un intervalo de valores de segmento que incluyen caracteres comodín.                         | +Cuenta=\[120?:130?\]                                                                                       |
| Quitar una cuenta completamente calificada de otra cuenta completamente calificada.              | +División=\[000\], Cuenta=\[1205\], Departamento=\[00\]-División=\[100\], Cuenta=\[1205\], Departamento=\[00\] |
| Quitar un valor del segmento de otro valor del segmento.                                  | +Cuenta=\[1205\]-Cuenta=\[1210\]                                                                           |
| Quitar un valor del segmento que incluya un carácter comodín de otro valor del segmento. | +Cuenta=\[1200\]-Cuenta=\[11??\]                                                                           |
| Quitar un intervalo de cuentas completas cualificadas.                                           | -División=\[000:100\], Cuenta=\[1200:1205\], Departamento=\[00:01\]                                           |
| Quitar un intervalo de valores de segmento.                                                     | -Cuenta=\[1200:1205\]                                                                                       |
| Quitar un intervalo de valores de segmento que incluyen caracteres comodín.                    | -Cuenta=\[120?:130?\]                                                                                       |

Aunque puede modificar las cuentas directamente, también puede usar el cuadro de diálogo **Dimensiones** para aplicar el formato adecuado a sus vínculos de datos financieros. Cualquiera de los valores puede incluir caracteres comodín (? o \*). Sin embargo, el diseñador de informes no puede seleccionar cuentas, dimensiones ni campos del sistema de Microsoft Dynamics ERP que incluyan los siguientes caracteres reservados: &, \*, \[, \], { o }.

> [!NOTE]
> Para restar valores, debe escribirlos entre paréntesis. Por ejemplo, si escribe **450?-(4509)**, se mostrará **+Cuenta=\[4509\]-Cuenta=\[450?\]** y le estará dando instrucciones al diseñador de informes para que reste el importe en el segmento 4509 del importe para cualquier segmento de cuenta que empiece por 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Agregar o quitar cuentas de otras cuentas

1. En el diseñador de informes, abra la definición de filas para modificarla.
2. En la fila apropiada, haga doble clic en la celda de la columna **Víncular a las dimensiones financieras**.
3. En la primera fila del cuadro de diálogo **Dimensiones**, siga estos pasos:

    1. En el primer campo, seleccione todas las dimensiones (predeterminado) o haga clic para abrir el cuadro de diálogo **Gestionar los conjuntos de dimensiones**, donde puede crear, modificar, copiar o eliminar un conjunto.
    2. Haga doble clic en la celda **Operador +/-** y seleccione el signo más (**+**) o menos (**-**) que se aplica a uno o más valores de dimensión o conjuntos en la fila.
    3. En la columna correspondiente del valor de dimensión, haga doble clic en la celda para abrir el cuadro de diálogo **Dimensiones** y seleccione si este valor de dimensión es individual o para un intervalo, un conjunto de valores de dimensión o las cuentas de balance. Para las descripciones de los campos en el cuadro de diálogo **Dimensiones**, consulte la sección “Cuadro de diálogo Descripción de la dimensión”.
    4. Especifique los valores de segmento en la columna **Desde** y en la columna **Hasta**.

4. Repita los pasos del 2 al 3 para agregar más operaciones.

> [!NOTE]
> El operador se aplica a todas las dimensiones de la fila.

## <a name="description-of-the-dimensions-dialog-box"></a>Descripción del cuaro de diálogo Dimensiones
En la tabla siguiente se describen los campos del cuadro de diálogo **Dimensiones**.

| Artículo                | Descripción |
|---------------------|-------------|
| Individual o intervalo | En el campo **Desde**, especifique el nombre de una cuenta, o haga clic en el botón **Explorar** ![Explorar.](media/browse.gif "Examinar") para buscar la cuenta. Para seleccionar un intervalo, escriba o busque un valor en el campo **Hasta**. |
| Conjunto de valores de dimensión | En el campo **Nombre**, especifique el nombre de un conjunto de valores de dimensión. Para crear, modificar, copiar o eliminar un conjunto, haga clic en **Administrar los conjuntos de valores de dimensión**. El campo **Fórmula** se rellena con la fórmula de la celda **Vínculo a las dimensiones financieras** para este conjunto de valores de dimensión en la definición de filas. |
| Cuentas totales   | En el campo **Nombre**, escriba o busque una dimensión de las cuentas de balance. El campo **Fórmula** se rellena con la fórmula en la celda **Vínculo a las dimensiones financieras** para esta cuenta de balance en la definición del informe. |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Agregar conjuntos de valores de dimensión en una definición de filas
Un conjunto de valores de dimensión es un grupo con nombre de valores de dimensión. Un conjunto de valores de dimensión puede contener valores en una sola dimensión únicamente, pero puede usar un valor de dimensión establecido en las definiciones de varias filas, definiciones de columna, definiciones de organigrama y definiciones de informe. También puede combinar conjuntos de valores de dimensión en una definición del informe. Cuando un cambio en los datos financieros requiere que cambie el conjunto de valores de dimensión, puede actualizar la definición del conjunto de valores de dimensión, y esa actualización se aplicará a todas las áreas que usan el conjunto de valores de dimensión. Por ejemplo, si se indica a menudo un intervalo de valores para vincular a los datos financieros, como los valores de 5100 a 5600, puede asignar este intervalo a un conjunto de cuentas que se denomina Ventas. Una vez creado el grupo de valores de dimensión, puede seleccionarlo como vínculo a datos financieros. En otro ejemplo, si el intervalo de valores de 5100 a 5600 asignado a Ventas y 4175 se asigna a Descuentos, puede determinar las ventas totales si resta Descuentos de Ventas. Esta operación se indica como **(5100:5600)-4175**.

### <a name="create-a-set-of-dimension-values"></a>Crear un conjunto de valores de dimensión

1. En el diseñador de informes, abra la definición de la fila, la columna o el organigrama para modificarlas.
2. En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3. En el cuadro de diálogo **Administrar los conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de conjunto de valores de dimensión que quiere crear y haga clic en **Nuevo**.
4. En el cuadro de diálogo **Nuevo**, especifique un nombre y una descripción del conjunto.
5. En la columna **Desde**, haga doble clic en una celda.
6. En el cuadro de diálogo **Cuenta**, seleccione el nombre de la cuenta en la lista, o busque la entrada en el campo **Buscar**. A continuación, haga clic en **Aceptar**.
7. Repita los pasos 5 a 6 en la columna **Hasta** para diseñar una fórmula para dicho operador.
8. Cuando la fórmula se completa, haga clic en **Aceptar**.
9. En el cuadro de diálogo **Administrar grupos de dimensiones**, haga clic en **Cerrar**.

### <a name="update-a-set-of-dimension-values"></a>Actualizar un grupo de valores de dimensión

1. En el Diseñador de informes, abra la definición de fila, columna u organigrama que desee modificar.
2. En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3. En el cuadro de diálogo **Gestionar conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de dimensión.
4. En la lista, seleccione el conjunto de valores de dimensión para actualizarlo, y haga clic en **Modificar**.
5. En el cuadro de diálogo **Modificar**, modifique los valores de la fórmula para incluir en el conjunto.

    > [!NOTE]
    > Si agrega nuevas cuentas o dimensiones, asegúrese de modificar los conjuntos existentes de valores de dimensión para incorporar los cambios.

6. Haga doble clic en la celda y seleccione el operador apropiado, la cuenta **Desde** y la cuenta **Hasta**.
7. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Modificar** y guardar los cambios.

### <a name="copy-a-dimension-set"></a>Copiar un conjunto de dimensiones

1. En el diseñador de informes, abra la definición de la fila, la columna o el organigrama para modificarlas.
2. En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3. En el cuadro de diálogo **Gestionar conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de dimensión.
4. En la lista, elija el conjunto que quiere copiar y haga clic en **Guardar como**.
5. Especifique un nombre nuevo para el conjunto copiado y después haga clic en **Aceptar**.

### <a name="delete-a-dimension-set"></a>Eliminar un grupo de dimensiones

1. En el Diseñador de informes, abra la definición de fila, columna u organigrama que desee modificar.
2. En el menú **Editar**, haga clic en **Administrar los conjuntos de valores de dimensión**.
3. En el cuadro de diálogo **Gestionar conjuntos de valores de dimensión**, en el campo **Dimensión**, seleccione el tipo de dimensión.
4. Seleccione el grupo que se debe eliminar y haga clic en **Eliminar**. Haga clic en **Sí** para eliminar permanentemente el grupo de valores de dimensión.

## <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]