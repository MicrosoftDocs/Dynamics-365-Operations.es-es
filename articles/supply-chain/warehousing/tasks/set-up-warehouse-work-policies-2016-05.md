--- 
title: "Configurar directivas de trabajo de almacén"
description: "Los procesos de almacén no siempre incluyen trabajo de almacén."
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b7d579ca7e2b9ca8cbead74b2c2ababfd142f171
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-warehouse-work-policies"></a>Configurar directivas de trabajo de almacén 

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los procesos de almacén no siempre incluyen trabajo de almacén. Al definir una directiva de trabajo, puede evitar la creación de trabajo para picking de materia prima y ubicación de bienes terminados para un conjunto de productos en ubicaciones específicas. La empresa de datos de demostración USMF se usó para crear este registro. Esta guía de tareas requiere la aplicación Dynamics AX 7.0.1 o versiones posteriores.

1. Vaya a Gestión de almacenes > Configurar > Trabajo > Directivas de trabajo.
2. Haga clic en Nuevo.
3. En el campo Nombre de directiva de trabajo, escriba "Ningún trabajo de ubicación".
4. Haga clic en Guardar.
5. Haga clic en Agregar.
6. En la lista, marque la fila seleccionada.
7. En el campo Tipo de pedido de trabajo, seleccione "Ubicación de bienes terminados".
8. Haga clic en Agregar.
9. En la lista, marque la fila seleccionada.
10. En el campo Tipo de pedido de trabajo, seleccione "Ubicación de coproducto y producto derivado".
11. Expanda la sección Ubicaciones del inventario.
12. Haga clic en Agregar.
13. En la lista, marque la fila seleccionada.
14. En la lista Almacén, especifique “51".
15. En el campo Ubicación, especifique o seleccione ·"001".
16. Expanda la sección Productos.
17. En el campo Selección de productos, seleccione "Seleccionado".
18. Haga clic en Agregar.
19. En la lista, marque la fila seleccionada.
20. En el campo Número de artículo, especifique o seleccione "L0101".
21. Haga clic en Guardar.


