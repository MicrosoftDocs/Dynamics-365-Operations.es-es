---
title: Aprovisionar Human Resources en la infraestructura de finanzas y operaciones
description: Este artículo explica el proceso de aprovisionamiento de un nuevo entorno de producción para Microsoft Dynamics 365 Human Resources en la infraestructura de finanzas y operaciones.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2fd8176d16178ecc4ba667e5937f2cec2e0af2c3
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2022
ms.locfileid: "9221606"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>Aprovisionar Human Resources en la infraestructura de finanzas y operaciones

_**Se aplica a:** Human Resources en la infraestructura de aplicaciones de finanzas y operaciones_ 

> [!NOTE]
> A partir de julio de 2022, los nuevos entornos de Human Resources no se pueden aprovisionar en la infraestructura de Human Resources independiente y los nuevos proyectos de Microsoft Dynamics Lifecycle Services (LCS) no se pueden crear en ella. Los clientes pueden desplegar entornos de Human Resources en la infraestructura de finanzas y operaciones.

Este artículo explica el proceso de aprovisionamiento de un nuevo entorno de producción para Microsoft Dynamics 365 Human Resources en la infraestructura de finanzas y operaciones.

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar a aprovisionar un nuevo entorno, deben cumplirse los siguientes requisitos previos:

- Haber comprado Human Resources a un proveedor de soluciones en la nube (CSP) o mediante un contrato de arquitectura empresarial (EA). Si dispone de una licencia existente de Dynamics 365 que ya incluye el plan de servicio de Human Resources y no puede realizar los pasos de este artículo, póngase en contacto con soporte.
- El administrador global ha iniciado sesión en [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com) y ha creado un nuevo proyecto de finanzas y operaciones.

## <a name="provision-a-human-resources-trial-environment"></a>Proporcionar un entorno de prueba de recursos humanos

> [!NOTE]
> A partir de abril de 2022, los entornos de prueba de Recursos Humanos no estarán disponibles en la aplicación independiente. Los clientes potenciales que estén interesados en evaluar las capacidades de Human Resources en aplicaciones de finanzas y operaciones pueden utilizar la prueba gratuita de 30 días junto con los datos de demostración. Dynamics 365 Finance incluirá las capacidades de Human Resources que se aportan a la infraestructura de Finance a través de la fusión de la aplicación independiente. Para más información, vea [La fusión de las ofertas de recursos humanos reúne capacidades para los clientes](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Para obtener más información sobre pruebas de Dynamics 365 Finance, consulte la [guía paso a paso](../fin-ops-core/fin-ops/get-started/before-you-buy.md).

## <a name="plan-human-resources-environments"></a>Planificar entornos de Human Resources

Antes de crear su primer entorno de Human Resources, debe planificar cuidadosamente las necesidades del entorno para el proyecto. Una suscripción básica a Human Resources incluye dos entornos: un entorno de producción y un entorno de prueba de aceptación estándar predeterminado (espacio aislado). En función de la complejidad del proyecto, tiene la opción de comprar entornos adicionales para respaldar las actividades del proyecto.

Algunas consideraciones sobre entornos opcionales adicionales:

- **Migración de datos**: las actividades de migración de datos permiten que su entorno de espacio aislado se utilice con fines de prueba durante todo el proyecto. Cuando tenga un entorno adicional, las actividades de migración de datos podrán continuar mientras las actividades de prueba y configuración se llevan a cabo simultáneamente en un entorno diferente.
- **Integración**: configure y pruebe integraciones, que pueden incluir integraciones nativas o integraciones personalizadas, como las de nómina, sistemas de seguimiento de candidatos o sistemas y proveedores de prestaciones.
- **Formación**: es posible que necesite un entorno independiente configurado con un conjunto de datos de entrenamiento para capacitar a sus empleados en el uso del nuevo sistema. 
- **Proyecto multifase**: es posible que necesite un entorno adicional para la configuración, la migración de datos, las pruebas u otras actividades en una fase del proyecto que se planifica después de la puesta en funcionamiento inicial del proyecto.
- **Desarrollo**: en la infraestructura de finanzas y operaciones, ahora puede ampliar la solución y desarrollar sus propias personalizaciones. Cada desarrollador debe utilizar su propio entorno de desarrollo. Para más información, consulte [Implementar y acceder a entornos de desarrollo](../fin-ops-core/dev-itpro/dev-tools/access-instances.md).
- **GOLD**: para implementaciones nuevas, una práctica común es usar un entorno GOLD separado que se mantiene impecable para la configuración y la migración de datos. Este entorno se puede utilizar a lo largo de la implementación para actualizar otros entornos. Se utilizará para crear el nuevo entorno de producción que tiene la configuración base y la migración de datos. No puede implementar un entorno de producción en la infraestructura de finanzas y operaciones hasta que haya completado el proceso de preparación para la puesta en marcha. Para obtener más información, consulte [Prepararse para la publicación](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> Al considerar sus entornos, le recomendamos el siguiente método:
>
> - Utilice su entorno de prueba de aceptación estándar predeterminado (anteriormente espacio aislado) u otro entorno para realizar una transición simulada antes de la puesta en marcha.
> - Mantenga una lista de comprobación de transición detallada que incluya cada uno de los paquetes de datos necesarios para migrar los datos finales al entorno de producción durante la transición de puesta en funcionamiento. Esta recomendación es especialmente importante si no tiene un entorno GOLD separado para almacenar sus configuraciones.
> - Utilice su entorno de prueba de aceptación estándar predeterminado (anteriormente espacio aislado) u otro entorno de nivel 2 o superior como su entorno de PRUEBA a lo largo de su proyecto. Si necesita entornos adicionales, su organización puede adquirirlos por un coste adicional.

## <a name="create-an-lcs-project"></a>Crear un proyecto de LCS

Para usar LCS para administrar sus entornos de Human Resources, primero debe crear un proyecto de LCS. Si está migrando su entorno de Human Resources a la infraestructura de finanzas y operaciones, debe crear un nuevo proyecto LCS para aplicaciones de finanzas y operaciones. Si ya tiene un proyecto de LCS para otras aplicaciones de finanzas y operaciones, puede habilitar las características de Human Resources en el espacio de trabajo **Administración de características**. Para más información, consulte [Resumen de administración de funciones](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Cuando un nuevo cliente se registra en Human Resources, la suscripción incluye un espacio de trabajo de proyecto de implementación. Cuando el cliente active el servicio, el administrador de inquilinos debe iniciar sesión en <https://lcs.dynamics.com> mediante el uso de la cuenta de inquilino. El espacio de trabajo del proyecto se crea automáticamente para la organización. Para obtener más información, consulte [Lifecycle Services (LCS) para clientes de aplicaciones de finanzas y operaciones](../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md).

> [!NOTE]
> Para garantizar un aprovisionamiento exitoso, la cuenta que utiliza para aprovisionar el entorno de Recursos Humanos debe asignarse al rol de **Administrador de sistema** o **Personalizador del sistema** en el entorno de Power Apps asociado al entorno de Recursos Humanos. Para más información sobre cómo asignar roles de seguridad a los usuarios en Microsoft Power Platform, vea [Configurar la seguridad de usuario para los recursos](/power-platform/admin/database-security).

Debe completar el proceso de incorporación del proyecto LCS antes de poder comenzar a implementar entornos. Para obtener más información, consulte [Incorporación de proyecto](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md). Para obtener más información sobre cómo usar LCS, consulte [Guía del usuario de Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md).

## <a name="deploy-human-resources-environments"></a>Implementar entornos de Human Resources

La implementación de aplicaciones de finanzas y operaciones, incluido Human Resources, en la nube requiere que comprenda el entorno y la suscripción en la que está implementando, quién puede realizar qué tareas y qué datos y personalizaciones debe administrar. Le recomendamos que utilice una cuenta de servicio en lugar de un usuario designado cuando implemente entornos nuevos. Para obtener más información sobre cómo implementar entornos en la infraestructura de finanzas y operaciones, consulte [Descripción general de la implementación en la nube](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Para implementar un entorno de producción para Human Resources en la infraestructura de finanzas y operaciones debe completar el proceso de preparación para la puesta en marcha. Para obtener más información, consulte [Prepararse para la publicación](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md). Este proceso incluye el calculador de suscripciones en LCS. Para obtener más información, consulte [Calculador de suscripción](../fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator.md).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Integrar Microsoft Power Platform con Human Resources

Microsoft Power Platform proporciona un conjunto de capacidades para las aplicaciones de Dynamics 365 a través del centro de administración de Power Platform. Puede integrar y ampliar el uso de datos de Human Resources utilizando Microsoft Power Platform. Para obtener información sobre cómo integrar Human Resources con Microsoft Power Platform, vea [Integración de Microsoft Power Platform con aplicaciones de finanzas y operaciones](../fin-ops-core/dev-itpro/power-platform/overview.md).

## <a name="supported-geographies"></a>Geografías admitidas

Para obtener información sobre los idiomas y las zonas geográficas compatibles con Human Resources, consulte [Global por diseño: conozca los países y los idiomas compatibles](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Conceda acceso al entorno

De forma predeterminada, solo tiene acceso el administrador global que creó el entorno. Debe conceder acceso de forma explícita a los usuarios de aplicaciones adicionales. Debe agregar usuarios y asignar los roles adecuados a ellos en el entorno de Human Resources. Para obtener más información, consulte [Crear nuevos usuarios](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) y [Asignar usuarios a roles de seguridad](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>Recursos adicionales
Puede obtener más información sobre cómo usar y administrar proyectos en LCS en la infraestructura de la aplicación de finanzas y operaciones utilizando los siguientes recursos:

- [Recursos para Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Manual del usuario de Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Información general de la implementación del autoservicio](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Página principal de operaciones de movimientos de base de datos](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
