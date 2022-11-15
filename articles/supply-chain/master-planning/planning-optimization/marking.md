---
title: Marcado de inventario
description: Este artículo proporciona información sobre las opciones que están disponibles para marcar el inventario en pedidos firmes.
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
ms.openlocfilehash: c86db6a670d7d0f7bfe74b7466b9bce766e4a08d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740613"
---
# <a name="inventory-marking"></a>Marcado de inventario

[!include [banner](../../includes/banner.md)]

Este artículo proporciona información sobre las opciones que están disponibles para marcar el inventario en pedidos firmes.

*Calificación* se utiliza para vincular la oferta y la demanda. Se parece a la *vinculación*, que indica cómo la planificación maestra espera cubrir la demanda. Desde el punto de vista de la planificación, la principal diferencia es que el marcado es más permanente que el pegging.

El marcado se introdujo para admitir escenarios de costos especiales para el primero en entrar, el primero en salir (FIFO) y el último en entrar, primero en salir (LIFO). Sin embargo, ahora también se usa para algunos escenarios sin costos. La marcación entre oferta y demanda es opcional y casi permanente. El usuario puede eliminar manualmente la marca, o puede eliminarse ejecutando una explosión de línea de orden de venta donde **Eliminar marca** está seleccionada la opción.

La vinculación se controla mediante la planificación maestra durante la cobertura para vincular la demanda con el suministro requerido. La trazabilidad se puede actualizar para cada ejecución de planificación para optimizar el suministro que se requiere para cubrir la demanda. Cuando la planificación maestra actualiza la información de trazabilidad, respeta cualquier marca existente.

La vinculación comienza con la inclusión del marcado relevante, las reservas disponibles y las reservas en orden, en la siguiente secuencia:

1. Marcado entre oferta y demanda
1. Reservas disponibles
1. Reservas bajo pedido

Cuando firme una orden planificada, el cuadro de diálogo **Reafirmante** proporciona un campo **Actualizar marcado** que se utiliza para configurar las opciones de marcado para los pedidos que se crean durante el endurecimiento. Seleccione uno de los siguientes valores:

- *No* - No se aplica marcado de inventario.
- *Estándar* – El marcado de inventarios se actualiza de acuerdo con el diagrama de árbol: Un pedido de requisitos (bajo demanda) está marcado en función de un pedido de entrega (suministro). Si queda alguna cantidad en el pedido de cumplimiento, no se marca y la información de referencia se deja en blanco. Por ejemplo, si una orden de venta de 100 ea está vinculada a una orden de compra de 150 ea, la información de referencia se asignará solo a la orden de venta.
- *Extendido* – : el pedido de requisitos (demanda) y el pedido de cumplimiento (suministro) se marcan, independientemente de si queda alguna cantidad en el pedido de cumplimiento. Por ejemplo, si una orden de venta de 100 ea está vinculada a una orden de compra de 150 ea, la información de referencia se asignará a la orden de venta y a la orden de compra.
- *Estándar de un solo nivel* – Se utiliza el marcado de un solo nivel. El marcado de un solo nivel marca solo el artículo principal, no sus componentes de la lista de materiales (BOM). Por lo tanto, puede mantener flexible la asignación de componentes para órdenes de fabricación después de la puesta en firme. El marcado de un solo nivel permite que el sistema se optimice para los cambios de demanda de última hora. En el marcado de un solo nivel *estándar*, los pedidos de requisitos se marcan con respecto a sus pedidos de cumplimiento, pero los pedidos de cumplimiento no se marcan si tienen una cantidad restante.
- *Un solo nivel extendido* – Se utiliza el marcado de un solo nivel. En el marcado de un solo nivel *extendido*, los pedidos de requisitos se marcan con respecto a sus pedidos de cumplimiento y los pedidos de cumplimiento siempre se marcan sin importar si tienen una cantidad restante.

Para establecer la opción de marcado predeterminada para su sistema, vaya a **Planificacion maestra \> Configuración \> Parámetros de planificación maestra**. Luego, en la pestaña **Actualización estándar**, configure el campo **Actualizar marcado** con su opción preferida.

> [!NOTE]
> Las opciones *Estándar de un solo nivel* y *Ampliación de un solo nivel* están disponibles sólo si la función *Automatización de suministro bajo pedido* está habilitada en su sistema. Para obtener más información sobre esta característica y cómo habilitarla, consulte [Automatización de suministro bajo pedido](../make-to-order-supply-automation.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
