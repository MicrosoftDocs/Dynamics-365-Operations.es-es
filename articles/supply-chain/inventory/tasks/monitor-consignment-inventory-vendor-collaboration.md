---
title: Supervisar el inventario de entrega mediante la colaboración de proveedores
description: Este procedimiento muestra cómo utilizar la colaboración del proveedor para ver la información sobre el nivel de existencias del producto que ha incluido en la entrega a un cliente.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 589b478fa59f2fb2a5008d02e39f2808391d0994
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145595"
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

