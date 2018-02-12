---
title: Muestra notificaciones de pedidos en punto de venta
description: "En este tema se describe cómo habilitar notificaciones del pedido en el punto de venta y el marco de las notificaciones, que se pueden extender a otras operaciones."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ec6cb212766dd90fa9db7719a2119419ecb935c7
ms.openlocfilehash: aea36591a81f727059e37a958efa62a9ebde9d9d
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2017

---

# <a name="display-notifications-in-point-of-sale"></a>Muestra notificaciones en punto de venta

En el entorno de ventas al por menor moderno de hoy, a los socios del almacén se les asignan distintas tareas, como ayudar a clientes, especificar transacciones, realizar recuentos de existencias, y recibir los pedidos en almacén. El cliente de punto de venta (PDV) autoriza a los socios para hacer estas tareas y muchas más, todas en una única aplicación. Con varias tareas a realizar durante un día, los socios podrían necesitar que se les notifique cuando algo requiera su asistencia. El marco de notificación de PDV soluciona el problema permitiendo a los minoristas configurar notificaciones basados en roles. Con Dynamics 365 for Retail con la actualización de la aplicación 5, estas notificaciones solo se pueden configurar para las operaciones de PDV.

Actualmente, el sistema proporciona la capacidad para mostrar las notificaciones para la operación cumplimiento de pedido, no obstante, el marco se ha diseñado para ser extensible, de modo que en el futuro, los programadores puedan escribir un controlador de la notificación para cualquier operación y mostrar las notificaciones en PDV.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Habilitar notificaciones para las operaciones de cumplimiento de pedido

Para habilitar las notificaciones de las operaciones de cumplimiento de pedido, consulte a los siguientes pasos:

 - Ir a la página **Operaciones** (**Retail** > **Configuración del canal** > **Configuración de PDV** > **PDV** > **Operaciones**).
 - Busque la operación de cumplimiento de pedido y seleccione la casilla de verificación **Habilitar las notificaciones** para esta operación. Esto le indica al marco de notificación que escuche el controlador para la operación de cumplimiento de pedido. Si implementan el controlador, las notificaciones se mostrarán en PDV, si no, las notificaciones no se mostrarán para esta operación.
- Vaya a los permisos de PDV asociados a los trabajadores y en el ficha desplegable **Notificaciones** agregue la operación de cumplimiento de pedido con la “orden de visualización” como 1. Cuando hay más de una notificación configurada, se utiliza la orden de visualización para organizar la notificación de arriba a abajo con 1 en la parte superior. Sólo aquellas operaciones se pueden agregar a las que se ha seleccionado la casilla de verificación **Notificaciones de permiso**. Además, las notificaciones se mostrarán únicamente para las operaciones que se han agregado aquí y a sólo a los trabajadores para los que las operaciones se han agregado a los permisos correspondientes de PDV. 

> [!NOTE]
> Las notificaciones se pueden anular en el nivel de usuario desplazándose al registro del trabajador y seleccionando **Permisos de PDV** y después editando la suscripción de la notificación de ese usuario.

 - Ir a la página **Perfil de funcionalidad** (**Retail** > **Configuración del canal** > **Configuración de PDV** > **Perfiles de PDV** > **Perfiles de funcionalidad**). Actualice la propiedad **Intervalo de la notificación**, para establecer el intervalo en minutos en los que las notificaciones deben ser extraidas. Es recomendable establecer este valor a 10 minutos para evitar la comunicación innecesaria con Headquarters. Establecer el intervalo de la notificación en “0 " apagará las notificaciones.  

 - Vaya a Retail **Retail** > **TI de Retail** > **Programación de distribución**. Seleccione la programación “1060-Staff” para sincronizar los ajustes de la suscripción de la notificación y después haga click en **Ejecutar ahora**. A continuación, sincronice el intervalo de permiso seleccionando la "configuración 1070-Channel" y después haga click en **Ejecutar ahora**. 

## <a name="view-notifications-in-pos"></a>Ver notificaciones en PDV

Una vez completados los pasos anteriores, los trabajadores, para los que se configurar notificaciones, pueden ver las notificaciones en PDV. Para ver las notificaciones, haga clic en el icono de notificaciones en la barra de título de PDV. Esto muestra un centro de notificaciones con las notificaciones de la operación de cumplimiento. El centro de notificaciones se debe presentar a los siguientes grupos dentro de la operación de cumplimiento: 

- **Pedidos pendientes** - Este grupo muestra el recuento de los pedidos que se encuentran en estado pendiente, como pedidos que necesitan ser aceptados por un trabajador de PDV, teniendo los permisos necesarios para el almacén. Si hace clic en el número en el grupo abrirá la página **Cumplimiento del pedido** filtrado para mostrar sólo los pedidos pendientes asignados al almacén para cumplimiento. Si los pedidos se aceptan automáticamente para el almacén, el recuento para este grupo será cero.

- **Recogida del almacén** - Este grupo muestra el recuento de los pedidos que tengan el modo de entrega **Recogida** y la recogida se programa de almacén actual. Si hace clic en el número en el grupo se abrirá la página **Cumplimiento del pedido** filtrado para mostrar sólo los pedidos activos que están preparados para ser recogidos del almacen actual.

- **Envío desde el almacén** - Este grupo muestra el recuento de los pedidos que tengan el modo de entrega **Envío** y el envío se programa desde almacén actual. Si hace clic en el número en el grupo se abrirá la página **Cumplimiento del pedido** filtrado para mostrar sólo los pedidos activos que están preparados para ser enviados desde el almacen actual.

Cuando hay nuevos pedidos asignadas al almacén para el cumplimiento, el icono de la notificación cambiará para indicar las nuevas notificaciones y el recuento de los grupos correspondientes se actualizará. El usuario también puede hacer clic en el icono de actualización, junto al nombre de la operación, para actualizar inmediatamente el recuento de los grupos. El recuento también se actualizará en el intervalo predefinido. Cualquier grupo con un nuevo artículo, que no está en cuenta el trabajador actual, mostrará un icono de ráfaga que indica que este grupo tiene un nuevo artículo. Si hace clic en los mosaicos dentro de las notificaciones se abrirá la operación específica para la que está configurada esa notificación. En las situaciones anteriores, hacer clic en las notificaciones abrirá la página **Cumplimiento del pedido** y pasará los parámetros adecuados: pedidos pendientes, recogida de almacén y envío desde el almacén. 

> [!NOTE]
> Se permitirán notificaciones de pedidos pendientes en una próxima actualización en Dynamics 365 for Retail. 


