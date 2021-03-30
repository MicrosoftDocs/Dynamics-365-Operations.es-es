---
title: Ampliar las entidades de datos disponibles de inventario
description: Este tema proporciona un ejemplo que muestra cómo agregar campos extendidos a las vistas INVENTORSITEONHANDENTITY e INVENTWAREHOUSEONHANDENTITY, de modo que las capacidades de las entidades de datos disponibles del inventario puedan funcionar con las extensiones.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 0f48e424a9ab3349d3c114ecbd01424005b9a9c6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219350"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="d870e-103">Ampliar las entidades de datos disponibles de inventario</span><span class="sxs-lookup"><span data-stu-id="d870e-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d870e-104">Microsoft Dynamics 365 Supply Chain Management proporciona características de [extensibilidad](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) que le permiten [agregar campos a tablas mediante la extensión](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d870e-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span></span> <span data-ttu-id="d870e-105">Este tema proporciona un ejemplo que muestra cómo agregar campos extendidos a las vistas `INVENTORSITEONHANDENTITY` e `INVENTWAREHOUSEONHANDENTITY`, de modo que las capacidades de las entidades de datos disponibles del inventario puedan funcionar con las extensiones.</span><span class="sxs-lookup"><span data-stu-id="d870e-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="d870e-106">Para obtener más información sobre las entidades de datos, consulte [Descripción general de la administración de datos](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="d870e-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d870e-107">A continuación, se muestra una lista de algunas de las entidades de datos disponibles del inventario:</span><span class="sxs-lookup"><span data-stu-id="d870e-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="d870e-108">Inventario disponible por sitio</span><span class="sxs-lookup"><span data-stu-id="d870e-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="d870e-109">Inventario disponible por sitio V2</span><span class="sxs-lookup"><span data-stu-id="d870e-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="d870e-110">Inventario disponible por almacén</span><span class="sxs-lookup"><span data-stu-id="d870e-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="d870e-111">Inventario disponible por almacén v2</span><span class="sxs-lookup"><span data-stu-id="d870e-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="d870e-112">Después de agregar campos a las tablas utilizadas por la vista `inventSiteOnHandView` debe sincronizar el motor para que las extensiones se reconozcan correctamente.</span><span class="sxs-lookup"><span data-stu-id="d870e-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="d870e-113">Extienda la vista `InventSiteOnHandView` agregando el campo de extensión.</span><span class="sxs-lookup"><span data-stu-id="d870e-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="d870e-114">Extienda la vista `InventSiteOnHandAggregatedView` con los campos de extensión.</span><span class="sxs-lookup"><span data-stu-id="d870e-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="d870e-115">Extienda la clase viewBuilder de `InventSiteOnHandAggregatedViewBuilder` modificando el método `getExtensionFields()`.</span><span class="sxs-lookup"><span data-stu-id="d870e-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="d870e-116">De esta manera, asigna campos de vista antiguos a campos de vista nuevos cuando se ejecuta la sincronización de viewBuilder.</span><span class="sxs-lookup"><span data-stu-id="d870e-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="d870e-117">Por ejemplo, ha agregado los siguientes cuatro campos a la tabla `InventTable` mediante extensión:</span><span class="sxs-lookup"><span data-stu-id="d870e-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="d870e-118">Campo personalizado 1</span><span class="sxs-lookup"><span data-stu-id="d870e-118">Custom field 1</span></span>
- <span data-ttu-id="d870e-119">Campo personalizado 2</span><span class="sxs-lookup"><span data-stu-id="d870e-119">Custom field 2</span></span>
- <span data-ttu-id="d870e-120">Campo personalizado 3</span><span class="sxs-lookup"><span data-stu-id="d870e-120">Custom field 3</span></span>
- <span data-ttu-id="d870e-121">Campo personalizado 4</span><span class="sxs-lookup"><span data-stu-id="d870e-121">Custom field 4</span></span>

<span data-ttu-id="d870e-122">En este caso, debe modificar el método `getExtensionFields()` de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="d870e-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

<span data-ttu-id="d870e-123">Después de completar estos pasos, puede ampliar el inventario disponible por sitio y el inventario disponible por entidades de datos de almacén agregando los nuevos campos.</span><span class="sxs-lookup"><span data-stu-id="d870e-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="d870e-124">De esta manera, se asegura de que se reconozcan los campos extendidos y se incluyan durante la migración de datos que usa esas entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="d870e-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]