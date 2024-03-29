---
title: Diagnósticos de seguridad para las grabaciones de tareas
description: Este artículo proporciona información sobre cómo analizar y administrar los requisitos de permisos de seguridad basados en una grabación de tareas.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.search.form: ''
ms.openlocfilehash: e564a0499cb1a5dc00fc027c20a027f9b454600c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272532"
---
# <a name="security-diagnostics-for-task-recordings"></a>Diagnósticos de seguridad para las grabaciones de tareas

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Antes de comenzar

Este artículo proporciona información sobre cómo analizar y administrar los requisitos de permisos de seguridad basados en una grabación de tareas. Antes de completar los pasos de este artículo, debe tener una grabación de tareas del proceso de negocio que desea analizar. Para registrar un proceso comercial, consulte [Recursos de grabación de tareas](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Administrar la seguridad para la grabación de tareas

1. Vaya a **Administracion del sistema** > **Seguridad** > **Diagnóstico de seguridad para grabación de tareas**.
2. Abra la tarea de grabación desde su ubicación. Seleccione **Abrir desde este PC** o **Abierto desde Lifecycle Services** y luego seleccione **Cerrar**.
3. Esto abrirá la página **Detalles del elemento del menú de seguridad** que enumera los objetos de seguridad necesarios para el proceso.

 > [!NOTE]
 > Los elementos del menú **Acción** y **Salida** no están incluidos en la lista.

4. En el campo **Id. de usuario**, seleccione un usuario. Si el usuario no tiene permisos para algunos elementos del menú, el campo **Permisos que faltan** se actualizará a **Sí**.
  
  ![Página de detalles del elemento del menú de seguridad.](../media/Security-Menu-Item-Details.png)

5. Seleccione **Añadir referencia** para ver una lista de los objetos de seguridad, incluidos roles, deberes y privilegios que otorgan el permiso que falta.
6. Seleccione un objeto de seguridad en la lista:

    - Si **Papel** está seleccionado, seleccione **Agregar rol al usuario**. Esto abrirá la página **Asignar usuarios a roles**. Para obtener más información, consulte la página [Asignar usuarios a roles de seguridad](assign-users-security-roles.md).
    - Si está seleccionado **Derecho**, seleccione **Agregar derecho al rol**, seleccione los roles a los que se debe agregar el derecho y luego seleccione **Aceptar**.
    - Si está seleccionado **privilegio**, seleccione **Agregar privilegio a derechos**, seleccione los roles a los que se debe agregar el derecho y luego seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
