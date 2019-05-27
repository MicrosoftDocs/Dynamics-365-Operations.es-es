---
title: Crear un estado de ciclo de vida del producto para excluir productos de planificación maestra
description: Este procedimiento muestra cómo crear un estado de ciclo de vida de producto nuevo que excluya los productos de cálculo de la planificación maestra y de nivel L. MAT.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 156972cdbf4ffb02b01b00972cc83d003d941378
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567754"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Crear un estado de ciclo de vida del producto para excluir productos de planificación maestra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un estado de ciclo de vida de producto nuevo que excluya los productos de cálculo de la planificación maestra y de nivel L. MAT.


## <a name="create-an-obsolete-state"></a>Crear un estado obsoleto
1. Vaya a Gestión de información de productos > Configuración > Estado de ciclo de vida de producto.
2. Haga clic en Nuevo.
3. En el campo Estado, escriba un valor.
4. Seleccione No en el campo Es activo para planificación.
5. En el campo Descripción, escriba un valor.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Asociar el estado obsoleto a un producto emitido
1. Cierre la página.
2. Vaya a Gestión de información de productos > Productos > Productos emitidos.
3. Use el filtro rápido para buscar registros. Por ejemplo, filtre el campo Nombre de búsqueda con el valor "M00".
4. Haga clic en Editar.
5. En la lista, marque la fila seleccionada.
6. En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.

