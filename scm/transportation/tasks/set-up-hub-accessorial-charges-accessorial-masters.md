--- 
title: "Configuración de cargos adicionales del centro y listas maestras de cargos adicionales"
description: "Este procedimiento muestra cómo crear cargos adicionales maestros para un centro y cómo usarlos para crear un cargo adicional del centro."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 752a9a9a755ae7e4f2793fc712cc0c37c614ae71
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Configuración de cargos adicionales del centro y listas maestras de cargos adicionales

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


