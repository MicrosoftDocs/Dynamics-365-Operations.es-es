---
title: Códigos de error para la comprobación de estado de la asignación de la tabla
description: Este tema describe los códigos de error para la comprobación del estado de la asignación de la tabla.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 4f0b92a6bc6c051a6bb24b49d3280ca5ecea3625
ms.sourcegitcommit: c4500b626667185643b3a2e7fc3a004d42198d07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2021
ms.locfileid: "7725084"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Códigos de error para la comprobación de estado de la asignación de la tabla

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe los códigos de error para la comprobación del estado de la asignación de la tabla.

## <a name="error-100"></a>Error 100

El mensaje de error es "Versión mínima requerida de la plataforma Finance and Operations es PU 43 para ejecutar la recomendaciones de Finance and Operations".

La característica requiere actualizaciones de plataforma para la versión 10.0.19 o posterior de las aplicaciones de Finance and Operations.

## <a name="error-400"></a>Error 400

El mensaje de error es "No se encontraron datos de registro de eventos comerciales para la entidad \{Finance and Operations UniqueEntityName\}, lo que significa que la asignación no se está ejecutando o toda la asignación de campo es unidireccional".

## <a name="error-500"></a>Error 500

El mensaje de error es "No se encontraron configuraciones de proyecto para el proyecto \{nombre del proyecto\}. Esto podría deberse a que el proyecto no está habilitado o que todas las asignaciones de campo son unidireccionales desde Customer Engagement hasta Finance and Operations".

Compruebe las asignaciones para la asignación de la tabla. Si son unidireccionales desde las aplicaciones de Customer Engagement hasta las aplicaciones de Finance and Operations, no se genera tráfico para la sincronización en vivo desde las aplicaciones de Finance and Operations a Dataverse.

## <a name="error-900"></a>Error 900

El mensaje de error es "Formato de filtro de origen no válido \{sourceFilter\} para la entidad \{Finance and Operations UniqueEntityName\}".

El filtro de origen que se especifica en la asignación de la tabla para las aplicaciones de Finance and Operations no es sintácticamente correcto. Para validar los criterios de filtrado, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Error 1000

El mensaje de error es "La consulta de la entidad \{Finance and Operations UniqueEntityName\} usada para la sincronización en vivo de doble escritura es \{Finance and Operations EntityFilterQueryString\}. Los registros que cumplan con los criterios de consulta se recopilarán para la sincronización en vivo".

La consulta de entidad que se recuperó es la consulta SQL de respaldo para la entidad. Compruebe si hay uniones internas o filtros en la consulta que determinen los datos empresariales que se recopilan para la sincronización en vivo. Las uniones internas y los filtros son condiciones obligatorias que deben cumplirse para cada registro que se selecciona para la sincronización en vivo de escritura dual.

## <a name="error-1300"></a>Error 1300

El mensaje de error es "Los campos virtuales \{s.EntityFieldName\} para la entidad \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} no se pueden rastrear para escritura dual".

Los campos virtuales de las tablas de Finance and Operations no están habilitados para el seguimiento. La sincronización en vivo puede sincronizar los datos, pero no podrá recoger los cambios que se realizan en las columnas.

## <a name="error-1500"></a>Error 1500

El mensaje de error es: "Debe haber al menos un campo asignado a un campo que no sea de búsqueda en Customer Engagement para permitir el seguimiento en el origen de datos \{datasource.DataSourceName\}".

El origen de datos de la entidad no tiene ningún campo asignado para escritura dual. Los cambios en la tabla subyacente no se rastrearán para escritura dual.

## <a name="error-1600"></a>Error 1600

El mensaje de error es "El origen de datos: \{datasource.DataSourceName\} para la entidad \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} tiene un rango. Solo los registros que satisfacen la condición de rango se recogen para la salida".

Las entidades en las aplicaciones de Finance and Operations pueden tener orígenes de datos donde los rangos de filtro están habilitados. Estos rangos definen los registros que se recogen como parte de la sincronización en vivo. Si se omiten algunos registros de aplicaciones de Finance and Operations a Dataverse, compruebe si los registros cumplen los criterios de rango de la entidad. Una forma sencilla de realizar esta comprobación es ejecutar una consulta SQL que se parezca al siguiente ejemplo.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Error 1700

El mensaje de error es "Se realiza un seguimiento para la tabla: \{datasourceTable.Key.subscribedTableName\} para la entidad \{datasourceTable.Key.entityName\} para la entidad \{origTableToEntityMaps.EntityName\}. Las mismas tablas a las que se hace un seguimiento para múltiples entidades pueden afectar el rendimiento del sistema para las transacciones de sincronización en vivo".

Si varias entidades realizan el seguimiento de la misma tabla, cualquier cambio en la tabla desencadenará una evaluación de escritura dual para las entidades vinculadas. Aunque las cláusulas de filtro enviarán solo los registros válidos, la evaluación puede causar un problema de rendimiento si hay consultas de larga duración o planes de consultas no optimizados. Es posible que este problema no se pueda evitar desde la perspectiva empresarial. Sin embargo, si hay muchas tablas que se cruzan en varias entidades, debería tener en cuenta la posibilidad de simplificar la entidad o comprobar las optimizaciones para las consultas de entidad.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
