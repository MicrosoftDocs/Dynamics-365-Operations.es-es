---
title: Usar catálogos externos para la adquisición electrónica de marcaje de salida
description: Este tema explica cómo puede usar catálogos externos para crear y enviar solicitudes.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0734db6f777de2bcd6ea024c9255f589c155e44f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569831"
---
# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="2cd2c-103">Usar catálogos externos para la adquisición electrónica de marcaje de salida</span><span class="sxs-lookup"><span data-stu-id="2cd2c-103">Use external catalogs for PunchOut eProcurement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2cd2c-104">Mediante los catálogos externos para la adquisición electrónica de marcaje de salida, no tiene que mantener información sobre los productos de los proveedores en sus propios datos maestros.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="2cd2c-105">En su lugar, el carro de la compra en la página web de un proveedor se convierte en las líneas de la solicitud con la información correcta de producto.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="2cd2c-106">Debe evitar mantener las descripciones y los precios de los productos de los proveedores en sus propios datos de producto maestro.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="2cd2c-107">Es mejor usar catálogos externos para la adquisición electrónica de marcaje de salida.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="2cd2c-108">A continuación, cuando los empleados creen solicitudes, pueden consultar el sitio del catálogo externo del proveedor (es decir, salir del sistema y dirigirse al sitio del proveedor).</span><span class="sxs-lookup"><span data-stu-id="2cd2c-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="2cd2c-109">Los productos que se agregan al carro de la compra en la página web del proveedor se pueden convertir a continuación en líneas de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="2cd2c-110">Por lo tanto, se recopila la información de producto correcta: identificador, nombre, precio y demás datos del producto.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="2cd2c-111">Para usar catálogos externos, un empleado debe crear una solicitud en la página **Mis solicitudes de compra** .</span><span class="sxs-lookup"><span data-stu-id="2cd2c-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="2cd2c-112">El empleado que crea una solicitud se conoce como preparador de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="2cd2c-113">Como preparador, puede realizar las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="2cd2c-114">Use la acción de línea **Catálogos externos** para abrir una página que incluya todos los catálogos externos disponibles para el solicitante especificado, la entidad jurídica compradora y la unidad operativa receptora.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="2cd2c-115">Dependiendo de sus permisos, cambie el solicitante, la entidad jurídica compradora y la unidad operativa receptora.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="2cd2c-116">Un cambio en estos valores puede cambiar la lista de catálogos externos disponibles para un solicitante.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="2cd2c-117">Los catálogos externos disponibles dependen de las directivas de compra del activo actual para la entidad jurídica compradora o la unidad operativa receptora.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="2cd2c-118">Estas directivas pueden permitir o impedir el acceso a categorías de compras específicas.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="2cd2c-119">Por lo tanto, la lista de catálogos externos que se asignen a estas categorías de compras puede verse afectada.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="2cd2c-120">Para obtener más información sobre directivas, vea [Directivas de compra](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2c-120">For more information about policies, see [Purchasing policies](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="2cd2c-121">Para obtener los catálogos externos para categorías de compras específicas, escriba el texto en el campo de búsqueda de catálogos.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="2cd2c-122">Para agregar productos de un catálogo externo de un proveedor en la página web, haga clic en el catálogo externo.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="2cd2c-123">A continuación, agregue los productos al carro de la compra y confirme la compra. Las líneas del carro de la compra se transferirán a Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="2cd2c-124">Si existen varias opciones para categorías de compras, seleccione la categoría de compras correcta antes de agregar líneas a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="2cd2c-125">Una vez las líneas se hayan agregado a una solicitud, puede agregar más líneas sin usar catálogos externos.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="2cd2c-126">Como alternativa, puede continuar utilizando catálogos externos para agregar líneas.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="2cd2c-127">Cuando la solicitud esté lista, use la acción **Flujo de trabajo** > **Enviar** para enviarla para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="2cd2c-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>
