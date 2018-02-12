---
title: "Mensajes de acción"
description: "Un mensaje de acción es una sugerencia generada por el sistema para cambiar una orden de planificada o en firme existente."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0990ddc9c330b1d590e4c49eba0582c9cf70aa06
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="action-messages"></a>Mensajes de acción

[!include[banner](../includes/banner.md)]


Un mensaje de acción es una sugerencia generada por el sistema para cambiar una orden de planificada o en firme existente.

## <a name="introduction"></a>Introducción

Los mensajes de acción se generan por el cálculo de planificación maestra en respuesta a los requisitos modificados. Por ejemplo, la fecha de envío o la cantidad pueden haber cambiado en un pedido de ventas para el que ya se ha creado un pedido de compra para satisfacer la demanda. En este caso, se generan uno o varios mensajes de acción a través del cálculo de la planificación maestra para actualizar el pedido de compra. Puede decidir si desea aplicar los cambios sugeridos.

Configure la forma de calcular mensajes de acción para un grupo de cobertura que vincule a un artículo.

## <a name="select-action-messages"></a>Seleccione los mensajes de acción

En la página **Grupos de cobertura** puede seleccionar los mensajes de acción que desea que el sistema genere, y los grupos de cobertura o los artículos a los que se aplican los mensajes. Puede seleccionar los siguientes mensajes de acción.

| Mensaje             | Descripción                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Adelantar**         | Si selecciona este mensaje, el sistema generará mensajes de acción, si es necesario, para mover pedidos a una fecha anterior. En el campo **Margen anticipado** también puede especificar el número máximo de días entre la recepción y emisión sin la acción de anticipación. |
| **Retrasar**        | Si selecciona este mensaje, el sistema generará mensajes de acción, si es necesario, para mover pedidos a una fecha posterior. En el campo **Retrasar margen** puede especificar el número máximo de días entre la recepción y emisión sin la acción de retraso.       |
| **Disminuir**        | Si selecciona este mensaje, los pedidos de producción, los pedidos de compra y otras transacciones de recepción se deben disminuir para evitar el exceso de niveles de inventario.                                                                                                   |
| **Aumentar**        | Si selecciona este mensaje, los pedidos de producción, los pedidos de compra y otras transacciones de recepción se deben aumentar para evitar casos de escasez de inventario.                                                                                                    |
| **Acciones derivadas** | Si selecciona este mensaje, se crean mensajes de acción para requisitos derivados, por ejemplo, acciones para pedidos de componentes que satisfacen la producción.                                                                                                   |






