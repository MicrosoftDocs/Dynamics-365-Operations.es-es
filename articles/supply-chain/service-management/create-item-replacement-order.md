---
title: Creación de pedidos de sustitución de artículos
description: Los pedidos de sustitución de artículos se suelen crear una vez devuelto e inspeccionado un producto.
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 784a2522c27e8131f211ffc52319552b3b928cc3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "355021"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="61e36-103">Creación de pedidos de sustitución de artículos</span><span class="sxs-lookup"><span data-stu-id="61e36-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="61e36-104">Los pedidos de sustitución de artículos se suelen crear una vez devuelto e inspeccionado un producto.</span><span class="sxs-lookup"><span data-stu-id="61e36-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="61e36-105">Sin embargo, si es necesario sustituir un artículo antes de su devolución, o si no se va a devolver el artículo original, puede crear un pedido de sustitución de artículo inmediatamente después de crear un pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="61e36-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="61e36-106">Crear un pedido de sustitución después de recibir un artículo devuelto</span><span class="sxs-lookup"><span data-stu-id="61e36-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="61e36-107">Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.</span><span class="sxs-lookup"><span data-stu-id="61e36-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="61e36-108">Cree un nuevo pedido de devolución o seleccione un pedido de devolución de la lista para abrir el formulario **Pedido de devolución - Número de RMA: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="61e36-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="61e36-109">Haga clic en **Línea de devolución**, y después seleccione **Artículo de sustitución**.</span><span class="sxs-lookup"><span data-stu-id="61e36-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="61e36-110">Seleccione el artículo por el que desee sustituir el artículo devuelto.</span><span class="sxs-lookup"><span data-stu-id="61e36-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="61e36-111">Introduzca las especificaciones del artículo y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="61e36-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="61e36-112">Haga clic en **Albarán** para generar el albarán del pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="61e36-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="61e36-113">Un pedido de ventas se genera para el artículo de sustitución que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="61e36-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="61e36-114">Después de crear el pedido de ventas del artículo de sustitución, se buscan acuerdos de venta automáticamente y, si existe alguno aplicable, se aplica al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e36-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="61e36-115">Crear un pedido de sustitución antes de recibir un artículo devuelto</span><span class="sxs-lookup"><span data-stu-id="61e36-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="61e36-116">Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.</span><span class="sxs-lookup"><span data-stu-id="61e36-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="61e36-117">Cree un nuevo pedido de devolución o seleccione un pedido de devolución de la lista para abrir el formulario **Pedido de devolución - Número de RMA: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="61e36-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="61e36-118">Haga clic en **Buscar pedido de ventas** si desea identificar el pedido de ventas del artículo devuelto.</span><span class="sxs-lookup"><span data-stu-id="61e36-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="61e36-119">Complete el formulario **Buscar pedido de ventas** y después haga clic en **Aceptar** para cerrar el formulario y volver al formulario **Pedido de devolución - número RMA: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="61e36-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="61e36-120">La línea de pedido de ventas del artículo devuelto se copia en el pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="61e36-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="61e36-121">Haga clic en **Pedido de sustitución** para abrir el formulario **Crear pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="61e36-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="61e36-122">Active la casilla de verificación **Copiar líneas de pedidos devueltos** para transferir detalles desde el pedido de devolución que seleccionó en el formulario **Pedido de devolución - Número de RMA: %1, %2** hasta este pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e36-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="61e36-123">Introduzca o modifique los detalles según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="61e36-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="61e36-124">Si ha identificado el pedido de ventas en el paso 3 y la línea de pedido de ventas del artículo devuelto está vinculada a un acuerdo de venta, el identificador del acuerdo de venta aplicable para el pedido de sustitución del artículo se mostrará automáticamente en el campo **Id. del acuerdo de venta**.</span><span class="sxs-lookup"><span data-stu-id="61e36-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="61e36-125">Haga clic en **Aceptar** para cerrar el formulario **Crear pedido de ventas** y abrir el formulario **Pedido de ventas**, donde puede continuar especificando la información del nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e36-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="61e36-126">Cualquier línea de pedido de devolución aplicable se copiará en el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e36-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="61e36-127">Si el identificador del acuerdo de venta se muestra automáticamente en el campo **Id. del acuerdo de venta**, el acuerdo de venta está vinculado al encabezado de pedido de ventas correspondiente al pedido de sustitución de artículo.</span><span class="sxs-lookup"><span data-stu-id="61e36-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="61e36-128">Si existe un compromiso aplicable en el acuerdo de venta que no se ha satisfecho aún y se crea el pedido de ventas antes de que venza el acuerdo de venta, se establece un vínculo entre la línea del acuerdo de venta y la línea del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e36-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="61e36-129">Por lo tanto, la información del acuerdo de venta, como el precio del artículo, se copia en la nueva línea del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e36-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  


