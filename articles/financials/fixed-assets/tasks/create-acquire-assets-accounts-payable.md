---
title: Crear y adquirir activos desde Proveedores
description: Esta guía de la tarea le guiará por la creación y la adquisición de un activo fijo con el proceso de compra.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6c36338cc67855c79ec97d88bb8b633417b85c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "316427"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="0fe26-103">Crear y adquirir activos desde Proveedores</span><span class="sxs-lookup"><span data-stu-id="0fe26-103">Create and acquire assets from Accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0fe26-104">Esta guía de la tarea le guiará por la creación y la adquisición de un activo fijo con el proceso de compra.</span><span class="sxs-lookup"><span data-stu-id="0fe26-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="0fe26-105">Usa los roles de contable y responsable de proveedores y la empresa de prueba USMF.</span><span class="sxs-lookup"><span data-stu-id="0fe26-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="0fe26-106">Configurar los parámetros de activos fijos</span><span class="sxs-lookup"><span data-stu-id="0fe26-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="0fe26-107">Vaya a Activos fijos > Configuración > Parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="0fe26-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="0fe26-108">Expanda o contraiga la sección Pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="0fe26-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="0fe26-109">Active la casilla Permite la adquisición de activos desde Compras.</span><span class="sxs-lookup"><span data-stu-id="0fe26-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="0fe26-110">Active la casilla Crear activo durante la recepción de producto o el registro de facturas.</span><span class="sxs-lookup"><span data-stu-id="0fe26-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="0fe26-111">Crear una nueva factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="0fe26-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="0fe26-112">Vaya a Proveedores > Áreas de trabajo > Entrada de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="0fe26-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="0fe26-113">Haga clic en Nueva factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="0fe26-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="0fe26-114">En el campo Cuenta de facturación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0fe26-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="0fe26-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0fe26-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0fe26-116">En el campo Número, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0fe26-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="0fe26-117">En el campo Fecha de registro, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="0fe26-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="0fe26-118">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="0fe26-118">Click Add line.</span></span>
8. <span data-ttu-id="0fe26-119">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0fe26-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0fe26-120">Los artículos sin existencias o las categorías de compras se pueden usar para la adquisición del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="0fe26-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="0fe26-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0fe26-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="0fe26-122">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="0fe26-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0fe26-123">Una línea de factura creará solo un activo fijo, independientemente de la cantidad.</span><span class="sxs-lookup"><span data-stu-id="0fe26-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="0fe26-124">El valor del campo de cantidad de factura se transferirá a la cantidad de activo fijo.</span><span class="sxs-lookup"><span data-stu-id="0fe26-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="0fe26-125">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0fe26-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="0fe26-126">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="0fe26-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="0fe26-127">Haga clic en la ficha Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="0fe26-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="0fe26-128">Active la casilla Crear un activo fijo nuevo.</span><span class="sxs-lookup"><span data-stu-id="0fe26-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="0fe26-129">En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0fe26-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="0fe26-130">En la lista, seleccione el grupo de activos fijos que se usará al crear el nuevo activo fijo.</span><span class="sxs-lookup"><span data-stu-id="0fe26-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="0fe26-131">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0fe26-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="0fe26-132">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="0fe26-132">Click Post.</span></span>
    * <span data-ttu-id="0fe26-133">El activo fijo se creará y adquirirá cuando se registre la factura.</span><span class="sxs-lookup"><span data-stu-id="0fe26-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  

