---
title: Ajustes de Retail
description: Este procedimiento le guiará por la creación de un ajuste de precios de Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7443f69473c0aad478d47f80f284b1156bad9c24
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962994"
---
# <a name="retail-price-adjustments"></a><span data-ttu-id="17e74-103">Ajustes de Retail</span><span class="sxs-lookup"><span data-stu-id="17e74-103">Retail price adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17e74-104">Este procedimiento le guiará por la creación de un ajuste de precios de Commerce.</span><span class="sxs-lookup"><span data-stu-id="17e74-104">This procedure will walk through creating a commerce price adjustment.</span></span> <span data-ttu-id="17e74-105">Un ajuste de precios puede definir el precio de venta de un artículo directamente, o modificar su precio de venta de la base o precio de venta de contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="17e74-105">A price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="17e74-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="17e74-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="17e74-107">Haga clic en Administración de precios y descuentos.</span><span class="sxs-lookup"><span data-stu-id="17e74-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="17e74-108">Haga clic en la ficha Ajustes de precio.</span><span class="sxs-lookup"><span data-stu-id="17e74-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="17e74-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="17e74-109">Click New.</span></span>
    * <span data-ttu-id="17e74-110">Desde aquí puede crear todas las reglas de precios y descuentos más usadas, incluidos descuentos, ajustes de precios, diarios de acuerdos comerciales y reglas de precios de categoría.</span><span class="sxs-lookup"><span data-stu-id="17e74-110">From here you can create all of the most commonly used price and discount rules, including discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="17e74-111">Haga clic en Ajuste de precios.</span><span class="sxs-lookup"><span data-stu-id="17e74-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="17e74-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="17e74-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="17e74-113">Expanda la sección Líneas.</span><span class="sxs-lookup"><span data-stu-id="17e74-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="17e74-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="17e74-114">Click Add.</span></span>
    * <span data-ttu-id="17e74-115">Para este ejemplo, especifique "81126" en el campo Producto.</span><span class="sxs-lookup"><span data-stu-id="17e74-115">For this example, enter '81126' in the Product field.</span></span> <span data-ttu-id="17e74-116">A continuación, escriba "10,0" en el campo Porcentaje de descuento.</span><span class="sxs-lookup"><span data-stu-id="17e74-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="17e74-117">Un ajuste de precios de tipo de porcentaje de descuento reducirá un precio de ventas base o precio de ventas de contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="17e74-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="17e74-118">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="17e74-118">Click Add.</span></span>
    * <span data-ttu-id="17e74-119">Para este ejemplo, especifique "81125" en el campo Producto.</span><span class="sxs-lookup"><span data-stu-id="17e74-119">For this example, enter '81125' in the Product field.</span></span> <span data-ttu-id="17e74-120">A continuación, seleccione el "Importe de descuento por pronto pago" en el campo Método de descuento.</span><span class="sxs-lookup"><span data-stu-id="17e74-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="17e74-121">Por último, escriba "5.0" en el campo Importe de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="17e74-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="17e74-122">Un tipo de descuento de importe de descuento por pronto pago es un importe restado de un precio base o un precio de contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="17e74-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="17e74-123">Haga clic en Grupos de precios.</span><span class="sxs-lookup"><span data-stu-id="17e74-123">Click Price groups.</span></span>
    * <span data-ttu-id="17e74-124">Seleccione "RP-Houston" en el campo Grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="17e74-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="17e74-125">Esto asociará el ajuste de precios a la tienda Houston.</span><span class="sxs-lookup"><span data-stu-id="17e74-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="17e74-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="17e74-126">Click Save.</span></span>
11. <span data-ttu-id="17e74-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="17e74-127">Close the page.</span></span>
12. <span data-ttu-id="17e74-128">En el campo Estado, seleccione "Habilitado".</span><span class="sxs-lookup"><span data-stu-id="17e74-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="17e74-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="17e74-129">Click Save.</span></span>
14. <span data-ttu-id="17e74-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="17e74-130">Close the page.</span></span>
15. <span data-ttu-id="17e74-131">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="17e74-131">Refresh the page.</span></span>

