---
title: Novedades y cambios en Dynamics 365 Talent (1 de octubre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4c8392973e7f9c55d425dbe3efb9c8858f71e345
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550168"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-1-2019"></a>Novedades y cambios en Dynamics 365 Talent (1 de octubre de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2509. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada y navegación de empleados optimizadas

Esta funcionalidad ya está disponible en todos los entornos. Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**. Seleccione **Formulario y navegación de trabajador mejorado**. Esto habilita estos cambios para todos los usuarios. Puede desactivar esta opción en cualquier momento.

Para obtener más información, consulte [Entrada y navegación de empleados optimizadas](./streamlined-employee-entry.md). Para ver un vídeo de estos cambios, consulte [Dynamics 365 for Talent 2019 resumen general de liberar oleada 2](https://aka.ms/ROGT19RW2ROV).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Puede habilitar las características de vista previa en los entornos tanto de prueba como de entorno cerrado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es Producción o Espacio aislado. Las instancias del tipo Espacio aislado permiten la prueba temprana de nuevas características. Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](./provisioning-talent.md).

### <a name="compensation-date-defaults-to-a-different-date-than-the-position-assignment-337694"></a>La fecha de compensación se predetermina a una fecha distinta que la asignación de posición (337694)

Con este cambio la fecha inicial de compensación se predetermina a la fecha inicial de la posición de asignación.

### <a name="not-able-to-end-compensation-along-with-its-position-assignment-328993"></a>No poder finalizar la compensación junto con su asignación de puesto (328993)

Con este cambio, puede finalizar la compensación cuando termina la asignación de puesto usando **Finalizar asignaciónl** en la página **Asignaciones de puesto del trabajador** con acciones del personal activas.

### <a name="bank-account-validation-requires-routing-and-account-numbers-in-all-locations-340403"></a>La validación de la cuenta bancaria requiere el enrutamiento y los números de cuenta en todas las ubicaciones (340403)

Con los cambios de esta semana, se ha agregado una nueva opción de configuración para deshabilitar la validación requerida de **Número de ruta** y **Número de cuenta**. 

### <a name="attachments-are-not-enabled-in-mss-performance-journals-for-performance-feedback-341794"></a>Los datos adjuntos no están habilitados en los diarios de rendimiento de MSS para realimentación de rendimiento (341794)

Con la versión de esta semana, los datos adjuntos se habilitan para los artículos de realimentación en la página del diario de rendimiento.

### <a name="leave-request-details-dont-sync-from-common-data-service-to-talent-369608"></a>Los detalles de la solicitud de la licencia no se sincronizan de Common Data Service a Talent (369608)

Con estos cambios, los detalles de la solicitud de la licencia que se actualizan en Common Data Service sincronización de nuevo con Talent.

### <a name="job-description-doesnt-display-for-the-job-in-the-skill-gap-analysis-page-369398"></a>La descripción del trabajo no aparece para el trabajo en la página del análisis de lagunas de aptitudes (369398)

En la versión de esta semana, la descripción mostrará al seleccionar el trabajo en la página **Análisis de lagunas de aptitudes** .

## <a name="coming-soon"></a>Próximamente

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Los empleados, los administradores y profesionales de RR. HH. podrán imprimir la evaluación del rendimiento de un empleado.
