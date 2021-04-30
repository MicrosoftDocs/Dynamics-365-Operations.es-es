---
title: Colaboración de proveedor con proveedores externos
description: Este tema explica cómo los agentes de compras pueden colaborar con los proveedores externos para intercambiar información sobre los pedidos de compra y el inventario de entrega.
author: kamaybac
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart, PurchaseOrderResponseActionRemarks, PurchVendorPortalAllResponse, PurchOrderInExternalReview, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5f0ed7d3344b43c477923ebd8c69acfb6630e6f4
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910410"
---
# <a name="vendor-collaboration-with-external-vendors"></a>Colaboración de proveedor con proveedores externos

[!include [banner](../includes/banner.md)]

El módulo de **Colaboración del proveedor** se indica para los proveedores que no tienen integración de Intercambio de datos electrónicos (EDI) con Microsoft Dynamics 365 Supply Chain Management. Permite a los proveedores trabajar con pedidos de compra (PO), facturas, información de inventario de entrega, solicitudes de presupuesto (RFQ) y también las permite tener acceso a parte de los datos maestros de proveedores. Este tema explica cómo puede colaborar con los proveedores externos que usan la interfaz de colaboración de proveedor para trabajar con PO, solicitudes de presupuesto y el inventario de entrega. También explica cómo permitir a un proveedor específico utilizar la colaboración de proveedor y cómo definir la información que verán todos los proveedores cuando respondan a un PO.

Para obtener más información sobre lo que pueden hacer los proveedores externos en la interfaz de colaboración de proveedor, consulte [Colaboración de proveedor con los clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).

> [!NOTE]
> La información sobre la colaboración del proveedor en este tema sólo se aplica a la versión actual de Supply Chain Management. En Microsoft Dynamics AX 7.0 (febrero de 2016) y en Microsoft Dynamics AX versión de aplicación 7.0.1 (mayo de 2016), colabora con proveedores a través del módulo **Portal de proveedores**. Para obtener información sobre el módulo **Portal de proveedores**, consulte [Colaborar con proveedores mediante el portal de proveedores](collaborate-vendors-vendor-portal.md).

Para obtener más información sobre cómo los proveedores pueden utilizar la colaboración del proveedor en los procesos de facturación, consulte [Área de trabajo de facturación de colaboración de proveedor](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md). Para obtener información sobre cómo suministrar nuevos usuarios de colaboración de proveedor, consulte [Gestionar usuarios de colaboración del proveedor](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definir la información que se muestra a los proveedores cuando responden a los PO

Cuando los proveedores responden a un PO que les envía, ven uno de los tres de buzones de mensajes, donde deben confirmar que desean aceptar el PO, rechazarlo o aceptarlo con cambios. Puesto que la información que se debe mostrar al proveedor en ese momento puede ser específica para su negocio, puede especificar el texto que aparece en cada uno de los mensajes de confirmación. Por ejemplo, el texto puede notificar al proveedor sobre los siguientes pasos del proceso, o sobre los términos y condiciones.

Para definir el texto que se muestra en la respuesta del PO, suga estos pasos:

1. En la página **Información para los proveedores que responden al PO**, seleccione el tipo de respuesta y, a continuación, seleccione **Editar**.
2. En la casilla **Mensaje de información**, especifique la información que se debe mostrar a los proveedores en el cuadro de mensaje.

Si tiene que agregar mensajes en más de un idioma, cree mensajes separados y especifique los códigos de idioma adecuados para cada uno. Se mostrará el mensaje a cada proveedor en el idioma que este use el proveedor.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Configurar las opciones de colaboración de proveedor para un proveedor específico

Un administrador configura una configuración general para la colaboración de proveedor en Supply Chain Management, como los roles de seguridad disponibles para todos los proveedores con los que colabore. Sin embargo, también hay algunos ajustes que pueden ser diferentes para cada cuenta de proveedor. Debe configurar estos valores.

- Habilitar la colaboración de proveedor.
- Especificar si el proveedor debería ver información de precios.

### <a name="enabling-vendor-collaboration"></a>Habilitar la colaboración de proveedor

Antes de que las cuentas de usuario se puedan crear para un proveedor externo, deberá configurar la cuenta de proveedor para permitir que utilice la colaboración de proveedor. En la página **Proveedores**, en la pestaña **General** configure el campo **Activación de colaboración**. Las opciones siguientes están disponibles:

- **Activo (el PO se confirma automáticamente)**: los PO se confirman de forma automática si el vendedor los acepta sin cambios.
- **Activo (el PO no se confirma automáticamente)**: es necesario que su oganización confirme los PO manualmente cuando el proveedor los haya aceptado.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Especificar si el proveedor debería ver información de precios

Para compartir información de precios del PO a través de la interfaz de colaboración del proveedor, debe establecer la opción **Importe/precios de pedido de compra** en la pestaña **Valores predeterminados del pedido de compra** para la cuenta del proveedor en **Sí**. Esta información de precios incluye el precio por unidad, los descuentos, y los gastos.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Trabajar con PO cuando se usa la colaboración del proveedor

### <a name="sending-a-po-to-a-vendor"></a>Enviar un PO a un proveedor

Los PC se preparan en Supply Chain Management. Cuando un PO tiene un estado de **Aprobado**, se envía al proveedor mediante la selección de **Enviar para su confirmación** en la página **Pedido de compra**. El estado del PO cambia a **En proceso de revisión externa**. Después de enviar el PO, el proveedor puede consultarlo en la página **Pedidos de compra para revisar** de la interfaz de colaboración del proveedor. El proveedor puede aceptar el PO, rechazarlo o sugerir cambios en el mismo. El proveedor también puede agregar comentarios para comunicar información como cambios al pedido de compra. Si quiere que el proveedor se fije en un nuev PO, también puede usar el sistema de gestión de impresión para enviar el PO por correo electrónico.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>Confirmación y aceptación de un PO por parte del proveedor

Después de que un proveedor acepte un PO, el PO puede ser confirmado automáticamente o es posible que tenga que ser confirmado manualmente. Esto depende de si el campo de **Activación de la colaboración** está configurado como **Activo (el PO se confirma automáticamente)** o como **Activo (el PO no se confirma automáticamente)** por parte del proveedor.

La siguiente tabla muestra el intercambio de información normal, en función de la respuesta del proveedor cuando se le envía un PO para su confirmación.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Respuesta del proveedor</th>
<th>Resultado</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>El proveedor <strong>acepta</strong> el pedido y Supply Chain Management está configurado para confirmar automáticamente que el proveedor acepta.</td>
<td>El estado del pedido se actualiza a <strong>Confirmado</strong>. Si algo impide que el pedido se actualice, la respuesta del proveedor se registra igualmente como <strong>Aceptado</strong> pero el estado del PO permanece como <strong>En revisión externa</strong>. 

El PO que se envió al proveedor y que se encuentra en estado de <strong>En revisión externa</strong> se actualiza con las fechas de entrega confirmadas en las líneas. Esta actualización inicia una nueva versión que se configura automáticamente en estado <strong>Confirmado</strong>. Cuando se confirma el PO, este aparece en la interfaz de colaboración del proveedor.</td>
</tr>
<tr class="odd">
<td>El proveedor <strong>acepta</strong> el pedido, pero Supply Chain Management no está configurado para confirmar automáticamente PC que el proveedor acepta.</td>
<td>La respuesta del proveedor se registra como <strong>Aceptado</strong> pero el estado del PO permanece como estado <strong>En revisión externa</strong>.

El PO que se envió al proveedor y que se encuentra en estado de <strong>En revisión externa</strong> se actualiza con las fechas de entrega confirmadas en las líneas. Esta actualización inicia una nueva versión que se configura automáticamente en estado <strong>En revisión externa</strong>. A continuación puede confirmar manualmente el PO.</td>
</tr>
<tr class="even">
<td>El proveedor <strong>rechaza</strong> el pedido.</td>
<td>La respuesta del proveedor se registra como <strong>Rechazado</strong> y el estado de la OC permanece en estado <strong>Revisión externa</strong>. El rechazo se recibe junto con la nota de los proveedores.</td>
</tr>
<tr class="odd">
<td>El proveedor <strong>acepta</strong> el pedido <strong>con los cambios</strong>. Los cambios se sugieren en el nivel de línea. El proveedor puede aceptar o rechazar líneas individuales. A continuación se muestran algunos otros cambios que el proveedor puede sugerir:
<ul>
<li>Cambiar fechas o cantidades.</li>
<li>Divida las líneas para las diferentes fechas de entrega o cantidades.</li>
<li>Sustituir un artículo.</li>
</ul>
El proveedor no puede cambiar la información de precios y gastos. Sin embargo, el proveedor puede sugerir estos cambios mediante notas.</td>
<td>La respuesta del proveedor se registra como <strong>Aceptado con cambios</strong>, y el estado del PO se mantiene como <strong>En revisión externa</strong>. Los estados muestran los tipos de cambios que ha sugerido el proveedor. Para obtener más información sobre el consumo automático de los cambios, consulte la sección siguiente de este tema, sobre &quot;actualizar el PO cuando un proveedor sugiere cambios&quot;. </td>
</tr>
</tbody>
</table>

Puede usar el espacio de trabajo de espacio de trabajo **Preparación del pedido de compra** para supervisar a qué PO ha respondido el proveedor. Este espacio de trabajo contiene dos listas que albergan PO con el estado **En revisión externa**:

- En revisión externa requiere acción
- En revisión externa, en espera de respuesta del proveedor

### <a name="changing-a-po"></a>Cambiar un PO

Para cambiar un PO que ya ha sido respondido por el proveedor, debe enviar una nueva versión del PO al proveedor. El nuevo PO tendrá un sufijo de versión para indicar que es una versión modificada de un PO que se envió anteriormente. La página del **Historial de confirmación del proveedor del pedido de compra** le permite a usted y a sus proveedores hacer seguimiento del historial de cada pedido. La versión confirmada anteriormente de un PO permanece en la lista de PO confirmados hasta que se confirme el nuevo PO.

### <a name="canceling-a-po"></a>Cancelar un PO

Al cancelar un PO, el estado se cambia a **Aprobado**. Debe enviar el pedido de compra al proveedor de modo que pueda confirmar o rechazar la cancelación. Después de que se confirme la cancelación, la OC aparece en la lista de OC confirmadas del proveedor como **Cancelado**.

### <a name="adding-attachments-to-a-po"></a>Añadir datos adjuntos a un PO

Puede añadir datos adjuntos como archivos, imágenes y notas al PO mediante el sistema de gestión de documentos. Los datos adjuntos del tipo **Externo** serán visibles para el proveedor cuando le envíe el PO.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>Actualizar el PO cuando un proveedor sugiere cambios

Si un proveedor ha respondido al PO y sugerido cambios, el paso siguiente es procesar la respuesta.

En el espacio de trabajo **Preparación del pedido de compra**, en la lista **En revisión externa requiere acción**, puede identificar un PO al que un proveedor respondió como aceptado con cambios. De esta lista, también puede navegar a la respuesta del proveedor.

En una respuesta, un proveedor puede cambiar la siguiente información del encabezado:
 
- Referencia de documento de proveedor
- Modo de entrega
- Condiciones de entrega
- Fecha de entrega confirmada

El proveedor también puede agregar una nota o datos adjuntos.

En las líneas, el proveedor puede cambiar la cantidad y las fechas de entrega, agregar notas y datos adjuntos, rechazar una línea, sustituir una línea por otro producto que esté introducido como texto y dividir una línea en varias entregas. El estado de la línea varía, en función de los cambios que el proveedor ha sugerido:
    
- **Aceptado con cambios**
- **Rechazado**
- **Sustituido**: En este caso, se agregará una línea adicional que tenga el estado **Sustituir**.
- **Confirmado**
- **Dividir en programación**: En este caso, se agregarán líneas adicionales que tengan el estado **Líneas de programación**.

Si una línea no tiene cambios, el estado de la línea es **Aceptado**.

En la respuesta, los estados de línea indican los tipos de cambios que realizó el proveedor. Además, todos los campos cambiados aparecen en negrita para ayudarle a identificar los cambios.

Puede actualizar un PO seleccionando **Procesar actualización de PO** en la respuesta o en una línea al mismo tiempo. Un campo **¿Se ha procesado la actualización del PO?** en el encabezado y las líneas le indica si el sistema ha procesado el encabezado o las líneas para actualizar el PO con los posibles cambios que se originen de la respuesta. Puede ejecutar la acción **Procesar actualización de PO** solo una vez por encabezado o línea.

No todos los cambios sugeridos se pueden actualizar en un PO. Solo se actualiza en el encabezado, y las actualizaciones de fechas y cantidades en las líneas se pueden actualizar automáticamente en el PO. Para otros cambios, debe actualizar manualmente el PO. En este caso, el valor del campo **¿Se ha procesado la actualización del PO?** es **Actualización manual**. Por ejemplo, si un proveedor sugiere que una línea se divda en una programación, este cambio se debe realizar manualmente.

Cada línea que tenga un estado **Aceptado** tendrá una fecha de entrega confirmada. Cuando se ejecuta la acción **Procesar actualización de PO**, esta fecha se actualiza en el PO. Las notas y los datos adjuntos no se transfieren automáticamente al PO actual. Además, los acuerdos comerciales no se revaluarán en las líneas de PO cuando actualice el PO actual a través de la acción **Procesar actualización de PO**.

## <a name="po-statuses-and-versions"></a>Estados y versiones de PO

Esta sección describe los distintos estados que un PO puede tener hasta el momento en que se confirma. También describe cuándo se ponen a disposición para el proveedor las nuevas versiones del PO. El comportamiento varía en función de si usa la gestión de cambios para los PO. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versiones y estados si no utiliza la gestión de cambios

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC.

| Acción | Estado y versión |
|--------|--------------------|
| La versión inicial del PC se crea en Supply Chain Management. | El estado es **Aprobado**. |
| El PO se envía al proveedor. | Una versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**. |
| El proveedor envía una respuesta de **Aceptado con los cambios**. | El estado aún está **En revisión externa**. |
| Tiene que realizar algunos cambios que pide el proveedor. | El estado se cambia a **Aprobado**. |
| Envíe la nueva versión del PO al proveedor. | Una nueva versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**. |
| El proveedor acepta la nueva versión del PO. | El estado aún está **En revisión externa**, a menos que la cuenta de proveedor se haya configurado para establecer automáticamente el estado del PO a **Confirmado** cuando lo acepta. |

Los proveedores no tienen que confirmar el PO mediante la interfaz de colaboración de proveedor. También pueden enviar un mensaje de correo electrónico o comunicar la aceptación de un PO a través de otros canales. A continuación puede confirmar manualmente el pedido. En este caso, recibirá una advertencia de que se está confirmando el pedido aunque no haya respuesta del proveedor. El PO aparece a continuación en el historial de confirmaciones como un pedido confirmado abierto que no tiene ninguna respuesta. En este momento, el proveedor ya no tiene la opción de confirmar o de rechazar el PO.

> [!NOTE]
> La versión del PO que está disponible para otros procesos en Supply Chain Management siempre es la última versión, incluso si dicha versión no se ha registrado todavía en la interfaz de colaboración del proveedor.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versiones y estados si utiliza la gestión de cambios

Si se ha habilitado la gestión de cambios para los PO, el PO pasa por un flujo de trabajo de aprobación para lograr el estado de **Aprobado**. Este proceso no es visible para el proveedor.

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC cuando está activada la gestión de cambios. Una versión se registra cuando se aprueba el PO, no cuando el PO se envía al proveedor o se confirma.

| Acción | Estado y versión |
|--------|--------------------|
| La versión inicial del PC se crea en Supply Chain Management. | El estado es **Borrador**. |
| La OC se envía al proceso de aprobación. (El proceso de aprobaciónes un proceso interno en el que el proveedor no está involucrado.) | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si la OC no se rechaza durante el proceso de aprobación. El pedido de compra aprobado se registra como versión. | 
| El PO se envía al proveedor. | La versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**. |
| Tiene que realizar algunos cambios que pide el proveedor, ya sea manualmente o mediante la acción **Procesar actualización del PO** en la respuesta para actualizar el PO. | El estado se vuelve a cambiar a **Borrador**. |
| La OC se envía al proceso de aprobación de nuevo. | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si la OC no se rechaza durante el proceso de aprobación. De manera alternativa, el sistema puede estar configurado de modo que los cambios de campo específicos no necesitan volver a ser aprobados. En este caso, el estado cambia primero a **Borrador** y a continuación se actualizan automáticamente a **Aprobado**. El pedido de compra aprobado se registra como nueva versión. |
| Envíe la nueva versión del PO al proveedor. | La nueva versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**. |
| El proveedor aprueba la nueva versión de la OC. | El estado se cambia a **Confirmado** automáticamente o cuando reciba la respuesta del proveedor y después confirma la OC. |

## <a name="sharing-information-about-consignment-inventory"></a>Compartir la información acerca del inventario de entrega

Si está usando el inventario de entrega, los proveedores pueden usar la interfaz de colaboración del proveedor para visualizar la información de las siguientes páginas:

- **Pedidos de compra que consumen el inventario de entrega**: los PO del inventario de entrega se generan cuando la propiedad del inventario pasa del proveedor a la empresa. El recibo del producto se publica al mismo tiempo. Estos PO de entrega solo se muestran en la página de **Pedidos de compra que consumen el inventario de entrega**. No se incluyen en la página **Todos los pedidos de compra confirmados** del módulo **Colaboración de proveedor**.
- **Productos recibidos del inventario de entrega**: esta página muestra todas las transacciones en las que la titularidad de los productos se ha transferido del proveedor a la empresa. Los proveedores pueden usar esta información para facturar al cliente.
- **Inventario de entrega disponible**: esta página muestra el inventario de entrega disponible que es propiedad del proveedor que se ha recibido en su almacén.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Trabajar con solicitudes de presupuesto cuando se usa la colaboración del proveedor

Esta sección describe las interacciones entre clientes y proveedores durante el proceso de solicitud de presupuesto. También explica cómo se comunica la información a los proveedores. Para una visión general básica del soporte para el proceso de solicitud de presupuesto, consulte [Visión general de las solicitudes de presupuesto](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Suplentes, datos adjuntos, modificaciones, y devoluciones

- **Suplentes**: En la cabecera de un caso de solicitud de presupuesto, puede especificar que se permiten suplentes para las líneas de artículos de fuera del catálogo. Cuando se habilitan los suplentes, los proveedores pueden agregar una línea alternativa para cada línea solicitada.
- **Datos adjuntos**: Los adjuntos se pueden agregar tanto a nivel de encabezado como el nivel de línea de un caso de solicitud de presupuesto. Los adjuntos se pueden clasificar como internos o externos. Los datos adjuntos internos se pueden ver únicamente en el lado del cliente, mientras que los proveedores pueden ver los datos adjuntos externos después de que se los envíen.

    Los proveedores también pueden agregar datos adjuntos en su respuesta de la oferta. Estos archivos adjuntos se pueden ver en el lado de cliente después de que un proveedor envíe la respuesta de la oferta. Los datos adjuntos que agregan los proveedores se clasifican siempre como externos. Para acceder a los datos adjuntos que un proveedor ha enviado junto con una oferta, seleccione **Datos adjuntos de la oferta** o **Datos adjuntos de la línea de la oferta**.
    
    Para abrir los archivos adjuntos que se envían junto con el caso de solicitud de presupuesto, use el símbolo de clip de papel en la respuesta.

- **Modificaciones** Cuando finaliza una modificación, se eliminan las respuestas de una oferta existentes para que se puedan reemplazar por los valores actualizados. La información como el precio y la cantidad de la línea de respuestas anteriores de la oferta se puede ver a través de los diarios en el caso de solicitud de presupuesto.

    Para aplicar el procesamiento de la modificación, en la página **Parámetros de adquisición y abastecimiento** , en la ficha desplegable **Solicitud de presupuesto**, establezca la opción **Bloquear solicitudes de presupuesto cuando se envíen** en **Sí**. (Esta opción se establece y se requiere para el sector público).

- **Devoluciones**: Si un proveedor ha enviado una oferta, pero se requiere más información o modificaciones para el caso de solicitud de presupuesto, el cliente puede devolver la oferta al proveedor. Los datos de la oferta que se registró anteriormente se conservan y el proveedor puede hacer las modificaciones solicitadas sin tener que reiniciar el proceso de la oferta.

## <a name="public-sector-extensions"></a>Extensiones del sector público

Para el sector público, la funcionalidad extendida habilita un caso de solicitud de presupuesto para enviarlo a los proveedores y publicarlo. Cuando publica una solicitud de presupuesto, cualquier persona que solicite la información puede ver el trabajo que cumpla con la mayoría de directivas el sector público. Todo el trabajo disponible se refleja en la página de lista **Solicitudes de presupuestos publicadas abiertas** y las solicitudes de presupuesto canceladas, pendientes o concedidas se pueden ver en la página de lista **Solicitudes de presupuesto publicadas cerradas** . Estos documentos también se pueden ver en el sitio fuera de Supply Chain Management a través de integraciones con las siguientes entidades de datos:

- Solicitudes de presupuestos publicadas
- Solicitudes publicadas para línea de presupuestos
- Solicitudes publicadas para datos adjuntos de encabezado de presupuestos

Estas entidades permiten que las personas que no sean usuarios aprovisionados de Supply Chain Management, pero que tenga acceso anónimo a un sitio externo, vean los trabajos disponibles y cerrados. Además, funciones ampliadas en **Registrar y enviar** permiten al usuario que configura los parámetros del proceso de solicitud de presupuesto definir una plantilla de correo electrónico. A continuación, cuando el profesional de compras crea el caso de solicitud de presupuesto, debe seleccionar la plantilla de correo electrónico para enviar la información necesaria a los proveedores en el caso de solicitud. 

El usuario que configura los parámetros del proceso de solicitud de presupuesto puede crear varias plantillas de correo electrónico. Estas plantillas de correo electrónico pueden contener tanto texto estático como los siguientes tokens de sustitución. Los tokens se reemplazarán con valores contextuales cuando se cree un correo electrónico.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Si se requiere una modificación y se configura después de que se envíe la solicitud de presupuesto, la solicitud de presupuesto se reenviará a todos los proveedores invitados. El documento publicado también se actualizará en la página **Solicitudes de presupuesto publicadas abiertas**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]