---
title: Mostrar notificaciones de pedidos en el punto de venta (PDV)
description: En este tema se describe cómo habilitar notificaciones de pedidos en el punto de venta y el marco de las notificaciones.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 04dd57aabcbdf5291f06317800b69f29f15d2763
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023881"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Mostrar notificaciones de pedidos en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

En el entorno de ventas al por menor moderno, a los socios del almacén se les asignan distintas tareas, como ayudar a clientes, especificar transacciones, hacer recuentos de existencias y recibir los pedidos en almacén. El cliente de punto de venta (PDV) proporciona una única aplicación en la que los socios pueden realizar todas estas tareas y muchas otras. Puesto que deben realizar varias tareas durante el día, es posible que tenga que notificarse a los socios cuando algo requiera su asistencia. El marco de notificación de PDV ayuda a permitir que los minoristas configuren notificaciones basadas en roles. A partir de Dynamics 365 for Retail con la actualización de la aplicación 5, estas notificaciones solo se pueden configurar para las operaciones de PDV.


Actualmente, el sistema solo puede mostrar notificaciones para operaciones de cumplimiento de pedido. Sin embargo, puesto que el marco se ha diseñado para que sea extensible, los desarrolladores finalmente podrán escribir un controlador de notificaciones para cualquier operación y mostrar las notificaciones de esa operación en el PDV.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Habilitar notificaciones para las operaciones de cumplimiento de pedido

Para habilitar las notificaciones de las operaciones de cumplimiento de pedido, siga estos pasos.

1. Vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Operaciones**.
2. Busque la operación **Cumplimiento de pedido** y seleccione la casilla **Habilitar notificaciones** para que especifique que el marco de notificación debe escuchar al controlador para esta operación. Si se implementa el controlador, las notificaciones para esta operación se mostrarán en el PDV.
3. En la pestaña **Retail y Commerce** &gt; **Empleados** &gt; **Trabajadores** &gt; debajo de la pestaña Commerce y abra los permisos de PDV asociados al trabajador. Expanda la pestaña desplegable **Notificaciones**, agregue la operación **Cumplimiento de pedido** y establezca el campo **Orden de visualización** en **1**. Si se configura más de una notificación, este campo se utiliza para organizar las notificaciones. Las notificaciones que tienen un valor **Orden de visualización** más bajo aparecen encima de las notificaciones que tienen un valor más alto. Las notificaciones que tienen un valor **Orden de visualización** de **1** se encuentran en la parte superior.

    Las notificaciones solo se muestran para las operaciones que se agregan en la pestaña desplegable **Notificaciones**, y puede agregar operaciones solo si se ha seleccionado la casilla **Habilitar notificaciones** para dichas operaciones en la página **Operaciones de PDV**. Además, las notificaciones para una operación se muestran a los trabajadores solo si la operación se agrega a los permisos de PDV para esos trabajadores.

    > [!NOTE]
    > Las notificaciones se pueden anular en el nivel de usuario. Abra el registro del trabajador, seleccione **Permisos de PDV**y, a continuación, edite la suscripción de notificación del usuario.

4. Vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de funcionalidad**. En el campo **Intervalo de la notificación**, especifique con qué frecuencia deben extraerse las notificaciones. Para algunas notificaciones, el PDV debe realizar llamadas en tiempo real a la aplicación de la oficina administrativa. Estas llamadas consumen la capacidad de cálculo de la aplicación de su oficina administrativa. Por lo tanto, al configurar el intervalo de la notificación, debe tener en cuenta sus requisitos empresariales y el impacto de las llamadas en tiempo real a la aplicación de la oficina administrativa. Un valor de **0** (cero) desactiva las notificaciones.
5. Vaya a **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programación de distribución**. Seleccione la programación **1060** (**Personal**) para sincronizar la configuración de la suscripción de la notificación y, a continuación, seleccione **Ejecutar ahora**. A continuación, seleccione la programación **1070** (**Configuración de canal**) para sincronizar el intervalo del permiso y seleccione **Ejecutar ahora**.

## <a name="view-notifications-in-the-pos"></a>Ver notificaciones en el PDV

Una vez que complete los pasos anteriores, los trabajadores podrán ver las notificaciones en el PDV. Para ver notificaciones, presione el icono de notificaciones en la esquina superior derecha del PDV. Aparece una centro de notificaciones y muestra las notificaciones para la operación de cumplimiento de pedido. El centro de notificaciones debe mostrar ahora los siguientes grupos en la operación de cumplimiento de pedido:

- **Recogida del almacén**: este grupo muestra el recuento de los pedidos que tengan un modo de entrega **Recogida** y que estén programados para su recogida desde el almacén actual. Puede presionar el número en el grupo para abrir la página **Cumplimiento de pedido**. En este caso, la página se filtrará de modo que muestre solo los pedidos activos que están configurados para su recogida desde el almacén actual.
- **Envío desde el almacén**: este grupo muestra el recuento de pedidos que tengan el modo de entrega **Envío** y que estén programados para su envío desde el almacén actual. Puede presionar el número en el grupo para abrir la página **Cumplimiento de pedido**. En este caso, la página se filtrará de modo que muestre solo los pedidos activos que están configurados para su envío desde el almacén actual.

Cuando se asignan nuevos pedidos al almacén para el cumplimiento, el icono de la notificación cambia para indicar que hay nuevas notificaciones, y se actualiza el recuento de los grupos correspondientes. Aún así, los grupos se actualizan a intervalos regulares, sin embargo, los usuarios de PDV pueden actualizar manualmente los grupos en cualquier momento seleccionando el botón **Actualizar** al lado del grupo. Por último, si un grupo tiene un nuevo artículo que el trabajador actual no ha visto, el grupo muestra un símbolo de ráfaga para indicar nuevo contenido.

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
