---
title: Generar informes financieros consolidados
description: Este tema describe las distintas situaciones donde se pueden generar los informes financieros consolidados.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: dda102b993ecc92a5089eb54d2708c2adebc572f
ms.sourcegitcommit: f59df61799915f6a79aec7e3e8664c02df6597da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "5044030"
---
# <a name="generate-consolidated-financial-statements"></a>Generar informes financieros consolidados

[!include [banner](../includes/banner.md)]

Este tema describe las distintas situaciones donde se pueden generar los informes financieros consolidados.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Consolidaciones de un solo nivel y varios niveles entre entidades jurídicas
El método más sencillo para consolidar mediante un informe financiero es usar los organigramas para agregar datos de distintas empresas que tienen el mismo plan contable y los mismos períodos fiscales. A continuación se muestran los pasos de alto nivel para realizar consolidaciones mediante un organigrama.

1. Cree una definición de filas, y asegúrese de que todas las cuentas adecuadas de todas las empresas se incluyen en las filas.
2. Cree una definición de columna que incluya todas las columnas que se requieren para el informe que está creando.
3. Cree un árbol de notificación que incluya un nodo de informes para cada empresa que utiliza en los informes consolidados.

> [!TIP]
> Para obtener más información acerca de cómo crear y gestionar definiciones de filas, definiciones de columna, y organigramas, consulte [Componentes de los informes financieros](../../dev-itpro/analytics/financial-report-components.md).

La ilustración siguiente muestra cómo puede usar una definición del organigrama en informes financieros para identificar cada empresa que va a consolidar.

![Definiciones de los organigramas](./media/reporting-tree-definition.png "Definiciones de los organigramas")

Tal y como muestra el informe consolidado de la siguiente ilustración, cuando se usa el organigrama junto con una definición de informe, puede ver cada empresa por separado. Los importes consolidados se muestran en el nivel del extracto.

![Consolidar nivel del extracto del importe](./media/consolidate-amount-summary-level.png "Consolidar nivel del extracto del importe")

También puede crear un árbol de varios niveles de notificación que incluya tantos niveles como sea necesario. La ilustración siguiente muestra una definición de varios niveles del árbol de notificación que tiene acumulaciones indicadas por región mundial.

![Definición de varios niveles del organigrama con acumulaciones por región](./media/multilevel-reporting-tree-definition-roll-ups-worldwide-region.png "Definición de varios niveles del organigrama con acumulaciones por región")

La ilustración siguiente muestra una definición de varios niveles del árbol de notificación que tiene acumulaciones indicadas por función.

![Definición de varios niveles del organigrama con acumulaciones por función](./media/multilevel-reporting-tree-definition-roll-ups-by-function.png "Definición de varios niveles del organigrama con acumulaciones por función")

### <a name="viewing-companies-side-by-side"></a>Ver empresas de forma simultánea
Muchos clientes prefieren los informes que contengan las empresas de forma simultánea y en los que una columna muestra el total consolidado. Este formato es fácil de conseguir una vez que haya creado el organigrama. Aquí se muestran los pasos de nivel superior para ver las empresas de forma simultánea en los informes financieros consolidados.

1. Cree una definición de columna que incluya una columna **Dimensión financiera** para cada empresa.
2. Use el campo **Unidad organizativa** para seleccionar la unidad del árbol y de notificación para cada columna.
3. Opcional: Agregue títulos y las columnas de totales.

La ilustración siguiente muestra una definición de columna en formato simultáneo.

![Definición de columnas en un formato en paralelo](./media/column-definition-side-by-side-format.png "Definición de columnas en un formato en paralelo")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Consolidaciones que usan estructuras de la organización que se crean a partir de las entidades jurídicas
Las jerarquías organizativas que contienen dimensiones o entidades jurídicas crean dinámicamente definiciones del organigrama en informes financieros. Una forma sencilla de agilizar las consolidaciones consiste en agregar una jerarquía organizativa al informe en los informes financieros. En función de la fecha del informe, el informe financiero seleccionará la jerarquía organizativa en la fecha de vigencia o antes, tal y como se muestra en la siguiente ilustración.

![Crear dinámicamente definiciones del organigrama](./media/dynamically-create-reporting-tree-definitions.png "Crear dinámicamente definiciones del organigrama")

## <a name="consolidations-that-involve-eliminations"></a>Consolidaciones que suponen eliminaciones
Las transacciones de eliminación son una parte habitual del proceso de consolidación. En este ejemplo, cinco cuentas se eliminan durante la consolidación: 142600, 211400, 401420, 401180, y 510820. Las empresas pueden configurar sus cuentas de empresas vinculadas de forma diferente. Por ejemplo, algunas empresas establecen el último dígito en 9 si la cuenta se usa en transacciones de empresas vinculadas. Independientemente del método, si conoce las cuentas de empresas vinculadas, puede mostrar las eliminaciones en sus informes financieros consolidados.

La ilustración siguiente muestra una definición de columna para una cuenta de resultados consolidada. Tres cuentas de empresas vinculadas de pérdidas y ganancias se definen para cada empresa mediante el filtro de la dimensión. Las columnas F, G y H incluyen las cuentas de eliminación solo para las empresas USMF, USRT y DEMF. Estas columnas se configuran de forma que **no** se impriman en el informe financiero.

![Cuenta de resultados en la definición de la columna](./media/column-definition-consolidated-income-statement.png "Cuenta de resultados en la definición de la columna")

Cuando se genera el informe, los importes de eliminación se calculan en las columnas F, G, y H y se suman en la columna I. La columna J muestra los importes consolidados. Estos importes de consolidación excluyen las eliminaciones para las empresas de USMF, USRT, y DEMF.

> [!TIP]
> Cree un segundo informe que muestre solo las entradas de eliminación, y utilícelo en un grupo de informes que incluya el informe consolidado. De esta manera, se tiene toda la información necesaria para crear cualquier entrada de diario necesaria.

La ilustración siguiente muestra el informe consolidado.

![Informe de ingresos del informe consolidado](./media/consolidated-report-income-statement.png "Informe de ingresos del informe consolidado")

Si usa cuentas, dimensiones, o ambas, el informe financiero le permite filtrar las entradas de eliminación mediante las capacidades de filtrado de la dimensión.

## <a name="minority-interest"></a>Interés minoritario
Una empresa puede que muestre solo un porcentaje de otra empresa. En esta situación, cuando va a generar un informe consolidado, es importante que tenga en cuenta solo el porcentaje que la empresa posee. El informe financiero tiene varias formas de mostrar interés minoritario, en función de la preferencia del usuario. Una forma consiste en usar un porcentaje de acumulación en la definición del organigrama. Otra forma es mostrar la propiedad minoritaria como línea independiente en un informe.

### <a name="using-the-reporting-tree-definition"></a>Uso de la definición del organigrama
En la definición del organigrama escriba el porcentaje de propiedad que en la columna **% acumulado** (columna H), como se muestra en la siguiente ilustración. Cuando se genera el informe, este porcentaje se usará para calcular el importe consolidado. En este ejemplo, Contoso posee solo el 80 por ciento de Contoso Alemania. Puede especificar **80** o **.8** en la columna **% acumulado** y el 80 por ciento se acumulará hasta el nivel consolidado.

> [!NOTE]
> Puede aplicar este porcentaje de propiedad a cualquier unidad de notificación y no solo en el nivel de empresa. 

![Uso del porcentaje de la definición del organigrama](./media/Using-reporting-tree-definition-percentage.png "Uso del porcentaje de la definición del organigrama")

Cuando se genera el informe, el informe de Contoso Alemania mostrará el 100 por ciento del importe de ventas, y el 80 por ciento del importe se asignará y se consolidará hasta el nivel consolidado para las ventas.

Si posee menos del 1 por ciento de una empresa, puede seleccionar la casilla de verificación **Permitir acumulado inferior a 1%** en la pestaña **Opciones adicionales** de la página **Valores del informe** , tal y como se muestra en la siguiente ilustración. En este caso, los valores de la columna **% acumulado** del organigrama se tratarán como menos de 1 por ciento. Por ejemplo, si especifica **.8**, se acumulará el 0,8 por ciento hasta el nivel consolidado, no el 80 por ciento. Como alternativa, puede alcanzar el mismo resultado dejando la casilla de verificación **Permitir acumulado inferior a 1%** desactivada y especificando **.008** en la columna **% acumulado**.

![Opciones de configuración de informes](./media/reporting-setting-options.png "Opciones de configuración de informes")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>Mostrar la propiedad como una fila independiente en el informe consolidado
Otra opción para el interés minoritario es mostrar el 100 por ciento de la filial para cada línea del informe pero restar el interés que no controla del ingreso neto.

Tal y como muestra la siguiente ilustración, una restricción de columna e informe **IF THEN ELSE** en la definición de fila se puede utilizar para calcular el interés minoritario en informes financieros.

![Mostrar la propiedad como una fila independiente en el informe consolidado](./media/Showing-ownership-separate-row-consolidated-report.png "Mostrar la propiedad como una fila independiente en el informe consolidado")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Numerosos planes contables en entidades jurídicas
A menudo, entidades jurídicas diferentes tienen diferentes planes contables pero de todos modos siguen queriendo generar informes financieros consolidados. En esta situación, el informe financiero se puede usar para consolidar los datos, de manera que pueda generar informes financieros consolidados. Aquí mostramos los pasos de nivel superior para consolidar cuando existen distintos planes de cuentas entre entidades jurídicas.

1. Cree una definición de fila que incluya varios vínculos a dimensiones financieras. Debe haber un vínculo para cada plan de cuentas.
2. Use la restricción de la unidad de informe de la definición de columna para asignar cada empresa a la columna adecuada.


Se pueden agregar numerosos vínculos a varias dimensiones financieras para cada fila de la definición de fila de cada plan de cuentas de empresa única. En la siguiente ilustración, la empresa USMF utiliza el conjunto de cuentas de la primera columna **Vínculo a las dimensiones financieras** (la columna J), y la empresa DEMF utiliza las cuentas de la segunda columna **Vínculo a las dimensiones financieras** columna (K).

> [!TIP]
> Para obtener más información acerca de la celda **Vínculo a las dimensiones financieras**, consulte Especificar un vínculo a la celda Dimensiones financieras.

![Vínculo de configurar cuentas primero para dimensiones financieras](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Vínculo de configurar cuentas primero para dimensiones financieras")

Puede usar un organigrama para definir qué vínculo de las dimensiones financieras de la definición de filas se utiliza para cada empresa. Seleccione la definición de filas en la columna E, y luego seleccione el vínculo de fila adecuado en al columna F, tal y como se muestra en la siguiente ilustración.

![Definición de la fila de vincular dimensiones financieras utilizada](./media/link-financial-dimensions-row-definition-used.png "Definición de la fila de vincular dimensiones financieras utilizada")

> [!TIP]
> Al crear vínculos a dimensiones financieras, use la descripción para identificar las empresas a las que se aplica cada vínculo. De esta manera, puede seleccionar más fácilmente la empresa correcta al crear un organigrama. En la definición de columna, el campo **Unidad organizativa** le permite restringir cada columna a una unidad del organigrama, de modo que pueda ver los datos de forma simultánea. Si no indica una empresa específica para una columna, los datos consolidados de todas las empresas se mostrarán.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Diferentes calendarios fiscales en numerosas entidades jurídicas
Entidades jurídicas pueden tener diferentes calendarios fiscales pero de todos modos se les sigue pidiendo que generen informes financieros consolidados. Hay dos maneras de consolidar cuando existen varios períodos fiscales entre entidades jurídicas:

- Cree una definición de columna, y utilice el período y el año para asignar los períodos adecuados para cada empresa.
- En **Configuración** \> **Otros** \> **Opciones adicionales**, seleccione si consolidar mediante la fecha final del período o el número del período.

Cuando está diseñando la definición de columna para varias empresas con diferentes períodos fiscales, es importante que considere qué empresa asignará al campo **Nombre de la empresa** en la definición de informe. El calendario fiscal de la empresa se usará como el calendario fiscal base para la definición de informe. Por ejemplo, la tabla siguiente muestra el período fiscal establecido para las empresas USMF e INMF. Para los informes consolidados, mejor usar el calendario fiscal que USMF utiliza. La columna ”Asignación" muestra el período y el año equivalentes para cada empresa si un informe se genera para el 30 de junio de 2018.

| Compañía   | Ejercicio                                  | Distribución                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Año fiscal, del 1 de julio al 30 de junio          | Período 12, ejercicio 2018 | 
| INMF      | Año natural, del 1 de enero al 31 de diciembre | Período 6, ejercicio 2018  |

En la siguiente ilustración, la empresa de USMF se especifica en el campo **Nombre de la empresa** en la definición de informe. Por lo tanto, el calendario fiscal de la empresa USMF se usará como el calendario fiscal base. En este ejemplo, cuando un informe se genera para el 30 de junio de 2018, la empresa USMF utilizará el período BASE, que se define como período 12 en la definición de informe. La empresa INMF utilizará BASE-6, que es el período 6. Ambas columnas incluirán los datos para junio de 2018.

![Período base del informe](./media/report-base-period.png "Período base del informe")

La ilustración siguiente muestra las opciones de la definición de informe que le permiten seleccionar si el número del período o la fecha final del período se usa para la consolidación.

![Opciones del número del periodo de definición del informe](./media/options-report-definition-period-number.png "Opciones del número del periodo de definición del informe")

## <a name="business-unit-consolidations"></a>Consolidaciones de unidad de negocio
Este tema se ha enfocado en el uso de definiciones y jerarquías organizativas del organigrama en el informe financiero para la consolidación. También puede usar el organigrama para crear informes de consolidación de unidad de negocio, como informes acerca de ventas u operaciones mundiales. Estos informes son un requisito común. Para crearlos, seleccione una empresa y una dimensión para cada unidad en la que desee realizar una consolidación. Por ejemplo, en la siguiente ilustración, la acumulación de la unidad de negocio se logra repitiendo cada empresa en la columna **Empresa** (columna A) e identificando un grupo de valores de dimensión de departamento por empresa en la columna **Dimensiones** (columna D).

![Informes de consolidaciones de unidad de negocio](./media/business-unit-consolidation-reports.png "Informes de consolidaciones de unidad de negocio")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Consolidaciones que implican varias divisas contables
El informe financiero proporciona mayor flexibilidad al visualizar datos reales, del presupuesto, de control presupuestario y de planificación de presupuesto en varias divisas. Al aunar los datos de configuración clave, no debe realizar ninguna configuración adicional en el informe financiero para ver ningún informe, en cualquier divisa, en cualquier momento, para ningún usuario.

### <a name="prerequisites"></a>Requisitos previos
Para calcular correctamente los saldos convertidos, el informe financiero requiere que la categoría **Cuenta de ganancias retenidas** se asigne a la cuenta de ganancias retenidas en el lista **cuenta principal**. El informe financiero no admite registros en la cuenta de ganancias retenidas. Si se registran transacciones en la cuenta de ganancias retenidas, los saldos convertidos no se calculan correctamente. Recomendamos que los usuarios configuren una cuenta de ganancias retenidas adicionales para registrar ajustes en la cuenta de ganancias retenidas.

En la cuenta principal, los campos **Tipo de cambio del informe financiero** y **Tipo de conversión de la divisa** de la ficha desplegable **Informe financiero** deben definirse para cada cuenta, tal y como se muestra en la siguiente ilustración. Puede completar esta tarea en función de la cuenta o bien puede usar las plantillas de cuenta para desplegar con facilidad los cambios.

- En el campo **Tipo de cambio del informe financiero**, seleccione el tipo de cambio que contiene las divisas y tipos de cambio que se aplican a la cuenta. Esta tabla de divisas y tipos de cambio se aplicará a los datos reales en el informe financiero.
- En el campo **Tipo de traducción de divisa**, seleccione el método que se usa para calcular la divisa de la cuenta. Este método de divisa se usa para los datos reales y de presupuesto en los informes financieros.

![Cuentas principales de informes financieros](./media/Financial-reporting-main-accounts.png "Cuentas principales de informes financieros")

Para los datos del presupuesto, el control presupuestario y planificación de presupuesto, se define el tipo de cambio en la página **Libro mayor**. Esta tabla se usará para extraer los tipos de cambio, y el tipo de conversión de la divisa que se asigna a la cuenta que se utilizará.

### <a name="currency-translation-methods"></a>Métodos de conversión de divisas
Existen cuatro opciones para calcular los tipos de cambio en los informes financieros:

- **Media ponderada** Este método se usa con más frecuencia para las cuentas de pérdidas y ganancias. Se usa la siguiente fórmula:

    (Tipo de cambio × día en vigor) ÷ días del período

- **Media** Este método es un método alternativo para las cuentas de pérdidas y ganancias. Se usa la siguiente fórmula:

    Total de tipos de cambio ÷ Número de tipos de cambio

- **Actual** Este método se usa con más frecuencia para las cuentas de balance de situación. El tipo de cambio que se usa es el tipo de la fecha del informe o columna o anterior a dicho informe o columna en el informe financiero.
- **Fecha de transacción** Este método se usa para las cuentas de activos fijos. El tipo de cambio que se usa es el tipo del día en que se adquirió el activo. Si un índice no se especifica para esa fecha, se utiliza el tipo anterior que se ha especificado más cercano a la fecha de la adquisición del activo.

### <a name="report-designer-options-for-currency-translation"></a>Opciones del diseñador de informes para la converesión de la divisa
En el informe financiero, todos los informes se pueden mostrar en cualquier número de divisas de notificación. Los siguientes campos de la definición del informe admiten esta capacidad:

- La sección **Información de divisa** en la página **Definición de informe**. Esta sección muestra la divisa en la que se muestran los valores cuando se genera un informe.
- Una casilla de verificación **Incluir todas las divisas funcionales** nueva. Si se activa esta casilla de verificación, se agrega un informe para cada divisa de notificación a la cola de informes hasta después de que se genere el informe que usa la divisa funcional de la empresa. Si se desactiva la casilla, aún podrá seleccionar una divisa de notificación en el visor web. En este caso, la divisa de notificación se procesará solo si la selecciona.

Las opciones de la definición de informe le permiten fácilmente convertir un informe en todas las divisas de notificación. Por lo tanto, es posible que pueda eliminar definiciones de informe duplicadas que solo difieran en las divisas que se usan. Si necesita un informe que muestre varias divisas de forma simultánea, puede continuar utilizando el campo **Visualización de la divisa** en la página **Definición de columna** para convertir solo esa columna del informe en una divisa de notificación alternativa.

### <a name="currency-translation-adjustment"></a>Ajuste de la conversión de divisa
El ajuste de la conversión de divisa (CTA) es la diferencia entre los tipos que se utilizan para calcular las cuentas de balance de situación y el tipo que se usa para las cuentas de resultados. Esta diferencia hará que el balance de situación esté fuera de saldo. Puede usar el informe financiero para calcular el CTA de dos maneras:

- Use la página **Ajustes de redondeo** en la definición de fila, como se muestra en la siguiente ilustración.

    ![Ajuste de conversión de divisa, ajustes de redondeo](./media/Currency-translation-adjustment-rounding-adjustments.png "Ajuste de conversión de divisa, ajustes de redondeo")

    Cuando especifica la fila que debe mostrar el ajuste de redondeo (CTA), la fila total de los activos, la fila total de pasivos y recursos propios, y el umbral que le interesa, el informe financiero calculará la diferencia y lo pondrá en la fila deseada. Una línea llamada **Redondear el ajuste** se creará y se mostrará al explorar en profundidad, tal y como se muestra en la siguiente ilustración.

    ![Explorar ajustes de redondeo](./media/rounding-adjustment-drill-down.png "Explorar ajustes de redondeo")

- Ponga todas las cuentas en un intervalo, de activos a los gastos. Tal y como se muestra en la siguiente ilustración, la diferencia será la misma cantidad que el ajuste de redondeo (CTA). Por lo tanto, puede utilizarla como un total de la comprobación para asegurarse de que la página de ajuste de redondeo no incluye ningún saldo de cuenta que faltara.

    ![Comprobación de formulario de ajustes de redondeo](./media/rounding-adjustment-form-check.png "Comprobación de formulario de ajustes de redondeo")

### <a name="balance-calculation-approach"></a>Enfoque de cálculo de saldo
Para obtener los importes convertidos correctamente cuando se usan divisas, el informe financiero utiliza los métodos de cálculo siguientes para los saldos:

- **Media ponderada y media** Cada período se calcula en su media ponderada, y se suman las columnas como trimestral y año hasta la fecha.
- **Histórico** Cualquier cuenta que use el método histórico de conversión siempre se remota a la fecha de transacción. Si una fecha de adquisición está asociada a la transacción, esa fecha se usa para recopilar el tipo de cambio. A continuación cada período se suma y se guarda para ayudar a mejorar el tiempo de cálculo.
- **Actual** Las columnas calculadas y de total, como las columnas para los valores trimestral y año hasta la fecha, se calculan con la tasa de zona que se determina en la columna o en el informe. Por ejemplo, la columna **Trimestre 1** utilizará la tasa del 31 de marzo si se usa un año natural.

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más información acerca de las conversiones de consolidación y divisas, consulte el tema principal de este tema [Visión general de consolidaciones financieras y conversión de divisas](./financial-consolidations-currency-translation.md).

Para obtener más información acerca de cómo especificar los detalles de consolidaciones en línea, consulte [Consolidaciones financieras en línea](./consolidate-online.md).
