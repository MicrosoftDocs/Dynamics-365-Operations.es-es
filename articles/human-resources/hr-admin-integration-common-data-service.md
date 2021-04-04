---
title: Configurar integración de Dataverse
description: Puede activar o desactivar la integración entre Microsoft Dataverse y Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una tabla para ayudar a solucionar problemas de datos entre los dos entornos.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73e2d2d56da812060961c34d7cb72b71b6b2df34
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465807"
---
# <a name="configure-dataverse-integration"></a>Configurar integración de Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede activar o desactivar la integración entre Microsoft Dataverse y Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una tabla para ayudar a solucionar problemas de datos entre los dos entornos.

> [!NOTE]
> Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Cuando desactiva la integración, los usuarios pueden realizar cambios en Human Resources o Dataverse, pero esos cambios no se sincronizan entre los dos entornos.

De forma predeterminada, la integración entre Human Resources y Dataverse está desactivada.

Es posible que desee desactivar la integración en estas situaciones:

- Está completando datos a través del Marco de gestión de datos y debe importar los datos varias veces para que estén en un estado correcto.

- Hay problemas con los datos en Human Resources o Dataverse. Si desactiva la integración, puede eliminar un registro en un entorno sin eliminarlo en el otro. Cuando vuelva a activar la integración, el registro en el entorno donde no se eliminó se sincronizará con el entorno donde se eliminó. La sincronización comienza la próxima vez que se ejecuta el trabajo por lotes **La integración de Dataverse omitió la solicitud de sincronización**.

> [!WARNING]
> Cuando desactive la integración de datos, asegúrese de no editar el mismo registro en ambos entornos. Cuando vuelva a activar la integración, el registro que editó por última vez se sincronizará. Por lo tanto, si no realizó los mismos cambios en el registro en ambos entornos, puede producirse la pérdida de datos.

## <a name="access-the-dataverse-integration-page"></a>Acceder a la página de integración de Dataverse

1. En la instancia de Human Resources donde desea ver o configurar opciones para la integración con Dataverse, seleccione la ventana **Administración del sistema**.

    [![Ventana Administración del sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Seleccione la ficha **Vínculos**.

    [![Pestaña Vínculos](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Debajo de **Integraciones**, seleccione **Configuración de Dataverse**.

    [![Vínculo de configuración de Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Activar o desactivar la integración de datos entre Human Resources y Dataverse

- Para activar la integración, establezca la opción **Habilitar la integración de Dataverse** en **Sí** en la página **Integración de Microsoft Dataverse**.

    > [!NOTE]
    > Cuando active la integración, los datos se sincronizarán la próxima vez que se ejecute el trabajo por lotes **La integración de Dataverse omitió la solicitud de sincronización**. Todos los datos deben estar disponibles después de que se complete el trabajo por lotes.

- Para desactivar la integración, configure la opción como **No**.

[![Activar o desactivar la integración de Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> Recomendamos encarecidamente desactivar la integración con Dataverse al realizar tareas de migración de datos. Las grandes cargas de datos pueden afectar significativamente el rendimiento. Por ejemplo, cargar 2000 trabajadores puede llevar varias horas cuando la integración está habilitada, y menos de una hora cuando está deshabilitada. Los números proporcionados en este ejemplo son solo para fines de demostración. La cantidad exacta de tiempo que lleva importar registros puede variar mucho en función de muchos factores.

## <a name="view-data-integration-details"></a>Ver los detalles de la integración de datos

En la ficha desplegable **Administración** de la página **Integración de Microsoft Dataverse**, puede ver cómo se vinculan las filas entre Human Resources y Dataverse.

- Para ver las filas de una tabla, seleccione la tabla en el campo **Tabla de Dataverse**. La cuadrícula muestra todas las filas que están vinculadas a la tabla seleccionada.

> [!NOTE]
> No todas las tablas de Dataverse están incluidas actualmente. Solo las tablas que admiten el uso de campos personalizados aparecen en la cuadrícula. Hay nuevas tablas disponibles a través de lanzamientos continuos de Human Resources.

La cuadrícula incluye los siguientes campos:

- **Tabla de Dataverse**: nombre de la tabla en Dataverse.
- **Referencia de tabla de Dataverse**: el identificador que Dataverse usa para identificar un registro. Este valor es equivalente a un valor **RecId** de Human Resources. Puede encontrar el identificador abriendo la tabla de Dataverse en Microsoft Excel.
- **Nombre de la entidad de Human Resources**: la entidad de Human Resources que sincronizó los datos con Dataverse por última vez. La entidad puede tener el prefijo de Dataverse u otro prefijo.
- **Referencia de Human Resources**: el valor **RecId** que está asociado con el registro en Human Resources.
- **Eliminada de Dataverse**: valor que indica si la fila se ha eliminado de Dataverse.

> [!NOTE]
> Los registros de Human Resources se corresponden con filas de Dataverse.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Eliminar la asociación de un registro de Human Resources desde una fila de Dataverse

Si experimenta problemas durante la sincronización de datos entre Human Resources y Dataverse, puede resolverlos borrando el seguimiento y dejando que la tabla de seguimiento se vuelva a sincronizar. Si quita la asociación y luego cambia o elimina una fila en Dataverse, los cambios no se sincronizarán con Human Resources. Si realiza cambios en Human Resources, se crea un nuevo registro de seguimiento y la fila se actualiza en Dataverse.

- Para quitar la asociación de un registro de Human Resources con una fila de Dataverse, seleccione la tabla en el campo **Tabla de Dataverse** y active **Borrar información de seguimiento**.

[![Borrar la información de seguimiento](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Para ejecutar una sincronización completa en la tabla después de borrar el seguimiento, consulte el siguiente procedimiento.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Sincronizar una tabla entre Human Resources y Dataverse

Use este procedimiento cuando:

- Cambios de Dataverse tardan demasiado en aparecer en Human Resources.

- Debe actualizar la tabla de seguimiento después de borrar el seguimiento.

Para ejecutar una sincronización completa en una tabla entre Human Resources y Dataverse:

1. Seleccione la tabla en el campo **Tabla de Dataverse**.

2. Seleccione **Sincronizar ahora**.

[![Ejecutar una sincronización completa](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Consulte también

[Tablas de Dataverse](hr-developer-entities.md)<br>
[Configurar tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Preguntas frecuentes sobre tablas virtuales para Human Resources](hr-admin-virtual-entity-faq.md)<br>
[¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Actualizaciones de terminología](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]