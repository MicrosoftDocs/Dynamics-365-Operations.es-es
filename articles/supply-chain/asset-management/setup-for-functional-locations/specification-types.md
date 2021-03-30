---
title: Tipos de atributos de mantenimiento
description: En este tema se explica cómo crear tipos de atributos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b93c2ab284d5746f4ecd48cd8b8ffe59aea9f90
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217254"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="2f04f-103">Tipos de atributos de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="2f04f-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="2f04f-104">En este tema se explica cómo crear tipos de atributos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="2f04f-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="2f04f-105">Los atributos se utilizan para describir las propiedades de varios elementos.</span><span class="sxs-lookup"><span data-stu-id="2f04f-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="2f04f-106">Puede configurar los atributos de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="2f04f-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="2f04f-107">Tipos de ubicaciones funcionales</span><span class="sxs-lookup"><span data-stu-id="2f04f-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="2f04f-108">Crear ubicaciones funcionales</span><span class="sxs-lookup"><span data-stu-id="2f04f-108">Create functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="2f04f-109">Tipos de activos</span><span class="sxs-lookup"><span data-stu-id="2f04f-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="2f04f-110">Activos</span><span class="sxs-lookup"><span data-stu-id="2f04f-110">Assets</span></span>

<span data-ttu-id="2f04f-111">Los atributos que puede configurar varían, en función del elemento.</span><span class="sxs-lookup"><span data-stu-id="2f04f-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="2f04f-112">Por ejemplo, para una ubicación funcional, puede configurar los atributos para la configuración y el tamaño físico de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="2f04f-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="2f04f-113">Para un tipo de activo o un activo, puede configurar los atributos por volumen del motor, el consumo energético y carga de capacidad máxima en diferentes condiciones.</span><span class="sxs-lookup"><span data-stu-id="2f04f-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="2f04f-114">Crear tipos de atributo</span><span class="sxs-lookup"><span data-stu-id="2f04f-114">Create attribute types</span></span>

<span data-ttu-id="2f04f-115">Puede crear sus propios tipos de atributos.</span><span class="sxs-lookup"><span data-stu-id="2f04f-115">You can create your own attribute types.</span></span> <span data-ttu-id="2f04f-116">Además, puede transferir dimensiones de producto a la página **Tipos de atributo**.</span><span class="sxs-lookup"><span data-stu-id="2f04f-116">Additionally, you can transfer product dimensions to the **Attribute types** page.</span></span>

1. <span data-ttu-id="2f04f-117">Seleccione **Administración de activos** \> **Configuración** \> **Tipos de atributo**.</span><span class="sxs-lookup"><span data-stu-id="2f04f-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="2f04f-118">La primera vez que configura tipos de atributos, seleccione **Crear dimensiones del producto** para transferir automáticamente las dimensiones de producto estándar.</span><span class="sxs-lookup"><span data-stu-id="2f04f-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard product dimensions.</span></span>
3. <span data-ttu-id="2f04f-119">Seleccione **Nuevo** para crear un nuevo tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="2f04f-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="2f04f-120">En el campo **Tipo de atributo**, especifique un nombre para el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="2f04f-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="2f04f-121">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="2f04f-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="2f04f-122">En el campo **Unidad**, seleccione la unidad relevante del atributo, según convenga.</span><span class="sxs-lookup"><span data-stu-id="2f04f-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="2f04f-123">En el campo **Tipo de datos**, seleccione un tipo de datos para la unidad.</span><span class="sxs-lookup"><span data-stu-id="2f04f-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="2f04f-124">Si seleccionó **Cadena** como tipo de datos, siga estos pasos para crear valores para el tipo de atributo:</span><span class="sxs-lookup"><span data-stu-id="2f04f-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="2f04f-125">Seleccione el tipo de atributo y después **Valores**.</span><span class="sxs-lookup"><span data-stu-id="2f04f-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="2f04f-126">En el campo **Valores de atributo**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2f04f-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="2f04f-127">En el campo **Tipo de atributo**, seleccione un tipo de atributo (dimensión).</span><span class="sxs-lookup"><span data-stu-id="2f04f-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="2f04f-128">En el campo **Valor**, especifique un valor relaciondo.</span><span class="sxs-lookup"><span data-stu-id="2f04f-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="2f04f-129">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="2f04f-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="2f04f-130">Guarde el registro.</span><span class="sxs-lookup"><span data-stu-id="2f04f-130">Save the record.</span></span>
    7. <span data-ttu-id="2f04f-131">Vuelva a la página **Tipos de atributo**.</span><span class="sxs-lookup"><span data-stu-id="2f04f-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="2f04f-132">Guarde el registro.</span><span class="sxs-lookup"><span data-stu-id="2f04f-132">Save the record.</span></span>

    <span data-ttu-id="2f04f-133">El campo **Tipos de ubicación funcionales** muestra el número de ubicaciones técnicas que estén utilizando el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="2f04f-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="2f04f-134">El campo **Tipos del activo** muestra el número de tipos de activos que lo estén utilizando.</span><span class="sxs-lookup"><span data-stu-id="2f04f-134">The **Asset types** field shows the number of asset types that are using it.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]