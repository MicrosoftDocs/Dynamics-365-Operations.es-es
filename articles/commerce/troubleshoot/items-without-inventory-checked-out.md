---
title: Los artículos agotados se pueden comprar
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los clientes pueden agregar artículos agotados a su carrito y proceder al pago.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: af44def901d3aa7d4b24ab6abfac60d066a8d1a3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801756"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="f1f0f-103">Los artículos agotados se pueden comprar</span><span class="sxs-lookup"><span data-stu-id="f1f0f-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f1f0f-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los clientes pueden agregar artículos agotados a su carrito y proceder al pago.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="f1f0f-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1f0f-105">Description</span></span>

<span data-ttu-id="f1f0f-106">Los usuarios pueden agregar un artículo a su carrito, aunque no haya inventario disponible en la tienda, y luego pasar a la página de pago.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="f1f0f-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="f1f0f-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="f1f0f-108">Habilite la propiedad Mostrar errores de falta de existencias en el creador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="f1f0f-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="f1f0f-109">Para habilitar la propiedad **Mostrar errores de falta de existencias** en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f1f0f-110">Seleccione el sitio en el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="f1f0f-111">En el panel de navegación izquierdo, seleccione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="f1f0f-112">Seleccione **CartPage** para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="f1f0f-113">Seleccione la parte del **Carrito 1**, seleccione **Editar** y luego, en el panel de propiedades, seleccione la casilla **Mostrar errores de falta de existencias**.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="f1f0f-114">Guarde y publique la página.</span><span class="sxs-lookup"><span data-stu-id="f1f0f-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f1f0f-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f1f0f-115">Additional resources</span></span>

[<span data-ttu-id="f1f0f-116">Aplicar configuración de inventario</span><span class="sxs-lookup"><span data-stu-id="f1f0f-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="f1f0f-117">Calcular la disponibilidad de inventario para canales comerciales</span><span class="sxs-lookup"><span data-stu-id="f1f0f-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="f1f0f-118">Configurar búferes de inventario y niveles de inventario</span><span class="sxs-lookup"><span data-stu-id="f1f0f-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)
