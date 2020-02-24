---
title: Agregar un icono de favoritos
description: En este tema se explica cómo agregar un icono de favoritos al sitio.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 287663817232e7ce86e8fdb1fb5c2fcfeed33d20
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001554"
---
# <a name="add-a-favicon"></a><span data-ttu-id="2c976-103">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="2c976-103">Add a favicon</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2c976-104">En este tema se explica cómo agregar un icono de favoritos al sitio.</span><span class="sxs-lookup"><span data-stu-id="2c976-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="2c976-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="2c976-105">Overview</span></span>

<span data-ttu-id="2c976-106">Un icono de favoritos es un pequeño archivo gráfico que se muestra en una pestaña del explorador web, en la barra de direcciones, en el historial de exploración, y en marcadores o favoritos, entre otros lugares.</span><span class="sxs-lookup"><span data-stu-id="2c976-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="2c976-107">Recomendamos que agregue un icono de favoritos al sitio, ya que representa y refuerza su marca, y ayuda a diferenciar el sitio de otros que los clientes visitan.</span><span class="sxs-lookup"><span data-stu-id="2c976-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="2c976-108">Aunque puede agregar varios iconos favoritos de diversos tamaños y tipos de archivos al sitio, este tema muestra cómo agregar un icono favorito único.</span><span class="sxs-lookup"><span data-stu-id="2c976-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="2c976-109">Sin embargo, se utilizan el mismo proceso y ubicación para agregar más iconos favoritos.</span><span class="sxs-lookup"><span data-stu-id="2c976-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="2c976-110">Cargue un icono favorito en la colección de activos del sitio</span><span class="sxs-lookup"><span data-stu-id="2c976-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="2c976-111">Para cargar un icono favorito en la colección de activos del sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2c976-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="2c976-112">Vaya a **Activos \> Cargar \> Cargar activos**.</span><span class="sxs-lookup"><span data-stu-id="2c976-112">Go to **Assets \> Upload \> Upload assets**.</span></span>
1. <span data-ttu-id="2c976-113">Busque y seleccione el icono de favoritos en el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="2c976-113">Find and select the favicon on your local file system.</span></span>
1. <span data-ttu-id="2c976-114">Especifique un título y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2c976-114">Enter a title, and then select **OK**.</span></span> 
1. <span data-ttu-id="2c976-115">En el panel de propiedades de la derecha, copie la dirección URL pública del icono favorito.</span><span class="sxs-lookup"><span data-stu-id="2c976-115">In the property pane on the right, copy the public URL of the favicon.</span></span>

> [!NOTE]
> <span data-ttu-id="2c976-116">Si no selecciona la opción **Publicar activos tras la carga**, debe volver a la página **Activos** y publicar manualmente el icono favorito posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2c976-116">If you don't select the **Publish assets after upload** option, you must return to **Assets** page and manually publish the favicon later.</span></span>

## <a name="create-the-html-for-the-favicon"></a><span data-ttu-id="2c976-117">Crear el HTML para el icono favorito</span><span class="sxs-lookup"><span data-stu-id="2c976-117">Create the HTML for the favicon</span></span>

<span data-ttu-id="2c976-118">Para crear el HTML para el icono favorito, use el siguiente fragmento de código HTML.</span><span class="sxs-lookup"><span data-stu-id="2c976-118">To create the HTML for the favicon, use the following HTML snippet.</span></span> <span data-ttu-id="2c976-119">Para el atributo **href**, reemplace **"URL\_pública\_para\_su\_icono favorito"** por la dirección URL pública que ha copiado antes.</span><span class="sxs-lookup"><span data-stu-id="2c976-119">For the **href** attribute, replace **"Public\_URL\_for\_your\_favicon"** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a><span data-ttu-id="2c976-120">Agregar el HTML para el icono favorito al elemento \<head\> de sus páginas</span><span class="sxs-lookup"><span data-stu-id="2c976-120">Add the HTML for the favicon to the \<head\> element of your pages</span></span>

<span data-ttu-id="2c976-121">Para agregar un icono favorito al sitio, use el mismo procedimiento usado para agregar cualquier tipo de HTML o script al elemento **\<head\>** de las páginas de su sitio.</span><span class="sxs-lookup"><span data-stu-id="2c976-121">To add a favicon to your site, use the same procedure that is used to add any type of HTML or script to the **\<head\>** element of your site pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c976-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c976-122">Additional resources</span></span>

[<span data-ttu-id="2c976-123">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="2c976-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="2c976-124">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="2c976-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="2c976-125">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="2c976-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="2c976-126">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="2c976-126">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="2c976-127">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="2c976-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="2c976-128">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="2c976-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="2c976-129">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="2c976-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

