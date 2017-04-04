---
title: Opciones de formato avanzadas en informes financieros
description: "Al crear un informe en informes financieros, las funciones adicionales de formato están disponibles, incluidos los filtros para dimensiones, las restricciones de columnas y las unidades de informes, las filas sin impresión y las instrucciones IF/THEN/ELSE en los cálculos."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 631fec1dc135565e6d38e7faf193a7a898b508cb
ms.lasthandoff: 03/29/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Opciones de formato avanzadas en informes financieros

Al crear un informe en informes financieros, las funciones adicionales de formato están disponibles, incluidos los filtros para dimensiones, las restricciones de columnas y las unidades de informes, las filas sin impresión y las instrucciones IF/THEN/ELSE en los cálculos. 

La siguiente tabla explica las funciones avanzadas del formato que están disponibles cuando se diseñan informes.

| Función                   | Descripción                                                                                                                                                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Filtro de dimensiones           | Para obtener acceso a conjuntos de datos específicos, puede usar dimensiones en la definición de filas y la definición de la columna. Muchos informes usan únicamente el segmento natural en el formato de la fila. Sin embargo, las filas pueden modificarse de modo que incluyan valores de dimensión. Los filtros de la dimensión de la definición de la columna se usan para obtener acceso a valores de dimensión específicos. |
| Restricción de unidad de notificación | Puede configurar una fila del informe de modo que muestre solo la información que está vinculada a una unidad de notificación específica.                                                                                                                                                                                                                      |
| Filas sin impresión (NP)     | Las filas sin impresión son útiles en muchos informes. Si varios cálculos se requieren para obtener un valor, estos cálculos se pueden ocultar en el informe impreso. Las filas sin impresión también son útiles para la solución de problemas de diseños del informe y para la posición de celda avanzada.                                                    |
| Restricción de columna         | La restricción de la columna de la definición de filas es útil para ocultar los valores relevantes solo en algunas filas del informe. Cuando los cálculos de porcentaje se realizan en una fila, la restricción de la columna impide que las columnas totales u otras columnas se impriman cuando dichos números no se aplican.                              |
| Salto de columna               | Puede agregar saltos de la columna en una definición de fila para mostrar la información del informe a su lado. Puede agregar varios saltos de columna en una única definición de filas, y los encabezados de columna se repite en la parte superior de cada columna tras el salto de laolumna. Los comentarios para un informe se muestran entre los saltos de columna.                              |
| Instrucción IF/THEN/ELSE     | Puede modificar cálculos de una definición de fila o una definición de la columna.                                                                                                                                                                                                                                                         |

## <a name="advanced-cell-placement"></a>Colocación de celda avanzada
La posición de celda avanzada, o *forzar*, implica la posición de valores específicos en las celdas específicas. Por ejemplo, forzar se usa a menudo para mover los saldos correctos en un extracto de flujo de efectivo. Puede utilizar forzar para lo siguiente:

-   Mover valores desde Microsoft Excel a celdas específicas.
-   Codificar en duro valores específicos en un informe.
-   Modificar los signos copiando un valor de una celda anterior y multiplicando ese valor por -1.

**Nota:** En muchos casos, debe configurar su definición del informe para realizar cálculos de la columna antes de cálculos de la fila. Para completar esta configuración, siga estos pasos.

1.  En el diseñador de informes, abra la definición del informe para modificarla..
2.  En la pestaña **Configuración**, en **Prioridad de cálculo**, seleccione **Realizar el cálculo de la columna primero y a continuación la fila**.

## <a name="designing-the-report"></a>Diseño del informe
Cuando se diseña un informe, debe crear todas las filas de detalle primero para asegurarse de que los valores están tirados según lo previsto. A continuación agregue anulaciones del formato **NP** (sin impresión) para eliminar el detalle que incluye los valores finales. **Importante:** Cuando se usa el código de formato **CAL**  en la definición de filas, no puede explorar en profundidad el detalle de transacción. Para obligar, las fórmulas usan el formato siguiente: &lt;=&gt;la columna de destino&lt;que se origina código&gt;&lt;de column.row separa&gt; cualquier puesto adicional para una fila por comas y un espacio. Aquí se encuentra un ejemplo: D=C.190, E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Ejemplos de opciones de formato avanzadas
Los siguientes ejemplos muestran cómo dar formato a la definición de filas y la definición de columnas para forzar un informe básico de flujo de efectivo (ejemplo 1) y un informe estadístico (ejemplo 2).

### <a name="example-1-basic-forcing"></a>Ejemplo 1: forzar básico

En la tabla siguiente se muestra un ejemplo de una definición de fila que usa forzado básico.

| Código de fila | Descripción                      | Código de formato | Fórmulas, filas o unidades relacionadas | Anulación de formato | Saldo de comprobación | Control de impresión | Restricción de columna | Modificante de la fila               | Vínculo a dimensiones financieras |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Efectivo al inicio del período (NP) |             |                             |                 |                |               |                    | Modificador de la cuenta = \[/BB\] | +Segment2 \[\]= 1100         |
| 130      | Efectivo al inicio del período      | CAL         | C=C.100, F=D.100             |                 |                |               |                    |                            |                              |
| 160      |                                  |             |                             |                 |                |               |                    |                            |                              |
| 190      |                                  |             |                             |                 |                |               |                    |                            |                              |

En la tabla siguiente se muestra un ejemplo de una definición de columna que usa forzado en la fila.

|                              | A   | mil millones    | C        | D      | E      | F    |
|------------------------------|-----|------|----------|--------|--------|------|
| Encabezado 1                     |     |      |          |        |        |      |
| Encabezado 2                     | A   | mil millones    | C        | D      | E      | F    |
| Encabezado 3                     |     |      |          |        |        |      |
| Tipo de columna                  | FILA | DESC | FD       | FD     | FD     | CALC |
| Código de libro/Categoría de atributo |     |      | REAL   | REAL | REAL |      |
| Ejercicio                  |     |      | BASE     | BASE   | BASE   |      |
| Periodo                       |     |      | BASE     | BASE   | BASE   |      |
| Período de cobertura              |     |      | PERIÓDICO | YTD/BB | Ejercicio a fecha    |      |
| Fórmula                      |     |      |          |        |        | E-D  |
| Ancho de columna                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>Ejemplo 2: informes estadísticos

En la tabla siguiente se muestra un ejemplo de una definición de fila que usa forzado para un informe estadístico.

| Código de fila | Descripción               | Código de formato | Fórmulas, filas o unidades relacionadas     | Anulación de formato      | Saldo de comprobación | Control de impresión | Restricción de columna | Modificante de la fila | Vínculo a dimensiones financieras               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|---------------|--------------------|--------------|--------------------------------------------|
| 50       | Información estadística   | REM         |                                 |                      |                |               |                    |              |                                            |
| 100      | Recuento de personas: Estados Unidos            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 115      | Recuento de personas: international | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 130      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 190      | Ventas de Estados Unidos                  |             |                                 |                      | C              |               |                    |              | +Segment2 \[= 41\*\], Segment3 \[= 00\]    |
| 220      | Ventas internacionales       |             |                                 |                      | C              |               |                    |              | +Segment2 \[= 41\*\], 01:99\]de Segment3 \[= |
| 250      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 280      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 310      | Ventas de Estados Unidos                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |               |                    |              |                                            |
| 340      | Ventas internacionales       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |               |                    |              |                                            |

En la tabla siguiente se muestra un ejemplo de una definición de columna que usa forzado para un informe estadístico.

|                              | A   | mil millones    | C      | D            | E     | F            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| Encabezado 1                     | A   | mil millones    | C      | D            | E     | F            |
| Encabezado 2                     | -   | -    | Año hasta la fecha    | Ventas anuales | Personal | $ por persona |
| Encabezado 3                     |     |      |        |              |       |              |
| Tipo de columna                  | FILA | DESC | FD     | CALC         | CALC  | CALC         |
| Código de libro/Categoría de atributo |     |      | REAL |              |       |              |
| Ejercicio                  |     |      | BASE   |              |       |              |
| Periodo                       |     |      | BASE   |              |       |              |
| Período de cobertura              |     |      | Ejercicio a fecha    |              |       |              |
| Fórmula                      |     |      |        |              |       | E-D          |
| Ancho de columna                 | 5   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Limitar una fila a una unidad de notificación específica
Cuando una fila del informe se limita a una unidad de notificación específica, dicha fila muestra los datos vinculados únicamente para la unidad de notificación denominada y se omiten los datos para otras unidades de notificación en el organigrama. Por ejemplo, puede crear una fila que proporciona los detalles de los gastos de operaciones totales de un departamento específico. Su informe puede contener datos duplicados si el informe contiene un organigrama y una definición de fila que tiene más que sólo la cuenta natural. Por ejemplo, tiene un organigrama que enumera los seis departamentos de su organización, y también tiene una definición de fila que enumera una combinación específica de una cuenta y un departamento en la fila. Cuando se genera el informe, la combinación específica de una cuenta y de un departamento se imprimen en cada nivel del organigrama, aunque dicho departamento puede no coincidir con la cantidad que se encuentra en el organigrama. Este comportamiento ocurre porque la fila reemplaza lo que se filtra normalmente por la definición del informe. Una manera de evitar la duplicación de datos es restringir una fila a una unidad de notificación específica. **Nota:** Si una fila incluye dimensiones, y se restringe dicha fila a una unidad de notificación secundaria, el importe de la fila se incluye para esa unidad secundaria y para las unidades principales, pero ninguna duplicación ocurre.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Restringir una fila a una unidad de notificación

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después seleccione una definición de fila para modificarla.
2.  Haga doble clic en la celda **Fórmulas o filas o unidades relacionadas** adecuada.
3.  En el cuadro de diálogo **Selección de la unidad de notificación**, en el campo **Organigrama**, seleccione el organigrama que se asigna en la definición del informe.
4.  Seleccione una unidad de notificación y, a continuación, haga clic en **Aceptar**. La restricción aparece en la celda de la definición de filas.
5.  Haga doble clic en la celda en la columna **Vínculo a las dimensiones financieras** de la fila limitada, y especifique un vínculo al conjunto de datos financieros.

## <a name="selecting-print-control-in-a-row-definition"></a>Selección de control de impresión en una definición de filas
Puede especificar los códigos de control de impresión para cada columna mediante la celda **Control de impresión**.

### <a name="add-print-control-codes-to-a-report-row"></a>Agregar los códigos de control de impresión a una fila del informe

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  Haga doble clic en la celda **Control de impresión**.
3.  En el cuadro de diálogo **Control de impresión**, seleccione un código de control de impresión o mantenga presionada la tecla Ctrl para seleccionar varios códigos. También puede escribir los códigos de control de impresión directamente en la celda **Control de impresión**. Use comas para separar varios códigos de control de impresión.
4.  Seleccione cualquier opción condicional de impresión.
5.  Haga clic en **Aceptar**.

### <a name="regular-print-control-codes"></a>Códigos de control regulares de impresión

En la tabla siguiente se describen los códigos de control normales de impresión para una definición de filas.

| Código de control de impresión | Interpretación del código de control de impresión         | Descripción                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Fila sin impresión (NP)                                 | Evita que los importes en la fila se impriman en el informe, y excluye los importes de cálculos. Para incluir una columna de no impresión en un cálculo, vaya a la columna directamente en la fórmula de cálculo. Por ejemplo, la fila sin impresión 240 se incluye en el cálculo siguiente: **230+240+250**. Sin embargo, la fila sin impresión 240 no se incluye en el cálculo siguiente: **230:250**. |
| CS                 | Símbolo de la divisa; use el formato de la divisa en la fila | Incluya el símbolo de la divisa en todos los importes de menor porcentaje. Los valores de porcentaje nunca reciben un símbolo de la divisa.                                                                                                                                                                                                                                                                                                |
| XD                 | Eliminar la fila en el informe de detalle de la cuenta            | Elimine la visualización de cuentas en los informes de detalle a cuenta y los informes de detalle de transacción. Este control de impresión es útil cuando una fila incluye varias cuentas que no deben aparecer en el informe de detalle de la cuenta o el informe de detalle de transacción.                                                                                                                                                           |
| X0                 | Eliminar la fila si todos son ceros                        | Excluir una fila del informe si todas las celdas en esa fila están vacías o contienen ceros. Este control de impresión es importante solo si la opción de eliminar el saldo cero no se selecciona en la definición del informe.                                                                                                                                                                                            |
| B0                 | Deje en blanco las columnas con cero                         | Deje las columnas en blanco en una fila que contiene los importes cero.                                                                                                                                                                                                                                                                                                                                                      |
| XR                 | Eliminar acumulación                                  | Eliminar una acumulación. Si el informe usa un organigrama, los importes en esta fila no se agrupan en nodos principales posteriores.                                                                                                                                                                                                                                                                               |
| SR                 | Eliminar redondeo                                | Evitar que los importes en este fila se redondeen.                                                                                                                                                                                                                                                                                                                                                          |
| XT                 | Eliminar la fila en el informe de detalle de la transacción        | Eliminar la visualización de transacciones en los informes de detalle de transacción. Este control de impresión es útil cuando una fila incluye varias cuentas que no deben aparecer en un informe de detalle de transacción.                                                                                                                                                                                                             |

### <a name="conditional-print-control-codes"></a>Códigos de control de impresión condicionales

En la tabla siguiente se describen los códigos de control condicionales de impresión para una definición de filas.

| Código de control de impresión | Descripción                                  |
|--------------------|----------------------------------------------|
| (ninguno)             | Borre la selección condicional de impresión.       |
| DR                 | Impresión solo los saldos de débito para esta fila.  |
| CR                 | Impresión solo los saldos de crédito para esta fila. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Celda de restricción de la columna en una definición de filas
La celda **Restricción de la columna** en una definición de fila tiene varios fines. En función del tipo de fila, puede usar la celda **Restricción de la columna** para especificar una de las funciones siguientes:

-   La celda puede limitar la impresión de los importes de la fila en una columna específica. Esta función resulta útil si está creando un balance de situación tabular.
-   La celda puede especificar la columna de importes que hay que ordenar.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Usar una fórmula de cálculo en una definición de filas
Una definición de la fórmula de cálculo en una fila puede incluir ** **+,-** **, ** **\*,/y ** ** los operadores, y también ** IF/THEN/ELSE ** las instrucciones. Además, un cálculo puede implicar las celdas individuales y los importes absolutos (números reales que se incluyen en la fórmula). La fórmula puede contener hasta 1.024 caracteres. Los cálculos no se pueden aplicar a las filas que contengan las celdas de tipo **Vínculo a las dimensiones financieras** (FD). Sin embargo, puede incluir cálculos de filas consecutivas, eliminar la impresión de dichas filas y calcular el total de las filas de cálculo.

### <a name="operators-in-a-calculation-formula"></a>Operadores de una fórmula de cálculo

Una fórmula de cálculo usa operadores más complejos que una fórmula total de la fila. Sin embargo, se pueden utilizar ** **\*y/** ** los operadores así como los operadores adicionales para multiplicar (\*) y para dividir (/) importes. Para usar un intervalo especificado o una suma en una fórmula de cálculo, debe usar en el signo (@) antes de cualquier código de la fila, a menos que esté usando una columna en la definición de filas. Por ejemplo, para agregar el importe en la fila 100 el importe de la fila 330, puede usar la fórmula del total de fila ** 100+330 ** o la fórmula de cálculo **@100+@330**. **Nota:** Debe usar en el signo (@) antes de cada código de la fila que usa en una fórmula de cálculo. De lo contrario, el número se lee como un importe absoluto. Por ejemplo, la fórmula **@100+330 ** 330 USD agrega al importe de la fila 100. Al hacer referencia a una columna en una fórmula de cálculo no se requiere, no se requiere el signo (@).

### <a name="create-a-calculation-formula"></a>Crear una fórmula de cálculo

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Haga doble clic en la celda **Código de formato** y luego seleccione **CAL**.
3.  En la celda **Fórmulas, filas o unidades relacionadas**, especifique la fórmula de cálculo.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Ejemplo de una fórmula de cálculo para las filas específicas

En este ejemplo, la fórmula de cálculo **@100+@330** significa que el importe de la fila 100 se agregan al importe de la fila 330. La fórmula del total de fila ** 340+370 ** agregar el importe en la fila 340 al importe de la fila 370. (El importe en la fila 370 es el importe de la fórmula de cálculo.)

| Código de fila | Descripción                 | Código de formato | Fórmulas, filas o unidad relacionadas | Control de impresión | Modificante de la fila | Vínculo a dimensiones financieras |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Efectivo al inicio del período |             |                            | NP            | BB           | 1100:1110 de +Account=\]\[       |
| 370      | Efectivo al inicio del año   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Efectivo al inicio del período | TOT         | 340+370                    |               |              |                              |

Cuando la fila en una definición de fila tiene un código de formato **CAL**, y se especifica un cálculo matemático en la celda **Fórmulas o filas o unidades relacionadas**, también debe especificar la letra de la columna y de la fila asociadas en el informe. Por ejemplo, escriba A.120 ** ** para representar la columna A, fila 120. Como alternativa, puede usar una arroba (@) para indicar todas las columnas. Por ejemplo, escriba@120** ** para representar todas las columnas de la fila 120. Cualquier cálculo matemático que no tenga una letra de la columna o una arroba (@) se asume para ser un número real. ** Nota: ** Si usa un código de la fila de la etiqueta para hacer referencia a una fila, debe usar un período (.) como separador entre la letra de la columna y la etiqueta (por ejemplo, ** A.GROSS\_MARGIN/A.SALES **). Si usa una arroba (@), un separador no se requiere (por ejemplo, **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Ejemplo de una fórmula de cálculo para una columna específica

En este ejemplo, la fórmula **E=C.340** de cálculo significa que el cálculo en la celda en la columna C, fila 340, se realizará únicamente en la columna E. **Nota:** Cuando hace referencia a una columna en una fórmula de cálculo, el signo @ no se requiere.

| Código de fila | Descripción                 | Código de formato | Fórmulas, filas o unidad relacionadas | Control de impresión | Modificante de la fila | Vínculo a dimensiones financieras |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Efectivo al inicio del período |             |                            | NP            | BB           | 1100:1110 de +Account=\]\[       |
| 370      | Efectivo al inicio del año   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Efectivo al inicio del período | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Modificación de un número en columnas seleccionadas

Cuando modifica un número o un cálculo de una columna de una fila en particular pero no desea que afecte a otras columnas en el informe, puede especificar **CAL** (cálculo) en la columna **Código de formato** de la definición de filas.

-   Para realizar un cálculo en todas las columnas del informe (**FD**), no especifique una asignación de la columna.
-   Para limitar una a las columnas específicas, especifique la letra de la columna, un signo igual (**=**) y, a continuación la fórmula.
-   Puede especificar varias columnas. Cuando usa el signo @ con la situación específica de la columna, el signo @ está relacionado con la fila.
-   Puede especificar varias fórmulas de la columna en una fila. Escriba las fórumlas separadas por comas.

### <a name="calculation-examples"></a>Ejemplos de cálculo

| Cálculo            | Acción que se crea                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Para cada columna, el valor de la fila 130 se multiplica por 0.75. El resultado se configura en la fila actual de cada columna. |
| B=@130\*.75            | El mismo cálculo se realiza sólo en la columna B.                                                                      |
| A, B, C=@100/@130(\*) .75 | A= A.100/A.130 (\*) B= .75 (\*) B.100/B.130 .75 C= (C.100/C.130\*.75)                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>La expresiones IF/THEN/ELSE en una definición de filas

Las expresiones **IF/THEN/ELSE** se pueden agregar a cualquier cálculo válido y usar con el formato **CAL**. Puede especificar las fórmulas de cálculo **IF/THEN/ELSE** en la celda en la columna **Fórmulas o filas o unidades relacionadas** la columna. ** IF/THEN/ELSE ** las fórmulas de cálculo usan el formato siguiente: SI &lt;la fórmula OTRA de la fórmula del extracto&gt; verdadera &lt;o&gt; falsa &lt;ENTONCES&gt; ** fórmula &lt;OTRA&gt;** la parte del extracto es opcional.

#### <a name="if-statements"></a>Expresiones IF

La expresión que sigue a la expresión **IF** puede ser cualquiera expresión que se pueda evaluar como verdadera o falsa. La expresión que sigue a la expresión **IF** puede implicar una evaluación simple, o puede ser una expresión compleja que puede contener varias expresiones. A continuación se incluyen algunos ejemplos:

-   ** IF A.2000&gt;** (evaluación simple)
-   ** IF A.2000&gt;Y A.20010&lt;, 000 ** compleja (informe)
-   ** IF A.20010000&gt;O bien ((A.340/B.1200\*2) &lt;1200)** (Instrucción compleja que contiene expresiones varios)

El término **Períodos** en una expresión **IF** representa el número de períodos para el informe. Este término se usa normalmente para calcular un promedio del proyecto a la fecha. Por ejemplo, al ejecutar un informe para el período 7 YTD, la expresión **B.150/Períodos** significa que el valor de la fila 150 de la columna B se divide por 7.

#### <a name="then-and-else-formulas"></a>Las fórmulas THEN y ELSE

La fórmulas **THEN** y **ELSE** pueden ser cualquier cálculo válido, desde asignaciones muy simples de valor a fórmulas complejas. Por ejemplo, la instrucción ** IF A.2000&gt;ENTONCES A=B.200 ** medios, “si el valor de la celda de la columna A de la fila 200 más de 0 (cero), cursan el valor de la celda en la Empresa B de la columna de la fila 200 en la celda en la columna A de la ficha actual.” La expresión anterior **IF/THEN** configura un valor en una columna de la ficha actual. Sin embargo, puede usar el signo @ en evaluaciones de verdadero falso o la fórmula para representar todas las columnas. A continuación se muestran algunos otros ejemplos que se describen en las siguientes secciones:

-   ** IF A.200 &gt;0 ENTONCES B.200 **: Si el valor de la celda A.200 es positivo, el valor de la celda B.200 se coloca en cada columna de la ficha actual.
-   ** IF A.200 &gt;0 ENTONCES @200**: Si el valor de la celda A.200 es positivo, el valor de cada columna de la fila 200 se coloca en la columna correspondiente en la ficha actual.
-   ** IF @200&gt;0 ENTONCES @200**: Si el valor de la fila 200 de la columna actual es positivo, el valor de la fila 200 se coloca en la misma columna en la ficha actual.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Restricción de un cálculo a una unidad de notificación en una definición de filas

Para restringir un cálculo a una sola unidad de notificación en un árbol de informes, no para ejecutar el importe resultante hasta una unidad de alto nivel, puede usar@Unit** ** el código en ** las fórmulas o las filas o las unidades relacionadas ** la celda en la definición de filas. **@Unit** el código se enumera en la Empresa B de la columna del árbol del informe de errores, ** nombre de la unidad **. Cuando usa@Unit** ** el código, los valores no se agrupan por arriba, pero el cálculo se evalúa en todos los niveles de árbol de informes. **Nota:** Para usar esta función, un organigrama debe estar asociado con la definición de filas. La fila de cálculo puede hacer referencia a una fila de cálculo o a una fila de datos financieros. El cálculo se registra en la celda **Fórmulas o filas o unidades relacionadas** de la definición de filas y de la restricción financiera del tipo de datos. El cálculo debe usar un cálculo condicional que empiece por ** IF @Unit** construcción. A continuación se indica un ejemplo: SI @Unit(VENTAS) ENTONCES @100 0 este cálculo incluye el importe de la fila 100 en cada columna del informe, pero únicamente para la unidad de ventas. Si las unidades varias se denominan VENTAS, el importe aparece en cada una de las unidades. Además, la fila 100 puede ser una fila de datos financieros y se puede definir como sin impresión. En este caso, se evita que el importe aparezca en todas las unidades del organigrama. También puede limitar el importe a una columna única del informe, como la columna H, mediante una restricción de columna para imprimir el valor solo en esa columna del informe. Puede incluir combinaciones de **OR** en una expresión **SI**. A continuación se indica un ejemplo: SI @Unit(VENTAS) O bien SALESWEST @Unit(5) ENTONCES @100 ELSE puede especificar una unidad en una restricción del tipo de cálculo en una de las siguientes maneras:

-   Escriba un nombre de la unidad para incluir las unidades que coinciden. Por ejemplo, ** IF @Unit(VENTAS) ** permisos el cálculo para cualquier unidad que se denomina SALES, incluso si hay varias unidades de ventas en el árbol de informes.
-   Especifique el nombre de la empresa y la unidad para restringir el cálculo a unidades específicas de una empresa específica. Por ejemplo, escriba ** IF @Unit(CUMBRE: VENTAS **) limitar el cálculo a las unidades de ventas en la empresa de la CUMBRE.
-   Especifique el código completo de la jerarquía del organigrama para restringir el cálculo en una unidad específica. Por ejemplo, escriba ** IF @Unit(SUMMARY^ACME^WEST COAST^SALES **). **Nota:** Para buscar el código completo de la jerarquía, haga clic con el botón secundario en la definición del organigrama y luego seleccione **Copiar identificador de la unidad de notificación (código H)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Restringir un cálculo a una unidad de notificación

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  Haga doble clic en la celda **Código de formato** y luego seleccione **CAL**.
3.  Haga clic en ** las fórmulas o las filas o las unidades relacionadas ** a la celda, y especifique un cálculo condicional que empiece por ** IF @Unit** construcción.

### <a name="ifthenelse-statements-in-a-column-definition"></a>La expresiones IF/THEN/ELSE en una definición de columna

Una expresión **IF/THEN/ELSE** permite a cualquier cálculo depender de los resultados de cualquier otra columna. Puede hacer referencia a otras columnas, pero no puede hacer referencia a una celda del informe en la expresión **IF**. Cualquier cálculo se debe aplicar a la columna completa. Por ejemplo, la instrucción ** IF ENTONCES&gt;\*OTRA C de la B100 B 1.25 ** medios, “si es el importe B en la columna más de 100, cursan el valor B de la columna en ** CALC ** columna. Si el importe en la columna B no es más de 100, multiplique el valor de la columna C por 1.25, y configure el resultado en la columna **CALC**.” Siga siempre la expresión **IF** con una expresión de lógica que se pueda evaluar como verdadero o falso. Las fórmulas que usa para las expresiones **THEN** y **ELSE** pueden contener referencias a cualquier número de columnas, y estas fórmulas pueden ser tan complejas como quiera. **Nota:** No puede configurar los resultados del cálculo en ninguna otra columna. Los resultados deben encontrarse en la columna que contiene la fórmula.


