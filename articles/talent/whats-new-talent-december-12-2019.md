---
title: Novedades y cambios en Dynamics 365 Talent (10 de diciembre de 2019)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 18f86f5d87b780d5d4ffc83330d389077987dda6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528180"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Novedades y cambios en Dynamics 365 Talent (10 de diciembre de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2660. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Espacio de trabajo Administración de características.

El espacio de trabajo **Administración de características** proporciona una lista de características entregadas en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación. Para obtener más información acerca de la administración de características, consulte [Visión general de la Administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todas las características nuevas siguen en versión preliminar durante al menos 30 días como mínimo, y normalmente 30-60 días. Las características más importantes están disponibles en octubre y abril de cada año tras el periodo de prueba preliminar. En cuanto vea características nuevas en el espacio de trabajo **Administración de características**, puede activarlas. Algunas características pueden estar activadas de forma predeterminada.
 
A veces, una característica entera estará activada de forma predeterminada y no se puede desactivar (por ejemplo, el espacio de trabajo **Administración de características**).
 
Cuando una característica esté disponible, se puede activar y desactivar en los entornos de producción. El espacio de trabajo **Administración de características** indica cuando una característica de versión preliminar pasará a ser obligatoria. Esta fecha es un el 1 de octubre o el 1 de abril para que se corresponda con los planes semestrales de publicación. No pueden desactivar características obligatorias. Hasta que llegue a ser obligatoria, se puede activar y desactivar una característica en todos los entornos.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>El formulario de trabajador simplificado se ha movido al espacio de trabajo Administración de características (390583)

Con este cambio, el formulario de trabajador simplificado se puede habilitar en el espacio de trabajo **Administración de características**. Esta característica se ha movido del formulario **Parámetros del sistema** en **Administración del sistema**.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>Evitar la escritura de registros HcmWorkerPayrollInfo sin un valor de trabajador (394526)

Con esta versión ya no se crean los registros **HcmWorkerPayrollInfo** sin una referencia de trabajador en este escenario. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>El registro de mensajes asociado a la acción no se rellena si la acción no se completa (374007)

Esta versión incluye un cambio para rellenar el registro de mensajes de acción cuando se produce un error de una acción en determinados escenarios. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Creación de trabajo por lotes de integración de Common Data Service (388030)

Con este cambio, los trabajos por lotes para la integración de Common Data Service se crean cuando el servicio está habilitado.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Los valores adicionales de la lista de selección no se reflejen en Common Data Service después de hacer clic en Aplicar en el formulario de campos personalizados (379599)

Con este cambio, los nuevos valores de la lista de selección introducidos en Talent se sincronizan con Common Data Service al aplicar los cambios.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>La actualización a Common Data Service para la entidad Transacción bancaria de bajas se convierte en una inserción en lado de Talent (352938)

Este cambio corrige un problema consistente en que una actualización de una transacción bancaria de bajas crea un un registro nuevo en Talent.

## <a name="in-preview"></a>En vista previa

Las características de vista previa solo están disponibles en entornos de **Espacio aislado**.

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.



[!INCLUDE[footer-include](../includes/footer-banner.md)]