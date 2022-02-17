---
title: Retirada de las aplicaciones Dynamics 365 Talent - Attract and Onboard
description: Este tema describe la retirada de las aplicaciones Dynamics 365 Talent - Attract and Onboard.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: df33f35f66e356c3c2a99f0d81ebba1d0f34b5d9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069413"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Retirada de aplicaciones Dynamics 365 Talent: Attract and Onboard


En diciembre de 2019, anunciamos la retirada del 1 de febrero de 2022 de las aplicaciones Dynamics 365 Talent - Attract and Onboard, brindando a nuestros clientes dos años para planificar.

Para obtener más información sobre el retiro de estas aplicaciones, consulte:
 - [Retirada de las aplicaciones Dynamics 365 Talent - Attract and Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Crear una fuerza laboral más exitosa con Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Seguiremos apoyando Dynamics 365 Human Resources, que ayudará a nuestros clientes a obtener los conocimientos necesarios sobre la fuerza laboral para crear experiencias de empleados basadas en datos en múltiples áreas, como:

- Compensación
- Beneficios
- Bajas y ausencias
- Conformidad
- Payroll
- Comentarios de rendimiento
- Formación y certificación
- Programas de autoservicio

## <a name="dynamics-365-talent-apps-retirement-faq"></a>P+F sobre la retirada de las aplicaciones de Dynamics 365 Talent

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>¿Cuál es la experiencia de usuario para las aplicaciones Dynamics 365 Talent - Attract and Onboard a partir del 1 de febrero de 2022?

Los usuarios no podrán utilizar las aplicaciones y serán redirigidos a una página de retiro.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>¿Pueden los clientes continuar exportando datos para las aplicaciones Dynamics 365 Talent - Attract and Onboard después del 1 de febrero de 2022?
  
No, el retiro se anunció en diciembre de 2019 y las capacidades de exportación requeridas se proporcionaron hasta el 1 de febrero de 2022. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>¿Los datos del cliente relacionados con las aplicaciones Dynamics 365 Talent - Attract and Onboard en Dataverse se eliminarán después del 1 de febrero de 2022?

No, las entidades de Dataverse permanecerán en el entorno de Microsoft Dataverse del cliente incluso después de la jubilación, a menos que se elimine o desinstale la solución Human Capital Management Talent.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Sé el nombre del entorno Talent. ¿Cómo puedo ver los datos de Attract y Onboard en Dataverse?

1.  Inicie sesión en Power Apps: https://make.powerapps.com
2.  Seleccione el entorno en el que le gustaría ver los datos de atracción e incorporación.
3.  Vaya a **Dataverse > Tablas**. 
4.  Escriba "msdyn_" en **Buscar**. Si ve la lista de tablas que comienzan con "msdyn_" + nombres de tablas (ejemplo: msdyn_candidate), entonces ha encontrado el entorno con datos de Attract e Onboard.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>No sé el nombre del entorno Talent. ¿Cómo puedo encontrar el entorno que tiene los datos para las aplicciones Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard?

1)  Inicie sesión en el centro de administración de Power Platform: https://admin.powerplatform.microsoft.com/
2)  Seleccione **entornos**.
3)  Seleccione un entorno concreto para evaluar.
4)  Seleccione **Recursos > Aplicaciones de Dynamics 365**.
5)  Si ve la solución **HCM Talent** instalada, este entorno debe tener datos de Attract e Onboard almacenados en él. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> La solución **HCM Talent** también se usa en Dynamics 365 Human Resources.
