---
title: Crear criterios de selección de precios de venta
description: Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920540"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="c3e9d-103">Crear criterios de selección de precios de venta</span><span class="sxs-lookup"><span data-stu-id="c3e9d-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c3e9d-104">Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="c3e9d-105">Este procedimiento requiere que haya al menos un modelo de precio de ventas disponible.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="c3e9d-106">Este ejemplo usa el modelo de precio para el modelo de precio de ventas de la solución Altavoz en la empresa de los datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="c3e9d-107">Normalmente, un responsable de productos utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="c3e9d-108">Agregue un nuevo criterio para un modelo de precio de ventas existente</span><span class="sxs-lookup"><span data-stu-id="c3e9d-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="c3e9d-109">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="c3e9d-110">En la lista, seleccione la fila del modelo de producto de la solución Altavoz, pero no seleccione el vínculo del nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="c3e9d-111">En el panel de acciones, haga clic en **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="c3e9d-112">Seleccione **Criterios de modelo de precio**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="c3e9d-113">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-113">Select **New**.</span></span>
1. <span data-ttu-id="c3e9d-114">En el campo **Nombre**, escriba 'Grupo de clientes 10'.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="c3e9d-115">El nombre del criterio del modelo de precios se usa para ayudar a identificar los criterios de selección subyacentes.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="c3e9d-116">En el campo **Modelo de precio**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="c3e9d-117">En el campo **Tipo de pedido**, seleccione *Pedido de ventas*.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="c3e9d-118">El tipo de pedido determina los campos de base de datos que estarán disponibles para la consulta de selección.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="c3e9d-119">Especifique una fecha en el campo **Válido desde**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="c3e9d-120">En el campo **Vence el**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="c3e9d-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="c3e9d-122">Cree la consulta para los criterios de selección</span><span class="sxs-lookup"><span data-stu-id="c3e9d-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="c3e9d-123">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-123">Select **Edit**.</span></span>
2. <span data-ttu-id="c3e9d-124">En el campo **Tabla**, seleccione *Clientes*.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="c3e9d-125">En el campo **Campo**, seleccione *Grupo de clientes*.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="c3e9d-126">En este ejemplo, utilizaremos un grupo de clientes específico para los criterios de selección.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="c3e9d-127">En el campo **Criterios**, seleccione *Grupo de clientes 10*.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="c3e9d-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3e9d-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]