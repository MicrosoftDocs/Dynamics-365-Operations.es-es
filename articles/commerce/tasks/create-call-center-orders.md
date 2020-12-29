---
title: Crear pedidos de centro de llamadas
description: Este procedimiento le guía por la búsqueda de un cliente, la creación de un nuevo pedido, la búsqueda de un producto y el cobro de pagos del cliente.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c875eaa85d9da997b75b296ad9ace99ae1e91798
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594245"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="fab6f-103">Crear pedidos de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="fab6f-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fab6f-104">Este procedimiento le guía por la búsqueda de un cliente, la creación de un nuevo pedido, la búsqueda de un producto y el cobro de pagos del cliente.</span><span class="sxs-lookup"><span data-stu-id="fab6f-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="fab6f-105">Este procedimiento usa la empresa de datos de demostración USRT y está pensado para el funcionario de ventas.</span><span class="sxs-lookup"><span data-stu-id="fab6f-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="fab6f-106">Requisitos previos: el usuario que complete el procedimiento se configura como usuario del centro de llamadas y el catálogo semestral de Fabrikam se publica con al menos un código fuente en él.</span><span class="sxs-lookup"><span data-stu-id="fab6f-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="fab6f-107">Vaya a **Retail y Commerce \> Clientes \> Servicio al cliente**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="fab6f-108">En **SearchText**, especifique los criterios de búsqueda para buscar el cliente.</span><span class="sxs-lookup"><span data-stu-id="fab6f-108">For **SearchText**, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="fab6f-109">Para este procedimiento de ejemplo, escriba "Karen" y seleccione **Tabulador**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="fab6f-110">Selección Buscar.</span><span class="sxs-lookup"><span data-stu-id="fab6f-110">Select Search.</span></span>
    * <span data-ttu-id="fab6f-111">Dado que solo hay un cliente llamado "Karen" en los datos de demostración, el resultado se seleccionará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fab6f-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="fab6f-112">Seleccione **Nuevo pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="fab6f-113">Expanda o contraiga la sección de encabezado **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="fab6f-114">Seleccione el código fuente para el catálogo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="fab6f-115">Si no hay códigos de origen activos, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="fab6f-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="fab6f-116">Seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-116">Select **Add line**.</span></span>
8. <span data-ttu-id="fab6f-117">En el campo **Código de artículo**, especifique el término de búsqueda del artículo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-117">For **Item number**, enter the item search term.</span></span>
    * <span data-ttu-id="fab6f-118">Para este procedimiento de ejemplo, escriba el código de artículo parcial "8111 " y presione el tabulador. Esto hará que se muestre la ventana de búsqueda del artículo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="fab6f-119">Seleccione el producto que se agregará al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="fab6f-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="fab6f-120">Especifique la cantidad de ventas.</span><span class="sxs-lookup"><span data-stu-id="fab6f-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="fab6f-121">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-121">Select **Create**.</span></span>
12. <span data-ttu-id="fab6f-122">Seleccione **Completar** para capturar el pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="fab6f-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="fab6f-123">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-123">Select **Add**.</span></span>
    * <span data-ttu-id="fab6f-124">El vínculo "Agregar" se encuentra en la pestaña de pagos. Si está contraída, abra la pestaña de pagos.</span><span class="sxs-lookup"><span data-stu-id="fab6f-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="fab6f-125">Seleccione el método de pago.</span><span class="sxs-lookup"><span data-stu-id="fab6f-125">Select the payment method.</span></span>
    * <span data-ttu-id="fab6f-126">Para este procedimiento, seleccione el método de pago en efectivo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="fab6f-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fab6f-127">Close the page.</span></span>
16. <span data-ttu-id="fab6f-128">Especifique el importe.</span><span class="sxs-lookup"><span data-stu-id="fab6f-128">Enter the amount.</span></span>
    * <span data-ttu-id="fab6f-129">Para este procedimiento, especifique un importe igual al saldo del pedido que se puede ver en la página Resumen de pedido de ventas a la izquierda del campo de importe.</span><span class="sxs-lookup"><span data-stu-id="fab6f-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="fab6f-130">Esta acción le permitirá que completar el pedido como totalmente pagado.</span><span class="sxs-lookup"><span data-stu-id="fab6f-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="fab6f-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-131">Select **OK**.</span></span>
18. <span data-ttu-id="fab6f-132">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-132">Select **Submit**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fab6f-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fab6f-133">Additional resources</span></span>

[<span data-ttu-id="fab6f-134">Personalizar correos electrónicos transaccionales por modo de entrega</span><span class="sxs-lookup"><span data-stu-id="fab6f-134">Customize transactional emails by mode of delivery</span></span>](../customize-email-delivery-mode.md)

[<span data-ttu-id="fab6f-135">Cambiar el modo de entrega en PDV</span><span class="sxs-lookup"><span data-stu-id="fab6f-135">Change mode of delivery in POS</span></span>](../pos-change-delivery-mode.md)

