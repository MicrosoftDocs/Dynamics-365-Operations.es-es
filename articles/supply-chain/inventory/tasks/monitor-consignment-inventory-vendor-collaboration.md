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
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="d0e64-103">Supervisar el inventario de entrega mediante la colaboración de proveedores</span><span class="sxs-lookup"><span data-stu-id="d0e64-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0e64-104">Este procedimiento muestra cómo utilizar la colaboración del proveedor para ver la información sobre el nivel de existencias del producto que ha incluido en la entrega a un cliente.</span><span class="sxs-lookup"><span data-stu-id="d0e64-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="d0e64-105">También puede supervisar el consumo de las existencias cuando el cliente tiene la propiedad del inventario.</span><span class="sxs-lookup"><span data-stu-id="d0e64-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="d0e64-106">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="d0e64-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="d0e64-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d0e64-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="d0e64-108">Ver inventario consumido</span><span class="sxs-lookup"><span data-stu-id="d0e64-108">View consumed inventory</span></span>
1. <span data-ttu-id="d0e64-109">Ir a Colaboración de proveedor > Inventario de envío > Productos recibidos del inventario de envío.</span><span class="sxs-lookup"><span data-stu-id="d0e64-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="d0e64-110">La lista muestra las líneas de recepción de producto que se generaron cuando la propiedad del inventario de entrega se cambió del proveedor al cliente.</span><span class="sxs-lookup"><span data-stu-id="d0e64-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="d0e64-111">Es posible que tenga que desplazarse a la derecha para ver las cantidades y otra información.</span><span class="sxs-lookup"><span data-stu-id="d0e64-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="d0e64-112">Puede usar la información de esta lista para generar facturas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="d0e64-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="d0e64-113">También puede exportar los a Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="d0e64-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="d0e64-114">Haga clic en Ver pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d0e64-114">Click View purchase order.</span></span>
3. <span data-ttu-id="d0e64-115">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="d0e64-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="d0e64-116">La línea se marca como Entrega y la sección de encabezado muestra que el pedido de compra tiene un estado Recibido.</span><span class="sxs-lookup"><span data-stu-id="d0e64-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="d0e64-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d0e64-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="d0e64-118">Ver el inventario disponible</span><span class="sxs-lookup"><span data-stu-id="d0e64-118">View on-hand inventory</span></span>
1. <span data-ttu-id="d0e64-119">Ir a Colaboración de proveedor > Inventario de envío > Inventario de envío disponible.</span><span class="sxs-lookup"><span data-stu-id="d0e64-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="d0e64-120">La página Inventario de entrega disponible muestra las existencias que posee en el almacén del cliente.</span><span class="sxs-lookup"><span data-stu-id="d0e64-120">The On-hand consignment inventory page shows the stock that you own at the customer's warehouse.</span></span> <span data-ttu-id="d0e64-121">Puede mostrar dimensiones adicionales, como el sitio y el almacén, haciendo clic en la ficha Mostrar dimensiones.</span><span class="sxs-lookup"><span data-stu-id="d0e64-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

