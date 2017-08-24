--- 
title: "Identificación y resolución de conflictos en segregación de controles"
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: fdc0bbd0a239c8d7719271445a4d6a5323e87aad
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identificación y resolución de conflictos en segregación de controles

[!include[task guide banner](../../includes/task-guide-banner.md)]

Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios. Este concepto se denomina "segregación de controles". Cuando la definición de un rol de seguridad o las asignaciones de roles de un usuario infringen las reglas, se registra el conflicto. Todos los conflictos los debe resolver el administrador. Complete el siguiente procedimiento para identificar y resolver conflictos. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verificación del cumplimiento de las asignaciones de rol de usuario con las nuevas reglas de segregación de controles
1. Vaya a Administración del sistema > Seguridad > Segregación de controles > Verificar la conformidad de las asignaciones de roles de usuario.
2. Haga clic en Aceptar
    * Una notificación muestra los resultados de la validación.     Si existe conflicto, puede abrir la página Usuarios y cambiar las asignaciones de roles de usuario. Los conflictos también se registran en la página Conflictos de segregación de controles.     Para ejecutar el proceso de comprobación como un trabajo por lotes, seleccione Procesamiento por lotes y, a continuación, establezca los demás parámetros de lote. Después de que se ejecute el trabajo por lotes, puede revisar los conflictos en la página Conflictos de segregación de controles.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Visualización y resolución de asignaciones de roles de usuario en conflicto
1. Vaya a Administración del sistema > Seguridad > Segregación de controles > Conflictos de segregación de controles.
    * Seleccione un conflicto y haga clic en uno de los siguientes botones: Denegar asignación – denegar la asignación del usuario al rol de seguridad adicional. Si se rechaza una asignación de roles automática, se marca el usuario como excluido del rol. El usuario excluido no recibe el acceso asociado al rol, y no se le puede asignar al rol hasta que el administrador retire la exclusión.     Permitir asignación: anula el conflicto y permite asignar al usuario los dos roles de seguridad. Si se anula un conflicto, se debe especificar un motivo en el campo Motivo de la anulación.  
2. Cierre la página.
3. Vaya a Administración del sistema > Seguridad > Segregación de controles > Conflictos de segregación de controles sin resolver.
    * Seleccione un conflicto y haga clic en uno de los siguientes botones: Denegar asignación – denegar la asignación del usuario al rol de seguridad adicional. Si se rechaza una asignación de roles automática, se marca el usuario como excluido del rol. El usuario excluido no recibe el acceso asociado al rol, y no se le puede asignar al rol hasta que el administrador retire la exclusión.     Permitir asignación: anula el conflicto y permite asignar al usuario los dos roles de seguridad. Si se anula un conflicto, se debe especificar un motivo en el campo Motivo de la anulación.    
4. Cierre la página.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Verificación del cumplimiento de roles de usuario existentes con nuevas reglas de segregación de controles
1. Vaya a Administración del sistema > Seguridad > Segregación de controles > Reglas de segregación de controles.
    * Seleccione una regla.  
2. Haga clic en Validar controles y roles.
    * Si algunos roles existentes infringen la regla seleccionada, aparecerá un mensaje con el nombre del rol y los nombres de los deberes en conflicto. El administrador debe indicar cómo mitigar el riesgo de seguridad o modificar el rol de modo que no infrinja las reglas de segregación de controles.     Si ningún rol infringe la regla seleccionada, aparece un mensaje que indica que todos los roles son conformes.  


