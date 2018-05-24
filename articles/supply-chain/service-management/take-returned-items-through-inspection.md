---
title: "Inspeccionar artículos devueltos"
description: "Inspeccionar artículos devueltos."
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: df209cfdbdef591e9f24161b3651316c43d69ee0
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---


# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="61210-103">Inspeccionar artículos devueltos</span><span class="sxs-lookup"><span data-stu-id="61210-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="61210-104">Haga clic en **Gestión del inventario** \> **Periódico** \> **Administración de calidad** \> **Órdenes de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="61210-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="61210-105">Localice la línea de pedido que corresponde al artículo devuelto que va a inspeccionar.</span><span class="sxs-lookup"><span data-stu-id="61210-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="61210-106">Las órdenes de cuarentena solo pueden estar asociadas a un número de artículo.</span><span class="sxs-lookup"><span data-stu-id="61210-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="61210-107">Si se devuelven 10 artículos con números de artículos diferentes en un solo envío y se envían a cuarentena, se crearán 10 órdenes de cuarentena individuales.</span><span class="sxs-lookup"><span data-stu-id="61210-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="61210-108">Después de examinar el artículo, realice una selección en el campo **Código de disposición** para indicar qué acción debe tomarse con el artículo y cómo deberá gestionarse la transacción financiera relacionada.</span><span class="sxs-lookup"><span data-stu-id="61210-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="61210-109">Por ejemplo, las acciones incluyen la devolución del artículo al inventario y el reembolso al cliente, dar de baja el artículo y enviar un reemplazo al cliente o devolver el artículo al cliente sin crédito.</span><span class="sxs-lookup"><span data-stu-id="61210-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="61210-110">En caso de que no se pueda asignar el mismo código de disposición a varios artículos devueltos de un solo lote de números de artículo, debe dividir la orden de cuarentena (<STRONG>Funciones</STRONG> &gt; <STRONG>Dividir</STRONG>) para poder asignar un código de disposición diferente a cada sublote.</span><span class="sxs-lookup"><span data-stu-id="61210-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="61210-111">Una vez finalizada la inspección, haga clic en **Notificar como terminado** para liberar los artículos devueltos y crear una entrada del diario de recepción de artículos.</span><span class="sxs-lookup"><span data-stu-id="61210-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="61210-112">La persona o el departamento que recibe los artículos procesará el diario de los artículos que se devuelvan al inventario.</span><span class="sxs-lookup"><span data-stu-id="61210-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="61210-113">O bien</span><span class="sxs-lookup"><span data-stu-id="61210-113">–or–</span></span>
    
    <span data-ttu-id="61210-114">Finalice la orden de cuarentena y mueva los artículos al inventario directamente mediante una de las funciones del botón **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="61210-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="61210-115">Cierre el formulario para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="61210-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="61210-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61210-116">See also</span></span>

[<span data-ttu-id="61210-117">Especificar la disposición de artículos devueltos</span><span class="sxs-lookup"><span data-stu-id="61210-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  



