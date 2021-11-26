---
title: Trabajadores sin empleo
description: Los trabajadores sin empleo futuro, activo ni histórico con su organización aparecen en la página Trabajadores sin empleo.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d282c0fac00d6bc410717dd156aef9ffce352c6d
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771299"
---
# <a name="workers-without-employment"></a>Trabajadores sin empleo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Los trabajadores que no tienen empleo futuro, activo ni histórico con su organización aparecen en la página **Trabajadores sin empleo**. Los trabajadores de este tipo pueden aparecer cuando importa trabajadores que no tienen un registro de empleo o cuando elimina el empleo de un trabajador a través de **Trabajadores \> Historial de empleo**.

De forma predeterminada, la página **Trabajadores sin empleo** está disponible para los siguientes roles:

- Ayudante de Recursos humanos
- Director de Recursos humanos
- Contratante
- Director de compensaciones y prestaciones
- Administrador de nóminas
- Administrador de nóminas
- Director de cursos

En la lista **Trabajadores sin empleo**, puede eliminar las personas enumeradas. De forma predeterminada, este privilegio se otorga al rol de Asistente de Recursos humanos. Puede otorgar este privilegio a otros roles con los siguientes pasos:

1. Seleccione **Administración del sistema** y luego **Configuración de seguridad**.

2. En la pestaña **Privilegios**, filtre la lista **Privilegios** para **Mantener trabajadores**.

   [![Filtrar lista de privilegios.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. En la columna **Referencias**, seleccione **Elementos del menú de visualización**.

4. En **Elementos del menú de visualización**, seleccione **HcmWorkersWithoutEmployment**.

   [![Seleccionar formulario.](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Seleccione el permiso **Eliminar** para **Conceder**.

6. Seleccione la pestaña **Objetos sin publicar**.

7. Seleccione **Publicar todo**.

   [![Publicar cambios.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
