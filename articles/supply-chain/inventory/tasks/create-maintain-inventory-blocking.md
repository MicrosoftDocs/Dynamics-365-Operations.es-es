---
title: Creación y mantenimiento de un bloqueo del inventario
description: Este tema describe cómo usar un bloqueo de inventario para impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956167"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Creación y mantenimiento de un bloqueo del inventario

[!include [banner](../../includes/banner.md)]

Este tema describe cómo usar un bloqueo de inventario para impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida. Necesita tener un artículo con inventario disponible físico antes de comenzar los procedimientos de este tema.

## <a name="block-inventory"></a>Bloquear inventario

Para crear un registro de bloqueo de inventario de modo que el inventario esté bloqueado, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Bloqueo del inventario**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el encabezado del nuevo registro de bloqueo, establezca el campo **Número de artículo** al elemento que desea bloquear e introduzca una descripción.
1. En la ficha desplegable **General**, en el campo **Cantidad** escriba el número de artículos a bloquear.
1. En la ficha desplegable **Dimensiones de inventario**, especifique el sitio y el almacén donde se encuentran actualmente los artículos que desea bloquear.
1. En el panel Acciones, seleccione **Guardar**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Actualización de las condiciones de bloqueo de inventario

Para actualizar un registro de bloqueo de inventario, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Bloqueo del inventario**.
1. En el panel de lista, seleccione el registro de bloqueo relevante.
1. Edite el registro según sea necesario. Por ejemplo, podría cambiar el valor del campo **Fecha esperada** para indicar cuándo se espera que el inventario bloqueado quede disponible para reserva. Si la opción **Recepciones esperadas** está seleccionada, la fecha aparecerá en la transacción esperada. (La opción **Recepciones esperadas** está seleccionada de forma predeterminada cuando crea manualmente un registro de bloqueo).
1. En el panel Acciones, seleccione **Guardar**.

## <a name="unblock-inventory"></a>Desbloquear inventario

Para eliminar un registro de bloqueo de inventario de modo que el inventario esté bloqueado, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Bloqueo del inventario**.
1. En el panel de lista, seleccione el registro de bloqueo relevante.
1. En el panel de acciones, seleccione **Eliminar**.
1. Se le pedirá que confirme la operación. Seleccione **Sí** para continuar.
1. Cierre la página.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
