---
title: Crear un pedido de compra regido por el presupuesto
description: Use este procedimiento para crear un pedido de compra que se compruebe para ver si hay presupuesto disponible.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cbfbbef3bd7c7398f0f17b6cddbbff8c4755638d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963722"
---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="0ec87-103">Crear un pedido de compra regido por el presupuesto</span><span class="sxs-lookup"><span data-stu-id="0ec87-103">Create a purchase order governed by budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ec87-104">Use este procedimiento para crear un pedido de compra que se compruebe para ver si hay presupuesto disponible.</span><span class="sxs-lookup"><span data-stu-id="0ec87-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="0ec87-105">Este registro usa la empresa USMF con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="0ec87-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="0ec87-106">Revisar la configuración de control presupuestario</span><span class="sxs-lookup"><span data-stu-id="0ec87-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="0ec87-107">Vaya a Gestión presupuestaria > Configuración > Control presupuestario > Configuración de control presupuestario.</span><span class="sxs-lookup"><span data-stu-id="0ec87-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="0ec87-108">Haga clic en la pestaña Fondos presupuestarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="0ec87-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="0ec87-109">Haga clic en la pestaña Documentos y diarios.</span><span class="sxs-lookup"><span data-stu-id="0ec87-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="0ec87-110">Haga clic en la pestaña Definir reglas de control presupuestario.</span><span class="sxs-lookup"><span data-stu-id="0ec87-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="0ec87-111">Haga clic en la pestaña Definir grupos presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="0ec87-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="0ec87-112">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0ec87-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="0ec87-113">Crear el encabezado del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="0ec87-113">Create the purchase order header</span></span>
1. <span data-ttu-id="0ec87-114">Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="0ec87-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="0ec87-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0ec87-115">Click New.</span></span>
3. <span data-ttu-id="0ec87-116">En el campo Cuenta de proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0ec87-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="0ec87-117">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="0ec87-117">Expand the General section.</span></span>
5. <span data-ttu-id="0ec87-118">En el campo de Fecha de contabilidad, defina la fecha a "2016-01-01".</span><span class="sxs-lookup"><span data-stu-id="0ec87-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="0ec87-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0ec87-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="0ec87-120">Agregar una línea de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="0ec87-120">Add a purchase order line</span></span>
1. <span data-ttu-id="0ec87-121">En el campo Categoría de compras, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0ec87-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="0ec87-122">Establezca Cantidad en "2".</span><span class="sxs-lookup"><span data-stu-id="0ec87-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="0ec87-123">En el campo Unidad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0ec87-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="0ec87-124">Establezca el precio unitario en "10000".</span><span class="sxs-lookup"><span data-stu-id="0ec87-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="0ec87-125">Haga clic en Operaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="0ec87-125">Click Financials.</span></span>
6. <span data-ttu-id="0ec87-126">Haga clic en Distribuir importes.</span><span class="sxs-lookup"><span data-stu-id="0ec87-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="0ec87-127">En el campo Cuenta contable, especifique el valor "601300-001-023--".</span><span class="sxs-lookup"><span data-stu-id="0ec87-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="0ec87-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0ec87-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="0ec87-129">Realizar comprobación presupuestaria</span><span class="sxs-lookup"><span data-stu-id="0ec87-129">Perform budget checking</span></span>
1. <span data-ttu-id="0ec87-130">Haga clic en Operaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="0ec87-130">Click Financials.</span></span>
2. <span data-ttu-id="0ec87-131">Haga clic en Realizar comprobación presupuestaria.</span><span class="sxs-lookup"><span data-stu-id="0ec87-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="0ec87-132">Haga clic en Operaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="0ec87-132">Click Financials.</span></span>
4. <span data-ttu-id="0ec87-133">Haga clic en Errores o advertencias de la comprobación presupuestaria.</span><span class="sxs-lookup"><span data-stu-id="0ec87-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="0ec87-134">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="0ec87-134">Click Close.</span></span>

