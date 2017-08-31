--- 
title: "Supervisar el inventario de entrega mediante la colaboración de proveedores"
description: "Este procedimiento muestra cómo utilizar la colaboración del proveedor para ver la información sobre el nivel de existencias del producto que ha incluido en la entrega a un cliente."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ad4868991226aef21a0410860e3f98d11901ffbb
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Supervisar el inventario de entrega mediante la colaboración de proveedores

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo utilizar la colaboración del proveedor para ver la información sobre el nivel de existencias del producto que ha incluido en la entrega a un cliente. También puede supervisar el consumo de las existencias cuando el cliente tiene la propiedad del inventario. Puede utilizar este procedimiento en la empresa de datos de demostración USMF. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="view-consumed-inventory"></a>Ver inventario consumido
1. Ir a Colaboración de proveedor > Inventario de envío > Productos recibidos del inventario de envío.
    * La lista muestra las líneas de recepción de producto que se generaron cuando la propiedad del inventario de entrega se cambió del proveedor al cliente. Es posible que tenga que desplazarse a la derecha para ver las cantidades y otra información. Puede usar la información de esta lista para generar facturas para el cliente. También puede exportar los datos a Microsoft Excel.   
2. Haga clic en Ver pedido de compra.
3. Expanda la sección Detalles de línea.
    * La línea se marca como Entrega y la sección de encabezado muestra que el pedido de compra tiene un estado Recibido.  
4. Cierre la página.

## <a name="view-on-hand-inventory"></a>Ver el inventario disponible
1. Ir a Colaboración de proveedor > Inventario de envío > Inventario de envío disponible.
    * La página Inventario de entrega disponible muestra las existencias que posee en el almacén del cliente. Puede mostrar dimensiones adicionales, como el sitio y el almacén, haciendo clic en la ficha Mostrar dimensiones.   


