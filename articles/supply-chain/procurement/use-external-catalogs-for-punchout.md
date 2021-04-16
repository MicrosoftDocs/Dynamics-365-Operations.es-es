---
title: Usar catálogos externos para la adquisición electrónica de marcaje de salida
description: Este tema explica cómo puede usar catálogos externos para crear y enviar solicitudes.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a839f672454105871a101c190ee87d701e58db4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811071"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a><span data-ttu-id="662ac-103">Usar catálogos externos para la adquisición electrónica de marcaje de salida</span><span class="sxs-lookup"><span data-stu-id="662ac-103">Use external catalogs for PunchOut e-procurement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="662ac-104">Mediante los catálogos externos para la adquisición electrónica de marcaje de salida, no tiene que mantener información sobre los productos de los proveedores en sus propios datos maestros.</span><span class="sxs-lookup"><span data-stu-id="662ac-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="662ac-105">En su lugar, el carro de la compra en la página web de un proveedor se convierte en las líneas de la solicitud con la información correcta de producto.</span><span class="sxs-lookup"><span data-stu-id="662ac-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="662ac-106">Debe evitar mantener las descripciones y los precios de los productos de los proveedores en sus propios datos de producto maestro.</span><span class="sxs-lookup"><span data-stu-id="662ac-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="662ac-107">Es mejor usar catálogos externos para la adquisición electrónica de marcaje de salida.</span><span class="sxs-lookup"><span data-stu-id="662ac-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="662ac-108">A continuación, cuando los empleados creen solicitudes, pueden consultar el sitio del catálogo externo del proveedor (es decir, salir del sistema y dirigirse al sitio del proveedor).</span><span class="sxs-lookup"><span data-stu-id="662ac-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="662ac-109">Los productos que se agregan al carro de la compra en la página web del proveedor se pueden convertir a continuación en líneas de solicitud.</span><span class="sxs-lookup"><span data-stu-id="662ac-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="662ac-110">Por lo tanto, se recopila la información de producto correcta: identificador, nombre, precio y demás datos del producto.</span><span class="sxs-lookup"><span data-stu-id="662ac-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="662ac-111">Para usar catálogos externos, un empleado debe crear una solicitud en la página **Mis solicitudes de compra** .</span><span class="sxs-lookup"><span data-stu-id="662ac-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="662ac-112">El empleado que crea una solicitud se conoce como preparador de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="662ac-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="662ac-113">Como preparador, puede realizar las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="662ac-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="662ac-114">Use la acción de línea **Catálogos externos** para abrir una página que incluya todos los catálogos externos disponibles para el solicitante especificado, la entidad jurídica compradora y la unidad operativa receptora.</span><span class="sxs-lookup"><span data-stu-id="662ac-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="662ac-115">Dependiendo de sus permisos, cambie el solicitante, la entidad jurídica compradora y la unidad operativa receptora.</span><span class="sxs-lookup"><span data-stu-id="662ac-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="662ac-116">Un cambio en estos valores puede cambiar la lista de catálogos externos disponibles para un solicitante.</span><span class="sxs-lookup"><span data-stu-id="662ac-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="662ac-117">Los catálogos externos disponibles dependen de las directivas de compra del activo actual para la entidad jurídica compradora o la unidad operativa receptora.</span><span class="sxs-lookup"><span data-stu-id="662ac-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="662ac-118">Estas directivas pueden permitir o impedir el acceso a categorías de compras específicas.</span><span class="sxs-lookup"><span data-stu-id="662ac-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="662ac-119">Por lo tanto, la lista de catálogos externos que se asignen a estas categorías de compras puede verse afectada.</span><span class="sxs-lookup"><span data-stu-id="662ac-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="662ac-120">Para obtener más información sobre directivas, vea [Visión general de directivas de compra](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="662ac-120">For more information about policies, see [Purchasing policies overview](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="662ac-121">Para obtener los catálogos externos para categorías de compras específicas, escriba el texto en el campo de búsqueda de catálogos.</span><span class="sxs-lookup"><span data-stu-id="662ac-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="662ac-122">Para agregar productos de un catálogo externo de un proveedor en la página web, haga clic en el catálogo externo.</span><span class="sxs-lookup"><span data-stu-id="662ac-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="662ac-123">A continuación, agregue los productos al carro de la compra y confirme la compra. Las líneas del carro de la compra se transferirán a Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="662ac-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="662ac-124">Si existen varias opciones para categorías de compras, seleccione la categoría de compras correcta antes de agregar líneas a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="662ac-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="662ac-125">Una vez las líneas se hayan agregado a una solicitud, puede agregar más líneas sin usar catálogos externos.</span><span class="sxs-lookup"><span data-stu-id="662ac-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="662ac-126">Como alternativa, puede continuar utilizando catálogos externos para agregar líneas.</span><span class="sxs-lookup"><span data-stu-id="662ac-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="662ac-127">Cuando la solicitud esté lista, use la acción **Flujo de trabajo** > **Enviar** para enviarla para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="662ac-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="662ac-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="662ac-128">Additional resources</span></span>

- [<span data-ttu-id="662ac-129">Configurar un catálogo externo para la adquisición electrónica de marcaje de salida</span><span class="sxs-lookup"><span data-stu-id="662ac-129">Set up an external catalog for PunchOut e-procurement</span></span>](set-up-external-catalog-for-punchout.md)
- [<span data-ttu-id="662ac-130">Mejoras de cXML de compra</span><span class="sxs-lookup"><span data-stu-id="662ac-130">Purchasing cXML enhancements</span></span>](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]