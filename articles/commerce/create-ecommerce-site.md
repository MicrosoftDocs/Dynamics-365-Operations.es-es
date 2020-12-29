---
title: Crear un sitio de comercio electrónico
description: En este tema se describen los pasos y la información necesarios para crear un nuevo sitio de comercio electrónico con el generador de sitios de Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7d552f29fd8f52b512a7c21b36b0a814cac50646
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517193"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="f65d8-103">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="f65d8-103">Create an e-commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f65d8-104">En este tema se describen los pasos y la información necesarios para crear un nuevo sitio de comercio electrónico con el generador de sitios de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f65d8-104">This topic describes the steps and information required to create a new e-commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="f65d8-105">Cuando licencia las capacidades de Dynamics 365 Commerce, el creador de sitios contará con un sitio de inicio que puede usar como base para su propio sitio.</span><span class="sxs-lookup"><span data-stu-id="f65d8-105">When you license the Dynamics 365 Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="f65d8-106">Sin embargo, si desea comenzar desde cero o si desea establecer un segundo sitio, deberá establecer un nuevo sitio en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="f65d8-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="f65d8-107">Configurar su sitio</span><span class="sxs-lookup"><span data-stu-id="f65d8-107">Set up your site</span></span>

<span data-ttu-id="f65d8-108">Para configurar el sitio, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f65d8-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="f65d8-109">Abra el entorno del generador de sitios.</span><span class="sxs-lookup"><span data-stu-id="f65d8-109">Open the site builder environment.</span></span> <span data-ttu-id="f65d8-110">Encontrará un vínculo al generador de sitios en Microsoft Lifecycle Services (LCS), en la página de características del entorno para Commerce.</span><span class="sxs-lookup"><span data-stu-id="f65d8-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="f65d8-111">En la página principal para el entorno de creación del sitio, seleccione **Nuevo sitio**.</span><span class="sxs-lookup"><span data-stu-id="f65d8-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="f65d8-112">En el cuadro de diálogo **Nuevo sitio**, proporcione la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="f65d8-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="f65d8-113">Campo</span><span class="sxs-lookup"><span data-stu-id="f65d8-113">Field</span></span>                               | <span data-ttu-id="f65d8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f65d8-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="f65d8-115">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="f65d8-115">Site name</span></span>                           | <span data-ttu-id="f65d8-116">Especifique el nombre para mostrar que se debe usar para el sitio en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="f65d8-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="f65d8-117">Este nombre solo es visible en el entorno de creación y no se mostrará a los clientes.</span><span class="sxs-lookup"><span data-stu-id="f65d8-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="f65d8-118">Grupo de seguridad del administrador del sitio</span><span class="sxs-lookup"><span data-stu-id="f65d8-118">Site administrator's security group</span></span> | <span data-ttu-id="f65d8-119">Especifique el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que administra a los usuarios con el rol de administrador de este sitio.</span><span class="sxs-lookup"><span data-stu-id="f65d8-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="f65d8-120">Canal predeterminado (número de unidad operativa)</span><span class="sxs-lookup"><span data-stu-id="f65d8-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="f65d8-121">Seleccione la tienda en línea para la que este sitio servirá como el escaparate web.</span><span class="sxs-lookup"><span data-stu-id="f65d8-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="f65d8-122">Si desea que su sitio de comercio electrónico admita varias tiendas en línea, debe asociar las tiendas con su sitio en **Valores de configuración de sitio** después de configurar el sitio.</span><span class="sxs-lookup"><span data-stu-id="f65d8-122">If you want your e-commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="f65d8-123">Idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="f65d8-123">Default language</span></span>                            | <span data-ttu-id="f65d8-124">Especifique el idioma predeterminado para esta tienda en línea y mercado.</span><span class="sxs-lookup"><span data-stu-id="f65d8-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="f65d8-125">Una tienda en línea puede admitir varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="f65d8-125">An online store can support multiple languages.</span></span> <span data-ttu-id="f65d8-126">Si desea admitir varios idiomas para esta tienda en línea u otra tienda en línea, puede configurar dicha compatibilidad en **Valores de configuración de sitio** después de que se configure el sitio.</span><span class="sxs-lookup"><span data-stu-id="f65d8-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="f65d8-127">Dominio</span><span class="sxs-lookup"><span data-stu-id="f65d8-127">Domain</span></span>                              | <span data-ttu-id="f65d8-128">Seleccione un nombre de dominio que servirá como el dominio para esta tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="f65d8-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="f65d8-129">Si no ha configurado dominios en LCS, puede dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f65d8-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="f65d8-130">Cuando su dominio se haya configurado en LCS, debe agregarlo a la tienda en línea en **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="f65d8-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="f65d8-131">Ruta</span><span class="sxs-lookup"><span data-stu-id="f65d8-131">Path</span></span>                              | <span data-ttu-id="f65d8-132">Cuando el sitio admite más de un idioma para un nombre de dominio determinado, use el campo de ruta para crear una dirección URL de sitio única para dicha combinación de dominio e idioma.</span><span class="sxs-lookup"><span data-stu-id="f65d8-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="f65d8-133">Si el idioma que ha especificado en el campo **Idioma predeterminado** es el único idioma que admitirá para este dominio, o seguirá siendo el idioma predeterminado después de que haya localizado su sitio en otros idiomas, se recomienda dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f65d8-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="f65d8-134">Una vez creado el sitio, puede comprobar que esté asociado a la tienda en línea seleccionando la pestaña **Productos**. Solo debería ver la selección de productos que se ha asignado a la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="f65d8-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="f65d8-135">Puede usar el menú desplegable en la parte superior izquierda de la página para obtener acceso a los productos asignados por categoría.</span><span class="sxs-lookup"><span data-stu-id="f65d8-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f65d8-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f65d8-136">Additional resources</span></span>

[<span data-ttu-id="f65d8-137">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="f65d8-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="f65d8-138">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="f65d8-138">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="f65d8-139">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="f65d8-139">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="f65d8-140">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="f65d8-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="f65d8-141">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="f65d8-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="f65d8-142">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="f65d8-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="f65d8-143">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="f65d8-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="f65d8-144">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="f65d8-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="f65d8-145">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="f65d8-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="f65d8-146">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="f65d8-146">Enable location-based store detection</span></span>](enable-store-detection.md)
