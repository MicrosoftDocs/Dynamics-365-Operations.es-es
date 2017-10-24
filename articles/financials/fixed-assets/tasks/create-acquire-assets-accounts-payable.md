--- 
title: Crear y adquirir activos desde proveedores
description: "Esta guía de la tarea le guiará por la creación y la adquisición de un activo fijo con el proceso de compra."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9149378047fc22efbd401b7af86df07c1403e4f5
ms.openlocfilehash: cfe920b2ef493ab3ae36a9557001086ed99c3e4e
ms.contentlocale: es-es
ms.lasthandoff: 10/05/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="abbab-103">Crear y adquirir activos desde proveedores</span><span class="sxs-lookup"><span data-stu-id="abbab-103">Create and acquire assets from accounts payable</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="abbab-104">Esta guía de la tarea le guiará por la creación y la adquisición de un activo fijo con el proceso de compra.</span><span class="sxs-lookup"><span data-stu-id="abbab-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span> <span data-ttu-id="abbab-105">Usa los roles de contable y responsable de proveedores y la empresa de prueba USMF.</span><span class="sxs-lookup"><span data-stu-id="abbab-105">It uses the Accountant and Accounts payable clerks and the demo company USMF.</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="abbab-106">Configurar los parámetros de activos fijos</span><span class="sxs-lookup"><span data-stu-id="abbab-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="abbab-107">Vaya a Activos fijos > Configuración > Parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="abbab-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="abbab-108">Expanda o contraiga la sección Pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="abbab-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="abbab-109">Active la casilla Permite la adquisición de activos desde Compras.</span><span class="sxs-lookup"><span data-stu-id="abbab-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="abbab-110">Active la casilla Crear activo durante la recepción de producto o el registro de facturas.</span><span class="sxs-lookup"><span data-stu-id="abbab-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="abbab-111">Crear una nueva factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="abbab-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="abbab-112">Vaya a Proveedores > Áreas de trabajo > Entrada de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="abbab-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="abbab-113">Haga clic en Nueva factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="abbab-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="abbab-114">En el campo Cuenta de facturación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abbab-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="abbab-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="abbab-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="abbab-116">En el campo Número, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="abbab-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="abbab-117">En el campo Fecha de registro, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="abbab-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="abbab-118">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="abbab-118">Click Add line.</span></span>
8. <span data-ttu-id="abbab-119">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abbab-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="abbab-120">Los artículos sin existencias o las categorías de compras se pueden usar para la adquisición del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="abbab-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="abbab-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="abbab-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="abbab-122">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="abbab-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="abbab-123">Una línea de factura creará solo un activo fijo, independientemente de la cantidad.</span><span class="sxs-lookup"><span data-stu-id="abbab-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="abbab-124">El valor del campo de cantidad de factura se transferirá a la cantidad de activo fijo.</span><span class="sxs-lookup"><span data-stu-id="abbab-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="abbab-125">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="abbab-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="abbab-126">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="abbab-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="abbab-127">Haga clic en la ficha Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="abbab-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="abbab-128">Active la casilla Crear un activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="abbab-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="abbab-129">En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abbab-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="abbab-130">En la lista, seleccione el grupo de activos fijos que se usará al crear el nuevo activo fijo.</span><span class="sxs-lookup"><span data-stu-id="abbab-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="abbab-131">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="abbab-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="abbab-132">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="abbab-132">Click Post.</span></span>
    * <span data-ttu-id="abbab-133">El activo fijo se creará y adquirirá cuando se registre la factura.</span><span class="sxs-lookup"><span data-stu-id="abbab-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  


