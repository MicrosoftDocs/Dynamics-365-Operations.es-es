---
title: Crear materias primas (febrero de 2016)
description: Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "351065"
---
# <a name="create-raw-materials-february-2016"></a>Crear materias primas (febrero de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados. Es la tercera tarea en las series de cálculo BOM. La empresa de datos de prueba utilizada para crear esta tarea es USMF.


## <a name="create-the-first-material"></a>Cree el primer material
1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. Haga clic en Nuevo.
3. En el campo Número de producto, escriba un valor.
    * Para este ejemplo, escriba ITEM_A.  
4. En el campo Grupo de modelos de artículo, especifique o seleccione un valor.
    * Seleccione STD. El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.  
5. En el campo Grupo de artículos, especifique o seleccione un valor.
    * Por ejemplo, seleccione Audio. Esto no tiene aafecta de ninguna manera a los cálculos de coste.  
6. En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.
    * Seleccione SiteWH. Para la demostración solo se usarán el Sitio y el Almacén.  
7. En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.
    * Las dimensiones de seguimiento no se usarán en este ejemplo. Seleccione Ninguno.  
8. Haga clic en Aceptar
9. En el panel de acciones, haga clic en Administrar inventario.
10. Haga clic en Configuración predeterminada de pedido.
11. En el campo Sitio de compra, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
12. En el campo Sitio de inventario, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
13. En el campo Sitio de centas, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
14. Cierre la página.
15. Cierre la página.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Haga clic en ITEM_A.  
17. Expanda la sección Administrar costes.
18. Introduzca un valor en el campo Grupo de costes.
    * Para este ejemplo, introduzca M2.  
19. En el panel de acciones, haga clic en Gestionar costes.
20. Haga clic en Precio de artículo.
21. Haga clic en Nuevo.
22. En el campo Versión, especifique o seleccione un valor.
    * Para este ejemplo, seleccione 10, que es el Tipo de gestión de costes de coste estándar.  
23. En el campo Sitio, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
24. En el campo Precio, escriba un número.
    * Para este ejemplo, especifique 10.  
25. Haga clic en Guardar.
26. Haga clic en Activar precios pendientes.
27. Cierre la página.
28. Cierre la página.

## <a name="create-the-second-material"></a>Cree el segundo material
1. Haga clic en Nuevo.
2. En el campo Número de producto, escriba un valor.
    * Para este ejemplo, especifique ITEM_B.  
3. En el campo Grupo de modelos de artículo, especifique o seleccione un valor.
    * Seleccione STD. El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.  
4. En el campo Grupo de artículos, especifique o seleccione un valor.
    * Por ejemplo, seleccione Audio. Esto no tiene aafecta de ninguna manera a los cálculos de coste.  
5. En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.
    * Seleccione SiteWH. Para este ejemplo solo se usarán el Sitio y el Almacén.  
6. En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.
    * Las dimensiones de seguimiento no se usarán en este ejemplo. Seleccione Ninguno.  
7. Haga clic en Aceptar
8. En el panel de acciones, haga clic en Administrar inventario.
9. Haga clic en Configuración predeterminada de pedido.
10. En el campo Sitio de compra, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
11. En el campo Sitio de inventario, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
12. En el campo Sitio de centas, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
13. Cierre la página.
14. Cierre la página.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Haga clic en ITEM_B.   
16. Expanda la sección Administrar costes.
17. Introduzca un valor en el campo Grupo de costes.
    * Para este ejemplo, introduzca M2.  
18. En el panel de acciones, haga clic en Gestionar costes.
19. Haga clic en Precio de artículo.
20. Haga clic en Nuevo.
21. En el campo Versión, especifique o seleccione un valor.
    * Para este ejemplo, seleccione 10. Este es el Tipo de gestión de costes de coste estándar.  
22. En el campo Sitio, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
23. En el campo Precio, escriba un número.
    * Para la demostración, especifique 10.  
24. Haga clic en Guardar.
25. Haga clic en Activar precios pendientes.
26. Cierre la página.
27. Cierre la página.

## <a name="create-the-third-material"></a>Cree el tercer material
1. Haga clic en Nuevo.
2. En el campo Número de producto, escriba un valor.
    * Para la demostración, especifique ITEM_C.  
3. En el campo Grupo de modelos de artículo, especifique o seleccione un valor.
    * Seleccione STD. El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.  
4. En el campo Grupo de artículos, especifique o seleccione un valor.
    * Por ejemplo, seleccione Audio. Esto no tiene aafecta de ninguna manera a los cálculos de coste.  
5. En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.
    * Seleccione SiteWH. Para la demostración solo se usarán el Sitio y el Almacén.  
6. En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.
    * Las dimensiones de seguimiento no se usarán en este ejemplo. Seleccione Ninguno.  
7. Haga clic en Aceptar
8. En el panel de acciones, haga clic en Administrar inventario.
9. Haga clic en Configuración predeterminada de pedido.
10. En el campo Sitio de compra, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
11. En el campo Sitio de inventario, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
12. En el campo Sitio de centas, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
13. Cierre la página.
14. Cierre la página.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Haga clic en ITEM_C.   
16. Expanda la sección Administrar costes.
17. Introduzca un valor en el campo Grupo de costes.
    * Para este ejemplo, especifique M1.  
18. En el panel de acciones, haga clic en Gestionar costes.
19. Haga clic en Precio de artículo.
20. Haga clic en Nuevo.
21. En el campo Versión, especifique o seleccione un valor.
    * Para este ejemplo, seleccione 10. Este es el Tipo de gestión de costes de coste estándar.  
22. En el campo Sitio, especifique o seleccione un valor.
    * Para este ejemplo, seleccione Sitio 1.  
23. En el campo Precio, escriba un número.
    * Para este ejemplo, especifique 10.  
24. Haga clic en Guardar.
25. Haga clic en Activar precios pendientes.
26. Cierre la página.
27. Cierre la página.

