---
title: Supervisar el inventario de entrega mediante la colaboración de proveedores
description: Este procedimiento muestra cómo utilizar la colaboración del proveedor para ver la información sobre el nivel de existencias del producto que ha incluido en la entrega a un cliente.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0d194728805cd1eee741069538352b497867981
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571842"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Supervisar el inventario de entrega mediante la colaboración de proveedores

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo utilizar la colaboración del proveedor para ver la información sobre el nivel de existencias del producto que ha incluido en la entrega a un cliente. También puede supervisar el consumo de las existencias cuando el cliente tiene la propiedad del inventario. Puede utilizar este procedimiento en la empresa de datos de demostración USMF. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="view-consumed-inventory"></a>Ver inventario consumido
1. Ir a Colaboración de proveedor > Inventario de envío > Productos recibidos del inventario de envío.
    * La lista muestra las líneas de recepción de producto que se generaron cuando la propiedad del inventario de entrega se cambió del proveedor al cliente. Es posible que tenga que desplazarse a la derecha para ver las cantidades y otra información. Puede usar la información de esta lista para generar facturas para el cliente. También puede exportar los a Microsoft Excel.   
2. Haga clic en Ver pedido de compra.
3. Expanda la sección Detalles de línea.
    * La línea se marca como Entrega y la sección de encabezado muestra que el pedido de compra tiene un estado Recibido.  
4. Cierre la página.

## <a name="view-on-hand-inventory"></a>Ver el inventario disponible
1. Ir a Colaboración de proveedor > Inventario de envío > Inventario de envío disponible.
    * La página Inventario de entrega disponible muestra las existencias que posee en el almacén del cliente. Puede mostrar dimensiones adicionales, como el sitio y el almacén, haciendo clic en la ficha Mostrar dimensiones.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]