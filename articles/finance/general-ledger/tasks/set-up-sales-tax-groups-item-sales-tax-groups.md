---
title: Configurar grupos de impuestos y grupos de impuestos de artículos
description: Esta grabación de tarea le guía por la configuración de los impuestos y los grupos de impuestos de artículos.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 844eee7f81c64eb50ada44cbc151c8aa00c5ae98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815077"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="3c990-103">Configurar grupos de impuestos y grupos de impuestos de artículos</span><span class="sxs-lookup"><span data-stu-id="3c990-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3c990-104">Esta grabación de tarea le guía por la configuración de los impuestos y los grupos de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="3c990-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="3c990-105">Los códigos de impuestos son grupos de códigos de impuestos vinculados a clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="3c990-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="3c990-106">También están vinculados a cuentas contables de transacciones que no están registradas con un proveedor o cliente determinado.</span><span class="sxs-lookup"><span data-stu-id="3c990-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="3c990-107">Los grupos de impuestos de artículos son grupos de códigos de impuestos vinculados a los recursos como productos.</span><span class="sxs-lookup"><span data-stu-id="3c990-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="3c990-108">Los impuestos que se aplican a una transacción concreta se determinan a través de los códigos de impuestos incluidos en el grupo de impuestos y en el grupo de impuestos de artículos de la transacción.</span><span class="sxs-lookup"><span data-stu-id="3c990-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="3c990-109">Los impuestos puede calcularse solo si se selecciona un grupo de impuestos y un grupo de impuestos de artículos para cada transacción para la que se deben calcular o registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="3c990-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="3c990-110">Vaya al **Panel de navegación > Módulos > Impuestos > Impuestos indirectos > Impuestos > Grupos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="3c990-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="3c990-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3c990-111">Click **New**.</span></span>
3. <span data-ttu-id="3c990-112">En el campo **Grupo de impuestos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c990-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="3c990-113">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c990-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="3c990-114">Alterne la expansión de la sección **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3c990-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="3c990-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3c990-115">Click **Add**.</span></span>
7. <span data-ttu-id="3c990-116">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c990-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="3c990-117">En el campo **Código de impuestos**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3c990-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="3c990-118">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c990-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="3c990-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3c990-119">Click **Save**.</span></span>
11. <span data-ttu-id="3c990-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c990-120">Close the page.</span></span>
12. <span data-ttu-id="3c990-121">Vaya a **Impuestos > Impuestos indirectos > Impuestos > Grupos de impuestos de artículos**.</span><span class="sxs-lookup"><span data-stu-id="3c990-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="3c990-122">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3c990-122">Click **New**.</span></span>
14. <span data-ttu-id="3c990-123">En el campo **Grupos de impuestos de artículos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c990-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="3c990-124">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3c990-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="3c990-125">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3c990-125">Click **Add**.</span></span>
17. <span data-ttu-id="3c990-126">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c990-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="3c990-127">En el campo **Código de impuestos**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3c990-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="3c990-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c990-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="3c990-129">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3c990-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]