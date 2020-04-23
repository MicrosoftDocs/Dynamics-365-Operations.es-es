---
title: Fabricantes y modelos de activos
description: Este tema explica cómo configurar fabricantes de activos y los modelos relacionados en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2ef8a9afc007ce7e453f5e9cadfb912490545c0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205124"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="804fe-103">Fabricantes y modelos de activos</span><span class="sxs-lookup"><span data-stu-id="804fe-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="804fe-104">Este tema explica cómo configurar fabricantes de activos y los modelos relacionados en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="804fe-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="804fe-105">Los modelos pueden estar relacionados con los tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="804fe-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="804fe-106">Configurar relaciones entre productos y modelos</span><span class="sxs-lookup"><span data-stu-id="804fe-106">Set up product-model relations</span></span>

1. <span data-ttu-id="804fe-107">Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Fabricante y modelo**.</span><span class="sxs-lookup"><span data-stu-id="804fe-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="804fe-108">Seleccione **Nuevo** para crear un producto nuevo.</span><span class="sxs-lookup"><span data-stu-id="804fe-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="804fe-109">En el campo **Fabricante**, especifique un nombre para el fabricante del activo.</span><span class="sxs-lookup"><span data-stu-id="804fe-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="804fe-110">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="804fe-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="804fe-111">En el FastTab **Modelos** , seleccione **Agregar** para crear un modelo de activo que debe estar relacionado con el fabricante del activo.</span><span class="sxs-lookup"><span data-stu-id="804fe-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="804fe-112">En el campo **Modelo**, especifique un nombre para el modelo del activo.</span><span class="sxs-lookup"><span data-stu-id="804fe-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="804fe-113">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="804fe-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="804fe-114">En el campo **Tipo de activo**, seleccione el tipo de activo con el que debe estar relacionado el modelo del fabricante.</span><span class="sxs-lookup"><span data-stu-id="804fe-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="804fe-115">También puede configurar las relaciones para los tipos, los fabricantes, y los modelos de activos en la búsqueda **Tipos del activo**.</span><span class="sxs-lookup"><span data-stu-id="804fe-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="804fe-116">Para obtener más información, consulte [Tipos de activo](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="804fe-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="804fe-117">En el FastTab **Detalles**, el campo **Modelos** muestra el número de modelos de activos que se configuran en el fabricante del acivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="804fe-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="804fe-118">El campo **Activos** muestra el número de activos que utilizan el fabricante seleccionado.</span><span class="sxs-lookup"><span data-stu-id="804fe-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="804fe-119">El campo **Activos** muestra el número de objetos que utilizan el modelo de fabricante.</span><span class="sxs-lookup"><span data-stu-id="804fe-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="804fe-120">Un tipo de activo puede carecer de relaciones de modelo de fabricante de activos, puede estar relacionado con un solo modelo de fabricante de activos o puede estar relacionado con varios modelos de fabricante de activos.</span><span class="sxs-lookup"><span data-stu-id="804fe-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="804fe-121">Si un tipo de activos está relacionado con al menos un modelo de fabricante, solo las combinaciones configuradas en la búsqueda **Modelo de fabricante** se pueden seleccionar en las páginas de Administración de activos donde se puede configurar una combinación de tipo de activo, fabricante y modelo.</span><span class="sxs-lookup"><span data-stu-id="804fe-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="804fe-122">Las páginas son **Todos los activos**, **Niveles de servicio de activos**, **Valores predeterminados de tipo de trabajo** y **Líneas de presupuesto de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="804fe-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="804fe-123">Si algunos tipos de activos no están relacionados con ningún modelo de proveedor, en las páginas solo se muestran los tipos de activos y los modelos de fabricante que tampoco tienen ninguna relación con tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="804fe-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="804fe-124">Seleccionar un fabricante y un modelo en un objeto</span><span class="sxs-lookup"><span data-stu-id="804fe-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="804fe-125">Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**.</span><span class="sxs-lookup"><span data-stu-id="804fe-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="804fe-126">En la columna **Activo**, seleccione el vínculo para el activo.</span><span class="sxs-lookup"><span data-stu-id="804fe-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="804fe-127">Aparecerá la página **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="804fe-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="804fe-128">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="804fe-128">Select **Edit**.</span></span>
4. <span data-ttu-id="804fe-129">En el FastTab **General**, seleccione valores **Fabricante** y **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="804fe-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>
