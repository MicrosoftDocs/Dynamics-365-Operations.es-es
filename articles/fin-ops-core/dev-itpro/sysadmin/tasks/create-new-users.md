---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: maertenm
manager: AnnBe
ms.date: 10/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c347a34a389c32d005cc8086c4a1349ecb8a698
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570530"
---
# <a name="create-new-users"></a>Crear nuevos usuarios

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Asociar un usuario con una licencia (nuevos tipos de licencia solamente)
Para los clientes que tienen los nuevos tipos de licencia que se agregaron en octubre de 2019, los usuarios deben estar asociados a una licencia. Los usuarios que están asociados a una licencia automáticamente se añaden como usuarios del sistema que no tienen ningún rol la primera vez que inician sesión. Los usuarios que no estén asociadas a una licencia reciben un mensaje de advertencia.

Las administraciones del sistema pueden [asignar licencias a los usuarios](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) en el [Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-a-new-user"></a>Agregar un usuario nuevo
1. Vaya a **Administración del sistema \> Usuarios \> Usuarios**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Id. de usuario**, especifique un identificador único para el usuario. El identificador de usuario es obligatorio.  
4. En el campo **Nombre de usuario**, escriba el nombre de usuario.  
5. En el campo **Dominio**, especifique el dominio del usuario.  
6. En el campo **Alias** , escriba el alias del usuario.  
7. En el campo **Empresa**, seleccione la empresa deseada. 
8. En la ficha desplegable **Roles de usuario** , seleccione **Asignar roles** a [asignar usuarios a roles de seguridad](assign-users-security-roles.md)
9. Seleccione **Aceptar**.
10. Seleccione **Guardar**.

## <a name="import-users"></a>Importar usuarios
1. En el panel de acciones, seleccione **Importar usuarios**.
2. En la lista, marque la fila seleccionada.
3. Seleccionar **Importar usuarios**.
4. Seleccione **Cerrar**.

