---
title: Actualizar proceso
description: Microsoft Dynamics 365 Human Resources es un verdadero software como servicio (SaaS) que proporciona actualizaciones continuas y sin contacto del servicio para la aplicación y cambios de plataforma.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2466c53885340991aeeb0a07af83517473b332b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053644"
---
# <a name="update-process"></a>Actualizar proceso

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Microsoft Dynamics 365 Human Resources es un verdadero software como servicio (SaaS) que proporciona actualizaciones continuas y sin contacto del servicio. Estas actualizaciones contienen cambios tanto en la aplicación como en la plataforma que a menudo proporcionan mejoras críticas para el servicio, incluidas actualizaciones regulatorias.

## <a name="update-policy"></a>Directiva de actualización

Las actualizaciones se lanzan en una cadencia regular en todos los entornos. Human Resources es compatible según la [directiva de ciclo de vida de Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), que proporciona directrices coherentes y predecibles para la disponibilidad de la asistencia técnica.

## <a name="release-cadence"></a>Cadencia de lanzamiento 

Las actualizaciones de Human Resources se aplican a todos los entornos automáticamente. Human Resources proporciona dos tipos de lanzamientos:

- **Actualizaciones de servicio**: las actualizaciones se producen cada dos semanas e incluyen correcciones de errores y nuevas características. Las actualizaciones de servicio también incluyen actualizaciones de plataforma aplicables cuando se lanzan. Para tener una idea de cuándo se lanzan las actualizaciones de la Plataforma, vea [Tabla 3: Lanzamientos de plataforma](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases). Las actualizaciones quincenales tienen una implementación global por etapas en todas las regiones. Para obtener más información sobre las actualizaciones quincenales, vea [Novedades o cambios en Dynamics 365 Human Resources](hr-admin-whats-new.md).

    Todos los centros de datos compatibles se actualizan cada dos semanas, a menos que se indique lo contrario. Las regiones de EE. UU., Australia, Europa, Reino Unido, Asia y Canadá se incluyen en las actualizaciones quincenales. 

- **Actualizaciones de soluciones de Dataverse**: estas actualizaciones se producen aproximadamente cada seis semanas, según sea necesario. Incluyen nuevas entidades y cambios a entidades existentes en Dataverse. Estas actualizaciones se lanzan a las mismas regiones que las actualizaciones quincenales, y tardan aproximadamente seis semanas en replicarse en todos los centros de datos. Las actualizaciones de la solución pueden o no alinearse con las actualizaciones quincenales del servicio.

> [!NOTE]
> Las actualizaciones de la solución están disponibles en todos los centros de datos una vez que se lanzan. Si no desea esperar a que las actualizaciones se repliquen automáticamente, puede aplicarlas manualmente en cualquier entorno en cualquier centro de datos.

Cuando es necesario, Human Resources también proporciona los siguientes tipos de soluciones:

- **Revisión (hotfix)**: correcciones de errores que pueden ocurrir con o sin una versión de actualización de servicio quincenal

- **Corrección de emergencia**: las revisiones proactivas y reactivas que son de naturaleza independiente, pueden incluir solo cambios de configuración o código para resolver problemas del sitio en vivo, y pueden ocurrir aparte de una versión de actualización de servicio quincenal

Las versiones se revisan, prueban y validan en un entorno interno. Después de que las compilaciones se cierran, se implementan en producción.

## <a name="release-cadence-exceptions-in-2021"></a>Liberar excepciones de cadencia en 2021

Para tener en cuenta los días festivos, el calendario de lanzamientos para noviembre y diciembre de 2021 es el siguiente:

- Lanzamiento de noviembre: 1 de noviembre - 14 de noviembre
- Lanzamiento de diciembre: 29 de noviembre - 12 de diciembre
 
La cadencia de lanzamiento de dos semanas se reanudará como de costumbre el 10 de enero de 2022.

## <a name="communications"></a>Comunicaciones

Puede averiguar qué se está trabajando para Recursos Humanos y qué hemos publicado en las siguientes ubicaciones:

- [Hoja de ruta de Dynamics 365 Human Resources](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Planes de la versión de Dynamics 365](/dynamics365/release-plans/)

- [Novedades y cambios en Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Búsqueda de problemas en Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (solo para errores relacionados con la plataforma)

- [Blog de Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Comunidad de Human Resources en Yammer](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Vista previa de características en un entorno sandbox

Puede validar las funciones de vista previa en un entorno de espacio aislado antes de habilitarlas en su entorno de producción. Para obtener más información acerca de la activación nuevas características, consulte [Visión general de la Administración de características](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Todas las características nuevas siguen en versión preliminar durante al menos 30 días como mínimo, y normalmente 30-60 días. Las características más importantes están disponibles en octubre y abril de cada año tras el periodo de prueba preliminar. En cuanto vea características nuevas en el espacio de trabajo Administración de características, puede activarlas. Algunas características pueden estar activadas de forma predeterminada.

A veces, una característica entera estará activada de forma predeterminada y no se puede desactivar (por ejemplo, el espacio de trabajo Administración de características).

Cuando una característica esté disponible, se puede activar y desactivar en los entornos de producción. El espacio de trabajo Administración de características indica cuando una característica de versión preliminar pasará a ser obligatoria. Esta fecha es un el 1 de octubre o el 1 de abril para que se corresponda con los planes semestrales de publicación. No pueden desactivar características obligatorias. Hasta que llegue a ser obligatoria, se puede activar y desactivar una característica en todos los entornos.

Recomendamos encarecidamente obtener una vista previa de las características en un entorno de prueba o espacio aislado. Es mejor crear una copia de su entorno de producción o base de datos actual en un entorno de espacio aislado para que pueda obtener la experiencia completa de las nuevas funciones con sus datos.

Para obtener más información sobre el aprovisionamiento de un entorno de espacio aislado, vea [Aprovisionar un proyecto de Human Resources](hr-admin-setup-provision.md). Para eliminar un entorno de prueba, vea [Eliminar una instancia](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Informar de errores

Mientras prueba las funciones de vista previa o prueba nuevas capacidades, puede encontrar elementos que no funcionan como se esperaba. Informe sobre cualquier error a través del [soporte técnico de Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Consulte también

[Planes de la versión de Dynamics 365 y Power Platform](/dynamics365/release-plans)</br>
[Novedades y cambios en Dynamics 365 Human Resources](hr-admin-whats-new.md)</br>
[Directiva del ciclo de vida del software](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]