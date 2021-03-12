---
title: Crear criterios de selección de precios de venta
description: Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60a7c7230d4eb57d840121f6ee490bf829e0dc8f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999665"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="97d32-103">Crear criterios de selección de precios de venta</span><span class="sxs-lookup"><span data-stu-id="97d32-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="97d32-104">Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos.</span><span class="sxs-lookup"><span data-stu-id="97d32-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="97d32-105">Este procedimiento requiere que haya al menos un modelo de precio de ventas disponible.</span><span class="sxs-lookup"><span data-stu-id="97d32-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="97d32-106">Este ejemplo usa el modelo de precio para el modelo de precio de ventas de la solución Altavoz en la empresa de los datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="97d32-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="97d32-107">Normalmente, un responsable de productos utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="97d32-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="97d32-108">Agregue un nuevo criterio para un modelo de precio de ventas existente</span><span class="sxs-lookup"><span data-stu-id="97d32-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="97d32-109">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="97d32-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="97d32-110">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="97d32-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="97d32-111">En la lista, seleccione la fila del modelo de producto de la solución Altavoz, pero no haga clic en el vínculo del nombre del modelo.</span><span class="sxs-lookup"><span data-stu-id="97d32-111">In the list, select the row for the Speaker solution product model, but don't click the link for the model name.</span></span>
4. <span data-ttu-id="97d32-112">En el panel de acciones, haga clic en Modelo.</span><span class="sxs-lookup"><span data-stu-id="97d32-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="97d32-113">Haga clic en Criterios de modelo de precio.</span><span class="sxs-lookup"><span data-stu-id="97d32-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="97d32-114">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="97d32-114">Click New.</span></span>
7. <span data-ttu-id="97d32-115">En el campo Nombre, escriba "Grupo de clientes 10".</span><span class="sxs-lookup"><span data-stu-id="97d32-115">In the Name field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="97d32-116">El nombre del criterio del modelo de precios se usa para ayudar a identificar los criterios de selección subyacentes.</span><span class="sxs-lookup"><span data-stu-id="97d32-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="97d32-117">En el campo Modelo de precio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="97d32-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="97d32-118">En el campo Tipo de pedido, seleccione Pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="97d32-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="97d32-119">El tipo de pedido determina los campos de base de datos que estarán disponibles para la consulta de selección.</span><span class="sxs-lookup"><span data-stu-id="97d32-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="97d32-120">Especifique una fecha en el campo Válido desde.</span><span class="sxs-lookup"><span data-stu-id="97d32-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="97d32-121">En el campo Vence el, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="97d32-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="97d32-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="97d32-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="97d32-123">Cree la consulta para los criterios de selección</span><span class="sxs-lookup"><span data-stu-id="97d32-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="97d32-124">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="97d32-124">Click Edit.</span></span>
2. <span data-ttu-id="97d32-125">En el campo Tabla, seleccione Clientes.</span><span class="sxs-lookup"><span data-stu-id="97d32-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="97d32-126">Seleccione Grupo de clientes en el campo Campo.</span><span class="sxs-lookup"><span data-stu-id="97d32-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="97d32-127">En este ejemplo, utilizaremos un grupo de clientes específico para los criterios de selección.</span><span class="sxs-lookup"><span data-stu-id="97d32-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="97d32-128">En el campo Criterios, seleccione Grupo de clientes 10.</span><span class="sxs-lookup"><span data-stu-id="97d32-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="97d32-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="97d32-129">Click OK.</span></span>

