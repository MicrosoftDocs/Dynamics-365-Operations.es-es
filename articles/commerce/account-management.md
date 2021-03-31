---
title: Módulos y páginas de gestión de cuentas
description: Este tema cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 29523d03fb687684dae7d0ce08208905cce702df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206640"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="8aee3-103">Módulos y páginas de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="8aee3-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8aee3-104">Este tema cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8aee3-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8aee3-105">La gestión de cuentas hace referencia a un grupo de páginas que se usa para gestionar la información relacionada con cuentas del usuario en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8aee3-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="8aee3-106">Las páginas de la gestión de cuentas incluyen la página de aterrizaje de la gestión de cuentas, la página de perfil de usuario, la página de la dirección del usuario, la página del historial de pedidos, la página de detalles de pedidos, la página de fidelización y la página de la lista de deseos.</span><span class="sxs-lookup"><span data-stu-id="8aee3-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="8aee3-107">Página de aterrizaje de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="8aee3-107">Account management landing page</span></span>

<span data-ttu-id="8aee3-108">La página de aterrizaje de la gestión de cuentas utiliza los siguientes módulos:</span><span class="sxs-lookup"><span data-stu-id="8aee3-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="8aee3-109">**Contenedor**: todos los módulos de página de aterrizaje de administración de cuentas deben colocarse dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="8aee3-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="8aee3-110">**Ventana de bienvenida de cuenta**: este módulo se usa para proporcionar un mensaje de bienvenida en la página de administración de cuentas.</span><span class="sxs-lookup"><span data-stu-id="8aee3-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="8aee3-111">Incluye propiedades para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="8aee3-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="8aee3-112">**Ventana genérica de cuenta**: este módulo se puede utilizar para proporcionar encabezados y vínculos a páginas de administración de cuentas, como las páginas "Historial de pedidos" o "Mi perfil".</span><span class="sxs-lookup"><span data-stu-id="8aee3-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="8aee3-113">El módulo de ventana genérica se puede utilizar para configurar una ventana para cualquier página.</span><span class="sxs-lookup"><span data-stu-id="8aee3-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="8aee3-114">En Fabrikam, este módulo se utiliza para los vínculos de página "Historial de pedidos" y "Mi perfil" en la página de aterrizaje de administración de cuentas.</span><span class="sxs-lookup"><span data-stu-id="8aee3-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="8aee3-115">**Ventana de lista de deseos de cuenta**: este módulo se utiliza para proporcionar un resumen de los artículos de la lista de deseos del cliente.</span><span class="sxs-lookup"><span data-stu-id="8aee3-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="8aee3-116">Por ejemplo, es posible que indique “Tiene 10 artículos en su lista de deseos.”</span><span class="sxs-lookup"><span data-stu-id="8aee3-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="8aee3-117">Incluye las propiedades del encabezado y el vínculo "Ver detalles".</span><span class="sxs-lookup"><span data-stu-id="8aee3-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="8aee3-118">El vínculo "Ver detalles" se debe configurar para redirigir a la página de la lista de deseos.</span><span class="sxs-lookup"><span data-stu-id="8aee3-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="8aee3-119">**Ventana de dirección de la cuenta**: este módulo se utiliza para proporcionar un resumen de las direcciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="8aee3-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="8aee3-120">Por ejemplo, es posible que indique “Tiene 2 direcciones agregadas a su cuenta”.</span><span class="sxs-lookup"><span data-stu-id="8aee3-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="8aee3-121">Incluye las propiedades del encabezado y el vínculo "Ver detalles".</span><span class="sxs-lookup"><span data-stu-id="8aee3-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="8aee3-122">El vínculo "Ver detalles" se debe configurar para redirigir a la página de dirección del usuario.</span><span class="sxs-lookup"><span data-stu-id="8aee3-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="8aee3-123">**Ventana de fidelización de cuenta**: este módulo se usa para mostrar información del programa de fidelización y vincularla.</span><span class="sxs-lookup"><span data-stu-id="8aee3-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="8aee3-124">La ventana tiene dos estados: un estado muestra vínculos para unirse a un programa de fidelización si el usuario aún no es miembro.</span><span class="sxs-lookup"><span data-stu-id="8aee3-124">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="8aee3-125">El otro estado muestra vínculos para ver la página de detalles de fidelización cuando el usuario ya es miembro.</span><span class="sxs-lookup"><span data-stu-id="8aee3-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="8aee3-126">Las propiedades incluyen el encabezado, el vínculo "Registrarse" y el vínculo "Ver fidelización".</span><span class="sxs-lookup"><span data-stu-id="8aee3-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="8aee3-127">El vínculo "Ver fidelización" se debe configurar para redirigir a la página de fidelización.</span><span class="sxs-lookup"><span data-stu-id="8aee3-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="8aee3-128">El vínculo “Registrarse” se debe configurar para redirigir a una página donde los usuarios puedan unirse al programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="8aee3-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="8aee3-129">Página de historial de pedidos</span><span class="sxs-lookup"><span data-stu-id="8aee3-129">Order history page</span></span>

<span data-ttu-id="8aee3-130">La página de historial de pedidos utiliza el módulo del historial de pedidos para mostrar todos los pedidos recientes que el usuario ha realizado.</span><span class="sxs-lookup"><span data-stu-id="8aee3-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="8aee3-131">Página de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="8aee3-131">Order details page</span></span>

<span data-ttu-id="8aee3-132">La página de detalles de pedido proporciona información detallada para cada pedido y se obtiene acceso a ella desde la página de historial de pedidos.</span><span class="sxs-lookup"><span data-stu-id="8aee3-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="8aee3-133">Usa el módulo de detalles de pedido, que requiere que el id. de ventas o el id. de transacción recupere los detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="8aee3-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="8aee3-134">Página de perfil de usuario</span><span class="sxs-lookup"><span data-stu-id="8aee3-134">User profile page</span></span>

<span data-ttu-id="8aee3-135">La página de perfil de usuario muestran los detalles de la cuenta de un usuario, como el nombre y la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="8aee3-135">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="8aee3-136">Usa los detalles del perfil de usuario y los módulos de edición del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="8aee3-136">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="8aee3-137">Aunque la dirección de correo electrónico no se pueda quitar, se puede editar.</span><span class="sxs-lookup"><span data-stu-id="8aee3-137">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="8aee3-138">La página de perfil de usuario también muestra las preferencias del usuario que le permiten a un usuario optar o no por ciertas funciones, como la personalización de las listas de recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="8aee3-138">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="8aee3-139">Página de la dirección de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="8aee3-139">User address page</span></span>

<span data-ttu-id="8aee3-140">La página de la dirección del usuario muestra la lista de direcciones que están asociadas a la cuenta del usuario.</span><span class="sxs-lookup"><span data-stu-id="8aee3-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="8aee3-141">El usuario proporcionó estas direcciones durante la finalización de la compra o las agregó directamente en esta página.</span><span class="sxs-lookup"><span data-stu-id="8aee3-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="8aee3-142">El módulo de la dirección de usuario se utiliza para agregar y editar direcciones, establecer la dirección principal y representar las direcciones existentes en la página.</span><span class="sxs-lookup"><span data-stu-id="8aee3-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="8aee3-143">Página de lista de deseos</span><span class="sxs-lookup"><span data-stu-id="8aee3-143">Wish list page</span></span>

<span data-ttu-id="8aee3-144">La página de lista de deseos muestra los artículos que se han agregado a la lista de deseos del cliente.</span><span class="sxs-lookup"><span data-stu-id="8aee3-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="8aee3-145">Usa el módulo de la lista de deseos para representar artículos de la lista de deseos.</span><span class="sxs-lookup"><span data-stu-id="8aee3-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="8aee3-146">Página de fidelización</span><span class="sxs-lookup"><span data-stu-id="8aee3-146">Loyalty page</span></span>

<span data-ttu-id="8aee3-147">La página de fidelización permite a los clientes ver sus detalles de fidelización si ya son miembros del programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="8aee3-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="8aee3-148">También pueden ver los puntos que han obtenido y canjeado en transacciones recientes.</span><span class="sxs-lookup"><span data-stu-id="8aee3-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="8aee3-149">La página usa el módulo de detalles de fidelización para mostrar los detalles de fidelización.</span><span class="sxs-lookup"><span data-stu-id="8aee3-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="8aee3-150">Para unirse al programa de fidelización, se puede crear una página de marketing con módulos de registro y términos de fidelización.</span><span class="sxs-lookup"><span data-stu-id="8aee3-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="8aee3-151">Si el usuario no es miembro de un programa de fidelización, estos módulos le permitirán registrarse.</span><span class="sxs-lookup"><span data-stu-id="8aee3-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8aee3-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8aee3-152">Additional resources</span></span>

[<span data-ttu-id="8aee3-153">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="8aee3-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8aee3-154">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="8aee3-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8aee3-155">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="8aee3-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8aee3-156">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="8aee3-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="8aee3-157">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="8aee3-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8aee3-158">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="8aee3-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8aee3-159">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="8aee3-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8aee3-160">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="8aee3-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]