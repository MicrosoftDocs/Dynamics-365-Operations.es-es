---
title: Novedades o cambios en Dynamics 365 Talent (23 de julio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2019
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
ms.search.validFrom: 2019-07-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 360574d3c8e0b349119e0987f2453a5d5be21e90
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528156"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-23-2019"></a>Novedades o cambios en Dynamics 365 Talent (23 de julio de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="pdf-renderer-for-candidate-documents"></a>Procesador PDF para los documentos del candidato

Los usuarios de Attract ahora pueden los datos adjuntos PDF de los candidatos en el visor de documentos en lugar de descargar los datos adjuntos.

### <a name="signing-up-for-attract-user-research-group"></a>Suscribirse al grupo de investigación de usuarios de Attract 

Cuando planificamos nuevas capacidades de producto o características de vista preliminar de envío, buscamos que nuestros usuarios nos ayuden a dirigir adónde vamos. Los usuarios interesados ahora pueden suscribirse y formar parte de nuestro grupo de investigación de usuarios a través del vínculo de suscripción de nuestra aplicación.

### <a name="job-approvals-appear-on-the-home-page"></a>Aprobaciones de trabajos que aparecen en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar sus aprobaciones en **Asignada a usted**, que muestra el id. de trabajo, el cargo, otros aprobadores y la fecha en la que se asignó el trabajo. Los usuarios que envían un trabajo para su aprobación pueden revisar los trabajos en **Solicitado por usted**, que muestra los aprobadores que aún deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2394.

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Soporte de entidad para campos personalizados en Common Data Service 

Con esta versión, **Calendario laboral** y el día **Calendario laboral** ahora admiten campos personalizados en Common Data Service.

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitar los tipos de baja en las solicitudes de tiempo de indisponibilidad

Las organizaciones pueden proporcionar muchos tipos diferentes de bajas a los empleados. Sin embargo, puede que no sea adecuado que los empleados envíen solicitudes de tiempo de indisponibilidad para algunos tipos de baja. En su lugar, RR. HH. puede administrar estos tipos de baja. En esta versión, puede configurar qué tipos de baja permiten que los empleados pueden enviar solicitudes de tiempo de indisponibilidad. 

## <a name="in-preview"></a>En vista previa

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Las características de la vista previa solo están habilitado en instancias de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es **Producción** o **Espacio aislado**. Las instancias del tipo **Espacio aislado** permiten la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Ver información ampliada para el rendimiento en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones, que sus empleados gestionan en conjunto. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos. 

## <a name="coming-soon"></a>Próximamente

### <a name="region-support-for-canada-and-southeast-asia"></a>Compatibilidad de la región para Canadá y el Sudeste asiático

Estamos encantados de anunciar que las regiones de Canadá y del Sudeste asiático estarán disponibles para Talent el 1 de agosto de 2019. Con este cambio, puede crear entornos en las regiones canadienses y asiática, y todos los datos de Talent se mantendrán solo dentro de estas ubicaciones. Puede crear un entorno en estas nuevas regiones seleccionando la ubicación en el diálogo Nuevo entorno y usando dicho entorno para aprovisionar Talent en LCS como se describe aquí [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

La migración de datos de proyectos existentes de otras regiones a las regiones canadienses y asiática no se admite. Solo los nuevos proyectos pueden aprovisionarse en estas nuevas regiones compatibles.


[!INCLUDE[footer-include](../includes/footer-banner.md)]