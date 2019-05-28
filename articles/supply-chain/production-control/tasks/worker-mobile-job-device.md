---
title: Configurar un trabajador mediante el dispositivo móvil de trabajo
description: Este procedimiento le muestra cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bb4d806810660e55ef13a9ff21c07e0ce194496
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571367"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurar un trabajador mediante el dispositivo móvil de trabajo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.


## <a name="assign-roles-to-user-account"></a>Asignar roles a cuenta de usuario
1. Vaya a Administración del sistema > Usuarios > Usuarios.
2. Use el filtro rápido para filtrar por el nombre de un trabajador el que la cuenta de usuario está asociada al rol de operador de maquinaria. En los datos de ejemplo, el nombre sería Shannon.
3. Resalte el registro de la cuenta de usuario.
4. En la lista, haga clic en el vínculo "Nombre" en la fila seleccionada para ver los detalles de la cuenta de usuario.
5. En el árbol, seleccione el "Roles\Operador de máquina".
6. Cierre la página de detalles de la cuenta de usuario.
7. Cierre la página.

## <a name="configure-worker-account"></a>Configurar cuenta de trabajador.
1. Vaya a Recursos humanos > Trabajadores > Trabajadores.
2. Use el filtro rápido para filtrar por el nombre de un trabajador el que la cuenta de usuario está asociada al rol de operador de maquinaria. En los datos de ejemplo, el nombre sería Shannon.
3. Resalte el registro de la cuenta de usuario.
4. En la lista, haga clic en el vínculo "Nombre" en la fila seleccionada para ver los detalles de la cuenta de usuario.
5. Haga clic en la ficha Empleo.
6. Expanda la ficha desplegable Registro de horas y haga clic en Activar en terminales de registro.
7. Haga clic en Activar en terminales de registro.
8. En el campo Grupo de cálculo, escriba o seleccione un valor.
9. En el campo Grupo de cálculo predeterminado, escriba o seleccione un valor.
10. En el campo Grupo de aprobación, especifique o seleccione un valor.
11. En el campo Perfil estándar, especifique o seleccione un valor.
12. En el campo Grupo de perfiles, especifique o seleccione un valor.
13. Haga clic en Aceptar
14. Haga clic en Editar para especificar un número de tarjeta para el nuevo trabajador con registro de horas.
15. En el campo Id. de tarjeta, escriba un valor.
16. Haga clic en Guardar.
17. Use el acceso directo SaveRecord.
18. Cierre la página de detalles del trabajador.
19. Cierre la página.

## <a name="assign-worker-to-device-group"></a>Asignar trabajador a grupo de dispositivos.
1. Vaya a Control de producción > Configuración > Ejecución de fabricación > Configurar tarjeta de trabajo para dispositivos.
2. Haga clic en Agregar.
3. En la lista, marque la fila seleccionada.
4. Haga clic en Aceptar
5. Haga clic en Editar.
6. En el campo Unidad de producción, puede establecer el filtro predeterminado para el trabajador. Esto asegurará que solo se muestran los trabajos de producción para la unidad de producción seleccionada cuando el trabajador inicia sesión en el dispositivo.
7. Cierre la página.

