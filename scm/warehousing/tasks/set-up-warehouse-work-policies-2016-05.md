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
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 5db1c99833276a92467ed57b7be51b0ebaa74d83
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-warehouse-work-policies"></a>Configurar directivas de trabajo de almacén 

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


