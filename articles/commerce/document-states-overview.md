---
title: Estados y ciclo de vida de documentos
description: En este tema se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: edb81efc45fc5e7eed32cb7d9b8fda5ade987dd4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914896"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="55db3-103">Estados y ciclo de vida de documentos</span><span class="sxs-lookup"><span data-stu-id="55db3-103">Document states and lifecycle</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="55db3-104">En este tema se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55db3-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="55db3-105">Descripciones de estado de documento</span><span class="sxs-lookup"><span data-stu-id="55db3-105">Document state descriptions</span></span>

<span data-ttu-id="55db3-106">El tema [Elementos de página](page-elements-overview.md) muestra diversos tipos de documentos en el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="55db3-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="55db3-107">Estos tipos de documento pueden tener varios estados en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="55db3-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="55db3-108">Los estados de documentos ayudan a evitar conflictos de datos y a aplicar el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="55db3-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="55db3-109">Determinan quién puede cambiar los documentos, cuándo se pueden cambiar los documentos y cuándo se pueden ver los cambios por otras personas.</span><span class="sxs-lookup"><span data-stu-id="55db3-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="55db3-110">En la tabla siguiente se muestran los posibles estados de documentos de elementos de página en Commerce.</span><span class="sxs-lookup"><span data-stu-id="55db3-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="55db3-111">Estado del documento</span><span class="sxs-lookup"><span data-stu-id="55db3-111">Document state</span></span> | <span data-ttu-id="55db3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="55db3-112">Description</span></span> |
|---|---|
| <span data-ttu-id="55db3-113">Desprotegido</span><span class="sxs-lookup"><span data-stu-id="55db3-113">Checked out</span></span> | <span data-ttu-id="55db3-114">Si un artículo de CMS se desprotege para usted, no lo podrán editar otros usuarios del sistema autenticados.</span><span class="sxs-lookup"><span data-stu-id="55db3-114">When a CMS item is checked out to you, it can't be edited by any other authenticated system users.</span></span> <span data-ttu-id="55db3-115">Los cambios que realice al artículo solo serán visibles para usted.</span><span class="sxs-lookup"><span data-stu-id="55db3-115">Any changes that you make to the item are visible only to you.</span></span> |
| <span data-ttu-id="55db3-116">Protegido</span><span class="sxs-lookup"><span data-stu-id="55db3-116">Checked in</span></span> | <span data-ttu-id="55db3-117">Cuando se protege un artículo de CMS, todos los cambios son visibles para otros usuarios del sistema autenticados y dichos usuarios pueden desproteger a continuación el artículo y editarlo.</span><span class="sxs-lookup"><span data-stu-id="55db3-117">When a CMS item is checked in, all changes are visible to other authenticated system users, and those users can then check out the item and edit it.</span></span> <span data-ttu-id="55db3-118">Cada protección crea un registro de versión de documento en el historial del artículo.</span><span class="sxs-lookup"><span data-stu-id="55db3-118">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="55db3-119">Publicada</span><span class="sxs-lookup"><span data-stu-id="55db3-119">Published</span></span> | <span data-ttu-id="55db3-120">Cuando se publica un artículo de CMS, se envía a su sitio activo y usuarios externos no autenticados pueden detectarlo en Internet.</span><span class="sxs-lookup"><span data-stu-id="55db3-120">When a CMS item is published, it's pushed to your live site and becomes discoverable on the internet by non-authenticated external users.</span></span> <span data-ttu-id="55db3-121">Los artículos se pueden publicar solo si se han protegido.</span><span class="sxs-lookup"><span data-stu-id="55db3-121">Items can be published only if they have been checked in.</span></span> |
| <span data-ttu-id="55db3-122">Guardado</span><span class="sxs-lookup"><span data-stu-id="55db3-122">Saved</span></span> | <span data-ttu-id="55db3-123">Los cambios realizados en un artículo de CMS desprotegido se pueden guardar en el CMS antes de que el artículo se proteja o se publique.</span><span class="sxs-lookup"><span data-stu-id="55db3-123">Changes that have been made to a checked-out CMS item can be saved to the CMS before the item is checked in or published.</span></span> <span data-ttu-id="55db3-124">Estos cambios guardados no son visibles para otros usuarios del sistema autenticados hasta que el artículo se protege.</span><span class="sxs-lookup"><span data-stu-id="55db3-124">These saved changes aren't visible to other authenticated system users until the item is checked in.</span></span> <span data-ttu-id="55db3-125">No están visibles para usuarios externos hasta que se publica el artículo.</span><span class="sxs-lookup"><span data-stu-id="55db3-125">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="55db3-126">Desprotección descartada</span><span class="sxs-lookup"><span data-stu-id="55db3-126">Discarded check out</span></span> | <span data-ttu-id="55db3-127">Cuando se descarta un artículo de CMS desprotegido, se eliminan todos los cambios guardados y el artículo se revierte a la versión que se protegió más recientemente.</span><span class="sxs-lookup"><span data-stu-id="55db3-127">When a checked-out CMS item is discarded, all saved changes are deleted, and the item reverts to the version that was most recently checked in.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="55db3-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="55db3-128">Additional resources</span></span>

[<span data-ttu-id="55db3-129">Métodos para agregar contenido</span><span class="sxs-lookup"><span data-stu-id="55db3-129">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="55db3-130">Glosario del modelo de página</span><span class="sxs-lookup"><span data-stu-id="55db3-130">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="55db3-131">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="55db3-131">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="55db3-132">Trabajar con módulos</span><span class="sxs-lookup"><span data-stu-id="55db3-132">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="55db3-133">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="55db3-133">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="55db3-134">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="55db3-134">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="55db3-135">Personalizar navegación del sitio</span><span class="sxs-lookup"><span data-stu-id="55db3-135">Customize site navigation</span></span>](customize-site-navigation.md)