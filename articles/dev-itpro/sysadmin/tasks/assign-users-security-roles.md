--- 
title: Asignar usuarios a roles de seguridad
description: Para obtener acceso a Microsoft Dynamics 365 or Finance and Operations, los usuarios se deben asignar a roles de seguridad.
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: da96ec8357ea209fd958e32ab438b13e668735df
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---
# <a name="assign-users-to-security-roles"></a>Asignar usuarios a roles de seguridad

[!include[task guide banner](../../includes/task-guide-banner.md)]

Para obtener acceso a Microsoft Dynamics 365 or Finance and Operations, los usuarios se deben asignar a roles de seguridad. Este procedimiento explica cómo los administradores del sistema pueden asignar usuarios a roles automáticamente, en función de los datos empresariales. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="automatically-assign-users-to-roles"></a>Asignar usuarios automáticamente a roles
1. Vaya a Administración del sistema > Seguridad > Asignar usuarios a roles.
2. En el árbol, seleccione "Supervisor contable".
    * Seleccione el rol para el que desea configurar la regla. En este ejemplo, seleccione Supervisor contable.  
3. Haga clic en Agregar regla para abrir el cuadro desplegable.
4. En la lista, busque y seleccione el registro deseado.
    * Seleccione la consulta que se usará para esta regla.  
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Editar consulta.
    * Edite la consulta según sea necesario.  
7. Haga clic en Aceptar

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuarios de la asignación automática de roles
1. Cierre la página.
2. Vaya a Administración del sistema > Seguridad > Asignar usuarios a roles.
3. En el árbol, seleccione "Supervisor contable".
    * Seleccione una función. Para este ejemplo, seleccione Supervisor contable.  
4. Haga clic en Asignar o excluir usuarios de forma manual.
5. En la lista, marque la fila seleccionada.
    * Seleccione un usuario.  
6. Haga clic en Excluir de rol.
    * Haga clic en Excluir de rol para excluir los usuarios seleccionados del rol. Para quitar exclusiones, seleccione los usuarios para los que desea quitar las exclusiones y, a continuación, haga clic en Restablecer estado. Al eliminar una exclusión restableciendo el estado del usuario, el rol del usuario se asigna de nuevo automáticamente. Sin embargo, el usuario no se asigna inmediatamente al rol o se excluye del rol al restablecer el estado. En su lugar, el usuario se asigna al rol o se elimina del rol la próxima vez que se ejecutan las reglas para la asignación automática de roles.  


