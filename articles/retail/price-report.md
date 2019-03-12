---
title: Informes de precio comercial
description: Este tema proporciona una visión general de la función del informe de precio que pueda utilizar para ver los próximos cambios de precio para los productos.
author: shajain
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 6db6d1c6b6eb1d69b40fe75d97eeb71564986707
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "353066"
---
# <a name="retail-price-reports"></a><span data-ttu-id="8b35d-103">Informes de precio comercial</span><span class="sxs-lookup"><span data-stu-id="8b35d-103">Retail price reports</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]


<span data-ttu-id="8b35d-104">Para proporcionar precios competitivos a sus clientes, los minoristas cambian a menudo precios de los productos.</span><span class="sxs-lookup"><span data-stu-id="8b35d-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="8b35d-105">Los encargados de la tienda desean la habilidad de tener acceso a cambios de precio recientes o próximos de modo que puedan planificar los recursos requeridos para actualizar las etiquetas de precio presentadas en las estanterías de una tienda.</span><span class="sxs-lookup"><span data-stu-id="8b35d-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="8b35d-106">Con el lanzamiento 10.0 de Dynamics 365 for Retail un encargado de tienda puede abrir el informe **Precio** yendo a **Todas las tiendas al por menor \> Almacén \> Informe de precio** y ver los precios actualizados de los productos asociados a la tienda.</span><span class="sxs-lookup"><span data-stu-id="8b35d-106">With release 10.0 of Dynamics 365 for Retail, a store manager can open the **Price** report by navigating to **All retail stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="8b35d-107">Para habilitar el informe de precio, el parámetro **Informe de precio para tienda comercial** se debe activar.</span><span class="sxs-lookup"><span data-stu-id="8b35d-107">To enable the price report, the **Enable price report for Retail store** parameter must be turned on.</span></span> <span data-ttu-id="8b35d-108">Este parámetro está en la pestaña **Parámetros de ventas \> Descuentos \> Varios**. Abriendo la página **Informe de precio** aparece un cuadro de diálogo con distintas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="8b35d-108">This parameter is located on the **Retail parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="8b35d-109">Las configuraciones disponibles se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="8b35d-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="8b35d-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="8b35d-110">Configuration</span></span> | <span data-ttu-id="8b35d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b35d-111">Description</span></span> |
|---|---|
| <span data-ttu-id="8b35d-112">Desde / hasta fecha</span><span class="sxs-lookup"><span data-stu-id="8b35d-112">From date / To date</span></span>| <span data-ttu-id="8b35d-113">El intervalo de fechas para el que el informe del precio se va a producir.</span><span class="sxs-lookup"><span data-stu-id="8b35d-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="8b35d-114">La duración se limita actualmente en 7 días.</span><span class="sxs-lookup"><span data-stu-id="8b35d-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="8b35d-115">Canal</span><span class="sxs-lookup"><span data-stu-id="8b35d-115">Channel</span></span>| <span data-ttu-id="8b35d-116">La tienda minorista para la que se va a producir el informe del precio.</span><span class="sxs-lookup"><span data-stu-id="8b35d-116">The retail store for which the price report should be generated.</span></span> |
| <span data-ttu-id="8b35d-117">Mostrar productos con inventario disponible</span><span class="sxs-lookup"><span data-stu-id="8b35d-117">Display products with available inventory</span></span>| <span data-ttu-id="8b35d-118">Establecer esto en **Sí** mostrará los precios para solo los productos que tiene actualmente inventario físico disponible en la tienda.</span><span class="sxs-lookup"><span data-stu-id="8b35d-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="8b35d-119">Mostrar precios de las variantes</span><span class="sxs-lookup"><span data-stu-id="8b35d-119">Display prices for variants</span></span> | <span data-ttu-id="8b35d-120">Establecer esto en **Sí** mostrará los precios de variantes junto con los productos maestros.</span><span class="sxs-lookup"><span data-stu-id="8b35d-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="8b35d-121">Éste solo debe ser **Activado** si tiene precios específicos de variantes, porque el número de filas puede crecer mucho.</span><span class="sxs-lookup"><span data-stu-id="8b35d-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="8b35d-122">En versiones futuras, habilitaremos los precios basados en dimensiones de modo que el encargado de tienda puede elegir las dimensiones para las que los precios deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="8b35d-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="8b35d-123">Mostrar productos con cambios de precio</span><span class="sxs-lookup"><span data-stu-id="8b35d-123">Display products with price changes</span></span> | <span data-ttu-id="8b35d-124">Establecer esto en **Sí** mostrará los índices por solo las fechas en las que se ha cambiado el precio.</span><span class="sxs-lookup"><span data-stu-id="8b35d-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="8b35d-125">El precio para *un día antes* seleccionado **Desde fecha** se mostrará siempre, de modo que el encargado de tienda pueda identificar con facilidad los productos que no han cambiado los precios durante la duración completa seleccionada, y también puede ver el precio actual.</span><span class="sxs-lookup"><span data-stu-id="8b35d-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="8b35d-126">Después de que se cree el informe, el archivo de Excel se puede descargar para usar cualquier filtro necesario.</span><span class="sxs-lookup"><span data-stu-id="8b35d-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="8b35d-127">El informe del precio se puede usar para comprobar los precios históricos de los productos por últimas fechas.</span><span class="sxs-lookup"><span data-stu-id="8b35d-127">The price report can also be used to check the historical prices of products for past dates.</span></span>