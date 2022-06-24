---
title: Marcado de inventario con optimización de planificación
description: Este artículo proporciona información sobre las opciones que están disponibles para marcar el inventario en pedidos firmes cuando usa Planning Optimization.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2f1902ba76db59b61b0437eb3cd68ee94018b7c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844479"
---
# <a name="inventory-marking-with-planning-optimization"></a>Marcado de inventario con optimización de planificación

[!include [banner](../../includes/banner.md)]

Este artículo proporciona información sobre las opciones que están disponibles para marcar el inventario en pedidos firmes cuando usa Planning Optimization.

*Calificación* se utiliza para vincular la oferta y la demanda. Se parece a la *vinculación*, que indica cómo la planificación maestra espera cubrir la demanda. Desde el punto de vista de la planificación, la principal diferencia es que el marcado es más permanente que el pegging.

El marcado se introdujo para admitir escenarios de costos especiales para el primero en entrar, el primero en salir (FIFO) y el último en entrar, primero en salir (LIFO). Sin embargo, ahora también se usa para algunos escenarios sin costos. La marcación entre oferta y demanda es opcional y casi permanente. El usuario puede eliminar manualmente la marca, o puede eliminarse ejecutando una explosión de línea de orden de venta donde **Eliminar marca** está seleccionada la opción.

La vinculación se controla mediante la planificación maestra durante la cobertura para vincular la demanda con el suministro requerido. La trazabilidad se puede actualizar para cada ejecución de planificación para optimizar el suministro que se requiere para cubrir la demanda. Cuando la planificación maestra actualiza la información de trazabilidad, respeta cualquier marca existente.

La vinculación comienza con la inclusión del marcado relevante, las reservas disponibles y las reservas en orden, en la siguiente secuencia:

1. Marcado entre oferta y demanda
1. Reservas disponibles
1. Reservas bajo pedido

Cuando firme una orden planificada, el cuadro de diálogo **Reafirmante** proporciona un campo **Actualizar marcado** que se utiliza para configurar las opciones de marcado para los pedidos que se crean durante el endurecimiento. Seleccione uno de los siguientes valores:

- **No** - No se aplica marcado de inventario.
- **Estándar** – El marcado de inventarios se actualiza de acuerdo con el diagrama de árbol: Un pedido de requisitos (bajo demanda) está marcado en función de un pedido de entrega (suministro). Si queda alguna cantidad en el pedido de cumplimiento, no se marca y la información de referencia se deja en blanco. Por ejemplo, si una orden de venta de 100 ea está vinculada a una orden de compra de 150 ea, la información de referencia se asignará solo a la orden de venta.
- **Extendido** – : el pedido de requisitos (demanda) y el pedido de cumplimiento (suministro) se marcan, independientemente de si queda alguna cantidad en el pedido de cumplimiento. Por ejemplo, si una orden de venta de 100 ea está vinculada a una orden de compra de 150 ea, la información de referencia se asignará a la orden de venta y a la orden de compra.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]