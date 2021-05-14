---
title: Mantener L. MAT. para un modelo de configuración de producto
description: La ejecución de este procedimiento requiere un modelo de configuración de producto existente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921326"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="3f957-103">Mantener L. MAT. para un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="3f957-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f957-104">La ejecución de este procedimiento requiere un modelo de configuración de producto existente.</span><span class="sxs-lookup"><span data-stu-id="3f957-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="3f957-105">El modelo Altavoz superior de la empresa de demostración USMF se usa para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3f957-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="3f957-106">Adición de una línea de L. MAT</span><span class="sxs-lookup"><span data-stu-id="3f957-106">Add a BOM line</span></span>

1. <span data-ttu-id="3f957-107">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="3f957-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="3f957-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3f957-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3f957-109">Seleccione el Altavoz superior para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3f957-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="3f957-110">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f957-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="3f957-111">Expanda la sección **Líneas de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="3f957-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="3f957-112">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f957-112">Select **Add**.</span></span>
1. <span data-ttu-id="3f957-113">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f957-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="3f957-114">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f957-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="3f957-115">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f957-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="3f957-116">Agregar detalles de línea de L. MAT</span><span class="sxs-lookup"><span data-stu-id="3f957-116">Add BOM line details</span></span>

1. <span data-ttu-id="3f957-117">Seleccione **Detalles de línea de L. MAT.**.</span><span class="sxs-lookup"><span data-stu-id="3f957-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="3f957-118">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f957-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="3f957-119">Por ejemplo, puede seleccionar el artículo M0055.</span><span class="sxs-lookup"><span data-stu-id="3f957-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="3f957-120">Para cada propiedad de la línea de L. MAT, puede seleccionar si toma un valor fijo o se asigna a un atributo.</span><span class="sxs-lookup"><span data-stu-id="3f957-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="3f957-121">Seleccione la casilla **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="3f957-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="3f957-122">Seleccione *Sí* en el campo **Cálculo**.</span><span class="sxs-lookup"><span data-stu-id="3f957-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="3f957-123">La configuración de la propiedad **Cálculo** en *Sí* garantiza que se incluye la línea de L. MAT en los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="3f957-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="3f957-124">Seleccione la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3f957-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="3f957-125">Seleccione la casilla **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="3f957-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="3f957-126">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="3f957-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="3f957-127">El campo de cantidad determina qué cantidad del artículo se incluirá en la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f957-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="3f957-128">Esto podría ser un candidato obvio para una asignación de atributos.</span><span class="sxs-lookup"><span data-stu-id="3f957-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="3f957-129">Seleccione la pestaña **Dimensión**.</span><span class="sxs-lookup"><span data-stu-id="3f957-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="3f957-130">Compruebe si cualquiera de las dimensiones del producto está activas y, por tanto, debe tener un valor o atributo asignado.</span><span class="sxs-lookup"><span data-stu-id="3f957-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="3f957-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f957-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]