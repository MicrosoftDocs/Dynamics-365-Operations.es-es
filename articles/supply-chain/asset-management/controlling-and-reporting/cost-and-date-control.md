---
title: Controlar costes y fechas
description: Este tema explica el control de los costes y las fechas en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918404"
---
# <a name="cost-and-date-control"></a>Controlar costes y fechas

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, puede calcular los costes para obtener una visión general de los costes reales comparados con los costes del presupuesto sobre los activos, ubicaciones técnicas y órdenes de trabajo. Los costes reales se basan en las transacciones registradas. También puede crear un cálculo de fecha si desea comparar las fechas de inicio y fin programadas con las fechas de inicio y fin reales en las órdenes de trabajo.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Control de costes para los activos, las ubicaciones técnicas y las órdenes de trabajo

Los cálculos realizados para los activos, las ubicaciones técnicas y las órdenes de trabajo son idénticos casi. Únicamente la diferencia es que en los activos y las ubicaciones técnicas, también puede incluir subactivos y sububicaciones en el cálculo. La fecha es la fecha de la transacción en la que el registro se ha registrado.

1. Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Control de costes de activos** o **Control de costes de ubicación técnica** o **Administración de activos** > **Consultas** > **Órdenes de trabajo** > **Control de costes de órdenes de trabajo**.

2. En el diálogo**Control de costes de activos** / **Control de costes de la ubicación técnica** / **Control de costes de órdenes de pedido**, seleccione un período para el cálculo.

3. Si es necesario, seleccione un conjunto de dimensiones financieras que se incluirá en el cálculo.

4. Seleccione "Sí" en el botón de alternar **Omitir cero** si no desea mostrar los resultados con un coste de cero.

5. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de control de costes con respecto a las ubicaciones técnicas. Por ejemplo, si especifica el número "1 "en el campo, y tiene una jerarquía de ubicación técnica de varios niveles, todas las líneas de control de costes de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de control de costes en todo el nivel de la ubicación técnica con el que están relacionadas.

6. Seleccione "Sí" en el botón de alternar **Mostrar gasto comprometido abierto** si desea incluir esa columna en el cálculo.

7. Seleccione "Sí" en el botón de alternar **Incluir subactivos** para mostrar costes relacionados con los activos secundaria como líneas independientes.

8. Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de ubicaciones técnicas y órdenes de trabajo en la ficha desplegable **Registros a incluir**.

9. Haga clic en **Aceptar** para iniciar el cálculo.

La ilustración siguiente muestra un ejemplo del cuadro de diálogo **Control de costes de activos**.

![Figura 1](media/01-controlling-and-reporting.png)

10. En los grupos del panel de acciones **Agrupar por...** en la página **Control de costes de activos**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo de costes. Se resaltarán los botones del panel de acciones seleccionados. Haga clic en un botón para activarlo o desactivarlo.

La ilustración siguiente muestra un ejemplo de resultados del cálculo en **Control de costes de activos**.

![Figura 2](media/02-controlling-and-reporting.png)

Otra forma de realizar un cálculo de costes se seleccionar múltiples activos en **Todos los activos** o **Activos activos**. A continuación, haga clic en el botón **Control de costes** en la pestaña **General**. En el diálogo **Control de costes de activos**, los activos seleccionados se insertan automáticamente en el campo **Activo** en la ficha desplegable **Registros que incluir**. Haga clic en **Aceptar** y aparece un cálculo de costes de los activos seleccionados. El mismo procedimiento se puede realizar para las ubicaciones técnicas en **Todas las ubicaciones técnicas** o **Ubicaciones técnicas activas**, y para las órdenes de trabajo en **Todas las órdenes de trabajo** o **Órdenes de trabajo activas**.

>[!NOTE]
>El campo **Presupuesto original** muestra los costes del presupuesto según la previsión de órdenes de trabajo. El campo **Gasto comprometido** muestra el importe total de gastos que una entidad jurídica se ha comprometido a pagar. El campo **Gasto comprometido abierto** muestra los compromisos de pago de artículos, las horas y los servicios que pedido o recibido pero que aún no pagado. Cuando se han enviado todos los registros de consumo, los costes relacionados se incluyen en el campo **Coste real** .

## <a name="work-order-date-control"></a>Control de fecha de orden de trabajo

Use esta página para obtener una visión general de las fechas de inicio y fin en comparación con las fechas de inicio y fin reales en las órdenes de trabajo.

1. Haga clic en **Administración de activos** > **Consultas** > **Órdenes de trabajo** > **Control de fechas de la orden de trabajo**.

2. Haga clic en **Calcular**.

3. Seleccione una ubicación técnica en el campo **Ubicación técnica**.

4. Inserte el período para el que desea crear el cálculo en los campos **Fecha inicial** y **Fecha final**. Todas las órdenes de trabajo con el inicio esperado dentro del período se incluirán.

5. Haga clic en **Aceptar**.

6. En los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo. Se resaltarán los botones del panel de acciones seleccionados. Haga clic en un botón para activarlo o desactivarlo.

La ilustración siguiente muestra un ejemplo de resultados del cálculo en **Control de fechas de órdenes de trabajo**.

![Figura 3](media/03-controlling-and-reporting.png)

- El campo **Retraso de inicio promedio** muestra la diferencia en días entre la fecha de inicio programada para una orden de trabajo en comparación con la fecha de inicio real. Si, por ejemplo, la fecha de inicio real era dos días antes de la fecha de inicio programada, "-2 "se mostrará en este campo.  
- El campo **Retraso de fin promedio** muestra la diferencia en días entre la fecha de fin programada para una orden de trabajo en comparación con la fecha de fin real. Si, por ejemplo, la fecha de fin real era tres días después de la fecha de fin programada, "3 "se mostrará en este campo.  
- Los campos **Repeticiones** muestran el número de veces que se producen desviaciones en relación con la fecha de inicio programada y real y la fecha de fin programada y real en la orden de trabajo.
