---
title: Configuración de cobertura
description: Este tema proporciona información acerca de la configuración de cobertura que la programación maestra usa para calcular los requisitos de artículos.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538903"
---
# <a name="coverage-settings"></a><span data-ttu-id="a1f89-103">Configuración de cobertura</span><span class="sxs-lookup"><span data-stu-id="a1f89-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1f89-104">La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos.</span><span class="sxs-lookup"><span data-stu-id="a1f89-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="a1f89-105">Puede especificar la configuración de cobertura de varios modos:</span><span class="sxs-lookup"><span data-stu-id="a1f89-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="a1f89-106">Especifique la configuración de cobertura para un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="a1f89-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="a1f89-107">Puede crear un grupo de cobertura que contenga la configuración de todos los productos vinculados al grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="a1f89-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="a1f89-108">Para crear un grupo de cobertura, vaya a **Planificación maestra &gt; Configurar &gt; Cobertura &gt; Grupos de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="a1f89-109">Puede vincular un grupo de cobertura a un producto.</span><span class="sxs-lookup"><span data-stu-id="a1f89-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="a1f89-110">Si el vínculo es específico de un sitio, un almacén o una dimensión de producto, use el campo **Grupo de cobertura** de la página **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="a1f89-111">Si el vínculo es genérico, independientemente de las dimensiones de producto, use el campo **Grupo de cobertura** de la ficha desplegable **Plan** de la página **Detalles de producto**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="a1f89-112">De forma predeterminada, si no vincula ningún grupo de cobertura a un producto, la planificación maestra usa el grupo de cobertura general especificado en la página **Parámetros de planificación maestra** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a1f89-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="a1f89-113">Especifique la configuración de cobertura para un producto.</span><span class="sxs-lookup"><span data-stu-id="a1f89-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="a1f89-114">Puede crear una configuración de cobertura para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="a1f89-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="a1f89-115">Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="a1f89-116">Seleccione el producto y entonces, en el Panel de acciones, en la pestaña **Plan**, en el Grupo de **cobertura**, haga clic en **Cobertura de artículos** para abrir la página **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="a1f89-117">Si el producto ya está vinculado a un grupo de cobertura, puede anular la configuración del grupo de cobertura mediante el campo **Reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="a1f89-118">Las opciones de cobertura en la página**Cobertura de artículos** prevalece sobre la configuración en la página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="a1f89-119">Especifique la configuración de cobertura para un producto mediante un asistente.</span><span class="sxs-lookup"><span data-stu-id="a1f89-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="a1f89-120">El asistente le guía paso a paso con el proceso de configurar los parámetros principales de la cobertura de artículos.</span><span class="sxs-lookup"><span data-stu-id="a1f89-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="a1f89-121">En la página **Cobertura de artículos** del panel de acciones, seleccione **Asistente** para abrir el **Asistente de cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="a1f89-122">Especifique la configuración de cobertura para un grupo de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="a1f89-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="a1f89-123">Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="a1f89-124">En la página **Detalles de producto emitido**, en la ficha desplegable **General**, en la sección **Administración**, seleccione el vínculo en el campo **Grupo de dimensiones de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="a1f89-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="a1f89-125">En la página **Grupos de dimensiones de almacenamiento**, seleccione la casilla de verificación **Plan de cobertura por dimensión** para crear la configuración de cobertura para una dimensión en el grupo de dimensiones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a1f89-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="a1f89-126">Todas las dimensiones de producto, como configuración, color, tamaño, estilo, deben tener el campo **Plan de cobertura por dimensión** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a1f89-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a1f89-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a1f89-127">Additional resources</span></span>

[<span data-ttu-id="a1f89-128">Planes maestros</span><span class="sxs-lookup"><span data-stu-id="a1f89-128">Master plans</span></span>](master-plans.md)
