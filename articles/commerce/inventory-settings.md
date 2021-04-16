---
title: Aplicar configuración de inventario
description: Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b2c44eb5ece74de15e22180abc6d9d0448ab401b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798898"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="87920-103">Aplicar configuración de inventario</span><span class="sxs-lookup"><span data-stu-id="87920-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="87920-104">Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87920-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="87920-105">La configuración de inventario especifica si se debe verificar el inventario antes de agregar productos al carro.</span><span class="sxs-lookup"><span data-stu-id="87920-105">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="87920-106">También definen mensajes de comercialización relacionados con el inventario, como "En existencias" y "Solo quedan unos pocos".</span><span class="sxs-lookup"><span data-stu-id="87920-106">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="87920-107">Esta configuración garantiza que no se pueda comprar un producto si está agotado.</span><span class="sxs-lookup"><span data-stu-id="87920-107">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="87920-108">Dynamics 365 Commerce proporciona estimaciones de disponibilidad lista para productos.</span><span class="sxs-lookup"><span data-stu-id="87920-108">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="87920-109">Para obtener información sobre cómo se calcula la disponibilidad lista estimada, consulte [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="87920-109">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="87920-110">En el creador de sitios de Commerce, se pueden definir umbrales y rangos de inventario para un producto o una categoría.</span><span class="sxs-lookup"><span data-stu-id="87920-110">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="87920-111">Determinan si el inventario se puede clasificar como en existencias, bajas existencias o agotado.</span><span class="sxs-lookup"><span data-stu-id="87920-111">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="87920-112">Para más detalles, ver [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="87920-112">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="87920-113">La versión Dynamics 365 Commerce 10.0.12 incluye compatibilidad con intervalos y umbrales de inventario.</span><span class="sxs-lookup"><span data-stu-id="87920-113">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="87920-114">Configuración de inventario</span><span class="sxs-lookup"><span data-stu-id="87920-114">Inventory settings</span></span>

<span data-ttu-id="87920-115">En Comercio, la configuración del inventario se define en **Configuraciones del sitio \> Extensiones \> Gestión del inventario** en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="87920-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="87920-116">Hay cuatro configuraciones de inventario, una de las cuales está obsoleta (en desuso):</span><span class="sxs-lookup"><span data-stu-id="87920-116">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="87920-117">**Habilitar comprobación de existencias en la aplicación**: esta configuración activa una comprobación de inventario del producto.</span><span class="sxs-lookup"><span data-stu-id="87920-117">**Enable stock check in app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="87920-118">La cesta, el carro y la recogida en los módulos de la tienda verificarán el inventario del producto y permitirán agregar un producto al carro solo si el inventario está disponible.</span><span class="sxs-lookup"><span data-stu-id="87920-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="87920-119">**Nivel de inventario basado en**: esta configuración define cómo se calculan los niveles de inventario.</span><span class="sxs-lookup"><span data-stu-id="87920-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="87920-120">Los valores disponibles son **Total disponible**, **Físicamente disponible** y **Umbral de agotado**.</span><span class="sxs-lookup"><span data-stu-id="87920-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="87920-121">En Commerce, se pueden definir umbrales y rangos de inventario para cada producto y categoría.</span><span class="sxs-lookup"><span data-stu-id="87920-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="87920-122">Las API de inventario devuelven información de inventario de producto para las propiedades **Total disponible** y **Físicamente disponible**.</span><span class="sxs-lookup"><span data-stu-id="87920-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="87920-123">El minorista decide si el valor **Total disponible** o **Físicamente disponible** debe utilizarse para determinar el recuento de inventario y los rangos correspondientes para los estados en existencia y agotado.</span><span class="sxs-lookup"><span data-stu-id="87920-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="87920-124">El valor de **Umbral de agotado** de la opción **Nivel de inventario basado en** es un valor antiguo (heredado) y obsoleto.</span><span class="sxs-lookup"><span data-stu-id="87920-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="87920-125">Cuando se selecciona, el recuento de inventario se determina a partir de los resultados del valor **Total disponible**, pero el umbral está definido por la opción numérica **Umbral de agotado** que se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="87920-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="87920-126">Esta configuración de umbral se aplica a todos los productos en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="87920-126">This threshold setting applies to all products across an e-commerce site.</span></span> <span data-ttu-id="87920-127">Si el inventario está por debajo del número de umbral, un producto se considera agotado.</span><span class="sxs-lookup"><span data-stu-id="87920-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="87920-128">De lo contrario, se considera en existencias.</span><span class="sxs-lookup"><span data-stu-id="87920-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="87920-129">Las capacidades del valor **Umbral de agotado** son limitadas y no recomendamos que lo use en la versión 10.0.12 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="87920-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="87920-130">**Rangos de inventario**: esta configuración define los rangos de inventario para los que se muestran los mensajes para los módulos del sitio.</span><span class="sxs-lookup"><span data-stu-id="87920-130">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="87920-131">Solo es aplicable si el valor **Total disponible** o el valor **Físicamente disponible** se selecciona para la opción **Nivel de inventario basado en**.</span><span class="sxs-lookup"><span data-stu-id="87920-131">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="87920-132">Los valores disponibles son **Todos**, **Bajo y agotado** y **Agotado**.</span><span class="sxs-lookup"><span data-stu-id="87920-132">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="87920-133">Cuando se selecciona **Todos** se mostrarán los mensajes para todos los rangos de inventario, desde en existencias (mensaje "Disponible") hasta agotado (mensaje "Agotado").</span><span class="sxs-lookup"><span data-stu-id="87920-133">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="87920-134">Cuando se selecciona **Bajo y agotado**, se mostrarán los mensajes para todos los rangos de inventario, excepto en existencias (mensaje "Disponible").</span><span class="sxs-lookup"><span data-stu-id="87920-134">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="87920-135">Cuando se selecciona **Agotado**, solo se mostrará el mensaje "Agotado".</span><span class="sxs-lookup"><span data-stu-id="87920-135">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="87920-136">**Umbral de agotado**: esta configuración numérica antigua solo tendrá efecto si se selecciona el valor **Umbral de agotado** para la opción **Nivel de inventario basado en**.</span><span class="sxs-lookup"><span data-stu-id="87920-136">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="87920-137">Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="87920-137">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="87920-138">Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="87920-138">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="87920-139">Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="87920-139">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="87920-140">Módulos que usan configuraciones de inventario</span><span class="sxs-lookup"><span data-stu-id="87920-140">Modules that use inventory settings</span></span>

<span data-ttu-id="87920-141">Cuadro de compra, lista de deseos, carro y los módulos de icono de carro usan configuraciones de inventario para mostrar los rangos de inventario y los mensajes.</span><span class="sxs-lookup"><span data-stu-id="87920-141">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="87920-142">La siguiente imagen muestra un ejemplo de una página de detalles del producto (PDP) que muestra un mensaje de en existencias ("Disponible").</span><span class="sxs-lookup"><span data-stu-id="87920-142">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Ejemplo de un módulo PDP que tiene un mensaje de en existencias](./media/pdp-InStock.png)

<span data-ttu-id="87920-144&quot;>La siguiente imagen muestra un ejemplo de un PDP que muestra un mensaje (&quot;Agotado").</span><span class="sxs-lookup"><span data-stu-id="87920-144">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Ejemplo de un módulo PDP que tiene un mensaje de agotado](./media/pdp-outofstock.png)

<span data-ttu-id="87920-146&quot;>La siguiente imagen muestra un ejemplo de un carro que muestra un mensaje en existencias (&quot;Disponible").</span><span class="sxs-lookup"><span data-stu-id="87920-146">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Ejemplo de un módulo de carro que tiene un mensaje de en existencias](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="87920-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="87920-148">Additional resources</span></span>

[<span data-ttu-id="87920-149">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="87920-149">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="87920-150">Configurar búferes de inventario y niveles de inventario</span><span class="sxs-lookup"><span data-stu-id="87920-150">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="87920-151">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="87920-151">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="87920-152">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="87920-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="87920-153">Módulos y páginas de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="87920-153">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="87920-154">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="87920-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="87920-155">Actualizaciones de SDK y biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="87920-155">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
