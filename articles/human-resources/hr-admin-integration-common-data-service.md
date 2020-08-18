---
title: Configurar integración de Common Data Service
description: Puede activar o desactivar la integración entre Common Data Service y Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una entidad para ayudar a solucionar problemas de datos entre los dos entornos.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
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
ms.openlocfilehash: 8cbead2961c4576a5394080aae2fec109bce3f10
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621313"
---
# <a name="configure-common-data-service-integration"></a>Configurar integración de Common Data Service

Puede activar o desactivar la integración entre Common Data Service y Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una entidad para ayudar a solucionar problemas de datos entre los dos entornos.

Cuando desactiva la integración, los usuarios pueden realizar cambios en Human Resources o Common Data Service, pero esos cambios no se sincronizan entre los dos entornos.

De forma predeterminada, la integración entre Human Resources y Common Data Service está desactivada.

Es posible que desee desactivar la integración en estas situaciones:

- Está completando datos a través del Marco de gestión de datos y debe importar los datos varias veces para que estén en un estado correcto.

- Hay problemas con los datos en Human Resources o Common Data Service. Si desactiva la integración, puede eliminar un registro en un entorno sin eliminarlo en el otro. Cuando vuelva a activar la integración, el registro en el entorno donde no se eliminó se sincronizará con el entorno donde se eliminó. La sincronización comienza la próxima vez que se ejecuta el trabajo por lotes **La integración de Common Data Service omitió la solicitud de sincronización**.

> [!WARNING]
> Cuando desactive la integración de datos, asegúrese de no editar el mismo registro en ambos entornos. Cuando vuelva a activar la integración, el registro que editó por última vez se sincronizará. Por lo tanto, si no realizó los mismos cambios en el registro en ambos entornos, puede producirse la pérdida de datos.

## <a name="access-the-common-data-service-integration-page"></a>Acceder a la página de integración de Common Data Service

1. En la instancia de Human Resources donde desea ver o configurar opciones para la integración con Common Data Service, seleccione la ventana **Administración del sistema**.

    [![Ventana Administración del sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Seleccione la ficha **Vínculos**.

    [![Pestaña Vínculos](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Debajo de **Integraciones**, seleccione **Configuración de Common Data Service**.

    [![Vínculo de configuración de Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a>Activar o desactivar la integración de datos entre Human Resources y Common Data Service

- Para activar la integración, establezca la opción **Permitir la integración con Common Data Service** en **Sí**.

    > [!NOTE]
    > Cuando active la integración, los datos se sincronizarán la próxima vez que se ejecute el trabajo por lotes **La integración de Common Data Service omitió la solicitud de sincronización**. Todos los datos deben estar disponibles después de que se complete el trabajo por lotes.

- Para desactivar la integración, configure la opción como **No**.

[![Activar o desactivar la integración de Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)

> [!WARNING]
> Recomendamos encarecidamente desactivar la integración con Common Data Service al realizar tareas de migración de datos. Las grandes cargas de datos pueden afectar significativamente el rendimiento. Por ejemplo, cargar 2000 trabajadores puede llevar varias horas cuando la integración está habilitada, y menos de una hora cuando está deshabilitada. Los números proporcionados en este ejemplo son solo para fines de demostración. La cantidad exacta de tiempo que lleva importar registros puede variar mucho en función de muchos factores.

## <a name="view-data-integration-details"></a>Ver los detalles de la integración de datos

En la ficha desplegable **Administración** de la página **Integración de Common Data Service**, puede ver cómo se vinculan los registros entre Human Resources y Common Data Service.

- Para ver los registros de una entidad, seleccione la entidad en el campo **Nombre de entidad CDS**. La cuadrícula muestra todos los registros que están vinculados a la entidad seleccionada.

[![Ver los registros de una entidad](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)

> [!NOTE]
> No todas las entidades de Common Data Service están incluidas actualmente. Solo las entidades que admiten el uso de campos personalizados aparecen en la cuadrícula. Hay nuevas entidades disponibles a través de lanzamientos continuos de Human Resources.

La cuadrícula incluye los siguientes campos:

- **Nombre de entidad de CDS**: nombre de la entidad en Common Data Service.
- **Referencia de entidad de CDS**: el identificador que Common Data Service utiliza para identificar un registro. Este valor es equivalente a un valor **RecId** de Human Resources. Puede encontrar el identificador cuando abre la entidad de Common Data Service en Microsoft Excel.
- **Nombre de la entidad de Human Resources**: la entidad que sincronizó los datos con Common Data Service por última vez. La entidad puede tener el prefijo de Common Data Service u otro prefijo.
- **Referencia de Human Resources**: el valor **RecId** que está asociado con el registro en Human Resources.
- **Eliminado de CDS**: un valor que indica si el registro se eliminó de Common Data Service.

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a>Eliminar la asociación de un registro en Human Resources de Common Data Service

Si experimenta problemas durante la sincronización de datos entre Human Resources y Common Data Service, puede resolverlos borrando el seguimiento y dejando que la tabla de seguimiento se vuelva a sincronizar. Si elimina la asociación y luego cambia o elimina un registro en Common Data Service, los cambios no se sincronizarán con Human Resources. Si realiza cambios en Human Resources, se crea un nuevo registro de seguimiento y el registro se actualiza en Common Data Service.

- Para eliminar la asociación de un registro entre Human Resources y Common Data Service, seleccione la entidad en el campo **Nombre de entidad CDS** y luego seleccione **Borrar información de seguimiento**.

[![Borrar la información de seguimiento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)

Para ejecutar una sincronización completa en la entidad después de borrar el seguimiento, consulte el siguiente procedimiento.

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a>Sincronizar una entidad entre Human Resources y Common Data Service

Use este procedimiento cuando:

- Cambios de Common Data Service tardan demasiado en aparecer en Human Resources.

- Debe actualizar la tabla de seguimiento después de borrar el seguimiento.

Para ejecutar una sincronización completa en una entidad entre Human Resources y Common Data Service:

1. Seleccione la entidad en el campo **Nombre de entidad CDS**.

2. Seleccione **Sincronizar ahora**.

[![Ejecutar una sincronización completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)


