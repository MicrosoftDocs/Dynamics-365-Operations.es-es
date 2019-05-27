---
title: Delegación de elementos de trabajo de un flujo de trabajo
description: Si tiene planeado ausentarse de la oficina o, por alguna otra razón, no va a poder encargarse de los elementos de trabajo, puede delegar, o volver a asignar, sus elementos de trabajo a otros usuarios.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509463"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegar elementos de trabajo de un flujo de trabajo

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a>Delegación manual de un elemento de trabajo

Para delegar un elemento de trabajo individual, seleccione la opción **Delegar** en el menú **Flujo de trabajo** y especifique el usuario al que se delegará junto con un comentario. Esto reasignará el elemento de trabajo a dicho usuario para que puedan completarlo.

## <a name="automatically-delegate-work-items"></a>Delegación automática de elementos de trabajo

Si tiene planeado ausentarse de la oficina o de otro modo no va a poder dedicar tiempo a los elementos de trabajo durante un tiempo, puede delegar elementos nuevos de trabajo automáticamente a otros usuarios mediante la página **Opciones de usuario**.

### <a name="set-up-automatic-delegation"></a>Configuración de la delegación automática
1. Vaya a las opciones Común > Configuración > Opciones de usuario.
2. Haga clic en la pestaña Flujo de trabajo.
    * Asegúrese de que la sección Delegación está expandida.    Para configurar el sistema para que sus elementos de trabajo se deleguen de manera automática a otros usuarios, debe crear reglas de delegación, que especifican cuándo se delegan determinados tipos de elementos de trabajo. Siga estos pasos para crear una regla de delegación.  
3. Haga clic en Agregar.
4. En el campo Ámbito, seleccione una opción.
    * Todo: permite delegar todos los elementos de trabajo que tiene asignado el usuario.    Módulo: delegar solo los elementos de trabajo relacionados con un tipo específico de flujo de trabajo. Si selecciona esta opción, también debe seleccionar el tipo de flujo de trabajo en el campo Nombre.    Flujo de trabajo: delegue solo los elementos de trabajo relacionados con un flujo de trabajo específico. Si selecciona esta opción, también debe seleccionar el flujo de trabajo en el campo Nombre.  
5. En el campo Delegado, seleccione el usuario al que desea delegar los elementos de trabajo.
    * Use los campos Fecha/hora inicial y Fecha/hora final para especificar cuándo quiere delegar automáticamente los elementos de trabajo.  
6. En el campo Fecha/hora inicial, especifique una fecha y una hora.
7. En el campo Fecha/hora final, especifique una fecha y una hora.
8. Active la casilla de verificación Habilitado para activar la regla de delegación.
    * Si ha seleccionado Módulo como el Ámbito, deberá seleccionar el módulo en el campo Nombre.    Si ha seleccionado Flujo de trabajo como el Ámbito, deberá seleccionar el flujo de trabajo específico para delegar el campo Nombre.  
9. En el campo Comentario, introduzca un comentario en el que se explique el motivo por el que delega los elementos de trabajo.

