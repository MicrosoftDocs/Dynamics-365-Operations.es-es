---
title: Eliminar una estimación del proyecto
description: Este tema proporciona información sobre cómo eliminar una estimación del proyecto una vez completa.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410262"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="65fc6-103">Eliminar una estimación del proyecto</span><span class="sxs-lookup"><span data-stu-id="65fc6-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65fc6-104">Las estimaciones del proyecto proporcionan la visión financiera para el trabajo que se estima y programa para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="65fc6-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="65fc6-105">Para trabajar con estimaciones para un proyecto, es necesario adjuntar el proyecto a un proyecto de estimación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="65fc6-106">Un proyecto de estimación se basa siempre en un proyecto existente, pero varios proyectos pueden hacer referencia a un único proyecto de estimación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="65fc6-107">Solo se pueden adjuntar proyectos de precio fijo e inversión a los proyectos estimados, y esos proyectos deben pertenecer al mismo grupo de proyectos que el proyecto estimado.</span><span class="sxs-lookup"><span data-stu-id="65fc6-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="65fc6-108">Para eliminar un proyecto de estimación, debe estar completado.</span><span class="sxs-lookup"><span data-stu-id="65fc6-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="65fc6-109">Los siguientes pasos explican cómo eliminar una estimación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="65fc6-110">Vaya a **Gestión de proyectos y contabilidad** > **Todos los proyectos** y abra el proyecto.</span><span class="sxs-lookup"><span data-stu-id="65fc6-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="65fc6-111">En la pestaña **Gestionar**, seleccione **Estimados** y, en la página **Estimar**, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="65fc6-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="65fc6-112">En la página **Eliminar estimación** de la pestaña **General**, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="65fc6-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="65fc6-113">**Código de periodo**: seleccione el código de período para elegir los proyectos de estimación apropiados.</span><span class="sxs-lookup"><span data-stu-id="65fc6-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="65fc6-114">**Fecha de estimación**: seleccione la fecha de estimación apropiada para la eliminación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="65fc6-115">**Eliminar con advertencias WIP**: habilite esta opción para proporcionar notificaciones cuando se elimine una estimación asociada con un trabajo en curso (WIP).</span><span class="sxs-lookup"><span data-stu-id="65fc6-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="65fc6-116">Cuando esta opción no está habilitada, la eliminación no puede continuar cuando existan transacciones no estimadas.</span><span class="sxs-lookup"><span data-stu-id="65fc6-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="65fc6-117">Esta opción solo está disponible si la eliminación se aplica a un proyecto de estimación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="65fc6-118">No está disponible si se usan registros periódicos.</span><span class="sxs-lookup"><span data-stu-id="65fc6-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="65fc6-119">Esta configuración funciona con la configuración de la pestaña **Estimar** de la página **Parámetros del proyecto**, en el grupo de campos **Permitir eliminación cuando existan transacciones no estimadas**.</span><span class="sxs-lookup"><span data-stu-id="65fc6-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="65fc6-120">**Establecer etapa en Terminado**: habilite esta opción para establecer la etapa estimada del proyecto en **Terminado** después de ejecutar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="65fc6-121">**Imprimir lista de estimaciones**: seleccione la información que se incluirá cuando se imprima la lista de estimaciones.</span><span class="sxs-lookup"><span data-stu-id="65fc6-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="65fc6-122">**Mostrar registro de información**: habilite esta opción para mostrar el registro de información.</span><span class="sxs-lookup"><span data-stu-id="65fc6-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="65fc6-123">**Fecha de publicación**: elija la fecha de contabilización en el libro mayor de la estimación.</span><span class="sxs-lookup"><span data-stu-id="65fc6-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="65fc6-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65fc6-124">Select **OK**.</span></span>
5. <span data-ttu-id="65fc6-125">Una vez que se completa el proceso de eliminación, el proyecto de estimación eliminado se muestra con un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="65fc6-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="65fc6-126">Si no tenía la intención de eliminar una estimación, puede seleccionar la estimación eliminada y seleccionar **Invertir eliminación**.</span><span class="sxs-lookup"><span data-stu-id="65fc6-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
