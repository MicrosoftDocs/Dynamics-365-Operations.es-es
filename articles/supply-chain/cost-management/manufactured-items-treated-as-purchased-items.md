---
title: Configurar productos que pueden fabricarse o suministrarse
description: 'Los productos se pueden suministrar de distintas maneras: se pueden producir (fabricar) o adquirir (comprar). Este artículo describe algunos puntos típicos que se deben tener en cuenta al configurar los productos para admitir el abastecimiento múltiple.'
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9b5ba58703e636308d83a94ecc2e27e44812c49
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981544"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="afb7d-104">Configurar productos que pueden fabricarse o suministrarse</span><span class="sxs-lookup"><span data-stu-id="afb7d-104">Set up products that can be produced or procured</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afb7d-105">Los productos se pueden suministrar de distintas maneras: se pueden producir (fabricar) o adquirir (comprar).</span><span class="sxs-lookup"><span data-stu-id="afb7d-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="afb7d-106">Este artículo describe algunos puntos típicos que se deben tener en cuenta al configurar los productos para admitir el abastecimiento múltiple.</span><span class="sxs-lookup"><span data-stu-id="afb7d-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="afb7d-107">El abastecimiento múltiple se usa normalmente para un artículo comprado que a veces se fabrica, o cuando se modifica un artículo era principalmente un artículo fabricado de modo que pase a ser principalmente un artículo comprado.</span><span class="sxs-lookup"><span data-stu-id="afb7d-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="afb7d-108">El artículo se designa primero como artículo fabricado para definir la información de ruta y de lista de materiales y para admitir pedidos de producción para el artículo.</span><span class="sxs-lookup"><span data-stu-id="afb7d-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="afb7d-109">El tipo de producción debe establecerse en **L. MAT.** (o, en fabricación de procesos,**Fórmula** o **Coproducto**).</span><span class="sxs-lookup"><span data-stu-id="afb7d-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="afb7d-110">Cuando se usan costes estándar, se puede calcular el registro de costes de artículo para el artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="afb7d-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="afb7d-111">No obstante, es posible que el registro de coste de artículo no coincida con el coste estándar que desee asignar a los artículos de compra.</span><span class="sxs-lookup"><span data-stu-id="afb7d-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="afb7d-112">En este caso, deberá especificar manualmente el coste estándar que desee asignar y activarlo en el registro de costes de artículos.</span><span class="sxs-lookup"><span data-stu-id="afb7d-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="afb7d-113">Para calcular los costes, puede usar una lista de materiales y una ruta especiales que representan la combinación de suministro del producto a lo largo de un período fiscal, para minimizar las desviaciones en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="afb7d-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="afb7d-114">Además, un artículo fabricado en un sitio se puede transferir a otro sitio.</span><span class="sxs-lookup"><span data-stu-id="afb7d-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="afb7d-115">Por tanto, el coste del artículo se debe especificar y activar manualmente para el sitio al que se transfiere el artículo.</span><span class="sxs-lookup"><span data-stu-id="afb7d-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="afb7d-116">Cuando usa un artículo fabricado como componente de productos de alto nivel, los costes del componente deben tratarse como un artículo comprado.</span><span class="sxs-lookup"><span data-stu-id="afb7d-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="afb7d-117">Esta directriz se aplica independientemente de si los costes del componente se calcularon o se especificaron manualmente.</span><span class="sxs-lookup"><span data-stu-id="afb7d-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="afb7d-118">En otras palabras, un cálculo de lista de materiales debe tratar los costes del artículo como un componente comprado en lugar de calcular los costes basándose en la información de ruta y la lista de materiales del artículo.</span><span class="sxs-lookup"><span data-stu-id="afb7d-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="afb7d-119">Para evitar el cálculo, seleccione el indicador **Detener la expansión** incrustado en el grupo de cálculo de lista de materiales asignado al artículo.</span><span class="sxs-lookup"><span data-stu-id="afb7d-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="afb7d-120">Para evitar que se utilicen los requisitos de expansión en los cálculos de la programación maestra a través del artículo, defina el indicador de límite de expansión en 0 (cero) días en la cobertura del artículo o en el grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="afb7d-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="afb7d-121">El cálculo de la programación maestra tratará el artículo como un artículo comprado y no realizará más cálculos en cuanto a información de ruta y lista de materiales del artículo.</span><span class="sxs-lookup"><span data-stu-id="afb7d-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>





