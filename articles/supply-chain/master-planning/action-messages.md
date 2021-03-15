---
title: Mensajes de acción
description: Un mensaje de acción es una sugerencia generada por el sistema para cambiar una orden de planificada o en firme existente.
author: ChristianRytt
manager: tfehr
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd9efebbe5cfea1bb2c9beedfea4fa0492040ddc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989777"
---
# <a name="action-messages"></a>Mensajes de acción

[!include [banner](../includes/banner.md)]

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







[!INCLUDE[footer-include](../../includes/footer-banner.md)]