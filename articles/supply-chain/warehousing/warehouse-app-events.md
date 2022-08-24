---
title: Eventos de la aplicación de almacén
description: Este artículo describe el procesamiento de eventos de la aplicación de almacén que se usa para procesar mensajes de eventos de la aplicación de almacén como parte de un trabajo por lotes.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2dc24fed1ec71432d9e2a3e1cb5b366267c2938b
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218754"
---
# <a name="warehouse-app-event-processing"></a>Procesamiento de eventos de la aplicación de almacén

[!include [banner](../includes/banner.md)]

Los trabajos por lotes que se ejecutan en Supply Chain Management pueden usar datos de una cola para procesar eventos emitidos por la aplicación móvil Warehouse Management para reaccionar según sea necesario a los eventos señalados. Esta función agrega eventos relevantes a la cola en respuesta a ciertos tipos de acciones realizadas por los trabajadores que usan la aplicación. Un ejemplo es cuando se usa la característica *Crear y procesar pedidos de transferencia desde la aplicación de almacén*, el encabezado y las líneas de la orden de transferencia se crean y actualizan en el back-end cuando el sistema está ejecutando el trabajo por lotes **Procesar eventos de aplicaciones de almacén**.

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>Activar o desactivar la característica Procesar eventos de aplicación de almacén

A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada. A partir de la versión 10.0.29 de Supply Chain Management, esta característica es obligatoria. Por lo tanto, está activado de forma predeterminada y no se puede volver a desactivar. Si está ejecutando una versión que es anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Procesar eventos de aplicación de almacén* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurar un trabajo por lotes para procesar eventos de aplicaciones de almacén

### <a name="process-warehouse-app-events"></a>Procesar eventos de la aplicación de almacén

Configure un trabajo por lotes programado para procesar los eventos de la aplicación del almacén para la creación de la orden de transferencia y las actualizaciones de línea.

1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar eventos de aplicación de almacén**.
1. Se abre el cuadro de diálogo Eventos de la aplicación Process warehouse. Expanda la ficha desplegable **Ejecutar en segundo plano** y establezca **Procesamiento por lotes** en **Sí**.
1. En la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.
1. Se abre el cuadro de diálogo **Definir recurrencia**. Establezca el programa de ejecución según sea necesario para su empresa.
1. Seleccione **Aceptar** para volver al cuadro de diálogo **Procesar eventos de aplicaciones de almacén**.
1. Seleccione **Aceptar** en el cuadro de diálogo **Procesar eventos de aplicación de almacén** para agregar el trabajo por lotes a la cola de trabajos por lotes.

## <a name="query-warehouse-app-events"></a>Eventos de la aplicación de almacén de consultas

Puede ver la cola de eventos y los mensajes de eventos generados por la aplicación móvil Warehouse Management yendo a **Gestión de almacenes \> Consultas e informes \> Registros de dispositivos móviles \> Eventos de la aplicación de almacén**.

## <a name="the-standard-event-queue-process"></a>El proceso de cola de eventos estándar

La cola de eventos de aplicaciones de almacén se utilizará normalmente con el siguiente flujo descrito:

1. Un evento se agrega a la cola con un mensaje de evento. El nuevo mensaje tiene inicialmente un estado de evento de **Esperando**, lo que significa que el trabajo por lotes **Procesar eventos de aplicaciones de almacén** no recogerá ni procesará este mensaje.
1. Tan pronto como el estado del mensaje se actualice a **Puesto en cola**, el trabajo por lotes de eventos **Aplicación de almacén de procesos** recogerá y procesará el evento.
1. El trabajo por lotes actualiza los estados del evento a **Terminado** o **Error**, dependiendo de si el proceso solicitado fue posible.
1. Cuando todos los mensajes de eventos relacionados están **completados**, el evento se elimina de la cola.

 Para un ejemplo detallado, vea [Crear orden de transporte desde la aplicación de almacén](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Manejar errores de eventos

Como parte del procesamiento de eventos de almacén, es posible que la actividad de mensaje solicitada no reciba procesos del trabajo por lotes. En este caso, el mensaje del evento cambiará a **Error**. Puede usar la información de **Registro de lotes** para saber por qué y tomar las medidas necesarias para corregir cualquier problema.

Para un ejemplo detallado, vea [Crear orden de transporte desde la aplicación de almacén](create-transfer-order-from-warehouse-app.md).

Para restablecer un mensaje de evento de aplicación de almacén fallido:

1. Vaya a **Gestión de almacenes \> Consultas e informes \> Registros de dispositivos móviles \> Eventos de aplicaciones de almacén**.
1. En la ficha desplegable **Mensajes de eventos de la aplicación de almacén**, busque y seleccione un evento relevante que muestra **Error** en la columna **Estado del evento**.
1. Seleccione **Reiniciar** en la barra de herramientas **Mensajes de eventos de la aplicación de almacén**.
1. Continúe trabajando hasta que se restablezcan todos los mensajes relevantes.

También puede eliminar un mensaje de evento **Error** utilizando la opción **Eliminar** en la barra de herramientas **Mensajes de eventos de la aplicación de almacén**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
