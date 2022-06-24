---
title: Códigos de error para la comprobación de estado de la asignación de la tabla
description: Este artículo describe los códigos de error para la comprobación del estado de la asignación de la tabla.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 3ae78077fc716311c38620b14665af3983a44c2d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884094"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Códigos de error para la comprobación de estado de la asignación de la tabla

[!include [banner](../../includes/banner.md)]



Este artículo describe los códigos de error para la comprobación del estado de la asignación de la tabla.

## <a name="error-100"></a>Error 100

El mensaje de error es "Versión mínima requerida de la plataforma de Finanzas y operaciones es PU 43 para ejecutar la recomendaciones de Finanzas y operaciones".

La característica requiere actualizaciones de plataforma para la versión 10.0.19 o posterior de las aplicaciones de Finanzas y operaciones.

## <a name="error-400"></a>Error 400

El mensaje de error es "No se encontraron datos de registro de eventos comerciales para la entidad \{UniqueEntityName de Finanzas y operaciones\}, lo que significa que la asignación no se está ejecutando o toda la asignación de campo es unidireccional".

## <a name="error-500"></a>Error 500

El mensaje de error es "No se encontraron configuraciones de proyecto para el proyecto \{nombre del proyecto\}. Esto podría deberse a que el proyecto no está habilitado o que todas las asignaciones de campo son unidireccionales desde Customer Engagement hasta Finanzas y operaciones".

Compruebe las asignaciones para la asignación de la tabla. Si son unidireccionales desde las aplicaciones de Customer Engagement hasta las aplicaciones de Finanzas y operaciones, no se genera tráfico para la sincronización en vivo desde las aplicaciones de Finanzas y operaciones a Dataverse.

## <a name="error-900"></a>Error 900

El mensaje de error es "Formato de filtro de origen no válido \{sourceFilter\} para la entidad \{UniqueEntityName de Finanzas y operaciones\}".

El filtro de origen que se especifica en la asignación de la tabla para las aplicaciones de Finanzas y operaciones no es sintácticamente correcto. Para validar los criterios de filtrado, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Error 1000

El mensaje de error es "La consulta de la entidad \{UniqueEntityName de Finanzas y operaciones\} usada para la sincronización en vivo de doble escritura es \{EntityFilterQueryString de Finanzas y operaciones\}. Los registros que cumplan con los criterios de consulta se recopilarán para la sincronización en vivo".

La consulta de entidad que se recuperó es la consulta SQL de respaldo para la entidad. Compruebe si hay uniones internas o filtros en la consulta que determinen los datos empresariales que se recopilan para la sincronización en vivo. Las uniones internas y los filtros son condiciones obligatorias que deben cumplirse para cada registro que se selecciona para la sincronización en vivo de escritura dual.

## <a name="error-1300"></a>Error 1300

El mensaje de error es "Los campos virtuales \{s.EntityFieldName\} para la entidad \{EntityMetadata.EntityProperties.LogicalEntityName de Finanzas y operaciones\} no se pueden rastrear para escritura dual".

Los campos virtuales de las tablas de Finanzas y operaciones no están habilitados para el seguimiento. La sincronización en vivo puede sincronizar los datos, pero no podrá recoger los cambios que se realizan en las columnas.

## <a name="error-1500"></a>Error 1500

El mensaje de error es: "Debe haber al menos un campo asignado a un campo que no sea de búsqueda en Customer Engagement para permitir el seguimiento en el origen de datos \{datasource.DataSourceName\}".

El origen de datos de la entidad no tiene ningún campo asignado para escritura dual. Los cambios en la tabla subyacente no se rastrearán para escritura dual.

## <a name="error-1600"></a>Error 1600

El mensaje de error es "El origen de datos: \{datasource.DataSourceName\} para la entidad \{EntityMetadata.EntityProperties.LogicalEntityName de Finanzas y operaciones\} tiene un rango. Solo los registros que satisfacen la condición de rango se recogen para la salida".

Las entidades en las aplicaciones de Finanzas y operaciones pueden tener orígenes de datos donde los rangos de filtro están habilitados. Estos rangos definen los registros que se recogen como parte de la sincronización en vivo. Si se omiten algunos registros de aplicaciones de Finanzas y operaciones a Dataverse, compruebe si los registros cumplen los criterios de rango de la entidad. Una forma sencilla de realizar esta comprobación es ejecutar una consulta SQL que se parezca al siguiente ejemplo.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Error 1700

El mensaje de error es "Se realiza un seguimiento para la tabla: \{datasourceTable.Key.subscribedTableName\} para la entidad \{datasourceTable.Key.entityName\} para la entidad \{origTableToEntityMaps.EntityName\}. Las mismas tablas a las que se hace un seguimiento para múltiples entidades pueden afectar el rendimiento del sistema para las transacciones de sincronización en vivo".

Si varias entidades realizan el seguimiento de la misma tabla, cualquier cambio en la tabla desencadenará una evaluación de escritura dual para las entidades vinculadas. Aunque las cláusulas de filtro enviarán solo los registros válidos, la evaluación puede causar un problema de rendimiento si hay consultas de larga duración o planes de consultas no optimizados. Es posible que este problema no se pueda evitar desde la perspectiva empresarial. Sin embargo, si hay muchas tablas que se cruzan en varias entidades, debería tener en cuenta la posibilidad de simplificar la entidad o comprobar las optimizaciones para las consultas de entidad.

## <a name="error-1800"></a>Error 1800
El mensaje de error es: "Datasource : {} for entity CustCustomerV3Entity incluye un valor de rango. Modificaciones de registros entrantes de Dataverse a finanzas y operaciones puede verse afectado por valores de rango en la entidad. Pruebe las actualizaciones de registro de Dataverse a finanzas y operaciones con registros que no coincidan con los criterios de filtro para validar su configuración".

Si hay un rango especificado en la entidad en las aplicaciones de finanzas y operaciones, entonces la sincronización entrante de Dataverse a las aplicaciones de finanzas y operaciones se debe probar el comportamiento de actualización en los registros que no coinciden con este criterio de rango. La entidad trata cualquier registro que no coincida con el rango como una operación de inserción. Si hay un registro existente en la tabla subyacente, la inserción fallará. Le recomendamos que pruebe este caso de uso para todos los escenarios antes de implementarlo en producción.

## <a name="error-1900"></a>Error 1900
El mensaje de error es: "Entidad: tiene {} orígenes de datos que no se están siguiento para escritura dual saliente. Esto puede afectar el rendimiento de las consultas de sincronización en vivo. Remodele la entidad en finanzas y operaciones para eliminar orígenes de datos y tablas no utilizadas o implemente getEntityRecordIdsImpactedByTableChange para optimizar las consultas en tiempo de ejecución".

Si hay muchos orígenes de datos que no se utilizan para el seguimiento en la sincronización en vivo real de las aplicaciones de finanzas y operaciones, existe la posibilidad de que el rendimiento de la entidad pueda afectar la sincronización en vivo. Para optimizar las tablas rastreadas, use el método getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Error 5000
El mensaje de error es: "Los complementos sincrónicos están registrados para eventos de administración de datos para cuentas de entidades. Estos pueden afectar el rendimiento de importación de la sincronización inicial y la sincronización en vivo en Dataverse. Para obtener el mejor rendimiento, cambie los complementos a procesamiento asincrónicos. Lista de complementos registrados {}."

Los complementos asincrónicos en una entidad de Dataverse pueden afectar la sincronización en vivo y el rendimiento de la sincronización inicial a medida que aumenta la carga de transacciones. El enfoque recomendado es desactivar los complementos o hacer que estos complementos sean asincrónicos si se enfrenta tiempos de carga lentos en la sincronización inicial o la sincronización en vivo para una entidad en particular.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
