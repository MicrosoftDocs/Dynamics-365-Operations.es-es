---
title: Novedades y cambios en Dynamics 365 for Talent (27 de agosto de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8965636e539345be5ef0ad591f7017938efd322d
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529813"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Novedades y cambios en Dynamics 365 for Talent (27 de agosto de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2447. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Las características de la vista previa solo están habilitado en instancias de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es Producción o Espacio aislado. Las instancias del tipo Espacio aislado permiten la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de Producción. Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Ver información ampliada para el rendimiento en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>Eliminar entidades jurídicas no se permite si existen empleados dentro de la empresa (339849)

Con este cambio, no podrá quitar o eliminar empresas si existen empleados y otros datos relacionados para la entidad jurídica.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>Los análisis de inteligencia empresarial de la gestión de compensación no coinciden en el espacio de trabajo de la compensación (322493)

En esta versión, los análisis de compensación se han ajustado para reflejar de forma precisa los planes asignados a los empleados.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>El marcador de posición del flujo de trabajo %company% muestra DAT cuando se contratan empleados con el flujo de trabajo (343905)

Con esta versión, el marcador de posición de la la empresa presenta la entidad jurídica asociada al empleo del nuevo empleado.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>La entidad CDSJobPosition muestra un error cuando la está configurada la validez hasta la fecha (349387)

En esta versión, los orígenes de datos **Detalle del puesto** y **Duración del puesto** en la entidad **CDSJobPosition** permiten ediciones de Common Data Service en los campos **Fecha efectiva**. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>Para el cese del empleado, el último día trabajado se rellena en la fecha de finalización de asignación (332496)

En este cambio ahora la **Fecha final de la asignación** del puesto toma como valor predeterminado **Fecha final del empleo**. Puede cambiar estos valores predeterminados a medida que especifica datos.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>Las entidades jurídicas no están limitadas en la contratación (338871)
 
Este cambio limita el proceso de contratación para mostrar sólo las entidades jurídicas a las que el usuario tiene acceso.  

## <a name="in-preview"></a>En vista previa

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada y navegación de empleados optimizadas

Esta funcionalidad ya está disponible en los entornos de espacio aislado y prueba. Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**. Seleccione **Formulario y navegación de trabajador mejorado**. Esto habilita estos cambios para todos los usuarios. Puede desactivar esta opción en cualquier momento.

Para obtener más información, consulte [Entrada y navegación de empleados optimizadas](./streamlined-employee-entry.md).

## <a name="coming-soon"></a>Próximamente

### <a name="platform-update-29"></a>Actualización 29 de la plataforma

Para obtener más información acerca de la Platform update 29, consulte [Características de vista previa en Dynamics 365 for Finance and Operations platform update 29 (octubre de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).


[!INCLUDE[footer-include](../includes/footer-banner.md)]