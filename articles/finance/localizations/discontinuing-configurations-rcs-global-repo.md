---
title: Suspender configuraciones en el repositorio RCS Global
description: Este tema describe cómo interrumpir las configuraciones en el repositorio RCS Global.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 25ad0744e7c3320505c13c465d440b6a364da47c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840301"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="a8838-103">Suspender configuraciones en el repositorio RCS Global</span><span class="sxs-lookup"><span data-stu-id="a8838-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8838-104">Este tema describe cómo interrumpir la configuración en el repositorio RCS Global.</span><span class="sxs-lookup"><span data-stu-id="a8838-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="a8838-105">Anteriormente, solo era posible eliminar configuraciones que ya no eran necesarias.</span><span class="sxs-lookup"><span data-stu-id="a8838-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="a8838-106">Sin embargo, ahora puede marcar una configuración lanzada como **Interrumpida** en el repositorio RCS Global.</span><span class="sxs-lookup"><span data-stu-id="a8838-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="a8838-107">Con esta funcionalidad, también puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8838-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="a8838-108">Proporcione notificaciones anticipadas cuando se planea suspender una configuración.</span><span class="sxs-lookup"><span data-stu-id="a8838-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="a8838-109">Incluya detalles aplicables sobre la configuración de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="a8838-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="a8838-110">Establezca una fecha **Soportado hasta** para la configuración específica, para informar al usuario cuándo se suspenderá.</span><span class="sxs-lookup"><span data-stu-id="a8838-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="a8838-111">Cuando interrumpe una versión de configuración, puede especificar la siguiente información opcional:</span><span class="sxs-lookup"><span data-stu-id="a8838-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="a8838-112">**Configuración de la sustitución**</span><span class="sxs-lookup"><span data-stu-id="a8838-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="a8838-113">**Versión de configuración de reemplazo**</span><span class="sxs-lookup"><span data-stu-id="a8838-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="a8838-114">**Nota de texto libre**: utilice este campo para proporcionar enlaces de documentación o referencias</span><span class="sxs-lookup"><span data-stu-id="a8838-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="a8838-115">**Soportado hasta**: este campo proporciona la fecha propuesta hasta la cual se admitirá la configuración/versión actual.</span><span class="sxs-lookup"><span data-stu-id="a8838-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="a8838-116">Esta fecha debe actualizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="a8838-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="a8838-117">Para interrumpir la configuración, complete los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="a8838-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="a8838-118">Seleccione si desea interrumpir una sola versión o todas las versiones con la misma configuración en una operación, configurando **Todas las versiones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a8838-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="a8838-119">Seleccione el parámetro **Interrumpir** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a8838-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="a8838-120">Seleccione **Aceptar** para interrumpir las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a8838-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="a8838-121">El campo **Fecha de interrupción** se completará cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="a8838-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Interrumpir la información de configuración](media/Discontinue-details-2.png)
  
<span data-ttu-id="a8838-123">Puede revertir la configuración a **Compartido** o ajustar la información de interrupción en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a8838-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="a8838-124">Si comparte una configuración, especifique la fecha **Soportado hasta** y cualquier otra información relacionada con la interrupción para indicar sus planes para la interrupción futura.</span><span class="sxs-lookup"><span data-stu-id="a8838-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="a8838-125">Si desea compartir información sobre una interrupción planificada, antes de interrumpir realmente la configuración, el usuario puede completar previamente todos los campos relacionados con el reemplazo, pero dejar el parámetro **Interrumpir** establecido en **No**.</span><span class="sxs-lookup"><span data-stu-id="a8838-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="a8838-126">La interrupción no limita las operaciones con configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a8838-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="a8838-127">Puede continuar importando, ejecutando o derivando las configuraciones, estos campos son informativos.</span><span class="sxs-lookup"><span data-stu-id="a8838-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="a8838-128">Finance admite la visualización de esta información a partir de la versión 10.0.14</span><span class="sxs-lookup"><span data-stu-id="a8838-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="a8838-129">Dynamics 365 Finance admite la visualización de la información de interrupción, a partir de la versión 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="a8838-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="a8838-130">En la página **Repositorio global**, puede ver información actualizada relacionada con la interrupción.</span><span class="sxs-lookup"><span data-stu-id="a8838-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="a8838-131">De forma predeterminada, las configuraciones que están interrumpidas se filtran.</span><span class="sxs-lookup"><span data-stu-id="a8838-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="a8838-132">La página **Configuraciones importadas** (ERSolutionTable) muestra las configuraciones que ya estaban interrumpidas cuando se importaron.</span><span class="sxs-lookup"><span data-stu-id="a8838-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="a8838-133">Para aquellas configuraciones que fueron interrumpidas después de la importación, la información de interrupción se puede sincronizar ejecutando el trabajo **Importar actualizaciones de configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a8838-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


