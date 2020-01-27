---
title: Novedades o cambios en Dynamics 365 Talent (30 de julio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96937d48e0d1003adbc5f7fedc89b2686ace01cd
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899044"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-30-2019"></a>Novedades o cambios en Dynamics 365 Talent (30 de julio de 2019)

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2409.


### <a name="region-support-for-canada-and-southeast-asia"></a>Compatibilidad de la región para Canadá y el Sudeste asiático

Estamos encantados de anunciar que las regiones de Canadá y del Sudeste asiático estarán disponibles para Talent el 1 de agosto de 2019. Con este cambio, puede crear entornos en las regiones canadienses y asiática, y todos los datos de Talent se mantendrán solo dentro de estas ubicaciones. Puede crear un entorno en estas nuevas regiones seleccionando la ubicación en el diálogo Nuevo entorno y usando dicho entorno para aprovisionar Talent en LCS como se describe en [Aprovisionar Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

La migración de datos de proyectos existentes de otras regiones a las regiones canadienses y asiática no se admite. Solo los nuevos proyectos pueden aprovisionarse en estas nuevas regiones compatibles.

### <a name="new-active-positions-list-page"></a>Nueva página de lista de puestos activa

Las opciones para las listas basadas en puestos ahora incluyen: **Todos los puestos**, **Puestos activos**, **Vacantes**, y **Puestos inactivos**. La nueva página de lista **Puestos activos** sólo muestra aquellos puestos, vacantes o cubiertos, que están activos en la fecha actual. 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a>Permitir que los participantes del curso se agreguen a cursos abiertos

Los cambios de esta semana corrigen un problema que hacía que sólo los informes directos se pudiesen registrar para los cursos abiertos.

### <a name="fte-analysis-displaying-incorrect-fte-number"></a>Análisis de FTE muestra un número de FTE incorrecto

**Análisis de FTE** se ha corregido en la pestaña **Análisis** de **Administración de personal**.

### <a name="final-comments-label-translation"></a>Traducción de la etiqueta de comentarios finales

La etiqueta **Comentarios finales** ahora está traducida en la pantalla de revisión.

## <a name="in-preview"></a>En vista previa

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Las características de la vista previa solo están habilitado en instancias de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es **Producción** o **Espacio aislado**. Las instancias del tipo **Espacio aislado** permiten la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Ver información ampliada para el rendimiento en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos.
