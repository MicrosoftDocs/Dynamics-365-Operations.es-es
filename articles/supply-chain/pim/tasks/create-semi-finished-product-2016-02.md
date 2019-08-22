---
title: Crear un producto semi-terminado (febrero de 2016)
description: Esta tarea se centra en crear un producto semi-terminado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39fb652d704da33d24a206da2c18cc2a7a50e9e4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844522"
---
# <a name="create-a-semi-finished-product-february-2016"></a>Crear un producto semi-terminado (febrero de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea se centra en crear un producto semi-terminado. Es la segunda tarea en las series de cálculo BOM. La empresa de datos de prueba utilizada para crear esta tarea es USMF.

1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. Haga clic en Nuevo.
3. En el campo Número de producto, escriba un valor.
    * Para este ejemplo, especifique BOM 2.  
4. En el campo Grupo de modelos de artículo, especifique o seleccione un valor.
    * Seleccione STD. El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.  
5. En el campo Grupo de artículos, especifique o seleccione un valor.
    * Por ejemplo, seleccione Audio. Esto no tiene aafecta de ninguna manera a los cálculos de coste.  
6. En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.
    * Seleccione SiteWH. Para este ejemplo solo se usarán el Sitio y el Almacén.  
7. En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.
    * Las dimensiones de seguimiento no se usarán en este ejemplo, seleccione Ninguno.  
8. Haga clic en Aceptar
9. En el panel de acciones, haga clic en Administrar inventario.
10. Haga clic en Configuración predeterminada de pedido.
11. En el campo Tipo de pedido predeterminado, seleccione "Producción".
    * Dado que este es un producto semi-terminado que se generará, seleccione Producción.  
12. En el campo Sitio de compra, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
13. En el campo Sitio de inventario, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
14. En el campo Sitio de centas, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
15. Cierre la página.
16. En el panel de acciones, haga clic en Gestionar costes.
17. Haga clic en Precio de artículo.
18. Haga clic en Nuevo.
19. En la lista, marque la fila seleccionada.
20. En el campo Versión, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Versión 10.  
21. En el campo Sitio, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
22. Establezca el Precio en "10".
    * Para este ejemplo, escriba un precio de coste de 10.  
23. Haga clic en Guardar.
24. Haga clic en Activar precios pendientes.
25. Cierre la página.
26. Cierre la página.
27. Haga clic en BOM_2 para abrirlo.
28. Expanda la sección Administrar costes.
29. En el campo Grupo de costes, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Coste de grupo M1.  
30. Use el acceso directo para guardar un registro.
31. Cierre la página.

