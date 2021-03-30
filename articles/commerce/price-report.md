---
title: Informes de precio comercial
description: Este tema proporciona una visión general de la función del informe de precio que pueda utilizar para ver los próximos cambios de precio para los productos.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: f317b22f2794dc71093068a51c8e9d4e6d7d55ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231161"
---
# <a name="retail-price-reports"></a><span data-ttu-id="04aa9-103">Informes de precio comercial</span><span class="sxs-lookup"><span data-stu-id="04aa9-103">Retail price reports</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="04aa9-104">Para proporcionar precios competitivos a sus clientes, los minoristas cambian a menudo precios de los productos.</span><span class="sxs-lookup"><span data-stu-id="04aa9-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="04aa9-105">Los encargados de la tienda desean la habilidad de tener acceso a cambios de precio recientes o próximos de modo que puedan planificar los recursos requeridos para actualizar las etiquetas de precio presentadas en las estanterías de una tienda.</span><span class="sxs-lookup"><span data-stu-id="04aa9-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="04aa9-106">Con el lanzamiento 10.0 de Retail, un encargado de tienda puede abrir el informe **Precio** yendo a **Todas las tiendas \> Tienda \> Informe de precio** y viendo los precios actualizados de los productos asociados a la tienda.</span><span class="sxs-lookup"><span data-stu-id="04aa9-106">With release 10.0 of Retail, a store manager can open the **Price** report by navigating to **All stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="04aa9-107">Para habilitar el informe de precio, el parámetro **Habilitar informe de precio para tienda** debe estar activado.</span><span class="sxs-lookup"><span data-stu-id="04aa9-107">To enable the price report, the **Enable price report for store** parameter must be turned on.</span></span> <span data-ttu-id="04aa9-108">Este parámetro está en la pestaña **Parámetros de Commerce \> Descuentos \> Varios**. Abriendo la página **Informe de precio** aparece un cuadro de diálogo con distintas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="04aa9-108">This parameter is located on the **Commerce parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="04aa9-109">Las configuraciones disponibles se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="04aa9-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="04aa9-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="04aa9-110">Configuration</span></span> | <span data-ttu-id="04aa9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="04aa9-111">Description</span></span> |
|---|---|
| <span data-ttu-id="04aa9-112">Desde / hasta fecha</span><span class="sxs-lookup"><span data-stu-id="04aa9-112">From date / To date</span></span>| <span data-ttu-id="04aa9-113">El intervalo de fechas para el que el informe del precio se va a producir.</span><span class="sxs-lookup"><span data-stu-id="04aa9-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="04aa9-114">La duración se limita actualmente en 7 días.</span><span class="sxs-lookup"><span data-stu-id="04aa9-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="04aa9-115">Canal</span><span class="sxs-lookup"><span data-stu-id="04aa9-115">Channel</span></span>| <span data-ttu-id="04aa9-116">La tienda para la que se va a producir el informe del precio.</span><span class="sxs-lookup"><span data-stu-id="04aa9-116">The store for which the price report should be generated.</span></span> |
| <span data-ttu-id="04aa9-117">Mostrar productos con inventario disponible</span><span class="sxs-lookup"><span data-stu-id="04aa9-117">Display products with available inventory</span></span>| <span data-ttu-id="04aa9-118">Establecer esto en **Sí** mostrará los precios para solo los productos que tiene actualmente inventario físico disponible en la tienda.</span><span class="sxs-lookup"><span data-stu-id="04aa9-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="04aa9-119">Mostrar precios de las variantes</span><span class="sxs-lookup"><span data-stu-id="04aa9-119">Display prices for variants</span></span> | <span data-ttu-id="04aa9-120">Establecer esto en **Sí** mostrará los precios de variantes junto con los productos maestros.</span><span class="sxs-lookup"><span data-stu-id="04aa9-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="04aa9-121">Éste solo debe ser **Activado** si tiene precios específicos de variantes, porque el número de filas puede crecer mucho.</span><span class="sxs-lookup"><span data-stu-id="04aa9-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="04aa9-122">En versiones futuras, habilitaremos los precios basados en dimensiones de modo que el encargado de tienda puede elegir las dimensiones para las que los precios deben mostrarse.</span><span class="sxs-lookup"><span data-stu-id="04aa9-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="04aa9-123">Mostrar productos con cambios de precio</span><span class="sxs-lookup"><span data-stu-id="04aa9-123">Display products with price changes</span></span> | <span data-ttu-id="04aa9-124">Establecer esto en **Sí** mostrará los índices por solo las fechas en las que se ha cambiado el precio.</span><span class="sxs-lookup"><span data-stu-id="04aa9-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="04aa9-125">El precio para *un día antes* seleccionado **Desde fecha** se mostrará siempre, de modo que el encargado de tienda pueda identificar con facilidad los productos que no han cambiado los precios durante la duración completa seleccionada, y también puede ver el precio actual.</span><span class="sxs-lookup"><span data-stu-id="04aa9-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="04aa9-126">Después de que se cree el informe, el archivo de Excel se puede descargar para usar cualquier filtro necesario.</span><span class="sxs-lookup"><span data-stu-id="04aa9-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="04aa9-127">El informe del precio se puede usar para comprobar los precios históricos de los productos por últimas fechas.</span><span class="sxs-lookup"><span data-stu-id="04aa9-127">The price report can also be used to check the historical prices of products for past dates.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]