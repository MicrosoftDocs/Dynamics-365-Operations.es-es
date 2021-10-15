---
title: Configuración de cargos adicionales del centro y listas maestras de cargos adicionales
description: Este procedimiento muestra cómo crear cargos adicionales maestros para un centro y cómo usarlos para crear un cargo adicional del centro.
author: Henrikan
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1480dec82912d547bde5db614703164e3f8451c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576241"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Configuración de cargos adicionales del centro y listas maestras de cargos adicionales

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear cargos adicionales maestros para un centro y cómo usarlos para crear un cargo adicional del centro. El procedimiento usa el grupo de datos USMF. Esta configuración normalmente la realiza el coordinador de transporte.


## <a name="set-up-a-hub-master"></a>Configurar un centro maestro
1. Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales maestros.
2. Haga clic en Nuevo.
3. En el campo Cargos adicionales maestros, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Tipo de cargos adicionales, seleccione Centro.
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="set-up-a-hub-accessorial-charge"></a>Configuración de un cargo adicional del centro
1. Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales del centro.
2. Haga clic en Nuevo.
3. En el campo Id. de cargos adicionales del centro, escriba un valor.
4. En el campo Centro, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
6. En el campo Posición del centro, seleccione una opción.
    * Puede crear el cargo como recogida o como entrega. En función de lo que se seleccione, el cargo se aplicará al segmento de transporte correspondiente en la ruta.  
7. En el campo Cargos adicionales maestros, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione los cargos maestros que acaba de crear.  
9. Haga clic en Guardar.
10. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]