---
title: Estados y ciclo de vida de documentos
description: En este tema se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e3334e4284df681907d879ca2eab5cd12e764c99
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792832"
---
# <a name="document-states-and-lifecycle"></a><span data-ttu-id="5a6af-103">Estados y ciclo de vida de documentos</span><span class="sxs-lookup"><span data-stu-id="5a6af-103">Document states and lifecycle</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5a6af-104">En este tema se tratan los diversos estados de documentos de elementos de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a6af-104">This topic covers the various document states of page elements in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="document-state-descriptions"></a><span data-ttu-id="5a6af-105">Descripciones de estado de documento</span><span class="sxs-lookup"><span data-stu-id="5a6af-105">Document state descriptions</span></span>

<span data-ttu-id="5a6af-106">El tema [Elementos de página](page-elements-overview.md) muestra diversos tipos de documentos en el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="5a6af-106">The [Page elements](page-elements-overview.md) topic lists various documents types in the content management system (CMS).</span></span> <span data-ttu-id="5a6af-107">Estos tipos de documento pueden tener varios estados en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="5a6af-107">These document types can have several states in the authoring tool.</span></span> <span data-ttu-id="5a6af-108">Los estados de documentos ayudan a evitar conflictos de datos y a aplicar el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="5a6af-108">The document states help prevent data conflicts and enforce version control.</span></span> <span data-ttu-id="5a6af-109">Determinan quién puede cambiar los documentos, cuándo se pueden cambiar los documentos y cuándo se pueden ver los cambios por otras personas.</span><span class="sxs-lookup"><span data-stu-id="5a6af-109">They determine who can change the documents, when the documents can be changed, and when changes can be viewed by other people.</span></span>

<span data-ttu-id="5a6af-110">En la tabla siguiente se muestran los posibles estados de documentos de elementos de página en Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a6af-110">The following table shows the possible document states of page elements in Commerce.</span></span>

| <span data-ttu-id="5a6af-111">Estado del documento</span><span class="sxs-lookup"><span data-stu-id="5a6af-111">Document state</span></span>      | <span data-ttu-id="5a6af-112">Acción generador de sitios</span><span class="sxs-lookup"><span data-stu-id="5a6af-112">Site builder action</span></span>        | <span data-ttu-id="5a6af-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a6af-113">Description</span></span>                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="5a6af-114">Comprado</span><span class="sxs-lookup"><span data-stu-id="5a6af-114">Checked out</span></span>         | <span data-ttu-id="5a6af-115">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-115">Select **Edit**.</span></span>           | <span data-ttu-id="5a6af-116">El documento correspondiente se le ha retirado.</span><span class="sxs-lookup"><span data-stu-id="5a6af-116">The applicable document is checked out to you.</span></span> <span data-ttu-id="5a6af-117">Mientras un documento está en este estado, no puede ser modificado por otros usuarios autenticados del sistema y cualquier cambio que realice en el documento será visible solo para usted.</span><span class="sxs-lookup"><span data-stu-id="5a6af-117">While a document is in this state, it can't be changed by other authenticated system users, and any changes that you make to the document are visible only to you.</span></span> |
| <span data-ttu-id="5a6af-118">Guardado</span><span class="sxs-lookup"><span data-stu-id="5a6af-118">Saved</span></span>               | <span data-ttu-id="5a6af-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-119">Select **Save**.</span></span>           | <span data-ttu-id="5a6af-120">Los cambios que se han realizado en un documento desprotegido se guardan en la base de datos, pero el documento aún no se ha registrado ni publicado.</span><span class="sxs-lookup"><span data-stu-id="5a6af-120">Changes that have been made to a checked-out document are saved to the database, but the document isn't yet checked in or published.</span></span> <span data-ttu-id="5a6af-121">Los cambios guardados no son visibles para otros usuarios del sistema autenticados hasta que el autor selecciona **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-121">The saved changes aren't visible to other authenticated system users until the author selects **Finish editing**.</span></span> <span data-ttu-id="5a6af-122">No están visibles para usuarios externos hasta que se publica el artículo.</span><span class="sxs-lookup"><span data-stu-id="5a6af-122">They aren't visible to external users until the item is published.</span></span> |
| <span data-ttu-id="5a6af-123">Desprotección descartada</span><span class="sxs-lookup"><span data-stu-id="5a6af-123">Discarded check out</span></span> | <span data-ttu-id="5a6af-124">Seleccione **Descartar ediciones**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-124">Select **Discard edits**.</span></span>  | <span data-ttu-id="5a6af-125">Todos los cambios en el documento desprotegido se descartan y el elemento vuelve a la última versión que se registró.</span><span class="sxs-lookup"><span data-stu-id="5a6af-125">All changes to the checked-out document are discarded, and the item reverts to the last version that was checked in.</span></span> |
| <span data-ttu-id="5a6af-126">Entrada registrada</span><span class="sxs-lookup"><span data-stu-id="5a6af-126">Checked in</span></span>          | <span data-ttu-id="5a6af-127">Seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-127">Select **Finish editing**.</span></span> | <span data-ttu-id="5a6af-128">El documento editado está registrado.</span><span class="sxs-lookup"><span data-stu-id="5a6af-128">The edited document is checked in.</span></span> <span data-ttu-id="5a6af-129">Todos los cambios son visibles para otros usuarios del sistema autenticados, y esos usuarios pueden editar el documento.</span><span class="sxs-lookup"><span data-stu-id="5a6af-129">All changes are visible to other authenticated system users, and those users can then edit the document.</span></span> <span data-ttu-id="5a6af-130">Cada protección crea un registro de versión de documento en el historial del artículo.</span><span class="sxs-lookup"><span data-stu-id="5a6af-130">Each check-in creates a document version record in the item's history.</span></span> |
| <span data-ttu-id="5a6af-131">Publicadas</span><span class="sxs-lookup"><span data-stu-id="5a6af-131">Published</span></span>           | <span data-ttu-id="5a6af-132">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-132">Select **Publish**.</span></span>        | <span data-ttu-id="5a6af-133">El documento se publica y los cambios se envían a su sitio en vivo y los usuarios externos pueden descubrirlos.</span><span class="sxs-lookup"><span data-stu-id="5a6af-133">The document is published, and the changes are pushed to your live site and become discoverable by external users.</span></span> <span data-ttu-id="5a6af-134">Los elementos solo se pueden publicar si se registraron primero seleccionando **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="5a6af-134">Items can be published only if they have first been checked in by selecting **Finish editing**.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="5a6af-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5a6af-135">Additional resources</span></span>

[<span data-ttu-id="5a6af-136">Métodos para agregar contenido</span><span class="sxs-lookup"><span data-stu-id="5a6af-136">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="5a6af-137">Glosario del modelo de página</span><span class="sxs-lookup"><span data-stu-id="5a6af-137">Page model glossary</span></span>](page-elements-overview.md)

[<span data-ttu-id="5a6af-138">Trabajar con grupos de publicación</span><span class="sxs-lookup"><span data-stu-id="5a6af-138">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="5a6af-139">Habilitar y usar el uso compartido entre canales</span><span class="sxs-lookup"><span data-stu-id="5a6af-139">Enable and use cross-channel sharing</span></span>](cross-channel-sharing.md)

[<span data-ttu-id="5a6af-140">Trabajar con módulos</span><span class="sxs-lookup"><span data-stu-id="5a6af-140">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="5a6af-141">Trabajar con fragmentos</span><span class="sxs-lookup"><span data-stu-id="5a6af-141">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="5a6af-142">Visión general de plantillas y diseños</span><span class="sxs-lookup"><span data-stu-id="5a6af-142">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="5a6af-143">Personalizar navegación del sitio</span><span class="sxs-lookup"><span data-stu-id="5a6af-143">Customize site navigation</span></span>](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]