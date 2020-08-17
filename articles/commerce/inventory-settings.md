---
title: Aplicar configuración de inventario
description: Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 737e71dc73750bf151629fd904081924ac15b91e
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621230"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="7856f-103">Aplicar configuración de inventario</span><span class="sxs-lookup"><span data-stu-id="7856f-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7856f-104">Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7856f-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7856f-105">Información general</span><span class="sxs-lookup"><span data-stu-id="7856f-105">Overview</span></span>

<span data-ttu-id="7856f-106">La configuración de inventario especifica si se debe verificar el inventario antes de agregar productos al carro.</span><span class="sxs-lookup"><span data-stu-id="7856f-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="7856f-107">También definen mensajes de comercialización relacionados con el inventario, como "En stock" y "Solo quedan unos pocos".</span><span class="sxs-lookup"><span data-stu-id="7856f-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="7856f-108">Esta configuración garantiza que no se pueda comprar un producto si está agotado.</span><span class="sxs-lookup"><span data-stu-id="7856f-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="7856f-109">Dynamics 365 Commerce proporciona estimaciones de disponibilidad lista para productos.</span><span class="sxs-lookup"><span data-stu-id="7856f-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="7856f-110">Para obtener información sobre cómo se calcula la disponibilidad lista estimada, consulte [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="7856f-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="7856f-111">En el creador de sitios de Commerce, se pueden definir umbrales y rangos de inventario para un producto o una categoría.</span><span class="sxs-lookup"><span data-stu-id="7856f-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="7856f-112">Determinan si el inventario se puede clasificar como en existencias, bajas existencias o agotado.</span><span class="sxs-lookup"><span data-stu-id="7856f-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="7856f-113">Para más detalles, ver [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7856f-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="7856f-114">Configuración de inventario</span><span class="sxs-lookup"><span data-stu-id="7856f-114">Inventory settings</span></span>

<span data-ttu-id="7856f-115">En Comercio, la configuración del inventario se define en **Configuraciones del sitio \> Extensiones \> Gestión del inventario** en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="7856f-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="7856f-116">Hay cuatro configuraciones de inventario, una de las cuales está obsoleta (en desuso):</span><span class="sxs-lookup"><span data-stu-id="7856f-116">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="7856f-117">**Habilitar comprobación de inventario en la aplicación**: esta configuración activa una comprobación de inventario del producto.</span><span class="sxs-lookup"><span data-stu-id="7856f-117">**Enable inventory check on app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="7856f-118">La cesta, el carro y la recogida en los módulos de la tienda verificarán el inventario del producto y permitirán agregar un producto al carro solo si el inventario está disponible.</span><span class="sxs-lookup"><span data-stu-id="7856f-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="7856f-119">**Nivel de inventario basado en**: esta configuración define cómo se calculan los niveles de inventario.</span><span class="sxs-lookup"><span data-stu-id="7856f-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="7856f-120">Los valores disponibles son **Total disponible**, **Físicamente disponible** y **Umbral de agotado**.</span><span class="sxs-lookup"><span data-stu-id="7856f-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="7856f-121">En Commerce, se pueden definir umbrales y rangos de inventario para cada producto y categoría.</span><span class="sxs-lookup"><span data-stu-id="7856f-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="7856f-122">Las API de inventario devuelven información de inventario de producto para las propiedades **Total disponible** y **Físicamente disponible**.</span><span class="sxs-lookup"><span data-stu-id="7856f-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="7856f-123">El minorista decide si el valor **Total disponible** o **Físicamente disponible** debe utilizarse para determinar el recuento de inventario y los rangos correspondientes para los estados en existencia y agotado.</span><span class="sxs-lookup"><span data-stu-id="7856f-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="7856f-124">El valor de **Umbral de agotado** de la opción **Nivel de inventario basado en** es un valor antiguo (heredado) y obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7856f-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="7856f-125">Cuando se selecciona, el recuento de inventario se determina a partir de los resultados del valor **Total disponible**, pero el umbral está definido por la opción numérica **Umbral de agotado** que se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="7856f-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="7856f-126">Esta configuración de umbral se aplica a todos los productos en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="7856f-126">This threshold setting applies to all products across an e-Commerce site.</span></span> <span data-ttu-id="7856f-127">Si el inventario está por debajo del número de umbral, un producto se considera agotado.</span><span class="sxs-lookup"><span data-stu-id="7856f-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="7856f-128">De lo contrario, se considera en existencias.</span><span class="sxs-lookup"><span data-stu-id="7856f-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="7856f-129">Las capacidades del valor **Umbral de agotado** son limitadas y no recomendamos que lo use en la versión 10.0.12 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="7856f-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="7856f-130">**Rangos de inventario**: esta configuración define los rangos de inventario para los que se muestran los mensajes para los módulos del sitio.</span><span class="sxs-lookup"><span data-stu-id="7856f-130">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="7856f-131">Solo es aplicable si el valor **Total disponible** o el valor **Físicamente disponible** se selecciona para la opción **Nivel de inventario basado en**.</span><span class="sxs-lookup"><span data-stu-id="7856f-131">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="7856f-132">Los valores disponibles son **Todos**, **Bajo y agotado** y **Agotado**.</span><span class="sxs-lookup"><span data-stu-id="7856f-132">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="7856f-133">Cuando se selecciona **Todos** se mostrarán los mensajes para todos los rangos de inventario, desde en stock (mensaje "Disponible") hasta agotado (mensaje "Agotado").</span><span class="sxs-lookup"><span data-stu-id="7856f-133">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="7856f-134">Cuando se selecciona **Bajo y agotado**, se mostrarán los mensajes para todos los rangos de inventario, excepto en existencias (mensaje "Disponible").</span><span class="sxs-lookup"><span data-stu-id="7856f-134">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="7856f-135">Cuando se selecciona **Agotado**, solo se mostrará el mensaje "Agotado".</span><span class="sxs-lookup"><span data-stu-id="7856f-135">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="7856f-136">**Umbral de agotado**: esta configuración numérica antigua solo tendrá efecto si se selecciona el valor **Umbral de agotado** para la opción **Nivel de inventario basado en**.</span><span class="sxs-lookup"><span data-stu-id="7856f-136">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="7856f-137">Módulos que usan configuraciones de inventario</span><span class="sxs-lookup"><span data-stu-id="7856f-137">Modules that use inventory settings</span></span>

<span data-ttu-id="7856f-138">Cuadro de compra, lista de deseos, carro y los módulos de icono de carro usan configuraciones de inventario para mostrar los rangos de inventario y los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7856f-138">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="7856f-139">La siguiente imagen muestra un ejemplo de una página de detalles del producto (PDP) que muestra un mensaje de en existencias ("Disponible").</span><span class="sxs-lookup"><span data-stu-id="7856f-139">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Ejemplo de un módulo PDP que tiene un mensaje de en existencias](./media/pdp-InStock.png)

<span data-ttu-id="7856f-141">La siguiente imagen muestra un ejemplo de un PDP que muestra un mensaje ("Agotado").</span><span class="sxs-lookup"><span data-stu-id="7856f-141">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Ejemplo de un módulo PDP que tiene un mensaje de agotado](./media/pdp-outofstock.png)

<span data-ttu-id="7856f-143">La siguiente imagen muestra un ejemplo de un carro que muestra un mensaje en existencias ("Disponible").</span><span class="sxs-lookup"><span data-stu-id="7856f-143">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Ejemplo de un módulo de carro que tiene un mensaje de en existencias](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="7856f-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7856f-145">Additional resources</span></span>

[<span data-ttu-id="7856f-146">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="7856f-146">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7856f-147">Configurar búferes de inventario y niveles de inventario</span><span class="sxs-lookup"><span data-stu-id="7856f-147">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="7856f-148">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="7856f-148">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="7856f-149">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="7856f-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="7856f-150">Módulos y páginas de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="7856f-150">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="7856f-151">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="7856f-151">Store selector module</span></span>](store-selector.md)
