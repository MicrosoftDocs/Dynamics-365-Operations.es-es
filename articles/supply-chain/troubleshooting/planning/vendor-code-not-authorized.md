---
title: El código de proveedor no está autorizado para un producto y una fecha específicos
description: Cuando intenta confirmar un pedido planificado o agregar una línea a un pedido de compra, recibe un mensaje de error que indica que el código de proveedor no está autorizado para un producto y una fecha.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294176"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="33d70-103">El código de proveedor no está autorizado para un producto y una fecha específicos</span><span class="sxs-lookup"><span data-stu-id="33d70-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="33d70-104">Código de error: SYP4881415</span><span class="sxs-lookup"><span data-stu-id="33d70-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="33d70-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="33d70-105">Symptoms</span></span>

<span data-ttu-id="33d70-106">Cuando intenta confirmar un pedido planificado o agregar una línea a un pedido de compra, recibe el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="33d70-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="33d70-107">El código de proveedor %1 no está autorizado para %2 en %3.</span><span class="sxs-lookup"><span data-stu-id="33d70-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="33d70-108">Causa</span><span class="sxs-lookup"><span data-stu-id="33d70-108">Cause</span></span>

<span data-ttu-id="33d70-109">El error se produce porque el campo **Método de verificación de proveedor aprobado** está configurado en *Solo advertencia* o *No permitido* para el producto especificado, y el proveedor no está autorizado actualmente para suministrar ese producto.</span><span class="sxs-lookup"><span data-stu-id="33d70-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="33d70-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="33d70-110">Resolution</span></span>

<span data-ttu-id="33d70-111">Para solucionar este problema, desactive la verificación del proveedor para el producto relevante o apruebe al proveedor.</span><span class="sxs-lookup"><span data-stu-id="33d70-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="33d70-112">Para deshabilitar la verificación de proveedor de un producto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33d70-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="33d70-113">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="33d70-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="33d70-114">Abrir el producto relevante.</span><span class="sxs-lookup"><span data-stu-id="33d70-114">Open the relevant product.</span></span>
1. <span data-ttu-id="33d70-115">En la ficha desplegable **Compra**, establezca el campo **Método de verificación de proveedor aprobado** en un valor que no sea *Solo advertencia* o *No permitido*.</span><span class="sxs-lookup"><span data-stu-id="33d70-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="33d70-116">Para aprobar un proveedor de un producto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33d70-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="33d70-117">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="33d70-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="33d70-118">Abrir el artículo relevante.</span><span class="sxs-lookup"><span data-stu-id="33d70-118">Open the relevant item.</span></span>
1. <span data-ttu-id="33d70-119">En el panel de acciones, en la ficha **Compra**, en el grupo **Proveedor aprobado**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="33d70-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="33d70-120">En la página de lista **Proveedor aprobado**, agregue una fila a la cuadrícula y después establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="33d70-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="33d70-121">**Proveedor** - Seleccione el proveedor para aprobar el producto actual.</span><span class="sxs-lookup"><span data-stu-id="33d70-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="33d70-122">**Fecha efectiva** - Seleccione la primera fecha para la que se aprueba el proveedor.</span><span class="sxs-lookup"><span data-stu-id="33d70-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="33d70-123">**Fecha de vencimiento** - Seleccione la primera fecha para la que se aprueba el proveedor.</span><span class="sxs-lookup"><span data-stu-id="33d70-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="33d70-124">Para más información, consute [Aprobar proveedores para productos específicos](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="33d70-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>
