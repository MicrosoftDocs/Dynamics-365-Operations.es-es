---
title: Espacio de trabajo de control de costes
description: Este tema proporciona información sobre del espacio de trabajo Control de costes. Este espacio de trabajo es un punto central donde los directores responsables de supervisar un objeto de coste o un conjunto de objetos de coste dentro de una dimensión o a través de dimensiones pueden obtener acceso a los informes.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c6a196c677ed27666efec8a180f1d3b7e7ee931c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565810"
---
# <a name="cost-control-overview"></a>Visión general del Control de costes 

[!include [banner](../includes/banner.md)]

El espacio de trabajo **Control de costes** es un punto central donde los directores responsables de supervisar un objeto de coste o un conjunto de objetos de coste dentro de una dimensión o a través de dimensiones (por ejemplo, centros de coste y grupos de producto) pueden obtener acceso a los informes. Los informes del espacio de trabajo se gestionan plenamente por contables de coste, de modo que el diseño y los datos que se usan para informes sean coherentes a través de toda la organización.

## <a name="cost-control-workspace-configuration"></a>Configuración del espacio de trabajo del control de costes

Los contables de coste pueden definir tantas configuraciones de informe como sean necesarios para la composición o el diseño deseados de los datos. Una configuración de informe consta de seis secciones, cada una de la cuales contribuye a la selección de la composición de datos de destino o al diseño.

Para configurar un espacio de trabajo de control de costes, haga clic en **Contabilidad de costes** \> **Configuración** \> **Configuración del espacio de trabajo del control de costes**.

### <a name="general"></a>General

En la FastTab **General**, puede crear un diseño de informe único. El nombre del informe será un identificador único que los usuarios podrán reconocer en el espacio de trabajo **Control de costes**. También puede especificar si el informe se debe compartir o mantener en el ámbito interno para los contables de costes.

| Campo       | Descripción |
|-------------|-------------|
| Nombre        | Escriba un nombre único para el diseño. |
| Descripción | Indique una descripción detallada. |
| Publicado   | Si configura este campo en **Sí**, un usuario que esté asignado a uno de los roles siguientes puede ver el informe en el espacio de trabajo **Control de costes**:<ul><li>Administrador de contabilidad de costes</li><li>Contable de costes</li><li>Contable de costes</li><li>Controlador de objeto de coste</li></ul>Si configura este campo en **No**, solo los usuarios que estén asignados a uno de los roles siguientes pueden ver el informe en el espacio de trabajo **Control de costes**:<ul><li>Administrador de contabilidad de costes</li><li>Contable de costes</li><li>Contable de costes</li></ul> |

### <a name="data-filtering"></a>Filtrado de datos

En el FastTab **Filtrado de datos**, se definen los datos base para el informe. Los usuarios de este informe verán valores en el informe después de que se hayan procesado los datos de origen.

| Campo                                                             | Descripción |
|-------------------------------------------------------------------|-------------|
| Libro mayor de contabilidad de costes                                            | El **Libro mayor de la contabilidad de costes** en el que se basa el informe. El valor se deriva del campo **Unidad de control de costes**. |
| Unidad de control de costes                                                 | El valor que seleccione determina el libro mayor de contabilidad de costes y los objetos de coste en los que se basará este informe. |
| Jerarquía de dimensión estadística, jerarquía de dimensión de elemento de coste | Un registro de configuración del espacio de trabajo **Control de costes** puede notificar valores monetarios o no monetarios, pero no con el mismo diseño. Seleccione un valor en el campo **Jerarquía de dimensión de elemento de coste** para notificar valores monetarios. Seleccione un valor en el campo **Jerarquía de dimensión estadística** para notificar valores no monetarios. El registro de la jerarquía de dimensión que seleccione determina la estructura de informe y de los niveles de agregación.<blockquote>[!NOTE]<br>Para ver valores monetarios y no monetarios de forma simultánea, puede exportar datos a Microsoft Excel para el paquete de contenido de Microsoft Power BI.</blockquote> |
| Jerarquía de dimensión de objeto de coste                                   | Seleccione la jerarquía de dimensión de la dimensión del objeto de coste que se adapte al propósito del modo de notificación que esté definiendo. |
| Versión original del presupuesto                                           | Seleccione el identificador de la versión del presupuesto que actúe como el presupuesto original en el contexto de este informe. |
| Versión revisada del presupuesto                                            | Seleccione el identificador de la versión del presupuesto que actúe como el presupuesto revisado en el contexto de este informe. |

### <a name="assign-calculation-records"></a>Asignación de registros de cálculo

El cálculo de gastos generales lleva a cabo varios pasos de cálculo sobre los datos de origen, como clasificación del comportamiento de los costes, la distribución de costes y la asignación de costes. Los cálculos de los gastos generales se pueden realizar para el mismo período fiscal, en caso de que se detecte que faltan datos de origen o que haya que actualizar reglas. Cada cálculo de gastos generales se guarda con un identificador único. El contable de costes puede seleccionar un identificador de cálculo de gastos generales específico. Los usuarios del informe, como los directores, verán los resultados del cálculo de gastos generales en el espacio de trabajo **Control de costes**.

| Campo                  | Descripción |
|------------------------|-------------|
| Período de calendario fiscal | Seleccione el período de calendario fiscal al que asignar un identificador de cálculo de gastos generales.<blockquote>[!NOTE]<br>Los períodos fiscales que se muestran en el campo provienen del calendario fiscal que está asociado a la contabilidad de costes.</blockquote> |
| Versión real         | Seleccione el identificador de cálculo de gastos generales adecuado. |
| Versión de presupuesto         | Seleccione el identificador de cálculo de gastos generales adecuado. |
| Versión de presupuesto revisado | Seleccione el identificador de cálculo de gastos generales adecuado. |

### <a name="fiscal-periods-per-column"></a>Períodos fiscales por columna

En el FastTab **Períodos fiscales por columna**, el contable de costes elige qué período fiscal debe aparecer en el diseño del informe.

Los valores de las columnas seleccionados se multiplicarán por los valores seleccionado en el FastTab **Períodos fiscales por columna**.

| Campo                | Descripción |
|----------------------|-------------|
| Período actual       | Se muestra el saldo del período fiscal actual.<blockquote>[!NOTE]<br>De forma predeterminada, el periodo actual se determina por la fecha de la sesión. En el espacio de trabajo **Control de costes**, se puede seleccionar un período fiscal específico. El valor seleccionado representa el período actual.</blockquote> |
| Período anterior      | Se muestra el saldo del período fiscal anterior. Se usa la siguiente fórmula:<br>Periodo fiscal actual - 1<blockquote>[!NOTE]<br>De forma predeterminada, el periodo anterior se determina según la fecha de la sesión. En el espacio de trabajo **Control de costes**, se puede seleccionar un período fiscal específico como periodo actual. Después, **Período anterior** se volverá a calcular según corresponda.</blockquote> |
| Año hasta la fecha         | Aparece el año hasta la fecha. Se usa la siguiente fórmula:<br>YearToDate (periodo fiscal actual)<blockquote>[!NOTE]<br>De forma predeterminada, el periodo actual se determina por la fecha de la sesión. En el espacio de trabajo **Control de costes**, se puede seleccionar un período fiscal específico. El valor seleccionado representa el período actual y el valor de **Año hasta la fecha** se actualizará en consecuencia.</blockquote> |
| Año hasta la fecha, promedio | Aparece el promedio del año hasta la fecha. Se usa la siguiente fórmula:<br>(YearToDate [Periodo fiscal actual]) ÷ (Recuento [Periodo fiscal actual])<p><strong>Ejemplo </strong></p><ul><li>**Miembro de dimensión estadística:** empleados a jornada completa</li><li>**Fecha actual:** 3-21-2017</li><li>**Período:** período fiscal 1, período fiscal 2, período fiscal 3</li><li>**Magnitud:** 10, 10, 12</li></ul>En este caso, **Año hasta la fecha, promedio** = (10 + 10 + 12) ÷ 3 = 10,67<p>El valor de **Año hasta la fecha, promedio** se puede calcular para los miembros de la dimensión de elementos de coste y los miembros de la dimensión estadística.</p><blockquote>[!NOTE]<br>De forma predeterminada, el periodo actual se determina por la fecha de la sesión. En el espacio de trabajo **Control de costes**, se puede seleccionar un período fiscal específico. El valor seleccionado representa el período actual y los valores de **Año hasta la fecha** y **Año hasta la fecha, promedio** se actualizarán en consecuencia.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Columnas para mostrar de costes

En el FastTab **Columnas para mostrar de costes**, el contable de costes elige qué columnas debe contener el diseño del informe. Existen tres categorías: Coste fijo, Coste variable y Coste sin clasificar.

| Campo                 | Descripción |
|-----------------------|-------------|
| Coste fijo            | Este tipo de columna muestra el coste fijo, en función del identificador de gastos generales seleccionado.<blockquote>[!NOTE]<br>Este tipo de columna mostrará un saldo solo cuando un identificador de cálculo de gastos generales se seleccione para el período fiscal.</blockquote> |
| Coste variable         | Este tipo de columna muestra el coste variable, en función del identificador de gastos generales seleccionado.<blockquote>[!NOTE]<br>Este tipo de columna mostrará un saldo solo cuando un identificador de cálculo de gastos generales se seleccione para el período fiscal.</blockquote> |
| Coste fijo + variable | Este tipo de columna muestra el coste fijo y el coste variable en función del identificador de gastos generales seleccionado.<blockquote>[!NOTE]<br>Este tipo de columna mostrará un saldo solo cuando un identificador de cálculo de gastos generales se seleccione para el período fiscal.</blockquote> |
| Coste total            | Este tipo de columna muestra el coste total (coste sin clasificar, coste fijo y coste variable).<blockquote>[!NOTE]<br>El tipo de columna mostrará el saldo en todo momento.</blockquote> |
| Coste sin clasificar     | Este tipo de columna mostrará el coste sin clasificar.<blockquote>[!NOTE]<br>Esta columna se puede usar para validar si todos los costes se han ordenado correctamente por el cálculo de gastos generales o si las reglas del comportamiento de costes se deben ajustar.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Columnas para mostrar de costes presupuestados

En el FastTab **Columnas para mostrar de costes presupuestados**, el contable de costes elige qué columnas deben mostrarse para las versiones del presupuesto seleccionadas. Las selecciones individuales se pueden realizar para el presupuesto original y revisado.

> [!NOTE]
> Dado que los siguientes campos se comportan de la misma forma para el presupuesto original y el presupuesto revisado, se explicarán solo una vez.

| Campo                     | Descripción |
|---------------------------|-------------|
| Presupuesto                    | Los saldos presupuestarios se mostrarán por las columnas seleccionadas.<blockquote>[!NOTE]<br>Los saldos estarán basados en las versiones del presupuesto seleccionadas en el FastTab **Filtrado de datos**.</blockquote> |
| Desviación del presupuesto           | Calcule y muestre la diferencia entre los valores reales y los valores presupuestados. Se usa la siguiente fórmula:<br>Saldos presupuestario – Saldo real |
| Desviación del presupuesto en %      | Calcule y muestre la diferencia en porcentajes entre los valores reales y los valores presupuestados. Se usa la siguiente fórmula:<br>(Saldo del presupuesto – Saldo real) ÷ Saldo del presupuesto |
| Umbral de desviación del período | Establezca un umbral para la desviación en el importe monetario para el período actual. Si se supera el umbral, la línea se destaca en rojo en el espacio de trabajo **Control de costes**.<blockquote>[!NOTE]<br>Este campo solo se aplica a los elementos de coste que representan gastos.</blockquote> |
| Umbral de desviación del año   | Establezca un umbral para la desviación en el importe monetario para el año. Si se supera el umbral, la línea se destaca en rojo en el espacio de trabajo **Control de costes**. |
| % de umbral de desviación      | Establezca un umbral para la desviación en porcentaje. Si se supera el umbral, la línea se destaca en rojo en el espacio de trabajo **Control de costes**.<blockquote>[!NOTE]<br>El mismo umbral en porcentaje se aplica al período actual y al año.</blockquote> |

## <a name="cost-control-workspace"></a>Espacio de trabajo de control de costes

El espacio de trabajo **Control de costes** está diseñado como un informe web. Por lo tanto, todos los directores responsables de un objeto de coste pueden obtener permiso de acceso como se describe en [Definir los derechos de acceso de un controlador de objeto de coste](access-rights-cost-object-controller.md).

La lista de informes disponibles para los usuarios, como los directores, la controla la configuración de la opción **Publicación** en la página **Configuraciones del espacio de trabajo de control de costes**.

![Un informe que los usuarios pueden ver en el espacio de trabajo Control de costes](./media/report-cost-control.png)

Un director puede seleccionar el período del calendario fiscal que se va a ver. Se utiliza la fecha de la sesión para determinar el periodo actual predeterminado.

Los valores del período del calendario fiscal están determinados por el nombre del informe y se selecciona el calendario fiscal para la contabilidad de costes asociado al nombre del informe en la página **Configuraciones del espacio de trabajo de control de costes**.

En la jerarquía de la dimensión del objeto de coste, los usuarios pueden seleccionar el nivel de agregación en el que los saldos se deben mostrar. Al habilitar la seguridad de nivel de acceso, controla los permisos, de modo que los usuarios pueden seleccionar solo los niveles de la jerarquía a la que se les haya concedido el acceso. Por lo tanto, solo pueden ver los saldos agregados para los que se les ha concedido acceso.

### <a name="add-or-remove-columns"></a>Agregar o quitar columnas

Los usuarios pueden personalizar las columnas de un informe para que se adapte a sus requisitos.

### <a name="view-details"></a>Ver detalles

Los usuarios pueden explorar los detalles de los saldos que se muestran en el espacio de trabajo. Si los usuarios seleccionan un nodo de la jerarquía de dimensiones del elemento de coste y, a continuación, hacen clic en **Detalles de la vista**, el cuadro **Detalles del elemento de coste** muestra la información detallada del nodo.

Una cuadrícula muestra cada elemento de coste que está asociado al nodo de la jerarquía de la dimensión del elemento de coste, y sus valores. Las columnas que aparecen de la cuadrícula coinciden con la configuración del espacio de trabajo.

Dos gráficos muestran un resumen de los valores reales frente a los del presupuesto y la desviación del presupuesto por período.

![Los gráficos que muestran un resumen de los valores reales frente a los del presupuesto y la desviación del presupuesto por período](./media/cost-element-details-operations.png)

Los usuarios pueden hacer clic en **Entradas de costes** para explorar en profundidad los detalles de la entrada según necesiten.

![Entradas de costes](./media/cost-entries.png)

Por ejemplo, el alquiler es un gasto que se distribuye a los centros de coste. Un usuario que desee saber el coste del alquiler en el centro de costes debe realizar una exploración en profundidad para ver cómo se ha calculado el alquiler.

Si los usuarios hacen clic en **Base de asignación** en la página **Entradas de costes**, aparece un cuadro de diálogo. Los usuarios pueden asignar la base de la asignación a la regla y ver las medidas estadísticas correspondientes que se registran para el período.

En el siguiente ejemplo, la base de la asignación es del tipo **Base de asignación de la fórmula**, y se muestra la fórmula. Se enumeran los factores que definen la fórmula. Además, una cuadrícula muestra el cálculo que se realizó por objeto de coste.

![Cálculos por objeto de coste](./media/cost-entries-allocation-base.png)

Recursos adicionales 

[Definir los derechos de acceso de un controlador de objeto de coste](access-rights-cost-object-controller.md)


