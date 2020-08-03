---
title: Delegación de elementos de trabajo de un flujo de trabajo
description: Si tiene planeado ausentarse de la oficina o, por alguna otra razón, no va a poder encargarse de los elementos de trabajo, puede delegar, o volver a asignar, sus elementos de trabajo a otros usuarios.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 96777b66645453bc909bd4053e2724a37771d5d6
ms.sourcegitcommit: 561d06c2a74602dfaa40334d8afac5053aebc055
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "3541094"
---
# <a name="delegate-work-items-in-a-workflow"></a>Delegar elementos de trabajo de un flujo de trabajo

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>Delegación manual de un elemento de trabajo

Para delegar un elemento de trabajo individual, seleccione la opción **Delegar** en el menú **Flujo de trabajo** y especifique el usuario al que se delegará junto con un comentario. Esto reasignará el elemento de trabajo a dicho usuario para que puedan completarlo.

## <a name="manually-delegate-multiple-work-items"></a>Delegar manualmente múltiples elementos de trabajo

Se pueden delegar varios elementos de trabajo juntos desde la página **Elementos de trabajo asignados a mí**. Los siguientes tipos de flujo de trabajo se pueden elegir para la delegación masiva: flujo de trabajo de aprobación de acuerdo de compra, flujo de trabajo de orden de compra, revisión de solicitud de compra y flujo de trabajo de factura de proveedor. La característica **Delegar múltiples elementos de trabajo** está deshabilitada de manera predeterminada y se puede habilitar en **Espacios de trabajo> Gestión de funciones**. Póngase en contacto con el administrador del sistema para obtener ayuda para habilitar esta función.
1.  Vaya a **Común> Común> Elementos de trabajo> Elementos de trabajo asignados a mí**.
2.  Seleccione los elementos de trabajo que se delegarán.
3.  Haga clic en el menú **Delegar elementos de trabajo**.
4.  En el campo **Usuario**, seleccione el usuario al que desea delegar los elementos de trabajo.
5.  En el campo **Comentario**, escriba un comentario en el que se explique el motivo por el que delega los elementos de trabajo.
6.  Haga clic en el botón **Delegar elementos de trabajo** para completar la delegación del elemento de trabajo.

## <a name="automatically-delegate-work-items"></a>Delegación automática de elementos de trabajo

Si tiene planeado ausentarse de la oficina o de otro modo no va a poder dedicar tiempo a los elementos de trabajo durante un tiempo, puede delegar elementos nuevos de trabajo automáticamente a otros usuarios mediante la página **Opciones de usuario**.

### <a name="set-up-automatic-delegation"></a>Configuración de la delegación automática
1. Vaya a **Común > Configuración > Opciones de usuario**.
2. Haga clic en la pestaña **Flujo de trabajo**. Asegúrese de que está expandida la sección de delegación. Para configurar el sistema para que sus elementos de trabajo se deleguen de manera automática a otros usuarios, debe crear reglas de delegación, que especifican cuándo se delegan determinados tipos de elementos de trabajo. Siga estos pasos para crear una regla de delegación.  
3. Haga clic en **Agregar**.
4. En el campo **Ámbito**, seleccione una opción:
    - Todo: permite delegar todos los elementos de trabajo que tiene asignado el usuario.
    - Módulo: delegar solo los elementos de trabajo relacionados con un tipo específico de flujo de trabajo. Si selecciona esta opción, debe seleccionar el tipo de flujo de trabajo en el campo **Nombre**.
    - Flujo de trabajo: delegue solo los elementos de trabajo relacionados con un flujo de trabajo específico. Si selecciona esta opción, también debe seleccionar el flujo de trabajo en el campo **Nombre**.  
5. En el campo **Nombre**:
    - En el ámbito **Módulo**, seleccione el módulo de destino.
    - En el ámbito **Flujo de trabajo**, seleccione el flujo de trabajo de destino.
6. En el campo **Delegado**, seleccione el usuario al que desea delegar los elementos de trabajo. Use los campos **Fecha/hora de inicio** y **Fecha/hora de finalización** para especificar cuándo desea delegar automáticamente los elementos de trabajo.  
7. En el campo **Fecha y hora inicial**, especifique una fecha y una hora.
8. En el campo **Fecha y hora final**, especifique una fecha y una hora.
9. Active la casilla de verificación **Habilitado** para activar la regla de delegación. 
10. En el campo **Comentario**, escriba un comentario en el que se explique el motivo por el que delega los elementos de trabajo.
