---
title: Configurar códigos de barras
description: Este artículo describe cómo usar códigos de barras en Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 52801e0d09b1d7da50719966700ca45275d702f7
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057287"
---
# <a name="set-up-bar-codes"></a><span data-ttu-id="4339a-103">Configurar códigos de barras</span><span class="sxs-lookup"><span data-stu-id="4339a-103">Set up bar codes</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4339a-104">Este artículo describe cómo usar códigos de barras en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4339a-104">This article describes how to use bar codes in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4339a-105">Puede usar códigos de barras para comprar y vender productos, realizar un seguimiento de las variantes del producto y configurar los clientes y empleados.</span><span class="sxs-lookup"><span data-stu-id="4339a-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="4339a-106">También puede usar códigos de barras para emitir y endosar cupones, tarjetas de regalo y notas de crédito.</span><span class="sxs-lookup"><span data-stu-id="4339a-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="4339a-107">Puede configurar productos para que tengan códigos de barras estándar o códigos de barras internos personalizados.</span><span class="sxs-lookup"><span data-stu-id="4339a-107">You can set up products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="4339a-108">Los productos pueden tener más de un código de barras.</span><span class="sxs-lookup"><span data-stu-id="4339a-108">Products can have more than one bar code.</span></span> <span data-ttu-id="4339a-109">Por ejemplo, un producto puede tener varios códigos de barras si procede de distintos fabricantes o si tiene variaciones de tamaño, estilo o color.</span><span class="sxs-lookup"><span data-stu-id="4339a-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="4339a-110">Los códigos de barras pueden incluir el peso o el precio del producto.</span><span class="sxs-lookup"><span data-stu-id="4339a-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="4339a-111">Las máscaras de código de barras son plantillas que se usan para crear códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="4339a-111">Bar code masks are templates that are used to create bar codes.</span></span>

> [!NOTE]
> <span data-ttu-id="4339a-112">Si asigna un código de barras único a cada combinación de variantes, puede digitalizar el código de barras en la caja registradora para que el programa determine la variante del producto que se vende.</span><span class="sxs-lookup"><span data-stu-id="4339a-112">If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="4339a-113">También puede recopilar y consultar estadísticas sobre las venta por variante.</span><span class="sxs-lookup"><span data-stu-id="4339a-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="4339a-114">Se puede asignar un número único a cada grupo de tamaños, colores y estilos que identifique a este grupo en el código de barras.</span><span class="sxs-lookup"><span data-stu-id="4339a-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="4339a-115">Commerce usa la máscara de código de barras para generar automáticamente códigos de barras para cada combinación de variantes.</span><span class="sxs-lookup"><span data-stu-id="4339a-115">Commerce uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="4339a-116">Esta funcionalidad puede ser útil si existen muchos tamaños, colores y estilos, ya que el número de combinaciones aumenta significativamente con cada código de variante que se agrega.</span><span class="sxs-lookup"><span data-stu-id="4339a-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="4339a-117">Si no se usa esta funcionalidad, es necesario asignar códigos de barras manualmente a cada combinación que represente una variante de producto.</span><span class="sxs-lookup"><span data-stu-id="4339a-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span>

<span data-ttu-id="4339a-118">Los códigos de barras se crean manual o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4339a-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="4339a-119">Para crear códigos de barras, realice las siguientes tareas en el orden en el que aparecen.</span><span class="sxs-lookup"><span data-stu-id="4339a-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1. <span data-ttu-id="4339a-120">[Configuración de los caracteres de máscara de código de barras](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="4339a-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2. <span data-ttu-id="4339a-121">[Configuración de máscaras de código de barras](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="4339a-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3. <span data-ttu-id="4339a-122">Configure códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="4339a-122">Configure bar code setups.</span></span>
4. <span data-ttu-id="4339a-123">Cree códigos de barras para productos.</span><span class="sxs-lookup"><span data-stu-id="4339a-123">Create bar codes for products.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4339a-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4339a-124">Additional resources</span></span>

[<span data-ttu-id="4339a-125">Configuración de máscaras de código de barras</span><span class="sxs-lookup"><span data-stu-id="4339a-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)
