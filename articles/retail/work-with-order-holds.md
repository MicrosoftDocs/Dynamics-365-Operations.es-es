---
title: Configurar y trabajar con retenciones de pedidos del centro de llamadas
description: "En este tema se describe cómo ejecutar retenciones de pedidos con Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: ba8fade84358c960dcfd1e8d9ffef1ffede34871
ms.contentlocale: es-es
ms.lasthandoff: 01/04/2019

---

# <a name="configure-and-work-with-call-center-order-holds"></a>Configurar y trabajar con retenciones de pedidos del centro de llamadas

[!include [banner](includes/banner.md)]

Este tema describe las características de retención del pedido que Microsoft Dynamics 365 for Retail tiene para los pedidos de centro de llamadas.

## <a name="configuring-call-center-order-holds"></a>Configuración de las retenciones de pedidos del centro de asistencia telefónica

Para usar las características de retención de pedido del centro de asistencia telefónica, primero debe definir códigos de retención. Para crear un conjunto de códigos de retención definido por el usuario, basado en sus requisitos empresariales, vaya **Ventas y marketing** \> **Configuración** \> **Pedidos de ventas** \> **Códigos de bloqueo del pedido**. Puede indicar opcionalmente uno de los códigos de bloqueo como código de retención predeterminado configurando la opción **Valor predeterminado del pedido de ventas** en **Sí**. Esto código de retención se usará en cualquier momento en que un pedido de ventas se ponga en espera. Si un pedido de ventas ha reservado inventario, y las reservas se deben quitar automáticamente si el pedido está en espera por un motivo determinado, establezca la opción **Quitar las reservas de inventario** en **Sí** de los códigos de motivo.

Para especificar el tipo de nota que se capturará cuando los usuarios que ponen un pedido de ventas en espera especifiquen notas opcionales, vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes** y, a continuación, en la ficha desplegable **Configurar ventas**, en la pestaña **General**, establezca el campo **Tipo de nota**. Use el campo **Estado del pedido de ventas retenido** para definir el color que se usará para resaltar los pedidos de ventas que están en espera cuando se vean en la página **Servicio al cliente**.

Para crear un conjunto opcional de códigos de motivo de espera, vaya a **Retail** \> **Configuración del canal** \> **Códigos de información**. Estos códigos de información se pueden usar como código de motivo secundario para refinar el código de bloqueo principal. Seleccione **Nuevo** para crear un conjunto de códigos de motivos, y después seleccione **Subcódigos** para definir la lista de motivos adicionales. Para vincular los códigos de información que defina al canal de centro de asistencia telefónica, vaya **Retail** \> **Canales** \> **Centros de asistencia telefónica** \> **Todos los centros de asistencia telefónica**. En la ficha desplegable **General**, establezca el campo **Código de bloqueo**.

## <a name="putting-orders-on-hold"></a>Retener pedidos de ventas

Los pedidos que los usuarios del centro de asistencia telefónica crean en el programa de ventas al por menor de back-office pueden retenerse manual o automáticameante en situaciones específicas.

Durante la entrada de pedidos, pero antes de enviar y confirmar pedidos, los usuarios del centro de asistencia telefónica podrían desear poner un pedido en espera para evitar que se entregue al almacén para continuar el proceso. Por ejemplo, puede que el cliente que realiza el pedido no esté listo para confirmarlo o puede que falten datos críticos para procesar el pedido.

En la página entrada de pedidos, el usuario del centro de asistencia telefónica puede poner un pedido en espera mediante la opción **Bloqueos del pedido** en la pestaña **Pedido de ventas** del menú de entrada de pedidos. De manera alternativa, el usuario puede seleccionar el elemento de menú **Bloqueo** en la página **Resumen de pedido de ventas** que aparece al seleccionar **Completado** en un pedido de ventas del centro de llamadas.

En ambos casos, la página **Bloqueos del pedido** aparece. El usuario puede entonces seleccionar **Nuevo** para crear un bloqueo para el pedido. En el campo **Código de bloqueo**, el usuario debe seleccionar el código que mejor describe el motivo del bloqueo. En el campo **Código de motivo**, el usuario puede seleccionar opcionalmente un código adicional para proporcionar un segundo nivel de descripción de bloqueo.

En la ficha desplegable **Notas**, en el campo **Notas de bloqueo**, el usuario puede especificar notas adicionales, de texto libre, para proporcionar contexto adicional o información acerca del bloqueo. Estas notas pueden ayudar a otros usuarios que revisen el pedido bloqueado o trabajen con él más adelante.

Una vez especificada y guardada la información de bloqueo, el usuario puede cerrar la página **Bloqueos del pedido**. A continuación se devuelve al usuario a la página de entrada de pedidos de ventas. Si no se requieren ninguna otra acción en el pedido de ventas, el usuario puede cerrar la página de entrada de pedidos de ventas.

Si el indicador **Habilitar finalización de pedidos** está activado en el canal del centro de asistencia telefónica, el pago no tiene que aplicarse a un pedido que se haya puesto en espera. Por el contrario, para un pedido de ventas que no esté en espera, el usuario no puede salir de la página de entrada de pedidos de ventas hasta que no se haya aplicado el pago. Por supuesto, se exigirá el pago antes de liberar el bloqueo del pedido.

Además, los usuarios del centro de asistencia telefónica pueden colocar un bloqueo manual de fraudes en los pedidos que sean sospechosos por algún motivo. Los pedidos también pueden ponerse en espera automáticamente cuando coincidan con los criterios y las reglas de fraude activos. Para obtener más información acerca de este tipo de bloqueo de pedido, consulte [Configurar alertas de fraude](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Visualización y gestión de los pedidos que están en espera

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Ver información en espera de un único pedido de ventas

En la página **Servicio al cliente**, los usuarios pueden visualmente identificar los pedidos que están en espera, dado que las líneas de pedido se destacan de un color específico. Este color se define en el campo **Estado del pedido de ventas retenido** en la página **Parámetros de clientes**.

> [!NOTE]
> Si la línea está seleccionada en la página, el color de resalte no está visible.

Los usuarios también pueden ver la información detallada de estado de un pedido de ventas para saber si el pedido está en espera. La información del estado detallada se puede acceder desde la página **Todos los pedidos de ventas** o **Servicio al cliente**. Si un pedido está en espera, el indicador **No procesar** se establece para él, y el campo **Estado detallado** muestra el estado **en espera** o **Bloqueo de fraudes**, en función de la situación de ejemplo.

Para ver los detalles de un bloqueo de pedido individual, los usuarios pueden abrir una vista detallada de la página **Bloqueo del pedido** de la página **Servicio al cliente**, mediante el menú **Opciones** del pedido seleccionado. Los usuarios también pueden acceder a esta vista desde la página **Todo el pedido de ventas**, seleccionando el elemento de menú **Bloqueos del pedido** en la pestaña **pedido de ventas**.

### <a name="viewing-all-orders-that-are-on-hold"></a>Visualización de todos los pedidos que están en espera

Para ver todos los pedidos que se han colocado en bloqueo manual o automático, vaya a **Retail** \> **Clientes** \> **Bloqueos del pedido**.

El banco de trabajo **bloqueos de pedido** proporciona una lista de todos los pedidos que están en espera debido a acciones de retención manuales o relacionadas con fraude. Aprovechándose de las opciones de filtrado y de ordenación estándar de la página, los usuarios pueden crear vistas con las que pueden trabajar o gestionar códigos de bloqueo específicos cuya revisión esté bajo su responsabilidad. El banco de trabajo **Bloqueos de pedido** también indica el número de días que el pedido ha estado en espera. Esta información puede ayudar a los usuarios a dar prioridad a la cola.

Para obtener una visión más detallada de los pedidos que están en espera, los usuarios pueden hacer clic en la opción **Bloqueo del pedido** del menú. Esta información que proporciona información sobre el cliente, todas las notas que se han aplicado al pedido, el cliente o a la acción de bloqueo. La vista también proporciona detalles sobre el motivo de un bloqueo automático, si el pedido se puso en espera porque coincidió con una regla de fraude.

En la vista de la lista y la vista detallada de la página **Bloqueos del pedido**, los usuarios pueden ver o editar información adicional relacionada con el pedido, como los pagos, los totales, y las notas.

Las opciones de la pestaña **Retener finalización de la compra** pueden ser útiles si varios usuarios de su empresa trabajan en la cola de bloqueo al mismo tiempo. Si selecciona la opción **Desproteger**, los usuarios pueden indicar que trabajan para revisar y para investigar el bloqueo del pedido. De esta manera, otros usuarios no perderán el tiempo intentando hacer el mismo trabajo. En la vista detallada de la página **Bloqueos del pedido**, los usuarios pueden ver información sobre la fecha y la hora de desprotección, y el usuario que desprotegió el registro de bloqueo.

Después de que se desproteja un registro de bloqueo, solo el usuario que lo desprotegió puede borrar el desbloqueo. Esta restricción se ha creado para evitar que los usuarios tomen los registros donde otros usuarios ya están trabajando. Para liberar un pedido de nuevo a la cola para que otros usuarios puedan trabajar con él, el usuario que desprotegió el registro selecciona la opción **Liberar desprotección**.

> [!NOTE]
> El bloqueo no se libera cuando se libera la desprotección.

En algunos casos, como cuando un usuario está enfermo o ha dejado de trabajar para la empresa, es posible que los registros que dicho usuario ha desprotegido deban reasignarse a otro usuario. Un administrador puede reasignar los registros mediante la opción **Anular finalización de la compra**.

## <a name="releasing-orders-that-are-on-hold"></a>Liberar pedidos que están en espera

En la vista de la lista y la vista detallada de la página **Bloqueos del pedido**, la pestaña **Liberar retención** contiene las opciones que se usan para liberar un bloqueo del pedido. Utilice la opción **Liberar retención** para liberar un pedido del código de bloqueo seleccionado.

Los pedidos de centro de asistencia telefónica requieren un pago. Por lo tanto, un bloqueo no se puede liberar completamente si el pago no se ha aplicado al pedido. En la página **Parámetros de centro de asistencia telefónica**, en la pestaña **Bloqueos**, asegúrese de que el parámetro **Enviar cuando se libere** esté activada. Este valor ayuda a garantizar que un pedido de bloqueo liberado siga la lógica de envío del pedido correcta para validar y autorizar pagos. Si faltan pagos, el usuario recibe un error, y el código de bloqueo no se libera.

Si el parámetro **Enviar cuando se libere** no se ha establecido, los usuarios deben seleccionar la opción **Liberar y enviar** en el menú **Liberar bloqueo** para ayudar a garantizar que el pedido pase todas las validaciones necesarias de pago. Si el envío del pedido falla cuando el indicador **Habilitar finalización de pedidos** está activado en el canal de centro de asistencia telefónica, el pedido se libera de su estado de bloqueo, pero de los indicadores **No procesar** seguirán establecidos. Por lo tanto, el pedido no se libera al almacén hasta que se hayan aplicado y se hayan validado los pagos correctos.

Si los usuarios desean liberar un bloqueo pero realizar cambios adicionales al pedido antes de que este se haya liberado para continuar el proceso, pueden seleccionar la opción **Liberar y modificar**. Esta opción permite quitar el bloqueo codificado y abre los detalles del pedido de ventas de modo que los usuarios puedan realizar cambios adicionales al pedido. Los usuarios también pueden aplicar el pago y enviar el pedido de ventas con la lógica de validación del pago cuando el indicador **Habilitar finalización de pedidos** está activada en el canal del centro de llamadas.

## <a name="reporting-options"></a>Opciones del informe

Vaya a **Retail** \> **Consultas e informes** \> **Informes de centro de asistencia telefónica** \> **Informe de bloqueos del pedido** para ejecutar un informe acerca de los bloqueos del pedido por intervalo de fechas, código de espera, u otros criterios relacionados.

