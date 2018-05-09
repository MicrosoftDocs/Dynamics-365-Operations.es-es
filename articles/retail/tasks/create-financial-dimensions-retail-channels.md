--- 
title: "Creación de dimensiones financieras para los canales de Retail y configuración de los valores de dimensión en las tiendas"
description: "Este procedimiento le muestra el proceso de creación de una dimensión financiera de canal minorista con valores de dimensión y pasos para configurar valores de dimensión financiera en tiendas minoristas."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3782d5d2a43b6b22a6f5b25c806e9d4bba5999a5
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="dc415-103">Creación de dimensiones financieras para los canales de Retail y configuración de los valores de dimensión en las tiendas</span><span class="sxs-lookup"><span data-stu-id="dc415-103">Create financial dimensions for Retail channels and configure dimension values on stores</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="dc415-104">Este procedimiento le muestra el proceso de creación de una dimensión financiera de canal minorista con valores de dimensión y pasos para configurar valores de dimensión financiera en tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="dc415-104">This procedure walks through creating a retail channel financial dimension with dimension values and steps to configure financial dimension values on retail stores.</span></span> <span data-ttu-id="dc415-105">El tema no incluye otros pasos relacionados, como la creación de conjuntos de dimensiones y estructuras contables.</span><span class="sxs-lookup"><span data-stu-id="dc415-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="dc415-106">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="dc415-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="dc415-107">Vaya a Contabilidad general > Plan contable > Dimensiones > Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="dc415-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="dc415-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="dc415-108">Click New.</span></span>
3. <span data-ttu-id="dc415-109">En el campo Usar valores de, seleccione "Canales comerciales".</span><span class="sxs-lookup"><span data-stu-id="dc415-109">In the Use values from field, select 'Retail channels'.</span></span>
4. <span data-ttu-id="dc415-110">En el campo Nombre de dimensión, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="dc415-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="dc415-111">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="dc415-111">Click Activate.</span></span>
6. <span data-ttu-id="dc415-112">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="dc415-112">Click Close.</span></span>
7. <span data-ttu-id="dc415-113">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="dc415-113">Click Activate.</span></span>
8. <span data-ttu-id="dc415-114">Haga clic en Valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="dc415-114">Click Dimension values.</span></span>
9. <span data-ttu-id="dc415-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dc415-115">Close the page.</span></span>
10. <span data-ttu-id="dc415-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="dc415-116">Click Save.</span></span>
11. <span data-ttu-id="dc415-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dc415-117">Close the page.</span></span>
12. <span data-ttu-id="dc415-118">Vaya a Venta minorista y comercio > Canales > Tiendas > Todas las tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="dc415-118">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
13. <span data-ttu-id="dc415-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dc415-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="dc415-120">Expanda la sección Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="dc415-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="dc415-121">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="dc415-121">Click Edit.</span></span>
16. <span data-ttu-id="dc415-122">En el campo Retailchannel, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dc415-122">In the Retailchannel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="dc415-123">En la lista, busque y seleccione el valor de dimensión para el almacén que se está actualizando.</span><span class="sxs-lookup"><span data-stu-id="dc415-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="dc415-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dc415-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="dc415-125">En el campo de centro de coste, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dc415-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="dc415-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="dc415-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="dc415-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dc415-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="dc415-128">En el campo Departamento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dc415-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="dc415-129">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="dc415-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="dc415-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dc415-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="dc415-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="dc415-131">Click Save.</span></span>


