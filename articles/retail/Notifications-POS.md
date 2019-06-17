<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="Notifications-POS.md" target-language="es-ES">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>Notifications-POS.74d2b9.6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\Notifications-POS.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mostrar notificaciones de pedidos en el punto de venta (PDV)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to enable order notifications in the point of sale and the notification framework.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En este tema se describe cómo habilitar notificaciones de pedidos en el punto de venta y el marco de las notificaciones.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mostrar notificaciones de pedidos en el punto de venta (PDV)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In the modern retail environment, store associates are assigned various tasks, such as helping customers, entering transactions, doing stock counts, and receiving orders in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En el entorno de ventas al por menor moderno, a los socios del almacén se les asignan distintas tareas, como ayudar a clientes, especificar transacciones, hacer recuentos de existencias y recibir los pedidos en almacén.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The point of sale (POS) client provides a single application where associates can perform all these tasks and many others.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El cliente de punto de venta (PDV) proporciona una única aplicación en la que los socios pueden realizar todas estas tareas y muchas otras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>Because various tasks must be performed during the day, associates might have to be notified when something requires their attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puesto que deben realizar varias tareas durante el día, es posible que tenga que notificarse a los socios cuando algo requiera su asistencia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The notification framework in the POS helps by letting retailers configure role-based notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El marco de notificación de PDV ayuda a permitir que los minoristas configuren notificaciones basadas en roles.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>In Microsoft Dynamics 365 for Retail with application update 5, these notifications can be configured only for POS operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En Microsoft Dynamics 365 for Retail con la actualización de la aplicación 5, estas notificaciones solo se pueden configurar para las operaciones de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Currently, the system can show notifications only for order fulfillment operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Actualmente, el sistema solo puede mostrar notificaciones para operaciones de cumplimiento de pedido.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>However, because the framework is designed to be extensible, developers will eventually be able to write a notification handler for any operation and show the notifications for that operation in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sin embargo, puesto que el marco se ha diseñado para que sea extensible, los desarrolladores finalmente podrán escribir un controlador de notificaciones para cualquier operación y mostrar las notificaciones de esa operación en el PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Enable notifications for order fulfillment operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Habilitar notificaciones para las operaciones de cumplimiento de pedido</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To enable notifications for order fulfillment operations, follow these steps.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para habilitar las notificaciones de las operaciones de cumplimiento de pedido, siga estos pasos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operations<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vaya a <bpt id="p1">**</bpt>Venta minorista<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Configuración de canal<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Configuración de PDV<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>PDV<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operaciones<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Search for the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> operation, and select the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for it to specify that the notification framework should listen to the handler for this operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Busque la operación <bpt id="p1">**</bpt>Cumplimiento de pedido<ept id="p1">**</ept> y seleccione la casilla <bpt id="p2">**</bpt>Habilitar notificaciones<ept id="p2">**</ept> para que especifique que el marco de notificación debe escuchar al controlador para esta operación.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If the handler is implemented, notifications for this operation will then be shown in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se implementa el controlador, las notificaciones para esta operación se mostrarán en el PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Employees<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Workers<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph>, under Retail tab, open the POS permissions associated with the worker.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En la pestaña Retail, vaya a <bpt id="p1">**</bpt>Ventas al por menor<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Empleados<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Trabajadores<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> y abra los permisos de PDV asociados al trabajador.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Expand the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, add the <bpt id="p2">**</bpt>Order fulfillment<ept id="p2">**</ept> operation, and set the <bpt id="p3">**</bpt>Display order<ept id="p3">**</ept> field to <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Expanda la pestaña desplegable <bpt id="p1">**</bpt>Notificaciones<ept id="p1">**</ept>, agregue la operación <bpt id="p2">**</bpt>Cumplimiento de pedido<ept id="p2">**</ept> y establezca el campo <bpt id="p3">**</bpt>Orden de visualización<ept id="p3">**</ept> en <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If more than one notification is configured, this field is used to arrange the notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si se configura más de una notificación, este campo se utiliza para organizar las notificaciones.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Notifications that have a lower <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value appear above notifications that have a higher value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Las notificaciones que tienen un valor <bpt id="p1">**</bpt>Orden de visualización<ept id="p1">**</ept> más bajo aparecen encima de las notificaciones que tienen un valor más alto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Notifications that have a <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value of <bpt id="p2">**</bpt>1<ept id="p2">**</ept> are at the top.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Las notificaciones que tienen un valor <bpt id="p1">**</bpt>Orden de visualización<ept id="p1">**</ept> de <bpt id="p2">**</bpt>1<ept id="p2">**</ept> se encuentran en la parte superior.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Notifications are shown only for operations that are added on the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, and you can add operations there only if the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for those operations has been selected on the <bpt id="p3">**</bpt>POS operations<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Las notificaciones solo se muestran para las operaciones que se agregan en la pestaña desplegable <bpt id="p1">**</bpt>Notificaciones<ept id="p1">**</ept>, y puede agregar operaciones solo si se ha seleccionado la casilla <bpt id="p2">**</bpt>Habilitar notificaciones<ept id="p2">**</ept> para dichas operaciones en la página <bpt id="p3">**</bpt>Operaciones de PDV<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Additionally, notifications for an operation are shown to workers only if the operation is added to the POS permissions for those workers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Además, las notificaciones para una operación se muestran a los trabajadores solo si la operación se agrega a los permisos de PDV para esos trabajadores.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Notifications can be overridden at the user level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Las notificaciones se pueden anular en el nivel de usuario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Open the worker's record, select <bpt id="p1">**</bpt>POS permissions<ept id="p1">**</ept>, and then edit the user's notification subscription.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Abra el registro del trabajador, seleccione <bpt id="p1">**</bpt>Permisos de PDV<ept id="p1">**</ept>y, a continuación, edite la suscripción de notificación del usuario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS profiles<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Functionality profiles<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vaya a <bpt id="p1">**</bpt>Venta al por menor<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Configuración de canal<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Configuración de PDV<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Perfiles de PDV<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Perfiles de funcionalidad<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In the <bpt id="p1">**</bpt>Notification interval<ept id="p1">**</ept> field, specify how often notifications should be pulled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En el campo <bpt id="p1">**</bpt>Intervalo de la notificación<ept id="p1">**</ept>, especifique con qué frecuencia deben extraerse las notificaciones.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>For some notifications, the POS must make real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para algunas notificaciones, el PDV debe realizar llamadas en tiempo real a la aplicación de la oficina administrativa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>These calls consume the compute capacity of your back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Estas llamadas consumen la capacidad de cálculo de la aplicación de su oficina administrativa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Therefore, when you set the notification interval, you should consider both your business requirements and the impact of real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Por lo tanto, al configurar el intervalo de la notificación, debe tener en cuenta sus requisitos empresariales y el impacto de las llamadas en tiempo real a la aplicación de la oficina administrativa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>A value of <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero) turns off notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un valor de <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (cero) desactiva las notificaciones.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedule<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vaya a <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>TI de Retail<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Programación de distribución<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Select the <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Staff<ept id="p2">**</ept>) schedule to synchronize notification subscription settings, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Seleccione la programación <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Personal<ept id="p2">**</ept>) para sincronizar la configuración de la suscripción de la notificación y, a continuación, seleccione <bpt id="p3">**</bpt>Ejecutar ahora<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Next, select the <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Channel configuration<ept id="p2">**</ept>) schedule to synchronize the permission interval, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A continuación, seleccione la programación <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Configuración de canal<ept id="p2">**</ept>) para sincronizar el intervalo del permiso y seleccione <bpt id="p3">**</bpt>Ejecutar ahora<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>View notifications in the POS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ver notificaciones en el PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>After you complete the preceding steps, the workers will be able to view the notifications in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una vez que complete los pasos anteriores, los trabajadores podrán ver las notificaciones en el PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>To view notifications, press the notification icon in the top right corner of the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para ver notificaciones, presione el icono de notificaciones en la esquina superior derecha del PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>A notification center appears and shows notifications for the order fulfillment operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aparece una centro de notificaciones y muestra las notificaciones para la operación de cumplimiento de pedido.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>The notification center should show the following groups in the order fulfillment operation:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El centro de notificaciones debe mostrar ahora los siguientes grupos en la operación de cumplimiento de pedido:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Store pickup<ept id="p1">**</ept> – This group shows the count of orders that have a delivery mode of <bpt id="p2">**</bpt>Pickup<ept id="p2">**</ept>, and that are scheduled for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Recogida del almacén<ept id="p1">**</ept>: este grupo muestra el recuento de los pedidos que tengan un modo de entrega <bpt id="p2">**</bpt>Recogida<ept id="p2">**</ept> y que estén programados para su recogida desde el almacén actual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puede presionar el número en el grupo para abrir la página <bpt id="p1">**</bpt>Cumplimiento de pedido<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En este caso, la página se filtrará de modo que muestre solo los pedidos activos que están configurados para su recogida desde el almacén actual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source><bpt id="p1">**</bpt>Ship from store<ept id="p1">**</ept> – This group shows the count of orders that have the delivery mode of <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept>, and that are scheduled for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Envío desde el almacén<ept id="p1">**</ept>: este grupo muestra el recuento de pedidos que tengan el modo de entrega <bpt id="p2">**</bpt>Envío<ept id="p2">**</ept> y que estén programados para su envío desde el almacén actual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puede presionar el número en el grupo para abrir la página <bpt id="p1">**</bpt>Cumplimiento de pedido<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En este caso, la página se filtrará de modo que muestre solo los pedidos activos que están configurados para su envío desde el almacén actual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>When new orders are assigned to the store for fulfillment, the notification icon changes to indicate that there are new notifications, and the count for the appropriate groups is updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cuando se asignan nuevos pedidos al almacén para el cumplimiento, el icono de la notificación cambia para indicar que hay nuevas notificaciones, y se actualiza el recuento de los grupos correspondientes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Even though the groups are refreshed at regular intervals however, POS users can manually refresh the groups at any time by selecting the <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> button next to the group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aún así, los grupos se actualizan a intervalos regulares, sin embargo, los usuarios de PDV pueden actualizar manualmente los grupos en cualquier momento seleccionando el botón <bpt id="p1">**</bpt>Actualizar<ept id="p1">**</ept> al lado del grupo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Lastly, if a group has a new item, that the current worker hasn't viewed, then the group shows a burst symbol to indicate new content.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Por último, si un grupo tiene un nuevo artículo que el trabajador actual no ha visto, el grupo muestra un símbolo de ráfaga para indicar nuevo contenido.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Enable live content on POS buttons</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Habilitar contenido en vivo en los botones de PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>POS buttons can now show a count to help workers easily determine which tasks require their immediate attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Los botones de PDV pueden mostrar ahora un recuento para ayudar a los trabajadores a determinar con facilidad qué tareas requieren su asistencia inmediata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>To show this number on a POS button, you must complete the notification setup that is described earlier in this topic (that is, you must enable notifications for an operation, set up a notification interval, and update the POS permission group for the worker).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para mostrar este número en un botón de PDV, debe completar la configuración de notificación que se describe anteriormente en este tema (es decir, debe habilitar las notificaciones para una operación, configurar un intervalo de notificaciones y actualizar el grupo de permisos de PDV para el trabajador).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Additionally, you must open the button grid designer, view the button's properties, and select the <bpt id="p1">**</bpt>Enable live content<ept id="p1">**</ept> check box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Además, debe abrir el diseñador de cuadrícula de botones, ver las propiedades del botón y seleccione la casilla <bpt id="p1">**</bpt>Habilitar contenido en vivo<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>In the <bpt id="p1">**</bpt>Content alignment<ept id="p1">**</ept> field, you can select whether the count appears in the upper-right corner of the button (<bpt id="p2">**</bpt>Top right<ept id="p2">**</ept>) or in the center (<bpt id="p3">**</bpt>Center<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En el campo <bpt id="p1">**</bpt>Alineación de contenido<ept id="p1">**</ept>, puede seleccionar si el recuento aparece en la esquina superior derecha del botón (<bpt id="p2">**</bpt>Superior derecha<ept id="p2">**</ept>) o en el centro (<bpt id="p3">**</bpt>Centro<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The live content can be enabled for operations only if the <bpt id="p1">**</bpt>Enable notifications<ept id="p1">**</ept> check box has been selected for them on the <bpt id="p2">**</bpt>POS operations<ept id="p2">**</ept> page, as described earlier in this topic.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">El contenido en vivo se puede habilitar para las operaciones solo si se ha seleccionado la casilla <bpt id="p1">**</bpt>Habilitar notificaciones<ept id="p1">**</ept> en la página <bpt id="p2">**</bpt>Operaciones de PDV<ept id="p2">**</ept>, como se describe anteriormente en este tema.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The following illustration shows the live content settings in the button grid designer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La siguiente ilustración muestra la configuración de contenido en vivo en el diseñador de cuadrícula de botones.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source><bpt id="p1">![</bpt>Live content settings in the button grid designer<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Live content settings in the button grid designer<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Configuración de contenido en vivo en el diseñador de cuadrícula de botones<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Configuración de contenido en vivo en el diseñador de cuadrícula de botones<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>To show the notification count on a button, you need to ensure that the correct screen layout is being updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para mostrar el recuento de la notificación en un botón, deberá asegurarse que se esté actualizando el diseño de pantalla correcto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>To determine the screen layout that is being used by the POS, select the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> icon in upper-right corner and note the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para determinar el diseño de pantalla que está siendo usado por el PDV, seleccione el icono <bpt id="p1">**</bpt>Valores<ept id="p1">**</ept> en esquina superior derecha y anote el <bpt id="p2">**</bpt>Identificador de diseño de pantalla<ept id="p2">**</ept> y la <bpt id="p3">**</bpt>Resolución de diseño<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Now using Edge browser, go to the <bpt id="p1">**</bpt>Screen layout<ept id="p1">**</ept> page in Dynamics 365 for Finance and Operations, find the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept> identified above and select the <bpt id="p4">**</bpt>Enable live content<ept id="p4">**</ept> check box.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Ahora mediante el explorador Edge, vaya a la página <bpt id="p1">**</bpt>Diseño de Pantalla<ept id="p1">**</ept> en Dynamics 365 for Finance and Operations, encuentre el <bpt id="p2">**</bpt>Identificador de diseño de pantalla<ept id="p2">**</ept> y la <bpt id="p3">**</bpt>Resolución de diseño<ept id="p3">**</ept> identificados arriba y seleccione la casilla de verificación <bpt id="p4">**</bpt>Activar contenido activo<ept id="p4">**</ept> .</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Retail IT <ph id="ph2">\&gt;</ph> Distribution schedule<ept id="p1">**</ept> and run the 1090 (Registers) job to synchronize layout changes.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Vaya <bpt id="p1">**</bpt>Ventas al por menor <ph id="ph1">\&gt;</ph> TI de venta minorista <ph id="ph2">\&gt;</ph> Programación distribución<ept id="p1">**</ept> y ejecuta el trabajo 1090 (Registros) para sincronizar los cambios de diseño.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">![</bpt>Find the screen layout used by POS<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Find the screen layout <ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Encuentre el diseño de pantalla utilizado por PDV<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Encuentre el diseño de pantalla utilizado por PDV <ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The following illustration shows the effect of selecting <bpt id="p1">**</bpt>Top right<ept id="p1">**</ept> versus <bpt id="p2">**</bpt>Center<ept id="p2">**</ept> in the <bpt id="p3">**</bpt>Content alignment<ept id="p3">**</ept> field for buttons of various sizes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La siguiente ilustración muestra el efecto de seleccionar <bpt id="p1">**</bpt>Superior derecha<ept id="p1">**</ept> frente <bpt id="p2">**</bpt>Centro<ept id="p2">**</ept> en el campo <bpt id="p3">**</bpt>Alineación de contenido<ept id="p3">**</ept> para los botones de varios tamaños.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">![</bpt>Live content on POS buttons<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Live content on POS buttons<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Contenido en vivo en botones de PDV<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Contenido en vivo en botones de PDV<ept id="p2">")</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>