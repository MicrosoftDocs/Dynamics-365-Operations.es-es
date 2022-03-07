---
title: Mostrar notificaciones de pedidos en el punto de venta (PDV)
description: En este tema se describe cómo habilitar notificaciones de pedidos en el punto de venta y el marco de las notificaciones.
author: ShalabhjainMSFT
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: f7b28a33dff4af6bf2b97db825a5a8304213f3a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796495"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Mostrar notificaciones de pedidos en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

A los asociados de la tienda se les pueden asignar varias tareas en su tienda, como cumplimentar los pedidos o realizar la recepción de inventario o el recuento de existencias. El cliente de punto de venta (PDV) proporciona una única aplicación en la que los asociados pueden recibir notificaciones de estas tareas. El marco de notificación de PDV ayuda a permitir que los minoristas configuren notificaciones basadas en roles. A partir de la actualización 5 de la aplicación de Dynamics 365 Retail, estas notificaciones se pueden configurar para las operaciones de PDV.

El sistema puede mostrar notificaciones para la operación de *cumplimentación de pedido* y, a partir de la versión 10.0.18 de Commerce, las notificaciones también se pueden mostrar para la operación *orden de recuperación*. Sin embargo, puesto que el marco se ha diseñado para que sea extensible, los desarrolladores pueden [escribir un controlador de notificaciones](dev-itpro/extend-pos-notification.md) para cualquier operación y mostrar las notificaciones de esa operación en el PDV.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>Habilitar notificaciones para las operaciones de cumplimentación o recuperación de pedidos

Para habilitar las notificaciones de las operaciones de cumplimentación o recuperación de pedidos, consulte los siguientes pasos:

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> PDV \> Operaciones**.
1. Busque la operación **Cumplentación de pedido** o la operación **Pedido de recuperación** y luego seleccione **Habilitar notificaciones** para que la operación especifique que el marco de notificación debe escuchar al controlador para esta operación. Si se implementa el controlador, las notificaciones para esta operación se mostrarán en el PDV.
1. Vaya a **Retail y Commerce \> Empleados \> Trabajadores**.
1. Seleccione la pestaña **Commerce**, seleccione una fila de trabajador y luego seleccione **Permisos de PDV**. Seleccione la ficha desplegable **Notificaciones** para expandirla y luego agregue las operaciones para las que han habilitado las notificaciones. Si configura una sola notificación para un trabajador, asegúrese de que el valor **Orden de visualización** esté establecido en **1**. Si configura más de una operación, establezca los valores de **Orden de visualización** para indicar el orden en el que deben mostrarse las notificaciones. 

      Las notificaciones se muestran solo para las operaciones que se agregan en la ficha desplegable **Notificaciones**. Puede agregar operaciones allí solo si las casillas **Permitir notificaciones** para esas operaciones se han seleccionado en la página **Operaciones PDV**. Además, las notificaciones para una operación se muestran únicamente a los trabajadores si la operación se agrega a los permisos de PDV para esos trabajadores.

    > [!NOTE]
    > Las notificaciones se pueden anular en el nivel de usuario. Para hacerlo, abra el registro del trabajador, seleccione **Permisos de PDV** y, a continuación, edite la suscripción de notificación del usuario.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**. En el campo **Intervalo de la notificación**, especifique con qué frecuencia deben extraerse las notificaciones. Para algunas notificaciones, el PDV debe realizar llamadas en tiempo real a la aplicación de la oficina administrativa. Estas llamadas consumen la capacidad de cálculo de la aplicación de su oficina administrativa. Por lo tanto, al configurar el intervalo de la notificación, debe tener en cuenta sus requisitos empresariales y el impacto de las llamadas en tiempo real a la aplicación de la oficina administrativa. Un valor de **0** (cero) desactiva las notificaciones.
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**. Seleccione la programación **1060** (**Personal**) para sincronizar la configuración de la suscripción de la notificación y, a continuación, seleccione **Ejecutar ahora**. A continuación, seleccione la programación **1070** (**Configuración de canal**) para sincronizar el intervalo del permiso y seleccione **Ejecutar ahora**.

## <a name="view-notifications-in-the-pos"></a>Ver notificaciones en el PDV

Una vez que complete los pasos anteriores, los trabajadores podrán ver las notificaciones en el PDV. Para ver notificaciones, seleccione el icono de notificaciones en la esquina superior derecha del PDV. Aparece un panel de notificaciones que muestra notificaciones de las operaciones configuradas para el trabajador. 

Para la operación de **cumplimentación de pedido**, el panel de notificaciones mostrará los siguientes grupos:

- **Recogida del almacén**: este grupo muestra el recuento de las líneas de pedidos individuales que estén programados para su recogida desde la tienda actual. Puede seleccionar el número del grupo para abrir la operación **Cumplimentación del pedido** con un filtro, para que muestren solo las líneas de pedido activas configuradas para recogida en la tienda actual.
- **Enviar desde la tienda**: este grupo muestra el recuento de líneas de pedido individuales que se han configurado para enviarse desde la tienda actual del usuario. Puede seleccionar el número del grupo para abrir la operación **Cumplimentación del pedido** con una vista filtrada, para que se muestren solo las líneas de pedido activas configuradas para envío desde la tienda actual.

Para la operación de **recuperación de pedido**, el panel de notificaciones mostrará los siguientes grupos:

- **Pedidos a cumplimentar**: este grupo muestra el recuento de pedidos que están configurados para cumplimentación por recogida o envío para la tienda actual del usuario. Puede seleccionar el número del grupo para abrir la operación **Recuperar pedido** con una vista filtrada que solo muestra los pedidos abiertos que la tienda actual del usuario debe cumplimentar para los escenarios de recogida en tienda o envío desde tienda.
- **Pedidos a recoger**: este grupo muestra el recuento de pedidos programados para su recogida desde la tienda actual. Puede seleccionar el número del grupo para abrir la operación **Recuperar pedido** con una vista filtrada que solo muestra los pedidos abiertos que la tienda actual del usuario debe cumplimentar para recogida por parte del cliente en la tienda actual del usuario.
- **Órdenes a enviar**: este grupo muestra el recuento de pedidos a enviar desde la tienda actual del usuario. Puede seleccionar el número del grupo para abrir la operación **Recuperar pedido** con una vista filtrada que solo muestra los pedidos abiertos que la tienda actual del usuario debe cumplimentar para envío desde la tienda actual del usuario.

Tanto para las notificaciones de cumplimentación de pedidos como de recuperación de pedidos, cuando el proceso recoge los nuevos pedidos, el icono de la notificación cambia para indicar que hay nuevas notificaciones, y se actualiza el recuento de los grupos correspondientes. Incluso aunque los grupos se actualizan a intervalos regulares, los usuarios de PDV pueden actualizar manualmente los grupos en cualquier momento seleccionando el botón **Actualizar** al lado del grupo. Por último, si un grupo tiene un nuevo artículo que el trabajador actual no ha visto, el grupo muestra un símbolo de ráfaga para indicar nuevo contenido.

## <a name="enable-live-content-on-pos-buttons"></a>Habilitar contenido en vivo en los botones de PDV

Los botones de PDV pueden mostrar ahora un recuento para ayudar a los trabajadores a determinar con facilidad qué tareas requieren su asistencia inmediata. Para mostrar este número en un botón de PDV, debe completar la configuración de notificación que se describe anteriormente en este tema (es decir, debe habilitar las notificaciones para una operación, configurar un intervalo de notificaciones y actualizar el grupo de permisos de PDV para el trabajador). Además, debe abrir el diseñador de cuadrícula de botones, ver las propiedades del botón y seleccione la casilla **Habilitar contenido en vivo**. En el campo **Alineación de contenido**, puede seleccionar si el recuento aparece en la esquina superior derecha del botón (**Superior derecha**) o en el centro (**Centro**).

> [!NOTE]
> El contenido en vivo se puede habilitar para las operaciones solo si se ha seleccionado la casilla **Habilitar notificaciones** en la página **Operaciones de PDV**, como se describe anteriormente en este tema.

La siguiente ilustración muestra la configuración de contenido en vivo en el diseñador de cuadrícula de botones.

![Configuración de contenido en vivo en el diseñador de cuadrícula de botones](./media/ButtonGridDesigner.png "Configuración de contenido en vivo en el diseñador de cuadrícula de botones")

Para mostrar el recuento de la notificación en un botón, deberá asegurarse que se esté actualizando el diseño de pantalla correcto. Para determinar el diseño de pantalla que está siendo usado por el PDV, seleccione el icono **Valores** en esquina superior derecha y anote el **Identificador de diseño de pantalla** y la **Resolución de diseño**. Ahora mediante el explorador Edge, vaya a la página **Diseño de Pantalla**, encuentre el **Identificador de diseño de pantalla** y la **Resolución de diseño** identificados arriba y seleccione la casilla de verificación **Activar contenido activo**. Vaya **Retail y Commerce \> TI de Retail y Commerce \> Programación distribución** y ejecuta el trabajo 1090 (Registros) para sincronizar los cambios de diseño.

![Encuentre el diseño de pantalla utilizado por PDV](./media/Choose_screen_layout.png "Encontrar el diseño de pantalla")

La siguiente ilustración muestra el efecto de seleccionar **Superior derecha** frente **Centro** en el campo **Alineación de contenido** para los botones de varios tamaños.

![Contenido en vivo en los botones de PDV](./media/ButtonsWithLiveContent.png "Contenido en vivo en los botones de PDV")

[!INCLUDE[footer-include](../includes/footer-banner.md)]
