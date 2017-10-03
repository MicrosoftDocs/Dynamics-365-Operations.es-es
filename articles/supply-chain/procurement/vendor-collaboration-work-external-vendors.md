---
title: "Colaboración de proveedor con proveedores externos"
description: "Este tema describe cómo los agentes de compras pueden colaborar con los proveedores externos para intercambiar información sobre los pedidos de compra y el inventario de envío."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: cbd099403f48b502ca74bcb38ae12decedb8f2da
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Colaboración de proveedor con proveedores externos

[!include[banner](../includes/banner.md)]


Este tema describe cómo los agentes de compras pueden colaborar con los proveedores externos para intercambiar información sobre los pedidos de compra y el inventario de envío.

El módulo de **Colaboración del proveedor** se indica para los proveedores que no tienen integración de Intercambio de datos electrónicos (EDI) con Microsoft Dynamics 365 for Finance and Operations. Permite a los proveedores trabajar con información sobre el pedido de compra, la factura y el inventario de envío. Este tema describe cómo puede colaborar con los proveedores externos que usan la interfaz de colaboración de proveedor para trabajar con PO y el inventario de envío. También explica cómo permitir a un proveedor específico utilizar la colaboración de proveedor, y cómo definir la información que verán todos los proveedores cuando respondan a un PO. Para obtener más información sobre lo que pueden hacer los proveedores externos en la interfaz de colaboración de proveedor, consulte [Colaboración de proveedor con los clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Para obtener más información sobre cómo los proveedores pueden utilizar la colaboración del proveedor en los procesos de facturación, consulte [Área de trabajo de facturación de colaboración de proveedor](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Para obtener información sobre cómo suministrar nuevos usuarios de colaboración de proveedor, consulte [Gestionar usuarios de colaboración del proveedor](manage-vendor-collaboration-users.md).

Para obtener más información sobre cómo los proveedores pueden utilizar la colaboración del proveedor en los procesos de facturación, consulte [Área de trabajo de facturación de colaboración de proveedor](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). 

Para obtener información sobre cómo suministrar nuevos usuarios de colaboración de proveedor, consulte [Gestionar usuarios de colaboración del proveedor](manage-vendor-collaboration-users.md).

## <a name="define-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definir la información que se muestra a los proveedores cuando responden a los PO
Cuando los proveedores responden a un PO que les envía, ven un cuadro de mensaje donde deben confirmar que desean aceptar el PO, rechazarlo o aceptarlo con cambios. Puesto que la información que se debe mostrar al proveedor en ese momento puede ser específica para su negocio, puede especificar el texto que aparece en cada uno de los tres mensajes de confirmación. Por ejemplo, el texto puede notificar al proveedor sobre los siguientes pasos del proceso, o sobre los términos y condiciones.  

Para definir el texto que se muestra en la respuesta del PO:

1.  Abra la información de la página **Información para proveedores en respuesta a los PO**.
2.  Seleccione uno de los siguientes tipos de respuesta.
3.  Haga clic en **Editar**.
4.  Escriba la información que desea que los proveedores vean en el cuadro **Mensaje de información**.

Si tiene que agregar mensajes en más de un idioma, cree mensajes aparte y especifique los códigos de idioma adecuados para cada uno. Se mostrará el mensaje al proveedor en el idioma que este usa.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Configurar las opciones de colaboración de proveedor para un proveedor específico
La configuración general para la colaboración del proveedor en Finance and Operations las configura un administrador. Por ejemplo, un administrador determinará qué roles de seguridad están disponibles para todos los proveedores con los que colabora. También algunos ajustes que pueden ser diferentes para cada cuenta de proveedor, y se deben establecer estos:
-   Habilitar la colaboración de proveedor.
-   Decida si desea que el proveedor vea la información de precios.

### <a name="enable-vendor-collaboration"></a>Habilitar la colaboración de proveedor

Antes de que las cuentas de usuario se pueden crear para un proveedor externo, deberá configurar la cuenta de proveedor para permitir que utilicen la colaboración del proveedor. Para ello, configure el campo **Activación de la colaboración** para activarla en la ficha **General** de la página **Proveedores**. Existen dos opciones que puede elegir:

-   **Activo (el PO se confirma automáticamente)**: los pedidos de compra se confirman de forma automática cuando el vendedor los acepta sin cambios.
-   **Activo (el PO no se confirma automáticamente)**: es necesario que los pedidos de compra se confirmen manualmente por parte de la empresa cuando el proveedor los haya aceptado.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Decida si desea que el proveedor vea la información de precios

Si desea compartir información de precios como precio por unidad, descuentos y gastos mediante la interfaz de colaboración, necesita configurar la opción de **Importe/precios de pedido de compra** a **Sí** en la cuenta de proveedor. Esta opción está disponible en la ficha **Valores predeterminados del pedido de compra**.

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Trabajar con PO cuando se usa la colaboración del proveedor
### <a name="sending-a-po-to-the-vendor"></a>Enviar un PO al proveedor

Los pedidos de compra se preparan en Finance and Operations. Cuando el PO tiene un estado de **Aprobado**, se envía al proveedor mediante la acción **Enviar para su confirmación** en la página **Pedido de compra**. El estado del PO cambia a **En proceso de revisión externa**. Después de enviar el PO, el proveedor puede consultarlo en la página **Pedidos de compra para revisar** de la interfaz de colaboración del proveedor. El proveedor puede aceptar el pedido, rechazarlo o sugerir cambios en el mismo. El proveedor también puede agregar comentarios para comunicar información como cambios al pedido de compra. Si quiere que el proveedor se fije en una nueva OC, también puede usar el sistema de gestión de impresión para enviar la OC por correo electrónico.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Confirmación y aceptación del PO por parte del proveedor

Cuando un proveedor ha aceptado un pedido de compra, el PO puede confirmarse automáticamente, o es posible que necesite confirmarse de forma manual. Esto depende de si el campo de **Activación del proveedor** está configurado como **Activo (el PO se confirma automáticamente)** o como **Activo (el PO no se confirma automáticamente)** por parte del proveedor.  

La siguiente tabla muestra el intercambio de información normal, en función de cómo responde el proveedor cuando se le envía un PO para su confirmación.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Respuesta del proveedor</strong></td>
<td><strong>Resultado</strong></td>
</tr>
<tr class="even">
<td>El proveedor <strong>acepta</strong> el pedido. Finance and Operations se configura para confirmar automáticamente los PO cuando el proveedor los acepta.</td>

<td>El estado del pedido se actualiza a <strong>Confirmado</strong>. Si algo impide que el pedido se actualice, la respuesta del proveedor se registra igualmente como <strong>Aceptado</strong> pero el estado del PO permanece como estado <strong>En revisión externa</strong>. 

El PO que se envió al proveedor y que se encuentra en estado de **En revisión externa** se actualiza con las fechas de entrega confirmadas en las líneas. La actualización inicia una nueva versión que se actualizará automáticamente a estado **Confirmado**. Cuando se confirma el PO, este aparecerá en la interfaz de colaboración del proveedor.</td>
</tr>
<tr class="odd">
<td>El proveedor <strong>acepta</strong> el pedido. Finance and Operations no se configura para confirmar automáticamente los PO cuando el proveedor los acepta.</td>
<td>La respuesta del proveedor se registra como <strong>Aceptado</strong> pero el estado del PO permanece como estado <strong>En revisión externa</strong>.

El PO que se envió al proveedor y que se encuentra en estado de **En revisión externa** se actualiza con las fechas de entrega confirmadas en las líneas. La actualización inicia una nueva versión que se establecerá en **En revisión externa**. A continuación, podrá confirmar manualmente el PO.</td>

</tr>
<tr class="even">
<td>El proveedor <strong>rechaza</strong> el pedido.</td>
<td>La respuesta del proveedor se registra como <strong>Rechazado</strong> y el estado de la OC permanece en estado <strong>Revisión externa</strong>. El rechazo se recibe junto con la nota del proveedor.</td>
</tr>
<tr class="odd">
<td>El proveedor <strong>acepta el pedido con los cambios</strong>. Los cambios se sugieren en el nivel de línea. Es posible aceptar o rechazar líneas individuales. Otros cambios posibles incluyen:
<ul>
<li>Cambiar fechas o cantidades.</li>
<li>Dividir las líneas para las diferentes fechas de entrega o cantidades.</li>
<li>Sustituir un artículo.</li>
</ul>
La información de precios y gastos no se puede cambiar por parte del proveedor. Las sugerencias para los cambios en los precios se pueden realizar mediante notas.</td>
<td>La respuesta del proveedor se registra como <strong>Aceptado con cambios</strong>, y el estado del PO se mantiene como <strong>En revisión externa</strong>. Los estados muestran qué tipos de cambios ha sugerido el proveedor. Para obtener más información sobre el consumo automático de los cambios, consulte la sección siguiente sobre cómo actualizar el PO cuando un proveedor sugiere cambios. </td>
</tr>
</tbody>
</table>

Puede usar el espacio de trabajo de espacio de trabajo **Preparación del** **pedido de compra** para supervisar a qué PO ha respondido el proveedor. Este espacio de trabajo contiene dos listas que albergan pedidos de compra con el estado **En revisión externa**:

-   En revisión externa requiere de una acción.
-   En revisión externa en espera de respuesta del proveedor.

### <a name="changing-a-po"></a>Cambiar un PO

Para cambiar un PO que ya ha sido respondido, debe enviar una nueva versión del PO al proveedor. El nuevo PO tendrá un sufijo de versión para indicar que es una versión modificada de un PO que se comunicó anteriormente. La página del **Historial de confirmación del proveedor del pedido de compra** le permite a usted y a sus proveedores hacer seguimiento del historial de cada pedido. La versión confirmada anteriormente de un PO permanece en la lista de PO confirmados hasta que se confirme el nuevo PO.

### <a name="cancelling-a-po"></a>Cancelar un PO

Al cancelar un PO, el estado se cambia a **Aprobado**. Debe enviar de nuevo la OC al proveedor a través del portal de proveedores de modo que el proveedor pueda confirmar o rechazar la cancelación. Cuando se confirme la cancelación, el PO aparece en la lista de PO confirmados del proveedor como **Cancelado**.

### <a name="adding-attachments-to-a-po"></a>Añadir datos adjuntos a un PO

Puede añadir datos adjuntos como archivos, imágenes y notas al PO mediante el sistema de gestión de documentos. Los datos adjuntos del tipo **Externo** serán visibles para el proveedor cuando le envíe el PO.

## <a name="update-the-po-when-a-vendor-suggests-changes"></a>Actualice el PO cuando un proveedor sugiera cambios
Cuando un proveedor haya respondido al PO y sugerido cambios, el paso siguiente es procesar la respuesta.
En el **Espacio de trabajo de preparación del pedido de compra**, en la lista En revisión externa requiere acción, puede identificar un PO al que un proveedor respondió como aceptado con cambios. En la lista En revisión externa requiere acción, también puede ir a la respuesta del proveedor. En una respuesta, un proveedor puede cambiar la siguiente información del encabezado.
 
-   Referencia de documento de proveedor
-   Modo de entrega
-   Condiciones de entrega
-   Fecha de entrega confirmada

El proveedor también puede agregar una nota o datos adjuntos

En las líneas, el proveedor puede cambiar la cantidad y las fechas de entrega, agregar notas y datos adjuntos, rechazar una línea, sustituir una línea por otro producto que se marque como texto y dividir una línea en varias entregas. En función de los cambios que sugiera el proveedor, el estado de la línea tendrá tendrá distintos estados de línea:
    
-   **Aceptado con cambios**
-   **Rechazado**
-   **Sustituido** En este caso, se agregará una línea adicional que tenga el estado **Sustituir**.
-   **Confirmado** Dividir en programación En este caso, se agregarán líneas adicionales que tengan el estado **Líneas de programación**.

Si una línea no tiene cambios, el estado de la línea es **Aceptado**.

En la respuesta, puede ver los estados de línea mencionados anteriormente que indican los tipos de cambios que realizó el proveedor. Además, todos los campos cambiados aparecen en negrita para ayudarle a identificar los cambios.

Puede actualizar un PO haciendo clic en la acción **Procesar actualización de PO** en la respuesta o en una línea al mismo tiempo. Un indicador, **¿Se ha procesado la actualización del PO?**, en el encabezado y las líneas le permite ver si el sistema ha procesado el encabezado o las líneas para actualizar el PO con los posibles cambios que se originen de la respuesta. Puede ejecutar el proceso **Procesa actualización de PO** solo una vez por encabezado o línea.

No todos los cambios sugeridos se pueden actualizar en un PO. Solo se actualiza en el encabezado y las actualizaciones de fechas y cantidades en las líneas se pueden actualizar automáticamente en el PO. Para otros cambios, debe actualizar manualmente el PO. En este caso, el indicador **¿Se ha procesado la actualización del PO?** muestra **Actualización manual**. Un ejemplo de un cambio que tiene que tratarse manualmente sería cuando un proveedor sugiere dividir una línea en una programación.

Una línea que tiene un estado de **Aceptado** tendrá una fecha de entrega confirmada que se actualizará en el PO cuando ejecute **Procesar actualización PO**. Las notas y los datos adjuntos no se automáticamente transferirán al PO actual. Tenga en cuenta que cuando actualice el PO actual a través de la acción **Procesar actualización de PO**, los acuerdos comerciales no se revaluarán en las líneas de PO.


## <a name="po-statuses-and-versions"></a>Estados y versiones de PO
Esta sección describe los distintos estados que un PO puede tener hasta el momento en que se confirma. También describe hasta qué punto están disponibles para el proveedor las nuevas versiones del PO. El comportamiento varía en función de si usa la gestión de cambios para los PO. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versiones y estados si no utiliza la gestión de cambios

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Acción**                                                               | **Estado y versión**                                                                                                                                       |
| La versión inicial del PO se crea en Finance and Operations. | El estado es **Aprobado**.                                                                                                                                  |
| El PO se envía al proveedor.                                            | Una versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                          |
| El proveedor envía una respuesta de **Aceptado con los cambios**.                  | El estado aún está **En revisión externa**.                                                                                                                  |
| Tiene que realizar algunos cambios que pide el proveedor.                  | El estado se cambia a **Aprobado**.                                                                                                                        |
| Envíe la nueva versión del PO al proveedor.                        | Una nueva versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                      |
| El proveedor acepta la nueva versión del PO.                            | El estado aún está **En revisión externa** a menos que la cuenta de proveedor se haya configurado para establecer automáticamente el estado del PO a **Confirmado** cuando lo acepta. |


Los proveedores no tienen que confirmar el PO mediante la interfaz de colaboración de proveedor. También pueden enviar un mensaje de correo electrónico o comunicar la aceptación de una OC a través de otros canales. A continuación, puede confirmar el pedido manualmente en Finance and Operations. En este caso, recibirá una advertencia de que se está confirmando el pedido aunque no haya respuesta del proveedor. El PO aparece a continuación en el historial de confirmaciones como un pedido confirmado abierto que no tiene ninguna respuesta. El proveedor ya no tiene la opción de confirmar o de rechazar el PO.  


>[!NOTE]
>La versión del PO que está disponible para otros procesos en Dynamics 365 for Finance and Operations siempre es la última versión, incluso si dicha versión no se ha registrado todavía en la interfaz de colaboración del proveedor.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versiones y estados si utiliza la gestión de cambios

Si se ha habilitado la gestión de cambios para los PO, el PO pasa por un flujo de trabajo de aprobación para lograr el estado de **Aprobado**. Este proceso no es visible para el proveedor.  

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC cuando está activada la gestión de cambios. La versión se registra cuando se aprueba el PO, no cuando el PO se envía al proveedor o se confirma.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Acción**                                                               | **Estado y versión**                                                                                                                                       |
| La versión inicial del PO se crea en Finance and Operations.      | El estado es **Borrador**.  |
| La OC se envía al proceso de aprobación. (El proceso de aprobaciónes un proceso interno en el que el proveedor no está involucrado.)                                                           | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si el PO no se rechaza durante el proceso de aprobación. El pedido de compra aprobado se registra como versión.           | 
| El PO se envía al proveedor                                                            | La versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.      |
| Tiene que realizar algunos cambios que pide el proveedor, ya sea manualmente o mediante la acción en la respuesta para actualizar el PO.                                                            | El estado se vuelve a cambiar a **Borrador**.     |
|La OC se envía al proceso de aprobación de nuevo.                                                |  El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si el PO no se rechaza durante el proceso de aprobación. De manera alternativa, el sistema puede estar configurado de modo que los cambios de campo específicos no necesitan volver a ser aprobados. En este caso, el estado cambia primero a **Borrador** y a continuación se actualizan automáticamente a **Aprobado**. El pedido de compra aprobado se registra como nueva versión.                                         |
|Envíe la nueva versión del PO al proveedor.                                                |  La nueva versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                         |
|El proveedor aprueba la nueva versión de la OC.                                                |  El estado se cambia a **Confirmado** automáticamente o cuando reciba la respuesta del proveedor y después confirma la OC. |

## <a name="share-information-about-consignment-inventory"></a>Compartir la información acerca del inventario de envío
Si está usando el inventario de envío, los proveedores pueden usar la interfaz de colaboración del proveedor para visualizar la información de las siguientes páginas:

-   **Pedidos de compra que consumen el inventario de envío**: los pedidos de compra del inventario de envío se generan cuando la propiedad del inventario pasa del proveedor a la empresa. El recibo del producto se publica al mismo tiempo. Estos pedidos de compra de envío solo se muestran en la página de **Pedidos de compra que consumen el inventario de envío**. No se incluyen en la página **Todos los pedidos de compra confirmados** del módulo **Colaboración de proveedor**.
-   **Productos recibidos del inventario de envío**: esta página muestra todas las transacciones en las que la titularidad de los productos se ha transferido del proveedor a la empresa. Los proveedores pueden usar esta información para facturar al cliente.
-   **Inventario de envío disponible**: esta página muestra el inventario disponible de envío que es propiedad del proveedor y que se ha recibido en el almacén.





