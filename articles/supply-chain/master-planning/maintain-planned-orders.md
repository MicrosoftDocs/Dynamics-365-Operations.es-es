---
title: Mantener pedidos planificados
description: En este artículo se proporciona información sobre el modo de administrar pedidos planificados. Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.
author: t-benebo
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c127b25644e417983672c8111925ecd3a51d6ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850710"
---
# <a name="maintain-planned-orders"></a>Mantener pedidos planificados

[!include [banner](../includes/banner.md)]

En este artículo se proporciona información sobre el modo de administrar pedidos planificados. Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.

Puede gestionar pedidos planificados desde el espacio de trabajo **Planificación maestra**, la lista **Pedido planificado** o las listas **Pedidos de producción planificados**, **Pedidos de compra planificados** y **Transferencia planificada**. 

## <a name="planned-order-status"></a>Estado de pedido planificado
Puede usar el campo **Estado** para ayudar a realizar un seguimiento del progreso. Se usan los siguientes valores:

-   Cuando la planificación maestra genera pedidos planificados, estos tienen un estado **No procesado**.
-   Si decide no poner en firme un pedido planificado, puede darle un estado **Finalizado**.
-   Si desea consolidar un pedido planificado, puede cambiar el estado a **Aprobado**. Los pedidos planificados con estado **Aprobado** se respetan por la planificación maestra, por lo que no se modifican ni se eliminan durante una ejecución de planificación maestra posterior. Para lograr esto, la lógica de planificación copia los pedidos planificados **Aprobados** desde la versión anterior del plan a la nueva versión del plan durante la planificación maestra.

## <a name="firming-planned-orders"></a>Consolidar pedidos planificados 
Al consolidar los pedidos planificados, se crean los pedidos reales. También se llaman *pedidos liberados* o *abiertos*. Al poner en firme un pedido planificado, este se mueve a la sección de pedidos del módulo relevante.

Puede seleccionar dos opciones de consolidación en la página **Pedidos planificados**:

-   **Consolidar**: esto consolidará uno o varios pedidos planificados seleccionados.
-   **Consolidar todos**: esto consolidará todos los pedidos planificados en el filtro. Al usar **Consolidar todos**, no es necesario que seleccione el pedido planificado, todos los pedidos planificados en el filtro se consolidarán. Esta opción resulta útil si está consolidando un número elevado de pedidos planificados.

> [!NOTE]
> Puede llevar el seguimiento de un pedido planificado que se ha consolidado desde **Historial de consolidación** en **Formulario de pedidos planificados > Ver > Historial de consolidación**.

## <a name="parallelize-firming"></a>Paralelizar la puesta en firme
Si tiene previsto consolidar muchos pedidos al mismo tiempo, una ejecución en paralelo puede mejorar el tiempo de ejecución o el rendimiento. Esta opción está disponible al consolidar múltiples pedidos planificados con **Consolidar** o **Consolidar todos**. Están disponibles los siguientes parámetros:

-   **Consolidar en paralelo**: si se establece en **Sí** el proceso de consolidación se hará en paralelo con el número de subprocesos definidos en **Número de subprocesos**.
-   **Número de subprocesos**: controla el número de subprocesos utilizados para ejecutar en paralelo en proceso de consolidación. El parámetro se muestra solo cuando **Consolidación en paralelo** se establece en **Sí**.

> [!NOTE]
> La opción para **Paralelizar la puesta en firme** solo se muestra cuando se selecciona más de un pedido planificado para la puesta en firme.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los planes maestros](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]