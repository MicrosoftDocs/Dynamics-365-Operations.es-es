---
title: Crear una nomenclatura de números de producto para las variantes de producto predefinidas
description: Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6871765a450295a3f308ec7e706f1b126071585f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986056"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="3f67a-103">Crear una nomenclatura de números de producto para las variantes de producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="3f67a-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f67a-104">Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.</span><span class="sxs-lookup"><span data-stu-id="3f67a-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="3f67a-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="3f67a-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3f67a-106">La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño.</span><span class="sxs-lookup"><span data-stu-id="3f67a-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="3f67a-107">Esta tarea normalmente la realiza un diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="3f67a-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="3f67a-108">Crear una nomenclatura de número de producto</span><span class="sxs-lookup"><span data-stu-id="3f67a-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="3f67a-109">Seleccione **Definición de modelo de variante del producto**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="3f67a-110">Seleccione **Nomenclatura de producto**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="3f67a-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-111">Select **New**.</span></span>
4. <span data-ttu-id="3f67a-112">En el campo **Nombre**, escriba el nombre de la nomenclatura que ayude a identificar el grupo de dimensiones de producto de destino, por ejemplo, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="3f67a-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="3f67a-113">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f67a-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="3f67a-114">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-114">Select **Add**.</span></span>
7. <span data-ttu-id="3f67a-115">Seleccione el número de **Producto maestro**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="3f67a-116">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-116">Select **Add**.</span></span>
9. <span data-ttu-id="3f67a-117">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="3f67a-118">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f67a-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="3f67a-119">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-119">Select **Add**.</span></span>
12. <span data-ttu-id="3f67a-120">Seleccione **Color**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-120">Select **Color**.</span></span>
13. <span data-ttu-id="3f67a-121">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-121">Select **Add**.</span></span>
14. <span data-ttu-id="3f67a-122">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="3f67a-123">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f67a-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="3f67a-124">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-124">Select **Add**.</span></span>
17. <span data-ttu-id="3f67a-125">Seleccione **Tamaño**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-125">Select **Size**.</span></span>
18. <span data-ttu-id="3f67a-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3f67a-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="3f67a-127">Asignar la nomenclatura a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="3f67a-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="3f67a-128">Seleccione **Grupos de dimensiones de producto**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="3f67a-129">Seleccione el grupo **Dimensiones de productos SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="3f67a-130">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-130">Select **Edit**.</span></span>
4. <span data-ttu-id="3f67a-131">Seleccione **Sí** en el campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="3f67a-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="3f67a-132">En el campo **Nomenclatura del número de variante del producto**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f67a-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="3f67a-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3f67a-133">Close the page.</span></span>

