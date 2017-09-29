--- 
title: Crear atributos de lote para un producto
description: "Este procedimiento muestra cómo crear un atributo de lote, asignar intervalos de valor predeterminados e incluir el atributo en un grupo."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5694ac4ec47b446c19681bfb5c6b07ff82f4575f
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="d11e6-103">Crear atributos de lote para un producto</span><span class="sxs-lookup"><span data-stu-id="d11e6-103">Create batch attributes for a product</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d11e6-104">Este procedimiento muestra cómo crear un atributo de lote, asignar intervalos de valor predeterminados e incluir el atributo en un grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="d11e6-105">La empresa de datos de demostración utilizada para crear este procedimiento es la empresa USP2.</span><span class="sxs-lookup"><span data-stu-id="d11e6-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="d11e6-106">Vaya a Gestión del inventario > Configurar > Lote > Atributos de lote.</span><span class="sxs-lookup"><span data-stu-id="d11e6-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="d11e6-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-107">Click New.</span></span>
3. <span data-ttu-id="d11e6-108">En el campo Atributo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d11e6-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="d11e6-109">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d11e6-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d11e6-110">En el campo Tipo de atributo, seleccione Fracción.</span><span class="sxs-lookup"><span data-stu-id="d11e6-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="d11e6-111">Este procedimiento usa el tipo Fracción para habilitar valores decimales.</span><span class="sxs-lookup"><span data-stu-id="d11e6-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="d11e6-112">Puede seleccionar otros tipos de atributos.</span><span class="sxs-lookup"><span data-stu-id="d11e6-112">You can select other attribute types.</span></span> <span data-ttu-id="d11e6-113">Si selecciona el tipo Enumeración, debe especificar valores en la lista de numeración para poder especificar un valor en el campo Destino.</span><span class="sxs-lookup"><span data-stu-id="d11e6-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="d11e6-114">Escriba un número en el campo Mínimo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="d11e6-115">Escriba un número en el campo Máximo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="d11e6-116">Escriba un número en el campo Incremento.</span><span class="sxs-lookup"><span data-stu-id="d11e6-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="d11e6-117">En el campo Destino, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d11e6-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="d11e6-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d11e6-118">Click Save.</span></span>
11. <span data-ttu-id="d11e6-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d11e6-119">Close the page.</span></span>
12. <span data-ttu-id="d11e6-120">Vaya a Gestión del inventario > Configurar > Lote > Grupos de atributos de lote.</span><span class="sxs-lookup"><span data-stu-id="d11e6-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="d11e6-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-121">Click New.</span></span>
14. <span data-ttu-id="d11e6-122">En el campo Grupo de atributos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d11e6-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="d11e6-123">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d11e6-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="d11e6-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d11e6-124">Click Save.</span></span>
17. <span data-ttu-id="d11e6-125">Haga clic en Atributos de grupo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-125">Click Group attributes.</span></span>
18. <span data-ttu-id="d11e6-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d11e6-126">Click New.</span></span>
19. <span data-ttu-id="d11e6-127">En el campo Atributo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d11e6-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="d11e6-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d11e6-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="d11e6-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d11e6-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d11e6-130">Los atributos se pueden incluir en cualquiera de los grupos.</span><span class="sxs-lookup"><span data-stu-id="d11e6-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="d11e6-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d11e6-131">Click Save.</span></span>
23. <span data-ttu-id="d11e6-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d11e6-132">Close the page.</span></span>


