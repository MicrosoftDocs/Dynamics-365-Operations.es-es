---
title: "Colaboración de proveedor con los clientes"
description: "Este tema describe cómo puede usar la colaboración del proveedor para trabajar con los PO y supervisar el inventario de envío en Finance and Operations."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4ad7c4f14cf60b2f59124ac98d55c4b92edabb47
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="vendor-collaboration-with-customers"></a>Colaboración de proveedor con los clientes

[!include[banner](../includes/banner.md)]


Este tema describe cómo puede usar la colaboración del proveedor para trabajar con los PO y supervisar el inventario de envío en Finance and Operations.

Este tema describe cómo puede usar la colaboración del proveedor para trabajar con los clientes en Microsoft Finance and Operations. Incluye información acerca de cómo supervisar y responder a los pedidos de compra, y cómo controlar el inventario de envío. También es posible usar la colaboración de proveedor para trabajar con las facturas. Para obtener más información, consulte [Espacio de trabajo de facturación de colaboración de proveedor](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

## <a name="working-with-purchase-orders"></a>Trabajar con pedidos de compra
El área de trabajo de la **Confirmación del pedido de compra** le permite responder a los PO que se le han enviado para que los revise. También le permite ver información sobre pedidos de compra que están esperando una acción por parte del cliente, y los que han sido confirmados pero siguen abiertos. Existen tres listas en el espacio de trabajo de **Confirmación de pedido de compra**:

-   **Pedidos de compra para revisar**: esta lista muestra los PO que se han enviado y esperan una respuesta por su parte. Cuando responda, los PO desaparecerán de la lista. Si el cliente le envía una nueva versión del PO antes de que haya respondido el anterior, solo se muestra la última versión.
-   **Esperando la acción del cliente**: esta lista le permite ver los PO a los que ha respondido pero que el cliente todavía no ha confirmado. Si ha aceptado el PO, puede supervisarlo en esta lista hasta que el estado cambia a **Confirmado**. Si rechazó el PO o lo aceptó con cambios, puede supervisar el PO aquí hasta que el cliente le envía una nueva versión.
-   **Abrir los pedidos de compra confirmados**: esta lista contiene todos los PO de su cuenta que tienen el estado **Confirmado**. Cuando los productos o servicios se reciben completamente con el PO, el PO desaparece de la lista.

La lista siguiente muestra las cuatro páginas que puede usar para trabajar con pedidos de compra, dos de las cuales contienen la misma información que las listas del área de trabajo:

-   **Pedidos de compra para revisar** (ver más arriba)
-   **Historial de confirmación del pedido de compra del proveedor**: esta página contiene todos los PO y las versiones de PO que se han enviado al proveedor, y todas las respuestas que el proveedor ha devuelto.
-   **Abrir los pedidos de compra confirmados** (ver más arriba)
-   **Todos los pedidos de compra confirmados**: esta página contiene todos los PO que se han confirmado, incluidos aquellos donde se han recibido los productos o servicios. Puede usar esta lista para supervisar para qué PO puede enviar facturas.

### <a name="responding-to-purchase-orders"></a>Responder a pedidos de compra

Los pedidos de compra que el cliente le ha enviado para revisar están visibles en el espacio de trabajo **Confirmación del pedido de compra** y en la página **Pedidos de compra para revisar**. Cuando abre un pedido de compra, puede elegir aceptarlo, rechazarlo o aceptarlo con cambios. Podía haber documentos adjuntos en el encabezado del PO o en líneas individuales. También es posible que adjunte información a su respuesta en el encabezado del PO o en líneas individuales. Por ejemplo, puede sugerir un artículo sustituto para una de las líneas. Puede obtener una vista previa e imprimir el PO como archivo PDF mediante la opción **Vista preliminar/Imprimir**. Puede ocultar o mostrar las siguientes columnas de dimensión usando la acción **Mostrar dimensiones**: Sitio, Almacén, Color, Tamaño, Estilo, Configuración. Si usa la opción **Aceptar con cambios**, puede aceptar o rechazar líneas individuales. También puede realizar los siguientes cambios en las líneas:

-   Cambiar fechas o cantidades. Si desea actualizar la fecha de entrega confirmada en todas las líneas, use la opción **Actualizar la fecha de entrega** en el encabezado del PO.
-   Divida las líneas para las diferentes fechas de entrega o cantidades
-   Sustituir un artículo. Para ello, escriba una descripción del artículo y su número de artículo en el campo **Externo** de la sección **Detalles de línea**.

No puede cambiar la información sobre precios o gastos, pero puede hacer sugerencias para dichos cambios mediante el uso de notas. Si el cliente le envía una nueva versión de un PO, éste tendrá un sufijo de versión para indicar que es una versión modificada de un PO que se comunicó anteriormente. La página del **Historial de confirmación del proveedor del pedido de compra** le permite hacer seguimiento del historia de cada pedido.

## <a name="monitoring-consignment-inventory"></a>Supervisar el inventario de entrega
Si está usando el inventario de envío, puede usar la interfaz de colaboración del proveedor para visualizar la información de las siguientes páginas:

-   **Pedidos de compra que consumen el inventario de envío**: los pedidos de compra de inventario de envío se generan cuando el cliente se adueña del inventario. Estos pedidos de compra de envío solo se muestran en la página de **Pedidos de compra que consumen el inventario de envío**. No se incluyen en la página **Todos los pedidos de compra confirmados**.
-   **Productos recibidos de inventario de envío**: esta página muestra todas las transacciones en las que la titularidad de los productos se ha transferido a la empresa que está consumiendo el inventario. Esta información se puede utilizar para facturar al cliente.
-   **Inventario de envío disponible**: esta página muestra el inventario disponible de envío que es propiedad de la empresa y que está disponible en el almacén de los clientes.


<a name="see-also"></a>Consulte también
--------

[Gestionar usuarios de colaboración de proveedor](manage-vendor-collaboration-users.md)




