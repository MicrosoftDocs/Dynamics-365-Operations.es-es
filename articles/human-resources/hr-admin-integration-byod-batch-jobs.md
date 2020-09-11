---
title: Optimizar los trabajos por lotes programados de BYOD
description: Este tema explica cómo optimizar el rendimiento cuando utiliza la función Traer la propia base de datos (BYOD) con Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: d08762ff40b4da8264bd5bc4a1c16fd2afc4d610
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712626"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Optimizar los trabajos por lotes programados de BYOD

Este tema explica cómo optimizar el rendimiento cuando utiliza la función Traer la propia base de datos (BYOD). Para obtener más información sobre BYOD, consulte [Traer la propia base de datos (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json).

## <a name="performance-considerations-for-data-export"></a>Consideraciones de rendimiento para la exportación de datos

Una vez publicadas las entidades en la base de datos de destino, puede utilizar la función Exportar del espacio de trabajo **Administración de datos** para mover datos. La función Exportar le permite definir un trabajo de movimiento de datos que contiene una o más entidades. Para obtener más información sobre cómo usar la administración de datos para exportar datos, consulte [Resumen de trabajos de importación y exportación de datos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json).

Puedes usar la página **Exportar** para exportar datos a diferentes formatos de datos de destino, como un archivo de valores separados por comas (CSV). Esta página también admite bases de datos SQL como otro destino.

Puede crear un proyecto de datos que tenga varias entidades y usar un trabajo por lotes para programar la ejecución de ese proyecto de datos. Si selecciona la opción **Exportar en lote**, puede programar el trabajo de exportación de datos para que se ejecute periódicamente.

Para ayudar a preservar la confiabilidad general de la exportación BYOD, debe tener cuidado al agregar varias entidades a un proyecto de exportación. Cuando esté determinando la cantidad de entidades que agregará al mismo proyecto, considere los siguientes parámetros:

- La complejidad de las entidades
- El volumen de datos esperado por entidad
- El tiempo total que será necesario para completar la exportación a nivel de trabajo

Para obtener el mejor rendimiento, evite agregar cientos de entidades a un solo proyecto. Le recomendamos que cree varios trabajos, cada uno de los cuales contenga menos entidades.

## <a name="scheduling-byod-batch-jobs"></a>Programación de trabajos por lotes de BYOD

Para ayudar a reducir el impacto en los usuarios de Microsoft Dynamics 365 Human Resources, ejecute trabajos por lotes BYOD por la noche o fuera de horario. Asegúrese de verificar la zona horaria para los trabajos por lotes recurrentes. Algunos trabajos por lotes pueden usar la hora estándar del Pacífico (PST).

Para ayudar a evitar problemas de rendimiento, considere los siguientes factores cuando configure la frecuencia de programación para los trabajos por lotes BYOD:

- El tiempo necesario para completar cada trabajo por lotes
- La necesidad empresarial de los datos en BYOD

Establezca la frecuencia de cada trabajo por lotes en un valor que garantice que el trabajo se pueda completar mucho antes de su siguiente tiempo de ejecución programado. Evite ejecutar varios trabajos en paralelo, ya que este enfoque puede afectar negativamente el desempeño de Human Resources.

Para obtener el mejor rendimiento, utilice siempre la opción **Exportar en lote** de la página **Exportar** para programar trabajos por lotes BYOD. Evite programar exportaciones recurrentes en **Gestionar \> Administrar trabajos de datos recurrentes**.

## <a name="incremental-export"></a>Exportación incremental

Cuando agrega una entidad para la exportación de datos, puede realizar una inserción incremental (exportación) o una inserción completa. Una inserción completa elimina todos los registros existentes de una entidad en la base de datos BYOD. Si luego inserta el conjunto actual de registros de la entidad Human Resources.

Para hacer una inserción incremental, debe activar el seguimiento de cambios para cada entidad en la página **Entidades**. Para obtener más información, consulte [Habilitar el seguimiento de cambios para entidades](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

Si selecciona una inserción incremental, la primera inserción es siempre una inserción completa. SQL rastrea los cambios desde esta primera inserción completa. Cuando se inserta un nuevo registro, o cuando se actualiza o elimina un registro, el cambio se refleja en la entidad de destino.

## <a name="time-outs"></a>Tiempos de espera

Estos son los tiempos de espera predeterminados para las exportaciones BYOD:

- Diez minutos para operaciones de truncamiento
- Una hora para operaciones de inserción masiva

Cuando los volúmenes son altos, esta configuración de tiempo de espera puede no ser suficiente. Para actualizarlos, vaya a **Gestión de datos \> Parámetros del marco \> Traer la propia base de datos**. Estos tiempos de espera son específicos de la empresa y deben establecerse por separado para cada empresa.

## <a name="known-limitations"></a>Limitaciones conocidas

La característica BYOD tiene las siguientes limitaciones:

- No debería haber bloqueos activos en su base de datos durante la sincronización. Los bloqueos activos pueden causar escrituras lentas o incluso errores en la exportación de datos a su base de datos SQL de Azure.
- No puede exportar entidades compuestas a su propia base de datos. Actualmente, las entidades compuestas no son compatibles. Debe exportar las entidades individuales que componen la entidad compuesta. Sin embargo, puede exportar ambas entidades en el mismo proyecto de datos.
- Las entidades que no tienen claves únicas no se pueden exportar mediante inserción incremental. Es posible que se enfrente a esta limitación, especialmente cuando intente exportar de forma incremental registros de algunas entidades listas para usar. Debido a que estas entidades fueron diseñadas para permitir la importación de datos, no tienen una clave única.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="incremental-push-doesnt-work-correctly"></a>la inserción incremental no funciona correctamente

**Problema:** cuando se produce una inserción completa para una entidad, ve un gran conjunto de registros en BYOD cuando usa una declaración **Seleccionar**. Sin embargo, cuando realiza una inserción incremental, solo ve unos pocos registros en BYOD. Parece que la inserción incremental eliminó todos los registros y agregó solo los registros modificados en BYOD.

**Solución:** es posible que las tablas de seguimiento de cambios de SQL no estén en el estado esperado. En casos de este tipo, le recomendamos que desactive el seguimiento de cambios para la entidad y luego lo vuelva a activar. Para obtener más información, consulte [Habilitar el seguimiento de cambios para entidades](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

## <a name="see-also"></a>Consulte también

[Visión general de la administración de datos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages?toc=/dynamics365/human-resources/toc.json)<br>
[Usar su propia base de datos (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json)<br>
[Visión general de los trabajos de exportación e importación de datos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json)<br>
[Habilitar seguimiento de cambios para entidades](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json)
