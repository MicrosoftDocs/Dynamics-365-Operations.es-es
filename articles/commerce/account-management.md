---
title: Módulos y páginas de gestión de cuentas
description: Este tema cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785399"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="56d01-103">Módulos y páginas de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="56d01-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="56d01-104">Este tema cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="56d01-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="56d01-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="56d01-105">Overview</span></span>

<span data-ttu-id="56d01-106">La gestión de cuentas hace referencia a un grupo de páginas que se usa para gestionar la información relacionada con cuentas del usuario en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="56d01-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="56d01-107">Las páginas de la gestión de cuentas incluyen la página de aterrizaje de la gestión de cuentas, la página de perfil de usuario, la página de la dirección del usuario, la página del historial de pedidos, la página de detalles de pedidos, la página de fidelización y la página de la lista de deseos.</span><span class="sxs-lookup"><span data-stu-id="56d01-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="56d01-108">Página de aterrizaje de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="56d01-108">Account management landing page</span></span>

<span data-ttu-id="56d01-109">La página de aterrizaje de la gestión de cuentas utiliza los siguientes módulos:</span><span class="sxs-lookup"><span data-stu-id="56d01-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="56d01-110">**Colocación de contenido**: Este módulo es un módulo de contenedor que contiene todos los módulos de la página de aterrizaje de la gestión de cuentas.</span><span class="sxs-lookup"><span data-stu-id="56d01-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="56d01-111">**Elemento de bienvenida de la cuenta**: Este módulo se utiliza para proporcionar un mensaje de bienvenida en la página de gestión de cuentas.</span><span class="sxs-lookup"><span data-stu-id="56d01-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="56d01-112">Incluye las propiedades del encabezado y el tamaño del icono.</span><span class="sxs-lookup"><span data-stu-id="56d01-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="56d01-113">La propiedad **Tamaño de icono** define el ancho del módulo en el módulo de colocación de contenido.</span><span class="sxs-lookup"><span data-stu-id="56d01-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="56d01-114">Los valores oscilan entre **1** y **12**, donde **12** representa el ancho total del contenedor de colocación de contenido.</span><span class="sxs-lookup"><span data-stu-id="56d01-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="56d01-115">**Elemento de realización de pedidos de cuenta**: Este módulo se utiliza para proporcionar un resumen del número de pedidos que se han realizado por la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="56d01-116">Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles".</span><span class="sxs-lookup"><span data-stu-id="56d01-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="56d01-117">El vínculo “ver detalles” se debe configurar para redirigir a la página del historial de pedidos.</span><span class="sxs-lookup"><span data-stu-id="56d01-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="56d01-118">**Elemento de colocación del perfil de cuenta**: Este módulo se utiliza para proporcionar un resumen del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="56d01-119">Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles".</span><span class="sxs-lookup"><span data-stu-id="56d01-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="56d01-120">El vínculo “ver detalles” se debe configurar para redirigir a la página del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="56d01-121">**Elemento de lista de deseos de cuenta**: Este módulo se utiliza para proporcionar un resumen de los artículos de la lista de deseos del cliente.</span><span class="sxs-lookup"><span data-stu-id="56d01-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="56d01-122">Por ejemplo, es posible que indique “Tiene 10 artículos en su lista de deseos.”</span><span class="sxs-lookup"><span data-stu-id="56d01-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="56d01-123">Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles".</span><span class="sxs-lookup"><span data-stu-id="56d01-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="56d01-124">El vínculo “ver detalles” se debe configurar para redirigir a la página de la lista de deseos.</span><span class="sxs-lookup"><span data-stu-id="56d01-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="56d01-125">**Elemento de dirección de la cuenta**: Este módulo se utiliza para proporcionar un resumen de las direcciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="56d01-126">Por ejemplo, es posible que indique “Tiene 2 direcciones agregadas a su cuenta”.</span><span class="sxs-lookup"><span data-stu-id="56d01-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="56d01-127">Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles".</span><span class="sxs-lookup"><span data-stu-id="56d01-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="56d01-128">El vínculo “ver detalles” se debe configurar para redirigir a la página de dirección del usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="56d01-129">**Elemento de fidelización de cuenta**: Este módulo se usa para mostrar y vincular a la información del programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="56d01-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="56d01-130">Incluye las propiedades del encabezado, el tamaño del icono, el vínculo "ver detalles" y el vínculo "convertirse en un miembro".</span><span class="sxs-lookup"><span data-stu-id="56d01-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="56d01-131">El vínculo “ver detalles” se debe configurar para redirigir a la página de fidelización.</span><span class="sxs-lookup"><span data-stu-id="56d01-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="56d01-132">El vínculo “convertirse en un miembro” se debe configurar para redirigir a una página donde los usuarios puedan unirse al programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="56d01-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="56d01-133">Página de historial de pedidos</span><span class="sxs-lookup"><span data-stu-id="56d01-133">Order history page</span></span>

<span data-ttu-id="56d01-134">La página de historial de pedidos utiliza el módulo del historial de pedidos para mostrar todos los pedidos recientes que el usuario ha realizado.</span><span class="sxs-lookup"><span data-stu-id="56d01-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="56d01-135">Página de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="56d01-135">Order details page</span></span>

<span data-ttu-id="56d01-136">La página de detalles de pedido proporciona información detallada para cada pedido y se obtiene acceso a ella desde la página de historial de pedidos.</span><span class="sxs-lookup"><span data-stu-id="56d01-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="56d01-137">Usa el módulo de detalles de pedido, que requiere que el id. de ventas o el id. de transacción recupere los detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="56d01-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="56d01-138">Página de perfil de usuario</span><span class="sxs-lookup"><span data-stu-id="56d01-138">User profile page</span></span>

<span data-ttu-id="56d01-139">La página de perfil de usuario muestran los detalles de la cuenta de usuario, como el nombre y la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-139">The user profile page shows user account details, such as user's name and email address.</span></span> <span data-ttu-id="56d01-140">Permite usar el módulo del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-140">It uses the user profile module.</span></span> <span data-ttu-id="56d01-141">Aunque la dirección de correo electrónico no se pueda quitar, se puede editar.</span><span class="sxs-lookup"><span data-stu-id="56d01-141">Although the email address can't be removed, it can be edited.</span></span>

### <a name="user-address-page"></a><span data-ttu-id="56d01-142">Página de la dirección de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="56d01-142">User address page</span></span>

<span data-ttu-id="56d01-143">La página de la dirección del usuario muestra la lista de direcciones que están asociadas a la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="56d01-143">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="56d01-144">El usuario proporcionó estas direcciones durante la finalización de la compra o las agregó directamente en esta página.</span><span class="sxs-lookup"><span data-stu-id="56d01-144">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="56d01-145">El módulo de la dirección de usuario se utiliza para agregar y editar direcciones, establecer la dirección principal y representar las direcciones existentes en la página.</span><span class="sxs-lookup"><span data-stu-id="56d01-145">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="56d01-146">Página de lista de deseos</span><span class="sxs-lookup"><span data-stu-id="56d01-146">Wish list page</span></span>

<span data-ttu-id="56d01-147">La página de lista de deseos muestra los artículos que se han agregado a la lista de deseos del cliente.</span><span class="sxs-lookup"><span data-stu-id="56d01-147">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="56d01-148">Usa el módulo de la lista de deseos para representar artículos de la lista de deseos.</span><span class="sxs-lookup"><span data-stu-id="56d01-148">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="56d01-149">Página de fidelización</span><span class="sxs-lookup"><span data-stu-id="56d01-149">Loyalty page</span></span>

<span data-ttu-id="56d01-150">La página de fidelización permite a los clientes unirse a un programa de fidelización o, si ya son miembros del programa de fidelización, ver sus detalles de programa.</span><span class="sxs-lookup"><span data-stu-id="56d01-150">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="56d01-151">También pueden ver los puntos que han obtenido y canjeado en transacciones recientes.</span><span class="sxs-lookup"><span data-stu-id="56d01-151">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56d01-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="56d01-152">Additional resources</span></span>

[<span data-ttu-id="56d01-153">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="56d01-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="56d01-154">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="56d01-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="56d01-155">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="56d01-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="56d01-156">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="56d01-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="56d01-157">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="56d01-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="56d01-158">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="56d01-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="56d01-159">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="56d01-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="56d01-160">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="56d01-160">Footer module</span></span>](author-footer-module.md)
