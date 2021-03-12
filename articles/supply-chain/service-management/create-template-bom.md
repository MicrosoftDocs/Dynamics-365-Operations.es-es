---
title: Crear plantilla de L. MAT manual
description: Puede crear una plantilla de L. MAT mediante una serie de métodos.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b34cc2e9921df6e3ef619e2b2adaf8d2069fbac
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974569"
---
# <a name="create-a-template-bom"></a><span data-ttu-id="39d92-103">Crear plantilla de L. MAT manual</span><span class="sxs-lookup"><span data-stu-id="39d92-103">Create a template BOM</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="39d92-104">Puede crear una plantilla de L. MAT mediante cualquiera de los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="39d92-104">You can create a template BOM by using any of the following methods.</span></span> <span data-ttu-id="39d92-105">Para todos los métodos, los campos **Fecha inicial** y **Fecha final** son opcionales y solo para información.</span><span class="sxs-lookup"><span data-stu-id="39d92-105">For all methods, the **From date** and **To date** fields are optional and for information only.</span></span>

## <a name="create-a-template-bom-manually"></a><span data-ttu-id="39d92-106">Crear una plantilla de L. MAT manualmente</span><span class="sxs-lookup"><span data-stu-id="39d92-106">Create a template BOM manually</span></span>

1.  <span data-ttu-id="39d92-107">Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-107">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="39d92-108">Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-108">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="39d92-109">En **Copiar líneas de L. MAT desde la referencia**, seleccione la opción **Manual** .</span><span class="sxs-lookup"><span data-stu-id="39d92-109">Under **Copy BOM lines from reference**, select the **Manual** option.</span></span>

4.  <span data-ttu-id="39d92-110">En el campo **Código de artículo**,escriba un artículo del tipo **L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-110">In the **Item number** field, enter an item of the type **BOM**.</span></span>

5.  <span data-ttu-id="39d92-111">En el campo **Nombre**, especifique un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="39d92-111">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="39d92-112">En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.</span><span class="sxs-lookup"><span data-stu-id="39d92-112">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="39d92-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39d92-113">Click **OK**.</span></span>

<span data-ttu-id="39d92-114">Se crea una nueva plantilla de L. MAT en blanco.</span><span class="sxs-lookup"><span data-stu-id="39d92-114">A new, blank template BOM is created.</span></span>

## <a name="create-a-template-bom-based-on-another-template-bom"></a><span data-ttu-id="39d92-115">Crear una plantilla de L. MAT basada en otra plantilla de L. MAT</span><span class="sxs-lookup"><span data-stu-id="39d92-115">Create a template BOM based on another template BOM</span></span>

1.  <span data-ttu-id="39d92-116">Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-116">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="39d92-117">Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-117">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="39d92-118">En **Copiar líneas de L. MAT desde la referencia**, seleccione la opción **Plantilla de L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-118">Under **Copy BOM lines from reference**, select the **Template BOM** option.</span></span>

4.  <span data-ttu-id="39d92-119">En el campo **Número de referencia**, seleccione una plantilla de L. MAT existente para copiar a la nueva plantilla de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="39d92-119">In the **Reference number** field, select an existing template BOM to copy to your new template BOM.</span></span>

5.  <span data-ttu-id="39d92-120">En el campo **Nombre**, especifique un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="39d92-120">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="39d92-121">En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.</span><span class="sxs-lookup"><span data-stu-id="39d92-121">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="39d92-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39d92-122">Click **OK**.</span></span>

<span data-ttu-id="39d92-123">Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la plantilla de L. MAT original.</span><span class="sxs-lookup"><span data-stu-id="39d92-123">A new template BOM is created by using lines that correspond to the lines in the original template BOM.</span></span>

## <a name="create-a-template-bom-based-on-an-item-bom"></a><span data-ttu-id="39d92-124">Crear una plantilla de L. MAT basada en una L. MAT de artículo</span><span class="sxs-lookup"><span data-stu-id="39d92-124">Create a template BOM based on an item BOM</span></span>

1.  <span data-ttu-id="39d92-125">Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-125">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="39d92-126">Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-126">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="39d92-127">En **Copiar líneas de L. MAT desde la referencia**, seleccione **L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-127">Under **Copy BOM lines from reference**, select **BOM**.</span></span>

4.  <span data-ttu-id="39d92-128">En el campo **Número de referencia** , seleccione una versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="39d92-128">In the **Reference number** field, select a BOM version.</span></span> <span data-ttu-id="39d92-129">Se copia un artículo del tipo L. MAT en el **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="39d92-129">An item of the type BOM is copied to the **Item number**.</span></span>

5.  <span data-ttu-id="39d92-130">En el campo **Nombre**, especifique un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="39d92-130">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="39d92-131">En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.</span><span class="sxs-lookup"><span data-stu-id="39d92-131">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="39d92-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39d92-132">Click **OK**.</span></span>

<span data-ttu-id="39d92-133">Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la L. MAT que aparece en **Listas de materiales**.</span><span class="sxs-lookup"><span data-stu-id="39d92-133">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **Bills of materials**.</span></span>

## <a name="create-a-template-bom-based-on-a-production-bom"></a><span data-ttu-id="39d92-134">Crear una plantilla de L. MAT basada en una L. MAT de producción</span><span class="sxs-lookup"><span data-stu-id="39d92-134">Create a template BOM based on a production BOM</span></span>

1.  <span data-ttu-id="39d92-135">Haga clic en **Gestión de servicio** \> **Configuración** \> **Objetos de servicio** \> **Plantilla de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-135">Click **Service management** \> **Setup** \> **Service objects** \> **Template BOMs**.</span></span>

2.  <span data-ttu-id="39d92-136">Pulse CTRL+N para abrir el formulario **Crear plantilla de L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-136">Press CTRL+N to open the **Create template BOM** form.</span></span>

3.  <span data-ttu-id="39d92-137">En **Copiar líneas de L. MAT desde la referencia**, seleccione **Producción**.</span><span class="sxs-lookup"><span data-stu-id="39d92-137">Under **Copy BOM lines from reference**, select **Production**.</span></span>

4.  <span data-ttu-id="39d92-138">En el campo **Número de referencia** , seleccione una L. MAT de producción.</span><span class="sxs-lookup"><span data-stu-id="39d92-138">In the **Reference number** field, select a production BOM.</span></span>

5.  <span data-ttu-id="39d92-139">En el campo **Nombre**, especifique un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="39d92-139">In the **Name** field, enter a name for the template.</span></span>

6.  <span data-ttu-id="39d92-140">En los campos **Fecha inicial** y **Fecha final**, escriba un intervalo de fechas en el cual la plantilla de L. MAT esté activa.</span><span class="sxs-lookup"><span data-stu-id="39d92-140">In the **From date** and **To date** fields, enter a date interval in which the template BOM is active.</span></span>

7.  <span data-ttu-id="39d92-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39d92-141">Click **OK**.</span></span>

<span data-ttu-id="39d92-142">Se crea una nueva plantilla de L. MAT con líneas que se corresponden con las líneas de la L. MAT que aparece en **L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="39d92-142">A new template BOM is created by using lines that correspond to the lines of the BOM listed in **BOM**.</span></span>

## <a name="see-also"></a><span data-ttu-id="39d92-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39d92-143">See also</span></span>

[<span data-ttu-id="39d92-144">Plantilla de L. MAT</span><span class="sxs-lookup"><span data-stu-id="39d92-144">Template BOMs</span></span>](template-boms.md)

  


