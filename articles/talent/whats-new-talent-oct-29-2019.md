---
title: Novedades y cambios en Dynamics 365 Talent (29 de octubre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 09d53c82b4244f20d0d7f301691b01263258a32f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529693"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Novedades y cambios en Dynamics 365 Talent (29 de octubre de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2586. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>Eliminar partes sin roles estará activada solo de forma predeterminada (371233)

Al aprovisionar un nuevo entorno en Talent, **Eliminar partes si no hay roles** está activada de forma predeterminada. Al eliminar un trabajador, la parte asociada al trabajador no se quita a menos que esta configuración esté activada. Este cambio limita los registros duplicados en la libreta de direcciones global cuando necesite importar, cambia o volver a importar trabajadores.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>El borrador y solicitudes canceladas de licencia se deben permitir ser eliminado en Common Data Service (376999)

Con este cambio, ahora puede eliminar solicitudes de ausencia con un estado **Borrador** o **Cancelado** en Common Data Service.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Los valores adicionales de la lista en campos personalizados no se reflejen en Common Data Service después de hacer clic en Aplicar en el formulario Campos personalizados (379599)

Al agregar nuevos valores de la lista a un campo personalizado existente que ya se ha sincronizado con Common Data Service, estarán ahora disponibles Common Data Service después de que aplique los cambios en el formulario **Campos personalizados**.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Aplicar las listas de comprobación de incorporación en entidades jurídicas cuando haya más de un empleado (371270)

En la versión de esta semana, puede aplicar listas de comprobación a los empleados con más de un empleo en **Formulario de trabajador > Listas de comprobación**.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>Se ha quitado la característica de vista previa de inscripción abierta de beneficios

Junto con nuestro anuncio en la entrada de blog de [inversiones estratégica en la excelencia operativa de Core HR](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft ha quitado la característica de inscripción abierta de beneficios de la versión preliminar pública. La nueva funcionalidad se publicará en el futuro. El uso de producción de la función vista previa de inscripción abierta de beneficios no se admite.

## <a name="coming-soon"></a>Próximamente

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.

### <a name="feature-management-workspace"></a>Espacio de trabajo Administración de características.

Las características se suman y se actualizan en cada versión. La experiencia de administración de características proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación.

Para obtener más información acerca de los cambios que se incluyen con la administración de características, consulte [Visión general de la administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
