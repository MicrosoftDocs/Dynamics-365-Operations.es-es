--- 
title: "Mantener L. MAT. para un modelo de configuración de producto"
description: "La ejecución de este procedimiento requiere un modelo de configuración de producto existente."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: ca2f50ffbe7fb95bfe7cc83175cb98e3d5887a98
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="2a76e-103">Mantener L. MAT. para un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="2a76e-103">Maintain BOM for a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2a76e-104">La ejecución de este procedimiento requiere un modelo de configuración de producto existente.</span><span class="sxs-lookup"><span data-stu-id="2a76e-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="2a76e-105">El modelo Altavoz superior de la empresa de demostración USMF se usa para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2a76e-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="2a76e-106">Adición de una línea de L. MAT</span><span class="sxs-lookup"><span data-stu-id="2a76e-106">Add a BOM line</span></span>
1. <span data-ttu-id="2a76e-107">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="2a76e-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="2a76e-108">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="2a76e-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="2a76e-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2a76e-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2a76e-110">Seleccione el Altavoz superior para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2a76e-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="2a76e-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2a76e-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2a76e-112">Expanda la sección Líneas de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="2a76e-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="2a76e-113">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="2a76e-113">Click Add.</span></span>
7. <span data-ttu-id="2a76e-114">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2a76e-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="2a76e-115">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2a76e-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="2a76e-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="2a76e-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="2a76e-117">Agregar detalles de línea de L. MAT</span><span class="sxs-lookup"><span data-stu-id="2a76e-117">Add BOM line details</span></span>
1. <span data-ttu-id="2a76e-118">Haga clic en Detalles de línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="2a76e-118">Click BOM line details.</span></span>
2. <span data-ttu-id="2a76e-119">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="2a76e-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="2a76e-120">Por ejemplo, puede seleccionar el artículo M0055.</span><span class="sxs-lookup"><span data-stu-id="2a76e-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="2a76e-121">Para cada propiedad de la línea de L. MAT, puede seleccionar si toma un valor fijo o se asigna a un atributo.</span><span class="sxs-lookup"><span data-stu-id="2a76e-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="2a76e-122">Active la casilla Establecer.</span><span class="sxs-lookup"><span data-stu-id="2a76e-122">Select the Set check box.</span></span>
4. <span data-ttu-id="2a76e-123">Seleccione Sí en el campo Cálculo.</span><span class="sxs-lookup"><span data-stu-id="2a76e-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="2a76e-124">La configuración de la propiedad Cálculo en Sí garantiza que se incluye la línea de L. MAT en los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="2a76e-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="2a76e-125">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="2a76e-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="2a76e-126">Active la casilla Establecer.</span><span class="sxs-lookup"><span data-stu-id="2a76e-126">Select the Set check box.</span></span>
7. <span data-ttu-id="2a76e-127">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="2a76e-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="2a76e-128">El campo de cantidad determina qué cantidad del artículo se incluirá en la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="2a76e-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="2a76e-129">Esto podría ser un candidato obvio para una asignación de atributos.</span><span class="sxs-lookup"><span data-stu-id="2a76e-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="2a76e-130">Haga clic en la ficha Dimensión.</span><span class="sxs-lookup"><span data-stu-id="2a76e-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="2a76e-131">Compruebe si cualquiera de las dimensiones del producto está activas y, por tanto, debe tener un valor o atributo asignado.</span><span class="sxs-lookup"><span data-stu-id="2a76e-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="2a76e-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2a76e-132">Click OK.</span></span>


