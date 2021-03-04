---
title: Aprobar pedidos planificados
description: Este tema describe la aprobación de pedidos planificados que se admiten en Planning Optimization.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b7975088be898ccecceb1f7be009cecff107f6e6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436826"
---
# <a name="approve-planned-orders"></a>Aprobar pedidos planificados

[!include [banner](../../includes/banner.md)]

Este tema proporciona información sobre cómo actualizar el estado de los pedidos planificados en Planning Optimization.

Tenga en cuenta que la aprobación de pedidos planificados es un paso opcional, en el proceso para crear un pedido en firme a partir de un pedido planificado. Se recomienda aprobar los pedidos planificados modificados; de lo contrario, las ediciones se ignorarán y se sobrescribirán en la siguiente ejecución de planificación.

![Flujo de pedido planificado](media/approved-planned-orders-1.png)

El campo **Estado** le ayuda a seguir su progreso utilizando los siguientes valores:

- **No procesado**: cuando la planificación maestra genera pedidos planificados, estos tienen un estado *No procesado*. Los pedidos planificados con este estado se eliminarán durante la siguiente ejecución de planificación.
- **Completado**: si decide no firmar un pedido planificado, puede cambiar el estado a *Completado* para indicar que completó la evaluación de este pedido planificado. Tenga en cuenta que un estado de *No procesado* y *Completado* se tratan de la misma manera por el sistema.
- **Aprobado**: si desea mantener las ediciones o tiene previsto poner en firme un pedido planificado, cambie el estado a *Aprobado*. Los pedidos planificados con estado *Aprobado* se consideran un suministro fijo y esperado por la planificación maestra, por lo que no se modifican ni se eliminan durante una ejecución de planificación maestra posterior. Para lograr esto, la lógica de planificación copia los pedidos planificados *Aprobados* desde la versión anterior del plan a la nueva versión del plan durante la planificación maestra. Tenga en cuenta los pedidos planificados con estado *Aprobado* solo se consideran un suministro dentro del plan maestro específico.

Puede gestionar pedidos planificados desde el espacio de trabajo **Planificación maestra**, la lista **Pedido planificado** o las listas **Pedidos de producción planificados**, **Pedidos de compra planificados** y **Transferencia planificada**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]