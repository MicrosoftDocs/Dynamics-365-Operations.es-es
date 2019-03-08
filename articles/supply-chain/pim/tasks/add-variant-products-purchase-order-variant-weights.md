---
title: Agregar variantes de productos a pedidos de compra con variantes de peso
description: Este procedimiento le guía por los pasos para el uso de pesos de variante con el fin de rellenar automáticamente las líneas de pedido de compra para cada variante de un producto.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 446260a09bd5177877637ac8a288ad584dfa2b2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "345499"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="f8faf-103">Agregar variantes de productos a pedidos de compra con variantes de peso</span><span class="sxs-lookup"><span data-stu-id="f8faf-103">Add variant products to purchase orders using variant weights</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8faf-104">Este procedimiento le guía por los pasos para el uso de pesos de variante con el fin de rellenar automáticamente las líneas de pedido de compra para cada variante de un producto.</span><span class="sxs-lookup"><span data-stu-id="f8faf-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="f8faf-105">Al seleccionar la cantidad del producto que desea comprar, las líneas de pedido de compra se crean para todas las variantes del producto con las cantidades sugeridas basadas en los pesos configurados en las variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="f8faf-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="f8faf-106">Este procedimiento no incluye pasos para configurar valores de peso en dimensiones de producto y variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="f8faf-106">This procedure doesn’t include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="f8faf-107">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="f8faf-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="f8faf-108">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f8faf-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="f8faf-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f8faf-109">Click New.</span></span>
3. <span data-ttu-id="f8faf-110">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f8faf-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f8faf-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8faf-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f8faf-112">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="f8faf-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="f8faf-113">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f8faf-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="f8faf-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8faf-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f8faf-115">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f8faf-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="f8faf-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f8faf-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="f8faf-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8faf-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="f8faf-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f8faf-118">Click OK.</span></span>
12. <span data-ttu-id="f8faf-119">Alterne la expansión de la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="f8faf-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="f8faf-120">Haga clic en la pestaña Variantes.</span><span class="sxs-lookup"><span data-stu-id="f8faf-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="f8faf-121">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="f8faf-121">Click Add line.</span></span>
15. <span data-ttu-id="f8faf-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8faf-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="f8faf-123">En el campo Código de artículo, escriba "0140".</span><span class="sxs-lookup"><span data-stu-id="f8faf-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="f8faf-124">Establezca el valor de cantidad en '1000'.</span><span class="sxs-lookup"><span data-stu-id="f8faf-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="f8faf-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f8faf-125">Click Save.</span></span>

