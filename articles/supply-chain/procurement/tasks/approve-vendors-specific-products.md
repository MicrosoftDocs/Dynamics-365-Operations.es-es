--- 
title: "Aprobar proveedores para productos específicos"
description: "Este procedimiento le muestra cómo aprobar los proveedores para los productos específicos."
author: mkirknel
manager: AnnBe
ms.date: 11/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ffc58d2afe73fa2290e4e73a058d47ffd64b8d54
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="approve-vendors-for-specific-products"></a>Aprobar proveedores para productos específicos

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo aprobar los proveedores para los productos específicos. Esto le permite controlar qué proveedores se pueden usar cuando el producto se agrega a un pedido de compra. Puede utilizar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Esta tarea la realizará normalmente un director de compras.

1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Expanda la sección Compra.
    * Si hay un proveedor principal que se muestra en el campo Proveedor, necesita agregar este proveedor como proveedor aprobado en los siguientes pasos. Anote el número del proveedor, si se muestra uno.  
5. En el panel de acciones, haga clic en Compra.
6. Haga clic en Configurar.
7. Haga clic en Agregar.
8. En el campo Proveedor, especifique o seleccione un valor.
    * Seleccione el proveedor aprobado. Al menos una de las líneas tiene que ser el proveedor principal si hubo una en el registro de producto. Si ha anotó el número del proveedor antes, selecciónelo aquí.  
9. En el campo Caducidad, especifique una fecha.
    * Elija una fecha que se encuentre unos meses en el futuro.  
10. Haga clic en Agregar.
11. En el campo Proveedor, especifique o seleccione un valor.
12. En el campo Caducidad, especifique una fecha.
    * Elija una fecha que sea diferente de la fecha de vencimiento anterior.  
13. Cierre la página.
14. Haga clic en Proveedores aprobados.
15. En el campo Caducidad, especifique una fecha.
    * Esta fecha actúa como filtro para que puede ver quiénes son los proveedores aprobados, hasta una fecha concreta.  
16. Cierre la página.
17. Haga clic en Período de vigencia.
18. En el campo Mostrar proveedores expirados por, especifique una fecha.
    * Puede usar esta página para identificar proveedores donde el estado de aprobación expirará después de una fecha concreta.  
19. Cierre la página.
20. Haga clic en Editar.
21. En el campo Método de comprobación de proveedor aprobado, seleccione una opción.
    * Este campo le permite seleccionar la directiva para lo que debería ocurrir si se agrega el producto a una línea de pedido de compra donde el proveedor no es un proveedor aprobado.  
22. Haga clic en Guardar.
23. Cierre la página.
24. Cierre la página.
25. Vaya a Adquisición y abastecimiento > Proveedores > Relaciones proveedor/artículo > Lista de proveedores aprobados por artículo.
    * Esta página le proporciona una visión general de todos los productos y los proveedores aprobados.  
26. Cierre la página.
27. Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.
    * También puede empezar desde un proveedor y después ir a la lista de productos aprobados para dicha cuenta de proveedor.  
28. En la lista, busque y seleccione el registro deseado.
29. En el panel de acciones, haga clic en Adquisición.
30. Haga clic en Lista de proveedores aprobados por proveedor.
31. Cierre la página.
32. Cierre la página.


