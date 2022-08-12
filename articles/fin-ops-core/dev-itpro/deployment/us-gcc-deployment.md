---
title: Dynamics 365 Finance, Supply Chain Management y Commerce en US Government Community Cloud (GCC)
description: Este artículo proporciona información sobre productos Microsoft Dynamics 365 US Government que están disponibles para entidades gubernamentales y privadas calificadas.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 41789d574cc7348dbf8a18db97da9c428da09602
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103950"
---
# <a name="dynamics-365-finance-supply-chain-management-and-commerce-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance, Supply Chain Management y Commerce en US Government Community Cloud (GCC)

[!include [banner](../includes/banner.md)]



Algunos productos Microsoft Dynamics 365 United States (US) Government están disponibles para entidades gubernamentales y privadas calificadas. Esas entidades se limitan a los siguientes tipos:

- Entidades gubernamentales federales, estatales, locales, tribales y territoriales de EE. UU.
- Entidades privadas que usan Dynamics 365 US Government para brindar soluciones a entidades gubernamentales o miembros calificados de la comunidad de la nube
- Entidades privadas que tienen datos de clientes sujetos a normativas gubernamentales y Dynamics 365 US Government es el servicio adecuado para cumplir los requisitos normativos

Para obtener información, consulte [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Incorporación

Para completar la incorporación inicial para un proyecto de implementación en Microsoft Dynamics Lifecycle Services (LCS), siga las instrucciones en [Incorporar un proyecto de implementación](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Sin embargo, no utilice el enlace a LCS público que se proporciona en esas instrucciones. En su lugar, utilice la siguiente URL para abrir LCS para US Government Community Cloud (GCC): <https://gov.lcs.microsoftdynamics.us>.

Una vez completada la incorporación inicial, siga las instrucciones en [Incorporación de proyectos](../lifecycle-services/project-onboarding.md). Una vez más, use [LCS para GCC](https://gov.lcs.microsoftdynamics.us) en lugar de LCS públicos.

## <a name="environment-deployment"></a>Implementación de entornos

Una vez que haya completado la incorporación del proyecto, puede revisar las capacidades adicionales de LCS que se describen en [Lifecycle Services (LCS)para clientes de aplicaciones de finanzas y operaciones](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). A continuación, pase a la implementación del entorno.

- Para implementar entornos administrados por Microsoft a través de LCS, siga las instrucciones en [Lifecycle Services (LCS) para clientes de aplicaciones de finanzas y operaciones](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- Para entornos hospedados en la nube, consulte [Implementar y acceder a entornos de desarrollo](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). También debe completar el proceso de incorporación de Resource Manager para sus conectores, como se describe en [Completar el proceso de incorporación de Azure Resource Manager para proyectos de US government Lifecycle Services](arm-onbarding-us-goverment.md).

> [!NOTE]
> Para proyectos de US Government LCS, solo se admiten suscripciones de Azure específicas para Azure Government.

## <a name="features-that-arent-available"></a>Funciones que no están disponibles

Algunas características no estarán disponibles para su implementación en GCC o no estarán disponibles para su uso con Dynamics 365 en GCC. Por ejemplo, Azure DevOps Services no estará disponible en GCC. Sin embargo, pueden utilizarse los servicios de Azure DevOps local o Azure DevOps público. Para obtener información detallada sobre la disponibilidad de funciones, consulte [Disponibilidad de funciones de US Government de aplicaciones de negocios](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>¿Se admiten Dynamics 365 Finance y Dynamics 365 Supply Chain Management en GCC-High?

No ¿Se admiten Dynamics 365 Finance y Dynamics 365 Supply Chain Management en solo en GCC?

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>¿Puedo usar Azure DevOps público con Finance y Supply Chain Management en GCC?

Sí, puede usar servicios de Azure DevOps público si no tiene requisitos para una solución certificada por el Federal Risk and Authorization Management Program (FEDRAMP). Alternativamente, puede usar Azure DevOps Server.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>¿Puedo implementar un entorno de desarrollo de nivel 1 hospedado en la nube en una suscripción de Azure Commercial?

No En [LCS para GCC](https://gov.lcs.microsoftdynamics.us), debe usar una suscripción a Azure Government para implementar un entorno hospedado en la nube.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>¿Qué puedo hacer si necesito un paquete de la biblioteca de activos compartidos, pero no está disponible en LCS para GCC?

Puede descargar el mismo paquete de la biblioteca de activos compartidos en [LCS público](https://lcs.dynamics.com). Alternativamente, su socio puede ayudarlo a descargar el paquete.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>¿Está disponible la herramienta de actualización de código en GCC?

No, la herramienta de actualización de código no está disponible actualmente en GCC. Sin embargo, puede crear un proyecto de cliente potencial en [LCS público](https://lcs.dynamics.com) y utilizar la herramienta de actualización de código. Tenga en cuenta que no podrá implementar entornos en proyectos potenciales.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>¿Puede mi socio abrir un vale de soporte en mi nombre?

Sí. Sin embargo, si su socio usa una identidad que no es de GCC, el vale de soporte se dirigirá a la cola de soporte público. Le recomendamos que utilice el derecho de GCC del cliente en LCS para abrir vales de soporte.

## <a name="see-also"></a>Consulte también

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Disponibilidad de la función US Government de aplicaciones de negocios](https://aka.ms/BAPFunctionalParity).
- [Manual del usuario de Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Información general de la implementación en la nube](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

