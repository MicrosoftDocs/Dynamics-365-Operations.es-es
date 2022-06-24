---
title: Crear proveedores de configuración y marcarlos como activos
description: En este artículo se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones.
author: NickSelin
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93c2e114c97290347b71e94d87ea5339688791cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883607"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Crear proveedores de configuración y marcarlos como activos

[!include [banner](../../includes/banner.md)]

En este artículo se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER). Cada configuración de informes electrónicos hará referencia al proveedor como autor de la configuración. En este ejemplo, creará un proveedor de configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que los proveedores de configuración de ER se comparten entre todas las empresas.

## <a name="create-a-provider"></a>Creación de un proveedor
1. Vaya al **panel de navegación** en la esquina superior izquierda y seleccione **Administración de la organización**.
2. Vaya a **Espacios de trabajo > Informes electrónicos**.
3. Vaya a **Vínculos relacionados > Proveedores de configuración**.
4. Seleccione **Nuevo**.
    - Cada registro de proveedor tiene un nombre y dirección URL únicos. Revise el contenido de esta página y omita este procedimiento si ya existe un registro para Litware, Inc. (https://www.litware.com).  
5. En el campo Nombre, escriba `Litware, Inc.`.
6. En el campo Dirección de Internet, escriba `https://www.litware.com`.
7. Seleccione **Guardar**.
8. Cierre la página.

## <a name="select-as-an-active-provider"></a>Selección como proveedor activo
1. Seleccione el proveedor Litware, Inc.
2. Seleccione **Definir como activo**.

![Página del espacio de trabajo de los informes electrónicos.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]