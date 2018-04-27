---
title: "Configuración de cobertura"
description: "La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 591b1cd739bb3be61299f33f180ca7c264d21a35
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="coverage-settings"></a><span data-ttu-id="09696-103">Configuración de cobertura</span><span class="sxs-lookup"><span data-stu-id="09696-103">Coverage settings</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="09696-104">La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos.</span><span class="sxs-lookup"><span data-stu-id="09696-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="09696-105">Puede especificar la configuración de cobertura de varios modos:</span><span class="sxs-lookup"><span data-stu-id="09696-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="09696-106">Especifique la configuración de cobertura para un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="09696-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="09696-107">Puede crear un grupo de cobertura que contenga la configuración de todos los productos vinculados al grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="09696-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="09696-108">Haga clic en **Planificación maestra &gt; Configurar &gt; Cobertura &gt; Grupos de cobertura** para crear un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="09696-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="09696-109">Puede vincular un grupo de cobertura a un producto.</span><span class="sxs-lookup"><span data-stu-id="09696-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="09696-110">Si el vínculo es específico de un sitio, un almacén o una dimensión de producto, use el campo **Grupo de cobertura** de la página **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="09696-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="09696-111">Si el vínculo es genérico, independientemente de las dimensiones de producto, use **Grupo de cobertura** en la ficha desplegable **Plan** de la página **Detalles de producto**.</span><span class="sxs-lookup"><span data-stu-id="09696-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="09696-112">Si no vincula ningún grupo de cobertura a un producto, la planificación maestra usa el **Grupo de cobertura general** especificado en la página **Parámetros de planificación maestra** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="09696-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="09696-113">Especifique la configuración de cobertura para un producto.</span><span class="sxs-lookup"><span data-stu-id="09696-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="09696-114">Puede crear una configuración de cobertura para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="09696-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="09696-115">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="09696-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="09696-116">Seleccione el producto, en el **Panel de acciones**, en la pestaña **Plan**, en el **Grupo de cobertura**, haga clic en **Cobertura de artículos** para abrir la página **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="09696-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="09696-117">Si el producto ya está vinculado a un grupo de cobertura, puede anular la configuración del grupo de cobertura mediante el campo **Reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="09696-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="09696-118">Las opciones de cobertura en la página**Cobertura de artículos** prevalece sobre la configuración en la página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="09696-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="09696-119">Especifique la configuración de cobertura para un producto mediante un asistente.</span><span class="sxs-lookup"><span data-stu-id="09696-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="09696-120">El asistente le guía paso a paso para ayudarle a configurar los parámetros de cobertura de los artículos principales.</span><span class="sxs-lookup"><span data-stu-id="09696-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="09696-121">En la página **Cobertura de artículos**, haga clic en **Asistente** para abrir el **Asistente de cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="09696-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

- <span data-ttu-id="09696-122">Especifique la configuración de cobertura para un grupo de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="09696-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="09696-123">Haga clic en <strong>Gestión de información de productos &gt; Común &gt; Productos emitidos</strong>.</span><span class="sxs-lookup"><span data-stu-id="09696-123">Click <strong>Product information management &gt; Common &gt; Released products</strong>.</span></span> <span data-ttu-id="09696-124">En la página <strong>Detalles de producto emitido **, en la ficha **General</strong>, en el grupo <strong>Administración</strong>, haga clic en el vínculo <strong>Grupo de dimensiones de almacenamiento</strong>.</span><span class="sxs-lookup"><span data-stu-id="09696-124">On the <strong>Released product detail **page, on the **General</strong> tab, in the <strong>Administration</strong> group, click the <strong>Storage dimension group</strong> link.</span></span> <span data-ttu-id="09696-125">En la página <strong>Grupo de dimensiones de almacenamiento</strong>, seleccione el campo <strong>Plan de cobertura por dimensión</strong> para crear la configuración de cobertura para una dimensión en el grupo de dimensiones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="09696-125">On the <strong>Storage dimension group</strong> page, select the <strong>Coverage plan by dimension</strong> field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="09696-126">Todas las dimensiones de producto, como configuración, color, tamaño, estilo, deben tener el campo <strong>Plan de cobertura por dimensión</strong> seleccionado.</span><span class="sxs-lookup"><span data-stu-id="09696-126">All product dimensions, such as configuration, color, size, style, must have the <strong>Coverage plan by dimension</strong> field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="09696-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09696-127">See also</span></span>
--------

[<span data-ttu-id="09696-128">Planes maestros</span><span class="sxs-lookup"><span data-stu-id="09696-128">Master plans</span></span>](master-plans.md)




