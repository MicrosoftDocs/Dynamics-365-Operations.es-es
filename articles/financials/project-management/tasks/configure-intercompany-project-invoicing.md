---
title: Configurar la facturación de proyectos de empresas vinculadas
description: Este tema muestra cómo configurar un proyecto facturando entre dos empresas de su organización.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867328"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="b13be-103">Configurar la facturación de proyectos de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="b13be-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b13be-104">Este tema muestra cómo configurar un proyecto facturando entre dos empresas de su organización.</span><span class="sxs-lookup"><span data-stu-id="b13be-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="b13be-105">Esta tarea usa el conjunto de datos USSI.</span><span class="sxs-lookup"><span data-stu-id="b13be-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="b13be-106">En el panel de exploración, vaya a **Módulos > Proveedores > Proveedores > Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="b13be-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="b13be-107">En la lista **Todos los proveedores** busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b13be-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="b13be-108">En el panel de acciones, seleccione **Gneral**.</span><span class="sxs-lookup"><span data-stu-id="b13be-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="b13be-109">Seleccione **Empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="b13be-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="b13be-110">Establezca el campo **Activo** en **Sí** para habilitar el comercio entre empresas.</span><span class="sxs-lookup"><span data-stu-id="b13be-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="b13be-111">En el campo **Empresa del cliente**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b13be-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="b13be-112">En el campo **Mi cuenta**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b13be-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="b13be-113">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b13be-113">Select **Save**.</span></span>
9. <span data-ttu-id="b13be-114">Cierre las páginas para regresar a la página principal.</span><span class="sxs-lookup"><span data-stu-id="b13be-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="b13be-115">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Administración de proyectos y parámetros de contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="b13be-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="b13be-116">Seleccione la pestaña **Empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="b13be-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="b13be-117">Desplace el control deslizante a la opción **Sí** para activar la programación de recursos y las hojas de horas de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="b13be-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="b13be-118">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b13be-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="b13be-119">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b13be-119">Select **New**.</span></span>
15. <span data-ttu-id="b13be-120">En el campo **Entidad jurídica a la que se presta el trabajador**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b13be-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="b13be-121">Seleccione la casilla **Acumular ingresos**.</span><span class="sxs-lookup"><span data-stu-id="b13be-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="b13be-122">En el campo **Hoja de horas predeterminada**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b13be-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="b13be-123">En el campo **Categoría de gastos predeterminada**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b13be-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="b13be-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b13be-124">Select **Save**.</span></span>
20. <span data-ttu-id="b13be-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b13be-125">Close the page.</span></span>
21. <span data-ttu-id="b13be-126">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Registrar > Configuración de registro**.</span><span class="sxs-lookup"><span data-stu-id="b13be-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="b13be-127">En el campo de **Tipos de cuenta contable**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="b13be-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="b13be-128">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b13be-128">Select **New**.</span></span>
24. <span data-ttu-id="b13be-129">En el campo **Cuenta principal** de la nueva fila, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="b13be-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="b13be-130">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b13be-130">Select **Save**.</span></span>
26. <span data-ttu-id="b13be-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b13be-131">Close the page.</span></span>
27. <span data-ttu-id="b13be-132">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Transferir precio**.</span><span class="sxs-lookup"><span data-stu-id="b13be-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="b13be-133">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b13be-133">Select **New**.</span></span>
29. <span data-ttu-id="b13be-134">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="b13be-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="b13be-135">En el campo **Entidad jurídica a la que se presta el trabajador**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b13be-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="b13be-136">En el campo de **Modelo de precio de transferencia**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="b13be-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="b13be-137">Escriba un número en el campo **Precio**.</span><span class="sxs-lookup"><span data-stu-id="b13be-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="b13be-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b13be-138">Select **Save**.</span></span>

