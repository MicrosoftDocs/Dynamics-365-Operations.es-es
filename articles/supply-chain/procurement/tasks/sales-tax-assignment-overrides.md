---
title: Asignación de impuestos y anulaciones
description: Este procedimiento muestra cómo asignar grupos de impuestos a canales de Commerce.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbc987ba7f0026f011a04a27d00bd3833453514b
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675076"
---
# <a name="sales-tax-assignment-and-overrides"></a>Asignación de impuestos y anulaciones

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo asignar grupos de impuestos a canales de Commerce. También recorre el proceso de crear una nueva anulación de impuestos y de asignarla a un grupo de anulaciones de impuestos de ventas existente. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a Retail y Commerce > Canales > Tiendas > Todas las tiendas.
2. En la lista, haga clic en el vínculo Id. de canal para “Houston”.
3. Haga clic en Editar.
    * El campo "Grupo de impuestos sobre las ventas" contiene la lista de grupos de impuestos para la empresa actual. El grupo actualmente asignado es un grupo de impuestos “Texas” genérico. También hay grupos de impuestos para “Washington “y “, Washington King County.” Los grupos de impuestos pueden incluir los impuestos aplicables para múltiples municipios.  
    * El campo "Anulación de impuestos" es donde los grupos de anulaciones de impuestos se pueden asignar al canal. Los grupos de anulaciones de impuestos se pueden utilizar para agrupar juntas las anulaciones de impuestos que funcionan para múltiples tiendas. En lugar de asignar manualmente las anulaciones de impuestos una a una, el grupo se puede crear y asignar directamente a los canales para ahorrar tiempo.  
4. Haga clic en Guardar.
5. Cierre la página.
6. Vaya a Retail y Commerce > Configuración de canal > Impuestos > Anulaciones de impuestos de ventas.
7. Haga clic en Nuevo.
8. En el campo Anulación de impuestos, proporcione un nombre para su nueva anulación.
9. En el campo Descripción, proporcione una descripción de la anulación.
10. Establezca el estado en “Habilitar”.
11. Expanda o contraiga la sección Anular.
12. En el campo Tipo, seleccione una opción.
    * Los grupos de impuestos de artículos se pueden utilizar para anular impuestos para elementos específicos que pertenecen al grupo. Por ejemplo, los artículos de alimentos se gravan normalmente de manera diferente que los bienes durables y probablemente tendrían su propio grupo de impuestos. Los grupos de impuestos son grupos de impuestos que son aplicables a un canal concreto. Por ejemplo, si un canal vende tanto al por menor como de negocio a negocio, se pueden usar diferentes grupos de impuestos de artículos. Se asignarían todos los impuestos aplicables al grupo de impuestos.  
    * Ahora puede seleccionar los impuestos "De" y "A" o "Grupo de impuestos de origen" y "Grupo de impuestos de destino" para crear su anulación de impuestos. El campo “De” indica el impuesto o el grupo de impuestos que se anulará. La anulación por Grupo de impuestos de artículos proporciona diferentes opciones a la anulación por grupo de impuestos. Las anulaciones de impuestos de ventas se pueden configurar para anular impuestos en transacciones completas o en líneas concretas en la transacción.  
13. Haga clic en Guardar.
14. Cierre la página.
15. Vaya a Retail y Commerce > Configuración de canal > Impuestos > Grupos de anulaciones de impuestos.
    * En este paso asignará la anulación de impuestos recién creada al grupo de anulaciones de impuestos de ventas asignado al canal Houston.  
16. Haga clic en Editar.
17. Expanda o contraiga la sección Configuración.
18. Haga clic en Agregar.
19. En el campo Anulación de impuestos, haga clic en el botón desplegable para abrir la búsqueda.
20. Seleccione la anulación de impuestos previamente creada del impuesto sobre venta en la lista.
21. En la lista, haga clic en el vínculo de la fila seleccionada.
22. Haga clic en Guardar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]