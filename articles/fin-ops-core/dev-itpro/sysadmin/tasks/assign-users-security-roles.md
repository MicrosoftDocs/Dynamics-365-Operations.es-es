---
title: Asignar usuarios a roles de seguridad
description: Para obtener acceso a aplicaciones de finanzas y operaciones, se debe asignar a los usuarios a roles de seguridad.
author: Peakerbl
ms.date: 02/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5e69a79f123daff3f85d0100647615ad818288e
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103880"
---
# <a name="manage-users-and-security-roles"></a>Administrar usuarios y roles de seguridad

[!include [banner](../../includes/banner.md)]

Para usar algo distinto de capacidades comunes, en las aplicaciones de finanzas y operaciones, los usuarios deben asignarse a roles de seguridad. Puede asignar usuarios a roles automáticamente, según las reglas y los datos comerciales, excluir usuarios de la asignación automática de roles o agregar usuarios a roles manualmente.

## <a name="automatically-assign-users-to-roles"></a>Asignar usuarios automáticamente a roles
Este procedimiento explica cómo los administradores del sistema pueden asignar automáticamente usuarios a roles, en función de los datos empresariales. 
1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.
2. En el árbol, seleccione "Supervisor contable". Seleccione el rol para el que desea configurar la regla. En este ejemplo, seleccione Supervisor contable. 
3. Seleccione **Agregar regla** para abrir el menú de diálogo.
4. En la lista **Seleccionar una consulta**, busque y seleccione el registro deseado. Seleccione la consulta que se usará para esta regla.  
5. En la lista **Nombre de la regla de pertenencia**, haga clic en el vínculo de la fila seleccionada.
6. Seleccione **Editar consulta**. Edite la consulta según sea necesario.  
7. Seleccione **Aceptar**.
8. Seleccione **Ejecutar asignación automática de roles**.
9. Vaya al **Panel de exploración > módulos > Administración del sistema > usuarios > usuarios** (idealmente en una ficha independiente de explorador).
10. Revise los roles asignados a varios usuarios para confirmar que la consulta de la asignación de roles fue correcta. Ajuste y vuelva a ejecutar si es necesario.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuarios de la asignación automática de roles
Este procedimiento explica cómo excluir usuarios de la asignación automática de roles.

1. Cierre la página.
2. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.
3. En el árbol, seleccione "Supervisor contable". Seleccione una función. Para este ejemplo, seleccione Supervisor contable.  
4. En el menú **Usuarios asignados al rol**, seleccione **Asignar o excluir usuarios de forma manual**.
5. En el lista **Asignar usuarios al rol o excluir usuarios del rol**, marque la fila seleccionada. Seleccione un usuario.  
6. En el **Panel de acciones**, seleccione **Excluir de rol**.
7. Seleccione **Excluir de rol** para excluir los usuarios seleccionados del rol. Para quitar exclusiones, seleccione los usuarios para los que desea quitar las exclusiones y, a continuación, haga clic en **Restablecer estado**. Al eliminar una exclusión restableciendo el estado del usuario, el rol del usuario se asigna automáticamente. Sin embargo, el usuario no se asigna inmediatamente al rol o se excluye del rol al restablecer el estado. En su lugar, el usuario se asigna al rol o se elimina del rol la próxima vez que se ejecutan las reglas para la asignación automática de roles.  

## <a name="manually-assign-users-to-roles"></a>Asignar manualmente usuarios a roles
Los usuarios que se asignan manualmente a roles de seguridad también los elimina manualmente el administrador. Estos usuarios no se eliminan de los roles a través de reglas de asignación automática de roles.

1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.
2. En el árbol, seleccione un rol y, en el menú **Usuarios asignados al rol**, seleccione **Asignar o excluir usuarios de forma manual**.
4. En **Asignar usuarios o excluir usuarios del rol**, los usuarios a los que no se les ha asignado el rol se enumeran con el **Modo de asignación** ajustado a **Ninguno**. Seleccione uno o más usuarios a los que se les debe asignar el rol.
5. En el **Panel Acciones**, seleccione **Asignar a rol**. El **Modo de asignación** se actualiza a **Manual** y los usuarios ahora tienen un nuevo rol asignado.

## <a name="manually-remove-users-from-roles"></a>Eliminar manualmente usuarios de roles
Los usuarios que se asignan manualmente a roles de seguridad también los elimina manualmente el administrador. Estos usuarios no se eliminan de los roles a través de reglas de asignación automática de roles.

1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.
2. Para eliminar un usuario, siga estos pasos:
   1. En el árbol, seleccione un rol. 
   2. En el área **Usuarios asignados al rol**, seleccione el usuario que debe eliminarse.
   3. Seleccione **Eliminar** y el usuario se elimina del rol.
3. Para eliminar a varios usuarios, siga estos pasos:
   1. En el árbol, seleccione un rol. 
   2. En el área **Usuarios asignados al rol**, seleccione **Asignar o excluir usuarios de forma manual**.
   3. En la página **Asignar usuarios o excluir usuarios del rol**, los usuarios a los que no se les ha asignado el rol se enumeran con el **Modo de asignación** ajustado a **Ninguno**. Seleccione los usuarios que deben ser excluidos del rol.
   4. En el **Panel de acciones**, seleccione **Excluir de rol**. La columna **Modo de asignación** se actualiza a **Manual** y los usuarios ahora están excluidos del rol.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

