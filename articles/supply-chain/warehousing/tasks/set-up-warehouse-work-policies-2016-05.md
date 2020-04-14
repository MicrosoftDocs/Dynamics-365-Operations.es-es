---
title: Configurar directivas de trabajo de almacén (solicitud, mayo de 2016)
description: Los procesos de almacén no siempre incluyen trabajo de almacén.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca54cceb83425c43b5d124cd6d11be0cdef4d63a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145925"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a>Configurar directivas de trabajo de almacén (solicitud, mayo de 2016)

[!include [banner](../../includes/banner.md)]

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

