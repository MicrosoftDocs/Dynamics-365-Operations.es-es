--- 
title: "Crear un proveedor de configuración y marcarlo como activo para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: 2dfa04f280249884af2a237807fb283059444a6c
ms.contentlocale: es-es
ms.lasthandoff: 11/02/2017

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a>Crear un proveedor de configuración y marcarlo como activo para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER). Cada configuración de informes electrónicos hará referencia al proveedor como autor de la configuración. En este ejemplo, creará un proveedor de configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que los proveedores de configuración de ER se comparten entre todas las empresas.


## <a name="create-a-provider"></a>Creación de un proveedor
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Proveedores de configuración.
3. Haga clic en Nuevo.
    * Cada registro de proveedor tiene un nombre y dirección URL únicos. Revise el contenido de esta página y omita este procedimiento si ya existe un registro para Litware, Inc. (http://www.litware.com).  
4. En el campo Nombre, especifique "Litware, Inc.".
    * Litware, Inc.  
5. En el campo Dirección de Internet, especifique "http://www.litware.com".
    * http://www.litware.com  
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="select-as-an-active-provider"></a>Selección como proveedor activo
1. Seleccione el proveedor Litware, Inc.
2. Haga clic en Definir como activo.


