---
title: Excluir productos que tienen estados del ciclo de vida del producto específicos
description: Este tema explica cómo excluir productos según el estado de su ciclo de vida cuando se usa la funcionalidad de Optimización de planificación.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 02c31aa3862df8dabc2b8c065dc3a94877d237f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992429"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a><span data-ttu-id="61376-103">Excluir productos que tienen estados del ciclo de vida del producto específicos</span><span class="sxs-lookup"><span data-stu-id="61376-103">Exclude products that have specific product lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61376-104">Los productos lanzados y las versiones de productos lanzados incluyen un campo **Estado del ciclo de vida del producto**.</span><span class="sxs-lookup"><span data-stu-id="61376-104">Released products and released product versions include a **Product lifecycle state** field.</span></span> <span data-ttu-id="61376-105">Este campo le permite controlar, entre otras cosas, qué productos se incluyen durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="61376-105">This field lets you control, among other things, which products are included during master planning.</span></span> <span data-ttu-id="61376-106">Puede agregar, eliminar y editar estados del ciclo de vida según sea necesario yendo a **Gestión de información de producto \> Preparar \> Estado del ciclo de vida del producto**.</span><span class="sxs-lookup"><span data-stu-id="61376-106">You can add, remove, and edit lifecycle states as required by going to **Product information management \> Setup \> Product lifecycle state**.</span></span> <span data-ttu-id="61376-107">Para cada estado del ciclo de vida del producto, establezca la opción **Está activo para planificar** en *Sí* si los productos que tienen ese estado deben incluirse durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="61376-107">For each product lifecycle state, set the **Is active for planning** option to *Yes* if products that have that state should be included during master planning.</span></span> <span data-ttu-id="61376-108">Cuando la opción se establece en *No*, los productos y variantes asociados se excluirán de toda la planificación maestra y todos los cálculos en el nivel de lista de materiales (BOM).</span><span class="sxs-lookup"><span data-stu-id="61376-108">When the option is set to *No*, the associated products and variants will be excluded from all master planning and all calculations at the bill of materials (BOM) level.</span></span>

<span data-ttu-id="61376-109">Productos y variantes lanzados donde el campo **Estado del ciclo de vida del producto** se deja en blanco se tratan como si tuvieran un estado de ciclo de vida del producto donde la opción **Está activo para planificar** está configurada en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="61376-109">Released products and variants where the **Product lifecycle state** field is left blank are treated as though they have a product lifecycle state where the **Is active for planning** option is set to *Yes*.</span></span> <span data-ttu-id="61376-110">En otras palabras, se incluirán durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="61376-110">In other words, they will be included during master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="61376-111">Para ayudar a evitar sugerencias de suministro innecesarias, le recomendamos encarecidamente que asocie todos los productos y variantes lanzados obsoletos con un estado del ciclo de vida del producto donde la opción **Está activo para planificar** está configurada en *No*.</span><span class="sxs-lookup"><span data-stu-id="61376-111">To help avoid unnecessary supply suggestions, we strongly recommend that you associate all obsolete released products and variants with a product lifecycle state where the **Is active for planning** option is set to *No*.</span></span> <span data-ttu-id="61376-112">Este enfoque es especialmente importante cuando trabaja con variantes de configuración de productos que no son reutilizables, porque ayudará a evitar el desperdicio.</span><span class="sxs-lookup"><span data-stu-id="61376-112">This approach is especially important when you work with product configuration variants that aren't reusable, because it will help prevent waste.</span></span>

## <a name="related-resources"></a><span data-ttu-id="61376-113">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="61376-113">Related resources</span></span>

<span data-ttu-id="61376-114">Para obtener más información acerca de los estados de ciclo de vida de producto, consulte la [Información general sobre el estado de ciclo de vida de producto](../../pim/product-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="61376-114">For more information about product lifecycle states, see [Product lifecycle state overview](../../pim/product-lifecycle.md).</span></span>

<span data-ttu-id="61376-115">Para obtener información detallada que incluye los pasos para usar estados de ciclo de vida del producto para excluir productos de la planificación maestra y cálculos a nivel de LM, vea [Crear un estado de ciclo de vida del producto para excluir productos de la planificación maestra](../../pim/tasks/exclude-products-master-planning.md).</span><span class="sxs-lookup"><span data-stu-id="61376-115">For detailed information that includes steps for using product lifecycle states to exclude products from master planning and BOM-level calculations, see [Create a product lifecycle state to exclude products from Master planning](../../pim/tasks/exclude-products-master-planning.md).</span></span>
