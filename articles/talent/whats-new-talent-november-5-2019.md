---
title: Novedades y cambios en Dynamics 365 Talent (5 de noviembre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 48de07178acfaccf11e0a02b2848bf24e6ccc117
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896782"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Novedades y cambios en Dynamics 365 Talent (5 de noviembre de 2019)

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2598. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="copy-a-core-hr-instance"></a>Copiar una instancia de Core HR

En la versión de esta semana, puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Talent: Core HR en un entorno de espacio retirado. Si tiene otro entorno de espacio retirado, también puede copiar la base de datos del entorno a un entorno de espacio aislado destinado. Para obtener más información, consulte:

- [Una administración de entorno más amplio](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) en el plan de la oleada 2 de la versión 2019 de Dynamics 365

- [Copiar una instancia de Core HR](hr-copy-instance.md) en la documentación de Talent

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>Los trabajos por lotes de la integración Common Data Service no se crean cuando está habilitada la integración Common Data Service (388030)

Este cambio creará trabajos por lotes para la integración de Common Data Service cuando esté habilitado.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>HcmPersonImageEntity no volverá a cambiar el tamaño de imagen de la persona cuando se carga (369469)

La versión de esta semana cambia cómo se cambia el tamaño a las imágenes para un mejor rendimiento cuando se importan a través de la gestión de datos.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>Una Fecha de disponible para la asignación de un puesto puede ser anterior a la Fecha de activación (340103)

Con este cambio, aparecerá una advertencia si selecciona una **Fecha de disponible para la asignación** que sea anterior a la **Fecha de activación** del puesto.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>No puede crear una solicitud de cambio de compensación en el autoservicio del empleado para los planes basados en pasos (376872)

Esta versión corrige un problema al solicitar cambios de compensación con el autoservicio del empleado para los planes basados en pasos. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>El código de motivo no se sincroniza con Common Data Service si la descripción tiene más de 30 caracteres, Core HR permite 60 (352682)

Con este cambio, los códigos de motivo con más de 30 caracteres se actualizarán en Common Data Service. Los cambios realizados en Common Data Service también se reflejarán en Talent.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Integración de direcciones de Talent a Finance and Operations (351961)

Esta versión corrige un problema en las direcciones que se actualizaban en Talent pero no se actualizaban en Finance and Operations. Los cambios en los bloques de direcciones ahora se actualizarán.

## <a name="coming-soon"></a>Próximamente

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.

### <a name="feature-management-workspace"></a>Espacio de trabajo Administración de características.

Las características se suman y se actualizan en cada versión. La experiencia de administración de características proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación.

Para obtener más información acerca de los cambios que se incluyen con la administración de características, consulte [Visión general de la administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
