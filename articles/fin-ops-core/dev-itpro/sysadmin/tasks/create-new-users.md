---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: maertenm
manager: AnnBe
ms.date: 02/06/2020
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
ms.openlocfilehash: 6d884dfe30be5684a90925d4d2d9ab7eebca5b44
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029818"
---
# <a name="create-new-users"></a>Crear nuevos usuarios

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Asociar un usuario con una licencia (nuevos tipos de licencia solamente)
Para los clientes que tienen los nuevos tipos de licencia que se agregaron en octubre de 2019, los usuarios deben estar asociados a una licencia. Los usuarios que están asociados a una licencia automáticamente se añaden como usuarios del sistema que no tienen ningún rol la primera vez que inician sesión.

Las administraciones del sistema pueden [asignar licencias a los usuarios](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) en el [Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a>Asociar un usuario externo con una licencia (nuevos tipos de licencia solamente)
Los usuarios externos al inquilino en el que se implementó el entorno deben estar representados en el directorio del inquilino host (Azure Active Directory (Azure AD)) para que se les puedan asignar licencias. Esos usuarios externos deben agregarse al inquilino en Azure AD como usuarios invitados y luego se les deben asignar las licencias correspondientes. Para obtener más información, consulte [Agregar usuarios de colaboración B2B de Azure Active Directory en el portal de Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="add-a-new-user"></a>Agregar un usuario nuevo
1. Vaya a **Administración del sistema \> Usuarios \> Usuarios**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Id. de usuario**, especifique un identificador único para el usuario. El identificador de usuario es obligatorio.  
4. En el campo **Nombre de usuario**, escriba el nombre de usuario.  
5. En el campo **Dominio**, especifique el dominio del usuario.  
6. En el campo **Alias** , escriba el alias del usuario.  
7. En el campo **Empresa**, seleccione la empresa deseada. 
8. En la ficha desplegable **Roles de usuario**, seleccione **Asignar roles** para asignar usuarios a roles de seguridad. Para obtener más información, consulte [Asignar usuarios a roles de seguridad](assign-users-security-roles.md).
9. Seleccione **Aceptar**.
10. Seleccione **Guardar**.

## <a name="import-users"></a>Importar usuarios
1. En el panel de acciones, seleccione **Importar usuarios**.
2. En la lista, marque la fila seleccionada.
3. Seleccionar **Importar usuarios**.
4. Seleccione **Cerrar**.

