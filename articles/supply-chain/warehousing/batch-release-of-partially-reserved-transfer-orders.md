---
title: Liberación por lotes de pedidos de transferencia parcialmente reservados
description: En este artículo se describe cómo configurar y aplicar la opción de liberación por lotes de pedidos de transferencia parcialmente reservados desde un dispositivo móvil.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 741377a43e2bfe702b213647cc6460a3d6ad93fb
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218694"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Liberación por lotes de pedidos de transferencia parcialmente reservados

[!include [banner](../includes/banner.md)]

La funcionalidad de la opción de liberación por lotes de pedidos de transferencia parcialmente reservados le permite liberar parcialmente pedidos de transferencia a un almacén mediante un trabajo por lotes.
Dado que tiene la opción de liberar una cantidad parcial, no tiene que esperar a que la totalidad del pedido esté disponible en el almacén antes de poder liberar un pedido.

La liberación de pedidos en un almacén es un proceso de procesos de gestión de almacenes (WMS). Este proceso implica actividades tales como la recogida, embalaje y envío que un trabajador del almacén puede efectuar usando un dispositivo móvil.

## <a name="where-it-applies"></a>Dónde se aplica

Para esta funcionalidad, los pedidos de transferencia se liberan en un almacén mediante un trabajo por lotes. Esta función resulta útil si no tiene suficiente inventario en el almacén, pero todavía quiere transferir artículos desde un almacén a otro.

## <a name="how-it-is-set-up"></a>Cómo se configura

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Especifique los criterios que han de cumplir los pedidos de transferencia y los de ventas.

Antes de que el pedido se pueda liberar parcialmente en un almacén en forma de lote, se deben cumplir los criterios de cumplimiento. Estos criterios de cumplimiento se determinan gracias a la directiva de cumplimiento.

Las directivas de cumplimiento de los pedidos de transferencia y ventas se especifican en el nivel de empresa. Según la configuración de la directiva de cumplimiento, la liberación de pedidos en lote se puede aceptar o rechazar. Será entonces cuando se procesen los pedidos en consecuencia.

- Para crear directivas de cumplimiento para pedidos de transferencia y ventas, vaya a **Gestión de almacenes \> Configuración \> Liberar en almacén \> Directivas de cumplimiento** y escriba un nombre y una descripción para crear una directiva de cumplimiento.
- Para especificar un índice de entrega, un tipo de valor y el mensaje que se muestra si se infringe la directiva de cumplimiento, vaya a **Gestión de almacenes \> Configuración \> Liberar en almacén \> Directivas de cumplimiento** y, a continuación configure los campos de **tasa de cumplimiento**, **tipo de valor** y **mensaje de infracción de cumplimiento**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Configurar las directivas de cumplimiento de los pedidos de transferencia y los de ventas

- Para configurar las directivas de cumplimiento de los pedidos de transferencia, vaya a **Gestión del inventario \> Configuración \> Parámetros de gestión de inventarios y almacenes** y luego en la ficha **Pedidos de transferencia**, en la sección **Gestión del almacenes**, seleccione una directiva de cumplimiento del pedido de transferencia.
- Para establecer las directivas de cumplimiento de los pedidos de ventas, vaya a **Clientes \> Configuración \> Parámetros de clientes** y, luego, en la ficha **Gestión de almacenes**, seleccione una directiva de cumplimiento del pedido de ventas.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-released-in-a-batch"></a>Permitir la liberación en lote y especificar la cantidad que se debe liberar en ese lote

Se usa un trabajo por lotes para liberar pedidos en lote en un almacén. Los parámetros que distinguen los pedidos que se deben ejecutar en un trabajo por lotes se establecen en el mismo trabajo por lotes.

El parámetro **Cantidad** especifica si la cantidad total o la cantidad reservada físicamente se debe liberar en el lote. El parámetro **Permitir la liberación de pedidos liberados parcialmente** determina si los pedidos del lote se deben aceptar o rechazar si se hubieran liberado con anterioridad.

- Para establecer los parámetros **Cantidad** y **Permitir la liberación de pedidos liberados parcialmente** de los pedidos de transferencia, vaya a **Gestión de almacenes \> Liberar en almacén \> Liberación automática de pedidos de transferencia**.
- Para establecer los parámetros **Cantidad** y **Permitir la liberación de pedidos liberados parcialmente de los pedidos de ventas**, vaya a **Gestión de almacenes \> Liberar en almacén \> Liberación automática de pedidos de ventas**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
