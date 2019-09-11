---
title: Agregar error a orden de trabajo
description: Este tema describe cómo agregar registros de error órdenes de trabajo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875887"
---
# <a name="add-fault-to-work-order"></a>Agregar error a orden de trabajo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Puede agregar los errores configurados en el diseñador de errores para una orden de trabajo. El activo seleccionado en la orden de trabajo debe contener tipos de activos con uno o más registros de error conectados con él. Consulte más información sobre la configuración en la sección [Administración de errores](../setup-for-work-orders/fault-management.md).

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. En la lista, seleccione la orden de trabajo donde desea crear un registro de error y haga clic en **Defecto de activo**.

3. En la ficha desplegable **Síntomas**, haga clic en **Agregar línea**. Un número secuencial de error se inserta automáticamente en el campo **Error** .

4. Seleccione el síntoma relevante en el campo **Síntoma del error**.

5. Seleccione **Área del error** y **Tipo de error**.

6. El campo **Fecha del error**, se inserta automáticamente la fecha actual. Puede seleccionar otra fecha, si fuera necesario.

7. En la ficha desplegable **Causas para el síntoma seleccionado** , agregue una línea que describa el motivo del problema.

8. En la ficha desplegable **Remedios para el síntoma seleccionado**, agregue una línea que describa una posible solución para el problema.

9. Haga clic en **Guardar**.

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Ver errores de activos

En la lista **Errores de activo**, puede obtener una visión general de todos los errores registrados en los activos.

Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Defectos de activos** para abrir la lista.


## <a name="print-asset-fault-report"></a>Imprimir informe de errores de activo

En la página de la lista **Todos los activos**, puede imprimir un informe de defectos de activos que muestra todos los registros de error junto con una visión general gráfica de las estadísticas del error.

1. Haga clic en **Administración de activos** > **Común** > **Activos** > **Todos los activos**.

2. En la lista **Activos**, seleccione el activo para el que desea imprimir un informe de error.

3. En la pestaña **General** > **Sección Informes**, haga clic en **Defecto de activo**.

4. Inserte un período específico o seleccionar un tipo de error.

5. Haga clic en **Aceptar** para imprimir el informe.

>[!NOTE]
>También puede imprimir un informe de error para varios activos o tipos de activo haciendo clic en **Administración de activos** > **Informes** > **Activos** > **Defecto de activo**.

