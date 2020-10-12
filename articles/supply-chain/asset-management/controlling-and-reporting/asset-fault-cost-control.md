---
title: Control de costes de defecto de activo
description: Este tema explica el control de costes de los defectos de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 93bd6fb320822f17af5725e227936df623f8d0be
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889178"
---
# <a name="asset-fault-cost-control"></a>Control de costes de defecto de activo

[!include [banner](../../includes/banner.md)]

 

En gestión de activos, puede calcular los costes en los registros de errores del activo para obtener una visión general de los costes reales comparados con los costes del presupuesto. Los costes reales se basan en las transacciones registradas. La fecha es la fecha del defecto en la que el síntoma se ha registrado.

1. Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Control de costes de los defectos de activos** para abrir la lista.

2. En el diálogo **Control de costes de los defectos de activos** , seleccione un conjunto de dimensiones financieras que se incluirá en el cálculo, si procede.

4. Seleccione "Sí" en el botón de alternar **Omitir cero** si no desea mostrar los resultados con un coste de cero.

5. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de control de costes con respecto a las ubicaciones técnicas. 

    Por ejemplo, si especifica el número "1 "en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas las líneas de control de costes de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. 
    
    Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de control de costes de los defectos del activo en todos los niveles de la ubicación técnica con los que están relacionadas.

6. Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de defectos y causas de los defectos en la ficha desplegable **Registros a incluir**.

7. Haga clic en **Aceptar** para iniciar el cálculo.

8. Haga clic en los botones **Agrupar por** para mostrar el nivel de detalle necesario del cálculo. Se resaltarán los botones **Agrupar por** seleccionados. Haga clic en un botón para activarlo o desactivarlo.

## <a name="example"></a>Ejemplo

Este ejemplo muestra un cálculo de control de costes de los errores de activos.

- El campo **Presupuesto original** muestra los costes del presupuesto según la previsión de órdenes de trabajo. 
- El campo **Coste real** muestra los costes registrados en órdenes de trabajo. 
- El campo **Gasto comprometido** muestra el total de costes a los que se comprometió la empresa con respecto a las órdenes de trabajo.

    ![Figura 1](media/05-controlling-and-reporting.png)

Para obtener más información sobre cómo configurar errores, consulte el tema [Administración de errores](../setup-for-work-orders/fault-management.md).
