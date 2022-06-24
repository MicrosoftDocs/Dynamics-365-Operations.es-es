---
title: Colaboración de proveedor con los clientes
description: Este artículo describe cómo puede usar la colaboración del proveedor para trabajar con los pedidos de compra y supervisar el inventario de envío.
author: GalynaFedorova
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart, VendVendorProfileCard, PurchVendorPortalAllResponse, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4e5748f2368376ee03f280f1487d1de65250d3a4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859180"
---
# <a name="vendor-collaboration-with-customers"></a>Colaboración de proveedor con los clientes

[!include [banner](../includes/banner.md)]

Este artículo describe cómo puede usar la colaboración del proveedor para trabajar con los clientes en Microsoft Dynamics 365 Supply Chain Management. Los proveedores pueden completar una serie de procesos empresariales de las áreas de trabajo siguientes:

- **Confirmación de pedidos de compra** Controle y respuesta a los pedidos de compra (PO).
- **Oferta del proveedor**: Ver solicitudes de presupuesto y responder a ellas especificando propuestas.
- **Información de proveedor**: Ver y actualizar datos maestros de proveedores.
- **Facturación**: Trabajo con facturas. Este artículo no cubre el área de trabajo **Facturación**. Para obtener más información sobre este área de trabajo, consulte [Espacio de trabajo de facturación de colaboración de proveedor](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md).

Los proveedores también pueden controlar la información acerca del inventario de entrega.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>Trabajar con PO en el espacio de trabajo de confirmación de pedido de compra

El área de trabajo de la **Confirmación del pedido de compra** le permite responder a los pedidos de compra (PO) que se le han enviado para que los revise. También le permite ver información sobre pedidos de compra que están esperando una acción por parte del cliente y los que han sido confirmados pero siguen abiertos.

Existen tres listas en el espacio de trabajo de **Confirmación de pedido de compra**:

- **Pedidos de compra para revisar**: esta lista muestra los PO que se han enviado y esperan una respuesta por su parte. Cuando responda, los PO desaparecerán de la lista. Si el cliente le envía una nueva versión del PO antes de que haya respondido el anterior, solo se muestra la última versión.
- **A la espera de acción del cliente**: esta lista muestra todos los PO a los que ha respondido pero que el cliente todavía no ha confirmado. Si ha aceptado un PO, puede supervisarlo en esta lista hasta que el estado cambie a **Confirmado**. Si rechazó un PO o lo aceptó con cambios, puede supervisarlo aquí hasta que el cliente le envíe una nueva versión.
- **Abrir los pedidos de compra confirmados**: esta lista muestra todos los PO de su cuenta que tienen el estado **Confirmado**. Cuando los productos o servicios se reciben completamente con el PO, el PO desaparece de la lista.

Se pueden usar las siguientes páginas para trabajar con los PO:

- **Pedidos de compra para revisión** Esta página contiene la misma información que la lista de **Pedidos de compra para revisión** en el área de trabajo. Consulte la descripción anterior en este artículo.
- **Historial de confirmación del proveedor del pedido de compra**: Esta página contiene todas las versiones del PO que se han enviado al proveedor. También contiene todas las respuestas que ha devuelto el proveedor.
- **Pedidos de compra confirmados abiertos** Esta página contiene la misma información que la lista de **Pedidos de compra confirmados abiertos** en el área de trabajo. Consulte la descripción anterior en este artículo.
- **Todos los pedidos de compra confirmados** Esta página contiene todos los PO que han sido confirmados. Los PO qeu se muestran en esta página incluye PO en los que se han recibido los productos o servicios. Puede usar esta lista para supervisar los PO para los que puede enviar facturas.

### <a name="responding-to-pos"></a>Responder a los PO

Los pedidos de compra que el cliente le ha enviado para revisar aparecen en el espacio de trabajo **Confirmación del pedido de compra** y en la página **Pedidos de compra para revisar**. Cuando abre un PO, puede elegir aceptarlo, rechazarlo o aceptarlo con cambios. Podía haber documentos adjuntos en el encabezado del PO o en líneas individuales. Además, puede adjuntar información a su respuesta en el encabezado del PO o en líneas individuales. Por ejemplo, puede sugerir un artículo sustituto para una de las líneas.

Puede obtener una vista previa e imprimir el PO como archivo PDF mediante la opción **Vista preliminar/Imprimir**. También puede usar la acción **Mostrar dimensiones** para ocultar o mostrar las siguientes columnas de dimensión: **Sitio**, **Almacén**, **Color**, **Tamaño**, **Estilo**, **Configuración**. 

Si usa la opción **Aceptar con cambios**, puede aceptar o rechazar líneas individuales. También puede realizar los siguientes cambios en las líneas:

- Cambiar fechas o cantidades. Para actualizar la fecha de entrega confirmada en todas las líneas, use la opción **Actualizar la fecha de entrega** en el encabezado del PO.
- Divida las líneas para las diferentes fechas de entrega o cantidades.
- Sustituir un artículo. En la sección **Detalles de la línea**, escriba una descripción del artículo y el número de artículo en el campo **Externo**.

No puede cambiar la información sobre precios o gastos, pero puede hacer sugerencias para dichos cambios mediante el uso de notas.

Si el cliente le envía una nueva versión de un PO, éste tendrá un sufijo de versión para indicar que es una versión modificada de un PO que se envió anteriormente. La página del **Historial de confirmación del proveedor del pedido de compra** le permite hacer un seguimiento del historial de cada pedido.

## <a name="monitoring-consignment-inventory"></a>Supervisar el inventario de entrega

Si está usando el inventario de entrega, puede usar la interfaz de colaboración del proveedor para visualizar la información de las siguientes páginas:

- **Pedidos de compra que consumen el inventario de entrega**: los PO del inventario de entrega se generan cuando el cliente adquiera propiedad del inventario. Estos PO de entrega sólo se muestran en esta página. No se incluyen en la página **Todos los pedidos de compra confirmados**.
- **Productos recibidos del inventario de entrega**: esta página muestra todas las transacciones en las que la titularidad de los productos se ha transferido a la empresa que está consumiendo el inventario. Esta información se puede utilizar para facturar al cliente.
- **Inventario de entrega disponible**: esta página muestra el inventario disponible de entrega que es propiedad de la empresa, pero que está disponible en el almacén de los clientes.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>Trabajo con solicitudes de presupuesto en el área de trabajo de oferta del proveedor

El área de trabajo **Oferta del proveedor** permite ver las solicitudes de presupuesto (RFQ) a las que su empresa ha sido invitada a responder. También puede responder a las solicitudes de presupuesto.

El área de trabajo también muestra a todas las solicitudes de presupuesto que ha perdido o ha obtenido. Además, si el sistema está configurado para el sector público, el área de trabajo muestra las solicitudes de presupuesto que están disponibles al público.

### <a name="viewing-rfqs"></a>Vista de solicitudes de presupuesto

Abra el espacio trabajo **Oferta del proveedor** para obtener acceso a la siguiente información:

- Seleccione **Nuevas invitaciones de loferta** para ver las solicitudes de presupuesto a las que su empresa ha sido invitada a responder. Desde aquí, puede ver una solicitud de presupuesto e iniciar el proceso de oferta. También puede ver solicitudes de presupuesto modificada para las que se debe presentar una nueva propuesta.
- Seleccione **Propuestas devueltas** para ver las solicitudes de presupuesto que el cliente ha devuelto para que pueda proporcionar más información o actualizar la propuesta.
- Seleccione **Propuestas en curso** para ver las solicitudes de presupuesto en las que usted o una persona de contacto que representa a su empresa haya estado trabajando pero aún no haya presentado.
- Seleccione **Propuestas adjudicadas** para ver cuándo el cliente le haya adjudicado al menos un artículo de línea de su oferta.
- Seleccione **Ofertas perdidas** para ver las ofertas en las que se han rechazado todas las líneas.
- Seleccione el vínculo **Solicitud de presupuesto** para ver una lista de todas las invitaciones de solicitud de presupuesto del proveedor y de cualquier oferta que se haya registrado. La página **Solicitud de presupuesto** muestra todas las solicitudes de presupuesto en las que un proveedor ha participado. Puede buscar por estado.
- Seleccione el vínculo **Propuestas rechazadas** para ver una lista de todas las solicitudes de presupuesto donde la persona de contacto del proveedor ha rechazado emitir una oferta.

### <a name="working-with-rfqs-that-are-publicly-available"></a>Trabajo con las solicitudes de presupuesto que están disponibles al público

Las personas que trabajan en el sector público pueden ver las solicitudes de presupuesto abiertas y vencidas que se han puesto a disposición del público.

- Seleccione el vínculo **Solicitudes de presupuestos publicadas abiertas** para ver una lista de solicitudes de presupuesto abiertas disponibles para el público. Una solicitud de presupuesto abierta es una solicitud de presupuesto que aún no ha vencido. Puede encontrar la fecha y hora de vencimiento en el encabezado de la solicitud de presupuesto.

    Si ha sido invitado a realizar una oferta, puede encontrar la misma solicitud de presupuesto en la página **Nuevas invitaciones a oferta**. En ocasiones, puede que desee realizar una oferta de una solicitud de presupuesto abierta, pero no ha sido invitado a realizar una oferta. En este caso, podrá invitarse usted mismo, siempre que el cliente haya habilitado la auto-invitación para el caso de solicitud de presupuesto. 

    La página **Nuevas convocatorias de ofertas** puede proporcionar un filtro que le permite ver las RFQ abiertas e identificar aquellas que contienen líneas que coinciden con sus categorías de compras aprobadas. Para que este filtro esté disponible, debe activar la función *Permitir que los proveedores busquen RFQ por categoría de adquisición* en su sistema. Los administradores pueden usar el espacio de trabajo **Administración de características** para verificar el estado de esta característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

    - **Módulo**: *Proveedores*
    - **Nombre de la función:** *Permitir que los proveedores busquen RFQ por categoría de adquisición* <!-- KFM: I don't see this here, is this right? -->

    Puede mejorar la accesibilidad del enlace **Abrir solicitudes de cotizaciones publicadas** activando la función *Mostrar el vínculo "Abrir solicitudes de cotización publicadas" como mosaico*. Esta función convierte el enlace en un mosaico y lo mueve a una ubicación destacada para que sea fácil de encontrar. Los administradores pueden usar el espacio de trabajo **Administración de características** para verificar el estado de esta característica y activarla si es necesario. (A partir de la versión 10.0.21 de Supply Chain Management, la función está activada de forma predeterminada). Allí, la función se muestra de la siguiente manera:

    - **Módulo**: *Adquisición y abastecimiento*
    - **Nombre de la característica**: *Mostrar el vínculo Abrir solicitudes publicadas para presupuestos como icono*

- Seleccione el vínculo **Solicitudes de presupuestos publicadas cerradas** para ver una lista de solicitudes de presupuesto cerradas disponibles para el público. Una solicitud de presupuesto cerrada es una solicitud de presupuesto que ha vencido. Puede encontrar la fecha y hora de vencimiento en el encabezado de la solicitud de presupuesto.

    Una solicitud de presupuesto cerrada muestra todas las ofertas de proveedor hasta el nivel de línea. A medida que las ofertas se conceden o se echazan, esta información se refleja en la solicitud de presupuesto cerrada. Los archivos adjuntos que se incluyan en la oferta también están disponible.

> [!NOTE]
> Nota: Esta funcionalidad solo está disponible si se activa la configuración del sector público.

### <a name="bidding"></a>El realizar una oferta

- Seleccione **Oferta** para empezar a realizar una oferta de una solicitud de presupuesto.

    Cuando la edición está habilitada para los campos de oferta en los encabezados y las líneas de la solicitud de presupuesto, puede introducir su oferta directamente en la cuadrícula de la línea. También debe considerar cualquier información adicional de la oferta que se deba agregar en los detalles de línea.

    Al empezar a trabajar en una oferta, aparece en la sección **Propuestas en curso** .

    En cualquier momento antes de la fecha de vencimiento, puede guardar una oferta. Puede volver más tarde para acabar y registrar la oferta. Después de registrar una oferta, puede volver a llamarla y actualizarla hasta la fecha de vencimiento.

- Seleccione **Restablecer desde la solicitud de presupuesto** para restablecer los datos especificados para una oferta y reviertir la solicitud de presupuesto original. Puede restablecer la cabecera o la línea.
- Seleccione **Agregar alternativa** o **Quitar alternativa** en la cuadrícula de la línea para trabajar con alternativas.

    Algunas solicitudes de presupuesto permiten ofertas alternativas. Puede especificar ofertas alternativas únicamente para las líneas del tipo **Categoría**, ya que los artículos específicos no se pueden agregar como alternativas. 

- Seleccione **Archivos adjuntos de la solicitud de presupuesto** o **Archivos adjuntos de las líneas de solicitudes de presupuesto** para abrir los archivos adjuntos que el cliente haya agregado a una solicitud de presupuesto. Seleccione **Archivos adjuntos de una oferta** o **Archivos adjuntos de la línea de una oferta** para cargar archivos adjuntos junto a la oferta.

    Es posible que haya cuestionarios que deba responder antes de que se le permita registrar una oferta.

- Seleccione **Rechazar** si no desea realizar ninguna oferta. Tras seleccionar **Rechazar**, no puede recuperar la acción e introducir una oferta.

Si se rectifica una solicitud de presupuesto, se debe introducir una nueva oferta. Puede obtener información acerca de la modificación en la pestaña **Modificaciones** de la página de solicitud de presupuesto. Las solicitudes de presupuesto enmendadas aparecen en la página **Nuevas invitaciones a oferta**.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>Acceso a los datos maestros de proveedores en el área de trabajo de información de proveedor

Como proveedor, puede tener acceso a parte de la información que el cliente mantiene en el registro maestro de proveedores. Por lo tanto, puede mantener la información actualizada. Para actualizar la información, debe tener un rol de administración de proveedor (externo).

La información accesible es el nombre del proveedor, direcciones, información de contacto, personas de contacto y su información de contacto, números de identificación, números de registro de impuestos, categorías de compras que el proveedor está autorizado a vender al cliente e información acerca de las certificaciones.

## <a name="additional-resources"></a>Recursos adicionales

[Gestionar usuarios de colaboración de proveedor](manage-vendor-collaboration-users.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
