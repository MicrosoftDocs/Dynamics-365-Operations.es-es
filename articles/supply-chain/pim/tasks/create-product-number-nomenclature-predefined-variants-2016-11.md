---
title: Crear una nomenclatura de números de producto para las variantes de producto predefinidas
description: Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920666"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="0d9ed-103">Crear una nomenclatura de números de producto para las variantes de producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="0d9ed-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0d9ed-104">Este tema explica cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="0d9ed-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0d9ed-106">La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="0d9ed-107">Esta tarea normalmente la realiza un diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="0d9ed-108">Crear una nomenclatura de número de producto</span><span class="sxs-lookup"><span data-stu-id="0d9ed-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="0d9ed-109">Vaya a **Gestión de información de productos \> Configuración \> Nomenclatura de productos**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="0d9ed-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-110">Select **New**.</span></span>
1. <span data-ttu-id="0d9ed-111">En el campo **Nombre**, escriba el nombre de la nomenclatura que ayude a identificar el grupo de dimensiones de producto de destino, por ejemplo, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="0d9ed-112">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="0d9ed-113">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-113">Select **Add**.</span></span>
1. <span data-ttu-id="0d9ed-114">Seleccione el número de **Producto maestro**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="0d9ed-115">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-115">Select **Add**.</span></span>
1. <span data-ttu-id="0d9ed-116">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="0d9ed-117">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="0d9ed-118">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-118">Select **Add**.</span></span>
1. <span data-ttu-id="0d9ed-119">Seleccione **Color**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-119">Select **Color**.</span></span>
1. <span data-ttu-id="0d9ed-120">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-120">Select **Add**.</span></span>
1. <span data-ttu-id="0d9ed-121">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="0d9ed-122">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="0d9ed-123">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-123">Select **Add**.</span></span>
1. <span data-ttu-id="0d9ed-124">Seleccione **Tamaño**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-124">Select **Size**.</span></span>
1. <span data-ttu-id="0d9ed-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="0d9ed-126">Asignar la nomenclatura a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="0d9ed-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="0d9ed-127">Seleccione **Grupos de dimensiones de producto**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="0d9ed-128">Seleccione el grupo **Dimensiones de productos SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="0d9ed-129">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-129">Select **Edit**.</span></span>
4. <span data-ttu-id="0d9ed-130">Seleccione **Sí** en el campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="0d9ed-131">En el campo **Nomenclatura del número de variante del producto**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="0d9ed-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0d9ed-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]