---
title: Crear rutas (febrero 2016)
description: Esta tarea se centra en la creación de rutas de producción para un producto terminado y para un producto semiterminado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567869"
---
# <a name="create-routes-february-2016"></a>Crear rutas (febrero 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea se centra en la creación de rutas de producción para un producto terminado y para un producto semiterminado. Es la quinta tarea en las series de cálculo BOM. La empresa de datos de prueba utilizada para crear esta tarea es USMF.


## <a name="create-a-route-for-a-semi-finished-product"></a>Cree una ruta para un producto semi-acabado.
1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione el número de artículo BOM_2.  
3. En el panel de acciones, haga clic en Ingeniero.
4. Haga clic en Ruta.
5. Haga clic en Nuevo.
6. Haga clic en Ruta y en versión de ruta.
7. En el campo Descripción, escriba un valor.
    * Por ejemplo, introduzca ROUTE_2.  
8. En el campo Sitio, especifique o seleccione un valor.
    * Para este ejemplo, introduzca o seleccione el Sitio 1.  
9. Haga clic en Aceptar
10. Haga clic en Nuevo.
11. En el campo Operación, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Ensamblado.  
12. En el campo Tiempo de ejecución, especifique un número.
    * Por ejemplo, escriba 1. Los tiempos de ejecución suelen ser parte del precio calculado para un artículo.  
13. En el campo Grupo de rutas, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Std.  
14. Haga clic en la pestaña Configurar.
15. En el campo Categoría de configuración, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Ensamblado.  
16. Haga clic en la ficha Tiempos.
17. En el campo Tiempo de configuración, especifique un número.
    * Para este ejemplo, especifique 1. Los tiempos de configuración suelen ser parte de un precio calculado para un artículo.  
18. En el Panel de acciones, haga clic en Versión de ruta.
19. Haga clic en Aprobar.
20. Seleccione Sí en ¿Desea aprobar también la ruta? .
21. Haga clic en Aceptar
22. En el Panel de acciones, haga clic en Versión de ruta.
23. Haga clic en Activar.
24. Cierre la página.
25. Cierre la página.

## <a name="create-a-route-for-a-finished-product"></a>Cree una ruta para un producto acabado
1. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione el número de artículo BOM_1.  
2. En el panel de acciones, haga clic en Ingeniero.
3. Haga clic en Ruta.
4. Haga clic en Nuevo.
5. Haga clic en Ruta y en versión de ruta.
6. En el campo Descripción, escriba un valor.
    * Para este ejemplo, introduzca ROUTE_1.  
7. En el campo Sitio, especifique o seleccione un valor.
    * Para este ejemplo, introduzca o seleccione el Sitio 1.  
8. Haga clic en Aceptar
9. Haga clic en Nuevo.
10. En el campo Operación, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Embalaje.  
11. En el campo Tiempo de ejecución, especifique un número.
    * Para este ejemplo, especifique 1.  
12. En el campo Grupo de rutas, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Std.  
13. Haga clic en la pestaña Configurar.
14. En el campo Categoría de configuración, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Embalaje.  
15. Haga clic en la ficha Tiempos.
16. En el campo Tiempo de configuración, especifique un número.
    * Para este ejemplo, especifique 1.  
17. En el Panel de acciones, haga clic en Versión de ruta.
18. Haga clic en Aprobar.
19. Haga clic en Aceptar
20. En el Panel de acciones, haga clic en Versión de ruta.
21. Haga clic en Activar.
22. Cierre la página.
23. Cierre la página.

## <a name="enable-automatic-consumption-of-setup-time"></a>Habilite el consumo automático del tiempo de configuración
1. Vaya al Control de producción > Configuración > Rutas > Grupos de rutas.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione Std en la lista.  
3. Haga clic en Editar.
4. Seleccione Sí en el campo Tiempo de configuración.
    * Los tiempos de configuración suelen ser parte de un precio calculado para un artículo.  
5. Haga clic en Guardar.
6. Cierre la página.

