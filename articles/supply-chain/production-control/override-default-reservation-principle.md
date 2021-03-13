---
title: Invalidar el principio de reserva predeterminado para materiales en producción
description: Este tema describe cómo establecer un principio de reserva predeterminado para cada grupo de modelos de artículos, de modo que se puedan aplicar automáticamente diferentes principios de reserva para cada artículo que forma parte de una lista de materiales de producción (L.MAT) o una fórmula de orden de lote.
author: johanhoffmann
manager: tfehr
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8756dc22ffd64f836740124ce08dadca84207147
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078303"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Invalidar el principio de reserva predeterminado para materiales en producción

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La función *Anular la reserva de producción predeterminada* le permite establecer un principio de reserva predeterminado para cada grupo de modelos de artículos. Por lo tanto, se pueden aplicar automáticamente diferentes principios de reserva para cada artículo que forma parte de una lista de materiales de producción (L.MAT) o una fórmula de orden de lote. Puede seleccionar si cada grupo de modelos de artículos debe anular el principio de reserva predeterminado que se establece para un pedido y qué principio de reserva debe usarse en su lugar (*manual*, *estimación*, *planificación*, *lanzamiento* o *comienzo*).

Cuando crea un nuevo pedido de producción o un pedido de lote, se le solicita que seleccione el principio de reserva que debe aplicarse a ese pedido y todas sus líneas de lista de materiales o líneas de fórmula. Cuando se utiliza la función *Anular la reserva de producción predeterminada*, algunas o todas las líneas de lista de materiales o fórmulas pueden anular ese principio de reserva y, en su lugar, utilizar el principio de reserva que se establece para el grupo de modelo de artículo relevante.

Por ejemplo, si tiene materias primas o ingredientes que requieren trabajo de selección, las líneas de lista de materiales o fórmula que se crean para esos productos requieren una reserva física, porque la reserva física es un requisito previo para la generación de trabajo de almacén. Normalmente, si desea que la reserva se produzca automáticamente, seleccione uno de los siguientes principios de reserva: *estimación*, *planificación*, *lanzamiento* o *comienzo*. Por otro lado, si tiene materiales o ingredientes que no requieren trabajo de recolección, porque se consumen directamente desde una ubicación, generalmente selecciona el principio de reserva *manual*, que no realiza ninguna reserva física ni genera ningún trabajo de selección.

## <a name="turn-on-the-feature"></a>Activar la característica

Antes de poder usar la característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *control de producción*
- **Nombre de la función:** *Anular la reserva de producción predeterminada*

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Asignar una política de reserva de producción a un grupo de modelos de artículos

1. Ir a **Gestión de costos &gt; Configuración de políticas de contabilidad de inventario &gt; Grupos de modelos de artículos**.
1. Cree o seleccione un grupo de modelos de artículos.
1. En la ficha desplegable **Políticas de inventario**, seleccione la casilla de verificación **Anular la reserva de producción de artículos**.
1. En el campo **Reserva**, seleccione el principio de reserva para los artículos que pertenecen al grupo de modelos seleccionado. (Estos elementos incluyen elementos que están en una lista de materiales o en una línea de fórmula).

    - **Manual** - Los artículos del grupo de modelos no se reservarán físicamente automáticamente para la producción. Sin embargo, aún se pueden reservar manualmente según sea necesario.
    - **Estimación** - Los artículos del grupo de modelos se reservarán físicamente durante la estimación del pedido de producción.
    - **Programación** - Los artículos del grupo de modelos se reservarán físicamente durante la programación del pedido de producción.
    - **Liberación** - Los artículos del grupo de modelos se reservarán físicamente cuando el pedido de producción se libere.
    - **Inicio** - Los artículos del grupo de modelos se reservarán físicamente al principio del pedido de producción.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Ejemplo: uso de principios de reserva en un escenario a granel / paquete

Se produce un material lubricante a granel en un mezclador de 1000 litros. Una vez que el material a granel está listo, se bombea a varias estaciones de llenado, donde se llenan botellas de diferentes tamaños. Una vez completado el llenado, las botellas se empaquetan en cajas. Luego, esas cajas se empaquetan en paletas.

En este escenario, se crea una orden de lote para hacer 1000 litros de material a granel. (Este pedido es el pedido a granel). Cuando se completa este pedido por lotes, se informa como terminado en la ubicación de entrada de material de las estaciones de servicio. Luego, se crea un pedido de lote para llenar y empacar cada tamaño de botella. (Estos pedidos son los pedidos del paquete). Los pedidos del paquete tienen una fórmula que se compone del material a granel, una botella vacía, una etiqueta y otros materiales de empaque. Debido a que el material a granel fluye directamente desde el tanque mezclador a las estaciones de llenado, no se requiere trabajo de almacén para recoger este ingrediente y el material a granel se consume directamente desde la ubicación de entrada. Por lo tanto, el principio de reserva se establece en *manual*. Los demás materiales se trasladan a la estación de servicio mediante un trabajo de selección. Por lo tanto, el principio de reserva para estas líneas se establece en *lanzamiento*, por ejemplo, para que la reserva se produzca automáticamente cuando se libere el pedido del paquete.