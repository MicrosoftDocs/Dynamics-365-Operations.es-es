---
title: "Colaboración de proveedor con proveedores externos"
description: "Este tema describe cómo los agentes de compras pueden colaborar con los proveedores externos para intercambiar información sobre los pedidos de compra y el inventario de envío."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: c8947f9335b3a2de83ab00bad1043ee14d35f2c8
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-with-external-vendors"></a>Colaboración de proveedor con proveedores externos

[!include[banner](../includes/banner.md)]


Este tema describe cómo los agentes de compras pueden colaborar con los proveedores externos para intercambiar información sobre los pedidos de compra y el inventario de envío.

El módulo de **Colaboración del proveedor** se indica para los proveedores que no tienen integración de Intercambio de datos electrónicos (EDI) con Microsoft Dynamics 365 for Operations. Permite a los proveedores trabajar con información sobre el pedido de compra, la factura y el inventario de envío. Este tema describe cómo puede colaborar con los proveedores externos que usan la interfaz de colaboración de proveedor para trabajar con PO y el inventario de envío. También explica cómo permitir a un proveedor específico utilizar la colaboración de proveedor, y cómo definir la información que verán todos los proveedores cuando respondan a un PO. Para obtener más información sobre lo que pueden hacer los proveedores externos en la interfaz de colaboración de proveedor, consulte [Colaboración de proveedor con los clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Para obtener más información sobre cómo los proveedores pueden utilizar la colaboración del proveedor en los procesos de facturación, consulte [Área de trabajo de facturación de colaboración de proveedor](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Para obtener información sobre cómo suministrar nuevos usuarios de colaboración de proveedor, consulte [Gestionar usuarios de colaboración del proveedor](manage-vendor-collaboration-users.md).

## <a name="define-the-information-shown-to-vendors-when-they-respond-to-pos"></a>Definir la información mostrada a los proveedores cuando responden a los PO
Cuando los proveedores responden a un PO que les envía, ven un cuadro de diálogo donde necesitan confirmar que desean aceptar, rechazar o aceptar el PO con cambios. La información que se debe mostrar al proveedor en ese momento puede ser específica para su negocio, por lo que puede especificar el texto que mostrará en cada uno de los tres mensajes de confirmación. Por ejemplo, el texto podría notificar al proveedor sobre los siguientes pasos del proceso, o sobre los términos y condiciones.  

Para definir el texto que se muestra en la respuesta del PO:

1.  Abra la información de la página **Información para proveedores en respuesta a los PO**.
2.  Seleccione uno de los siguientes tipos de respuesta.
3.  Haga clic en **Editar.**
4.  Escriba la información que desea que los proveedores vean en el cuadro **Mensaje de información**.

Si necesita agregar mensajes en más de un idioma, cree mensajes aparte con los códigos de idioma adecuados. Se mostrará el mensaje al proveedor en el idioma que usa.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Configurar las opciones de colaboración de proveedor para un proveedor específico
La configuración general para la colaboración del proveedor en Dynamics 365 for Operations las configura un administrador. Por ejemplo, determinarán qué roles de seguridad están disponibles para todos los proveedores con los que colabora. También algunos ajustes que pueden ser diferentes para cada cuenta de proveedor, y se deben establecer estos:

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

Los pedidos de compra se preparan en Dynamics 365 for Operations. Cuando el pedido de compra tiene un estado de **Aprobado**, se envía al proveedor mediante la acción **Enviar para su confirmación** en la página **Pedido de compra**. El estado del PO cambia a **En proceso de revisión externa**. Después de enviar el PO, el proveedor puede consultarlo en la página **Pedidos de compra para revisar** de la interfaz de colaboración del proveedor, donde pueden aceptar, rechazar o sugerir cambios al pedido. El proveedor también puede agregar comentarios para comunicar información como cambios al pedido de compra. Si quiere que el proveedor se fije en una nueva OC, también puede usar el sistema de gestión de impresión para enviar la OC por correo electrónico.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Confirmación y aceptación del PO por parte del proveedor

Cuando un proveedor ha aceptado un pedido de compra, el PO puede confirmarse automáticamente, o es posible que necesite confirmarse de forma manual. Esto depende de si el campo de **Activación del proveedor** está configurado como **Activo (el PO se confirma automáticamente)** por parte del proveedor o como **Activo (el PO no se confirma automáticamente)**.  

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
<td>El proveedor <strong>acepta</strong> el pedido. Dynamics 365 for Operations se configura para confirmar automáticamente los PO cuando el proveedor los acepta.</td>
<td>El estado del pedido se actualiza a <strong>Confirmado</strong>. Si algo impide que el pedido se actualice, la respuesta del proveedor se registra igualmente como <strong>Aceptado</strong> pero el estado del PO permanece como estado <strong>En revisión externa</strong>.</td>
</tr>
<tr class="odd">
<td>El proveedor <strong>acepta</strong> el pedido. Dynamics 365 for Operations no se configura para confirmar automáticamente los PO cuando el proveedor los acepta.</td>
<td>La respuesta del proveedor se registra como <strong>Aceptado</strong> pero el estado del PO permanece como estado <strong>En revisión externa</strong>.</td>
</tr>
<tr class="even">
<td>El proveedor <strong>rechaza</strong> el pedido.</td>
<td>La respuesta del proveedor se registra como <strong>Rechazado</strong> y el estado de la OC permanece en estado <strong>Revisión externa</strong>. El rechazo se recibe junto con la nota de los proveedores.</td>
</tr>
<tr class="odd">
<td>El proveedor <strong>acepta el pedido con los cambios</strong>. Los cambios se sugieren en el nivel de línea. Es posible aceptar o rechazar líneas individuales. Otros cambios posibles incluyen:
<ul>
<li>Cambiar fechas o cantidades.</li>
<li>Dividir las líneas para las diferentes fechas de entrega o cantidades.</li>
<li>Sustituir un artículo.</li>
</ul>
La información de precios y gastos no se puede cambiar por parte del proveedor. Las sugerencias para los cambios en los precios se pueden realizar mediante notas.</td>
<td>La respuesta del proveedor se registra como <strong>Aceptado con cambios</strong>, <strong></strong>y el estado del pedido de compra se mantiene como <strong>En revisión externa</strong>.</td>
</tr>
</tbody>
</table>

Puede usar el espacio de trabajo de espacio de trabajo **Preparación del** **pedido de compra** para supervisar a qué PO ha respondido el proveedor. Este espacio de trabajo contiene dos listas que albergan pedidos de compra con el estado **En revisión externa**:

-   En revisión externa requiere de una acción.
-   En revisión externa en espera de respuesta del proveedor.

### <a name="changing-a-po"></a>Cambiar un PO

Si tiene que cambiar un PO que ya ha sido respondido, debe enviar una nueva versión del PO al proveedor. El nuevo PO tendrá un sufijo de versión para indicar que es una versión modificada de un PO que se comunicó anteriormente. La página del **Historial de confirmación del proveedor del pedido de compra** le permite a usted y a sus proveedores hacer seguimiento del historial de cada pedido. La versión confirmada anteriormente del pedido de compra permanece en la lista de pedidos de compra confirmados hasta que se confirme el nuevo pedido de compra.

### <a name="cancelling-a-po"></a>Cancelar un PO

Al cancelar un PO, el estado se cambia a **Aprobado**. Debe enviar de nuevo la OC al proveedor a través del portal de proveedores de modo que el proveedor pueda confirmar o rechazar la cancelación. Cuando se confirme la cancelación, el PO aparece en la lista de PO confirmados del proveedor como **Cancelado**.

### <a name="adding-attachments-to-a-po"></a>Añadir datos adjuntos a un PO

Puede añadir datos adjuntos como archivos, imágenes y notas al PO mediante el sistema de gestión de documentos. Los datos adjuntos añadidos con la restricción de tipo **Externo** serán visibles para el proveedor cuando le envíe el PO.

## <a name="purchase-order-statuses-and-versions"></a>Estados y versiones de pedidos de compra
Esta sección describe los distintos estados que un PO puede tener hasta el momento en que se confirma, y cuándo están disponibles para el proveedor las nuevas versiones del PO. Existen diferencias en función de si utiliza la gestión de cambios para pedidos de compra. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versiones y estados si no utiliza la gestión de cambios

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Acción**                                                               | **Estado y versión**                                                                                                                                       |
| La versión inicial del PO se crea en Dynamics 365 for Operations. | El estado es **Aprobado**.                                                                                                                                  |
| El PO se envía al proveedor.                                            | Una versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                          |
| El proveedor envía una respuesta de **Aceptado con los cambios**.                  | El estado aún está **En revisión externa**.                                                                                                                  |
| Tiene que realizar algunos cambios que pide el proveedor.                  | El estado se cambia a **Aprobado**.                                                                                                                        |
| Envíe la nueva versión del PO al proveedor.                        | Una nueva versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                      |
| El proveedor acepta la nueva versión del PO.                            | El estado aún está **En revisión externa**a menos que la cuenta de proveedor se haya configurado para establecer automáticamente el estado del PO a **Confirmado** cuando lo acepta. |

Los proveedores no tienen que confirmar el PO mediante la interfaz de colaboración de proveedor. También pueden enviar un mensaje de correo electrónico o comunicar la aceptación de una OC a través de otros canales. A continuación puede confirmar el pedido manualmente en Dynamics 365 for Operations. Si lo hace, recibirá una advertencia de que se está confirmando el pedido aunque no haya respuesta del proveedor. El PO aparece a continuación en el historial de confirmaciones como un pedido confirmado abierto que no tiene ninguna respuesta. El proveedor ya no tiene la opción de confirmar o de rechazar el PO.  

**Nota:** La versión del PO que está disponible para otros procesos en Dynamics 365 for Operations siempre es la última versión, incluso si dicha versión no se ha registrado todavía en la interfaz de colaboración del proveedor.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versiones y estados si utiliza la gestión de cambios

Si se ha habilitado la gestión de cambios para los PO, el PO pasa por un flujo de trabajo de aprobación para lograr el estado de **Aprobado**. Este proceso no es visible para el proveedor.  

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC cuando está activada la gestión de cambios. La versión se registra cuando se aprueba el PO, no cuando el PO se envía al proveedor o se confirma.

|                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Acción**                                                                                                    | **Estado y versión**                                                                                                                                                                                                                                                                                                                                                                      |
| La versión inicial del PO se crea en Dynamics 365 for Operations.                                      | El estado es **Borrador**.                                                                                                                                                                                                                                                                                                                                                                    |
| La OC se envía al proceso de aprobación. (Esto es un proceso interno en el que el proveedor no está involucrado.) | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si el PO no se rechaza durante el proceso de aprobación. El pedido de compra aprobado se registra como versión.                                                                                                                                                                                                                     |
| El PO se envía al proveedor                                                                                  | La versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                                                                                                                                                                                                                                                       |
| Tiene que realizar algunos cambios que pide el proveedor.                                                       | El estado se vuelve a cambiar a **Borrador**.                                                                                                                                                                                                                                                                                                                                                    |
| La OC se envía al proceso de aprobación de nuevo.                                                            | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si el PO no se rechaza durante el proceso de aprobación. De manera alternativa, el sistema puede estar configurado de modo que los cambios de campo específicos no necesitan volver a ser aprobados. En este caso, el estado cambia primero a **Borrador** y a continuación se actualizan automáticamente a **Aprobado**. El pedido de compra aprobado se registra como nueva versión. |
| Envíe la nueva versión del PO al proveedor.                                                             | La nueva versión se registra en la interfaz de colaboración de proveedor y el estado se cambia a **En revisión externa**.                                                                                                                                                                                                                                                                   |
| El proveedor aprueba la nueva versión de la OC.                                                                | El estado se cambia a **Confirmado** automáticamente o cuando reciba la respuesta del proveedor y después confirma la OC.                                                                                                                                                                                                                                                     |

## <a name="share-information-about-consignment-inventory"></a>Compartir la información acerca del inventario de envío
Si está usando el inventario de envío, los proveedores pueden usar la interfaz de colaboración del proveedor para visualizar la información de las siguientes páginas:

-   **Pedidos de compra que consumen el inventario de envío**: los pedidos de compra del inventario de envío se generan cuando la propiedad del inventario pasa del proveedor a la empresa. El recibo del producto se publica al mismo tiempo. Estos pedidos de compra de envío solo se muestran en la página de **Pedidos de compra que consumen el inventario de envío**. No se incluyen en la página **Todos los pedidos de compra confirmados** del módulo **Colaboración de proveedor**.
-   **Productos recibidos del inventario de envío**: esta página muestra todas las transacciones en las que la titularidad de los productos se ha transferido del proveedor a la empresa. Los proveedores pueden usar esta información para facturar al cliente.
-   **Inventario de envío disponible**: esta página muestra el inventario disponible de envío que es propiedad del proveedor y que se ha recibido en el almacén.





