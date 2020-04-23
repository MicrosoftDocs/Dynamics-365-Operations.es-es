---
title: Procesar tasas de cambios
description: Procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources cuando un plan de prestaciones nuevo o existente tiene un cambio en la configuración de las reglas de idoneidad.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 850709480326f6a0871f19ea1bb287631cd58b42
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229956"
---
# <a name="process-rate-changes"></a><span data-ttu-id="e6df2-103">Procesar tasas de cambios</span><span class="sxs-lookup"><span data-stu-id="e6df2-103">Process rate changes</span></span>

<span data-ttu-id="e6df2-104">Procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources cuando un plan de prestaciones nuevo o existente tiene un cambio en la configuración de las reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="e6df2-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="e6df2-105">Si se crea una nueva regla de idoneidad y se asigna al plan, esto lleva al sistema a volver a ejecutar la idoneidad de los trabajadores para verificar si los trabajadores ahora son idóneos para el plan en función de las nuevas opciones de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="e6df2-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to rerun worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="e6df2-106">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de actualización de tasas de cambios**.</span><span class="sxs-lookup"><span data-stu-id="e6df2-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="e6df2-107">En el cuadro de diálogo **Ejecutar proceso de actualización de tasas de cambios**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e6df2-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="e6df2-108">Campo</span><span class="sxs-lookup"><span data-stu-id="e6df2-108">Field</span></span> | <span data-ttu-id="e6df2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6df2-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e6df2-110">**Período de inscripción**</span><span class="sxs-lookup"><span data-stu-id="e6df2-110">**Enrollment period**</span></span> | <span data-ttu-id="e6df2-111">El periodo de inscripción para procesar tasas de cambios.</span><span class="sxs-lookup"><span data-stu-id="e6df2-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="e6df2-112">Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e6df2-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="e6df2-113">Escriba información para proceso.</span><span class="sxs-lookup"><span data-stu-id="e6df2-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="e6df2-114">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6df2-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="e6df2-115">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6df2-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="e6df2-116">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6df2-116">Select **OK**.</span></span> <span data-ttu-id="e6df2-117">El proceso se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="e6df2-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="e6df2-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6df2-118">Select **OK**.</span></span>
