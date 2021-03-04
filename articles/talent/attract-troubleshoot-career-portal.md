---
title: Los usuarios de Attract no pueden solicitar puestos de trabajo desde el portal de proyectos profesionales
description: En este tema se explica cómo solucionar un problema en el que los usuarios de Attract no pueden solicitar trabajos desde el portal de proyectos profesionales.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462437"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Los usuarios de Attract no pueden solicitar puestos de trabajo desde el portal de proyectos profesionales

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Emitir

Los usuarios de Attract no pueden solicitar puestos de trabajo desde el portal de proyectos profesionales. Cuando intentan solicitar un trabajo creado en Dynamics 365 Talent: Attract, el navegador carga la página continuamente y no completa la acción.

## <a name="cause"></a>Causa

Este problema se produce cuando el equipo de relación con talentos no tiene el rol de usuario Talento.

## <a name="resolution"></a>Resolución

Asigne el rol de usuario Talento al equipo de relaciones con talentos.

1. Inicie sesión en el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com) con cualquiera de las siguientes credenciales de administrador:

   - Administrador de Dynamics 365
   - Administrador global
   - Administrador de Power Platform

2. En el panel de navegación, seleccione **Entornos** y, a continuación, el entorno en el que asignará el rol de usuario Talento al equipo de relaciones con talentos.

   ![Seleccionar entorno](./media/attract-troubleshoot-career-portal-select-environment.png)

3. En el panel **Entornos**, seleccione la **URL del entorno** e inicie sesión en el portal de administración del entorno (por ejemplo, https:<orgname>.crm.dynamics.com).

4. Seleccione **Configuración**, **Sistema** y, a continuación, **Seguridad**.

   ![Navegue hasta Seguridad](./media/attract-troubleshoot-career-portal-security.png)

5. Seleccione **Equipos**.

   ![Seleccione Equipos.](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Busque **Equipo de relaciones con talentos** en el cuadro de búsqueda y luego seleccione el equipo entre los resultados de búsqueda.

7. Seleccione **ADMINISTRAR ROLES** en la cinta de opciones.

8. En el cuadro de diálogo **Administrar roles de equipo**, seleccione **Usuario de Talent** en la lista de roles disponibles y, a continuación, **Aceptar** para aplicar el rol.

   ![Aplicar rol](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Pruebe sus cambios:

   1. Inicie sesión en el portal de portal de proyectos profesionales desde una nueva ventana de navegador.
   2. Solicite el trabajo en el portal de proyectos profesionales. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]