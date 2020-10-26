---
title: Crear una lista de materiales para un producto maestro basado en dimensiones
description: Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7961cfb4ad0e20c49d327d83f56c08811598ac1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986296"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Crear una lista de materiales para un producto maestro basado en dimensiones

[!include [banner](../../includes/banner.md)]

Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros. Los primeros 4 registros configuraron datos necesarios para completar este procedimiento. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Esta tarea la gestiona normalmente el diseñador de productos.


## <a name="select-the-product"></a>Seleccionar el producto
1. Haga clic en Mantenimiento de producto emitido.
2. Haga clic en Productos emitidos.
3. En la lista, marque la fila seleccionada.
    * Busque el producto maestro liberado con la tecnología de configuración basada en dimensiones que ha creado en la primera guía de tareas de esta secuencia.  
4. En el panel de acciones, haga clic en Ingeniero.
5. Haga clic en Versiones de L. MAT.

## <a name="create-new-bom-and-bom-version"></a>Crear una L. MAT y una versión de L. MAT nuevas
1. Haga clic en Nuevo.
2. Haga clic en L. MAT y versión de L. MAT.
3. En el campo Nombre, escriba un valor.
    * Configuración de un sitio  
    * En este procedimiento no establecemos un sitio específico para la L. MAT.  
4. Haga clic en Aceptar
5. Haga clic en Nuevo.
    * En este procedimiento agregaremos cuatro líneas a la L. MAT. Dos líneas representan opciones de cable y dos líneas representan opciones de armario.  
6. En la lista, marque la fila seleccionada.
7. En el campo Número de artículo, especifique o seleccione un valor.
    * Seleccione el número de artículo A0001, Cables HDMI de 6.  
8. En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de cable creado en la guía 4 de esta secuencia.  
9. Haga clic en Nuevo.
    * Seleccione el número de artículo A0002, Cables HDMI de 12.  
10. En la lista, marque la fila seleccionada.
11. En el campo Número de artículo, especifique o seleccione un valor.
12. En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de cable de nuevo.  
13. Haga clic en Nuevo.
14. En la lista, marque la fila seleccionada.
15. En el campo Número de artículo, especifique o seleccione un valor.
    * Seleccione el número de artículo D0002 Armario.  
16. En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de armario para esta línea de L. MAT.  
17. Haga clic en Nuevo.
18. En la lista, marque la fila seleccionada.
19. En el campo Número de artículo, especifique o seleccione un valor.
    * Seleccione el número de artículo M0007 Armario estándar como la última línea de L. MAT.  
20. En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de armario para la última línea de L. MAT.  

## <a name="approve-and-activate"></a>Aprobar y activar
1. Cierre la página.
2. Haga clic en Aprobar.
3. En el campo Aprobado por, especifique o seleccione un valor.
4. Seleccione Sí en ¿Desea aprobar también la lista de materiales? .
5. Haga clic en Aceptar
6. Haga clic en Activar.

