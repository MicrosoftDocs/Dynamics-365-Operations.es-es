---
title: Ejecución visual y colaborativa
description: En este artículo se describe cómo supervisar los puntos de desacoplo, las zonas de búfer, los pedidos planificados y el historial de planificación de requisitos de materiales basada en la demanda (DDMRP).
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 92e38c6ea19b60ae0a61e55f240ff52698e06933
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689786"
---
# <a name="visual-and-collaborative-execution"></a>Ejecución visual y colaborativa

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

En este artículo se describe cómo supervisar los puntos de desacoplo, las zonas de búfer, los pedidos planificados y el historial de planificación de requisitos de materiales basada en la demanda (DDMRP).

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Realice un seguimiento visual de los búferes y las cantidades de un artículo seleccionado

En Microsoft Dynamics 365 Supply Chain Management, puede realizar un seguimiento visual de cómo los búferes, las cantidades disponibles y los niveles de flujo neto cambian con el tiempo para cualquier producto lanzado seleccionado. Siga estos pasos para abrir y revisar los gráficos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione un elemento liberado que esté configurado como punto de desacoplo. (Para obtener más información, consulte [Posicionamiento de inventario](ddmrp-inventory-positioning.md).)
1. En el panel de acciones, en la pestaña **Plan**, seleccione **Cobertura de artículos**.
1. En la página **Cobertura de artículos**, seleccione un registro de cobertura de artículos que cree un punto de desacoplo. (Este registro mostrará el nombre de un grupo de cobertura que está configurado para crear puntos de desacoplo).
1. Seleccione la pestaña **Disponible**. Esta pestaña incluye un gráfico que muestra cómo las cantidades disponibles cambiaron con el tiempo, junto con el valor del nivel disponible que se registró para un período específico cada vez que se ejecutó la optimización de la planificación. La pestaña también incluye una tabla que muestra a cuál de las siguientes categorías pertenece cada nivel disponible registrado:

    - **Críticamente bajo** – Menos de la mitad del mínimo del período.
    - **Bajo** – Entre la mitad del mínimo y el mínimo.
    - **Disponible promedio** – Entre el mínimo y el mínimo más la zona verde.
    - **Superior al promedio** – Superior a la media.

    ![Niveles disponibles históricos en la pestaña Disponible.](media/ddmrp-on-hand-graph.png "Niveles disponibles históricos en la pestaña Disponible")

    > [!NOTE]
    > Los colores que se utilizan en la pestaña **Disponible** representan diferentes rangos que los colores similares utilizados en la pestaña **Valores de búfer**.

1. Para ver cómo cambiaron los valores de su búfer con el tiempo y cómo se comparan con los niveles disponibles y de flujo neto, seleccione la pestaña **Valores de búfer**.

    ![Niveles disponibles y de flujo neto históricos en la pestaña Valores de búfer.](media/ddmrp-buffer-values-graph.png "Niveles disponibles y de flujo neto históricos en la pestaña Valores de búfer")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Realice un seguimiento del estado y los pedidos planificados para todos los puntos de desacoplo

El espacio de trabajo **MRP controlado por demanda** proporciona varias herramientas, junto con indicadores clave de rendimiento (KPI) y descripciones generales del estado de sus artículos de punto de desacoplo y pedidos planificados relacionados. Para abrirlo, vaya a **Planificación maestra \> Espacios de trabajo \> MRP controlado por demanda**.

![MRP controlado por espacio de trabajo.](media/ddmrp-workspace.png "MRP controlado por espacio de trabajo")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Obtenga resúmenes de puntos de desacoplo y pedidos planificados

Además del espacio de trabajo **MRP controlado por demanda**, Supply Chain Management ofrece varias páginas en las que puede ver información sobre la configuración de DDMRP, los puntos de desacoplo y los pedidos planificados. Algunas de estas páginas también proporcionan botones convenientes en el Panel de acciones que le permiten administrar búferes, ejecutar la planificación maestra y abrir otras vistas relacionadas.

- Para ver el estado del punto de desacoplo por nivel de flujo neto, vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Estado de puntos de desacoplo por flujo neto**.
- Para ver el estado del punto de desacoplo por nivel de inventario disponible, vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Estado de puntos de desacoplo por disponible**.
- Para ver pedidos planificados para puntos de desacoplo, vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Pedidos planificados para puntos de desacoplo**.
- Para ver los plazos de entrega desacoplados, vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Plazo de entrega desacoplado**.

## <a name="clean-up-decoupling-point-buffer-values"></a>Limpiar valores de búfer de puntos de desacople

Con el tiempo, su sistema acumulará una gran cantidad de datos históricos relacionados con los cálculos de búfer en curso. Estos datos históricos harán que su volumen de datos aumente y eventualmente puede afectar el rendimiento de su sistema. Por lo tanto, le recomendamos que limpie de vez en cuando los valores antiguos del búfer del punto de desacoplo.

> [!WARNING]
> El trabajo de limpieza eliminará la configuración histórica del valor del búfer y la información histórica de disponible/flujo neto. No es reversible.

Siga estos pasos para limpiar los valores de búfer para su punto de desacoplo.

1. Vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Limpiar valores de búfer de puntos de desacople**.
1. En el cuadro de diálogo **Limpiar valores de búfer de puntos de desacople**, establezca los siguientes campos:

    - **Eliminar registros anteriores a (días)** – Especifique la antigüedad de los registros más recientes que desea conservar, en días. Se eliminarán todos los registros de valor de búfer de punto de desacoplo que sean más antiguos que este valor.
    - **Plan Maestro** – Seleccione un plan maestro que incluya los artículos que se deberían verse afectados por esta limpieza. La limpieza se aplicará a todos los artículos del plan después de aplicar la configuración de **Filtro** que especifique en este cuadro de diálogo.

1. Para limitar el conjunto de registros en el que debe ejecutarse el trabajo por lotes, en la ficha desplegable **Registros a incluir** seleccione el botón **Filtrar** para abrir el cuadro de diálogo **Consulta**. Este cuadro de diálogo funciona como otros tipos de [trabajos en segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, especifique cómo, cuándo y con qué frecuencia debe realizarse la limpieza. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para agregar un nuevo trabajo a una cola por lotes para ejecución.
