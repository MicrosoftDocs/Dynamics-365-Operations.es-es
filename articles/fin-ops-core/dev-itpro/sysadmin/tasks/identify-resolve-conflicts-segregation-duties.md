---
title: Identificar y resolver conflictos de segregación de controles
description: Este artículo explica cómo identificar y resolver conflictos de segregación de controles.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd36db5df2b6871d410bb1feaae825909ec9b3ff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883488"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identificar y resolver conflictos de segregación de controles

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo identificar y resolver conflictos de segregación de controles. Puede configurar reglas para controles diferentes que deban llevar a cabo diferentes usuarios. Este concepto se denomina "segregación de controles". Cuando la definición de un rol de seguridad o las asignaciones de roles de un usuario infringen las reglas, se registra el conflicto. Todos los conflictos los debe resolver el administrador. Complete el siguiente procedimiento para identificar y resolver conflictos.

Después de agregar una regla, verifique que todos los roles existentes sean compatibles. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Verifique que roles y controles de usuario existentes cumplen con las nuevas reglas de segregación de controles
1. Vaya a **Administración del sistema** > **Seguridad** > **Segregación de controles** > **Reglas de segregación de controles**.
3. Seleccione **Validar controles y roles**. Si algunos roles infringen las reglas, aparecerá un mensaje con el nombre de la regla, del rol y los nombres de los controles en conflicto. Los roles en conflicto deben modificarse mediante la **Configuración de seguridad** y no puede incluir controles en conflicto. Si ningún rol infringe la regla seleccionada, aparece un mensaje que indica que todos los roles son conformes.   

> [!NOTE]
> La validación solo se realiza para la regla seleccionada. Es importante validar el cumplimiento de cada regla.   

Cuando crea o modifica un rol, las reglas para la segregación de funciones se aplican automáticamente. No puede asignar controles en conflicto a un rol.

A continuación, verifique que todas las asignaciones de funciones existentes sean compatibles.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verifique que las asignaciones de rol de usuario cumplen con las nuevas reglas de segregación de controles
1. Vaya a **Administración del sistema > Seguridad > Segregación de controles > Verificar la conformidad de las asignaciones de roles de usuario**.
2. Seleccione **Aceptar**. Una notificación muestra los resultados de la validación. Los conflictos también se registran en la página **Conflictos no resueltos de segregación de controles**.   

Cuando asigna usuarios a roles, las reglas para la segregación de controles se aplican automáticamente. Si intenta asignar un usuario a roles que contienen deberes en conflicto, recibirá un mensaje de error. Luego, debe resolver el conflicto negando o permitiendo la asignación de roles adicionales. El rol adicional se asignará después de que se permita la asignación. 

> [!NOTE]
> Actualmente, los conflictos no se verifican para los usuarios a los que se les asignan roles según los grupos de dominio de Active Directory.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Visualización y resolución de asignaciones de roles de usuario en conflicto
1. Vaya a **Administración del sistema** > **Seguridad** > **Segregación de controles** > **Conflictos de segregación de controles sin resolver**. 
2. Seleccione un conflicto y, a continuación, seleccione una de las siguientes acciones: 

  - **Denegar asignación**: esto denegará la asignación del usuario al rol de seguridad adicional. Si se rechaza una asignación de roles automática, se marca el usuario como excluido del rol. El usuario excluido no recibe el acceso asociado al rol, y no se le puede asignar al rol hasta que el administrador retire la exclusión. 
-  **Permitir asignación**: esto anula el conflicto y permite asignar al usuario al rol de seguridad adicional. Si se anula un conflicto, se debe especificar un motivo en el campo **Motivo de la anulación**. Todas las asignaciones de roles anuladas se pueden ver en la página **Conflictos de segregación de controles**.  

> [!NOTE]
> Si se enumeran varios conflictos para el mismo usuario, seleccione el registro de usuario y evalúe los roles asignados en la página **Usuarios**. Para evitar este conflicto, valide cada regla después de agregarla o modificarla.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]