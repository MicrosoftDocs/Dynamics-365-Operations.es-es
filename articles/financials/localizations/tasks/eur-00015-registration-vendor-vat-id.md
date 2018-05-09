--- 
title: Registrar un id. de IVA de proveedor
description: "Este procedimiento muestra cómo agregar identificadores de registro de IVA y un impuesto salvo el número en una cuenta de proveedor."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c398ca76b2cef2c27b57bab4b50824ec59538297
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="register-a-vendor-vat-id"></a><span data-ttu-id="bad05-103">Registrar un id. de IVA de proveedor</span><span class="sxs-lookup"><span data-stu-id="bad05-103">Register a vendor VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bad05-104">Este procedimiento muestra cómo agregar identificadores de registro de IVA y un impuesto salvo el número en una cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="bad05-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="bad05-105">Este proceso es similar para las entidades jurídicas y clientes.</span><span class="sxs-lookup"><span data-stu-id="bad05-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="bad05-106">Para completar este procedimiento, debe configurar identificadores de IVA.</span><span class="sxs-lookup"><span data-stu-id="bad05-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="bad05-107">Este procedimiento se aplica a todos los países o regiones europeos.</span><span class="sxs-lookup"><span data-stu-id="bad05-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="bad05-108">Este procedimiento se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal en Alemania.</span><span class="sxs-lookup"><span data-stu-id="bad05-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="bad05-109">Este procedimiento se ha creado para un administrador de gestión de datos, un administrador de proveedores o un administrador de clientes.</span><span class="sxs-lookup"><span data-stu-id="bad05-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="bad05-110">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="bad05-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="bad05-111">Vaya a Proveedores > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="bad05-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="bad05-112">En la lista, busque y seleccione el proveedor DE-01001</span><span class="sxs-lookup"><span data-stu-id="bad05-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="bad05-113">Haga clic en Id. de registro.</span><span class="sxs-lookup"><span data-stu-id="bad05-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="bad05-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="bad05-114">Click Add.</span></span>
5. <span data-ttu-id="bad05-115">Seleccione el Id. de IVA.</span><span class="sxs-lookup"><span data-stu-id="bad05-115">Select VAT ID.</span></span>
6. <span data-ttu-id="bad05-116">En el campo Número de registro, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bad05-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="bad05-117">Especifique un identificador de IVA en Alemania para el proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bad05-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="bad05-118">El identificador debe coincidir el formato especificado del tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="bad05-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="bad05-119">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="bad05-119">Click the General tab.</span></span>
8. <span data-ttu-id="bad05-120">En el campo Vigente, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="bad05-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="bad05-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bad05-121">Click Save.</span></span>
10. <span data-ttu-id="bad05-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bad05-122">Click New.</span></span>
11. <span data-ttu-id="bad05-123">En el campo Nombre o descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bad05-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="bad05-124">Por ejemplo, escriba ITA.</span><span class="sxs-lookup"><span data-stu-id="bad05-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="bad05-125">En el campo País o región, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bad05-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="bad05-126">Por ejemplo, seleccione ITA.</span><span class="sxs-lookup"><span data-stu-id="bad05-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="bad05-127">Seleccione Sí en el campo Principal para país.</span><span class="sxs-lookup"><span data-stu-id="bad05-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="bad05-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bad05-128">Click Save.</span></span>
15. <span data-ttu-id="bad05-129">Haga clic en la ficha Visión general.</span><span class="sxs-lookup"><span data-stu-id="bad05-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="bad05-130">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="bad05-130">Click Add.</span></span>
17. <span data-ttu-id="bad05-131">En el campo Tipo de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bad05-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="bad05-132">Por ejemplo, seleccione Id. de IVA.</span><span class="sxs-lookup"><span data-stu-id="bad05-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="bad05-133">En el campo Número de registro, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bad05-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="bad05-134">Por ejemplo, especifique un identificador de IVA en Italia.</span><span class="sxs-lookup"><span data-stu-id="bad05-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="bad05-135">El identificador debe tener el mismo formato que el tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="bad05-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="bad05-136">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bad05-136">Click Save.</span></span>
20. <span data-ttu-id="bad05-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bad05-137">Close the page.</span></span>
21. <span data-ttu-id="bad05-138">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="bad05-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bad05-139">Por ejemplo, seleccione DE-01001.</span><span class="sxs-lookup"><span data-stu-id="bad05-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="bad05-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bad05-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="bad05-141">Expanda la sección Factura y entrega.</span><span class="sxs-lookup"><span data-stu-id="bad05-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="bad05-142">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="bad05-142">Click Edit.</span></span>
25. <span data-ttu-id="bad05-143">En el campo NIF, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bad05-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="bad05-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bad05-144">Click Save.</span></span>


