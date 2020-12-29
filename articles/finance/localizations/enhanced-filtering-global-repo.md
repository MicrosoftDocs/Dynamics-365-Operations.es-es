---
title: Filtrado mejorado de RCS en el repositorio RCS/Global
description: Este tema describe capacidades de filtrado mejoradas para el repositorio global de RCS, que se han mejorado para incluir los filtros adicionales.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447480"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="caf45-103">Opciones de filtrado de RCS mejoradas para encontrar configuraciones en el repositorio RCS/global</span><span class="sxs-lookup"><span data-stu-id="caf45-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="caf45-104">Este tema describe capacidades de filtrado mejoradas para el repositorio global Regulatory Configuration Service (RCS), que se han mejorado para incluir la capacidad de filtrar con los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="caf45-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="caf45-105">**País/región**: basado en los códigos de país ISO</span><span class="sxs-lookup"><span data-stu-id="caf45-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="caf45-106">Tipos de **Etiquetas** para:</span><span class="sxs-lookup"><span data-stu-id="caf45-106">**Tags** types for:</span></span>
  - <span data-ttu-id="caf45-107">Área funcional</span><span class="sxs-lookup"><span data-stu-id="caf45-107">Functional area</span></span>
  - <span data-ttu-id="caf45-108">Área de características</span><span class="sxs-lookup"><span data-stu-id="caf45-108">Feature area</span></span>
  - <span data-ttu-id="caf45-109">Sector</span><span class="sxs-lookup"><span data-stu-id="caf45-109">Industry</span></span> 
  - <span data-ttu-id="caf45-110">Documento empresarial</span><span class="sxs-lookup"><span data-stu-id="caf45-110">Business document</span></span> 

<span data-ttu-id="caf45-111">Para facilitar el descubrimiento de configuraciones específicas o relacionadas, puede aplicar filtros, individualmente o en grupos.</span><span class="sxs-lookup"><span data-stu-id="caf45-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="caf45-112">Por ejemplo, para encontrar un solo tipo de "documentos comerciales configurables" que estén relacionados con las facturas de proveedores, puede aplicar un filtro de **Tipo de documento comercial** para buscar ese tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="caf45-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="caf45-113">[![Sección de filtro para el repositorio global](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="caf45-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="caf45-114">Puede refinar aún más la búsqueda seleccionando el tipo de documento, por ejemplo, "factura de proveedor" y haciendo clic en **Aplicar filtro**.</span><span class="sxs-lookup"><span data-stu-id="caf45-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="caf45-115">El siguiente ejemplo muestra los resultados al filtrar en **Tipo de documento comercial** con el tipo de documento agregado.</span><span class="sxs-lookup"><span data-stu-id="caf45-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="caf45-116">[![Filtro aplicado e importación para tipo de documento empresarial](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="caf45-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="caf45-117">Los resultados filtrados se pueden importar en un repositorio RCS de usuarios o en un entorno de Dynamics 365 Finance, ya sea individualmente o como un conjunto.</span><span class="sxs-lookup"><span data-stu-id="caf45-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="caf45-118">Para hacer esto, seleccione el grupo de configuraciones y haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="caf45-118">To do this, select the group of configurations, and click **Import**.</span></span>
