---
title: Configurar un trabajador mediante el dispositivo móvil de trabajo
description: Este artículo explica cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.
author: johanhoffmann
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f6f51a66d49cafd172ba123bf883fb41cdcb5c3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844343"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurar un trabajador mediante el dispositivo móvil de trabajo

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Comprobar que el trabajador está asignado a un rol

Para este ejemplo, compruebe que se asigna al usuario "SHANNON" el rol de operadora de maquinaria antes de configurar la cuenta de la trabajadora.

1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.
2. Busque un usuario en el filtro rápido. Para este ejemplo, escriba `shannon`.
3. Seleccione el vínculo en la columna **Id. de usuario** de la cuenta de usuario que aparece.
4. En el árbol **Roles de usuario**, seleccione **Roles > Operador de maquinaria**.
5. Cierre las páginas **detalles de usuario** y **usuarios** para volver a la página principal.

## <a name="configure-worker-account"></a>Configurar la cuenta de trabajador
1. Vaya a **Panel de exploración > Módulos > Recursos humanos > Trabajadores > Trabajadores**.
2. Busque un usuario en el filtro rápido. Para este ejemplo, escriba `shannon`.
3. Seleccione el vínculo en la columna **Nombre** de la cuenta de usuario que aparece.
4. Seleccione la pestaña **Registro de horas**.
5. Seleccione **Activar en terminales de registro**.
6. Especifique o seleccione los valores de los siguientes campos:  

    - **Grupo de cálculo**  
    - **Grupo de cálculo predeterminado**  
    - **Grupo de aprobación**  
    - **Perfil estándar**  
    - **Grupo de perfiles**  

7. Seleccione **Aceptar**.
8. Seleccione **Editar** para especificar un número de tarjeta para el nuevo trabajador con registro de horas. En el campo **Id. de tarjeta**, especifique un valor.
9. Seleccione **Guardar**.
10. Cierre **Detalles del trabajador** y **Trabajadores**.

## <a name="assign-worker-to-device-group"></a>Asignar un trabajador a un grupo de dispositivos
1. Vaya a **Control de producción > Configuración > Ejecución de fabricación > Configurar tarjeta de trabajo para dispositivos**:
2. Seleccione **Agregar**.
3. En la lista, seleccione el trabajador que desee. Para este ejemplo, seleccione **SHANNON**.
4. Seleccione **Aceptar**.
5. Seleccione **Editar**.
6. En el campo **Unidad de producción**, puede establecer el filtro predeterminado para el trabajador. Esto asegurará que solo se muestran los trabajos de producción para la unidad de producción seleccionada cuando el trabajador inicia sesión en el dispositivo. Especifique el valor que desee.
7. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]