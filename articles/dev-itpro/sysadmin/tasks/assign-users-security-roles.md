---
title: Asignar usuarios a roles de seguridad
description: Para obtener acceso a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, se debe asignar a los usuarios a roles de seguridad.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c0afd0f5754e59307a82af9c9700b36c31edcc4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851368"
---
# <a name="assign-users-to-security-roles"></a>Asignar usuarios a roles de seguridad

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para obtener acceso a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, se debe asignar a los usuarios a roles de seguridad. Este procedimiento explica cómo los administradores del sistema pueden asignar usuarios a roles automáticamente, en función de los datos empresariales. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="automatically-assign-users-to-roles"></a>Asignar usuarios automáticamente a roles
1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.
2. En el árbol, seleccione "Supervisor contable". Seleccione el rol para el que desea configurar la regla. En este ejemplo, seleccione Supervisor contable. 
3. Haga clic en **Agregar regla** para abrir el cuadro desplegable.
4. En la lista **Seleccionar una consulta**, busque y seleccione el registro deseado. Seleccione la consulta que se usará para esta regla.  
5. En la lista **Nombre de la regla de pertenencia**, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en **Editar consulta**. Edite la consulta según sea necesario.  
7. Haga clic en **Aceptar**.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuarios de la asignación automática de roles
1. Cierre la página.
2. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.
3. En el árbol, seleccione "Supervisor contable". Seleccione una función. Para este ejemplo, seleccione Supervisor contable.  
4. En el menú **Usuarios asignados al rol**, seleccione **Asignar o excluir usuarios de forma manual**.
5. En el lista **Asignar usuarios al rol o excluir usuarios del rol**, marque la fila seleccionada. Seleccione un usuario.  
6. En el **Panel de acciones**, seleccione **Excluir de rol**.
    
    Haga clic en **Excluir de rol** para excluir los usuarios seleccionados del rol. Para quitar exclusiones, seleccione los usuarios para los que desea quitar las exclusiones y, a continuación, haga clic en **Restablecer estado**. Al eliminar una exclusión restableciendo el estado del usuario, el rol del usuario se asigna de nuevo automáticamente. Sin embargo, el usuario no se asigna inmediatamente al rol o se excluye del rol al restablecer el estado. En su lugar, el usuario se asigna al rol o se elimina del rol la próxima vez que se ejecutan las reglas para la asignación automática de roles.  
