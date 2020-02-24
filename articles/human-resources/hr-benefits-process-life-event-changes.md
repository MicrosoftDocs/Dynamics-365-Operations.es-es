---
title: Procesar cambios de eventos de vida
description: Procesar cambios de eventos de vida en Microsoft Dynamics 365 Human Resources para cambios en los eventos de la vida.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: f9bce9394a361bbecfcc0531c5d7ebe9302c8f11
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010479"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="f9ca1-103">Procesar cambios de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="f9ca1-103">Process life event changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="f9ca1-104">Procese cambios de eventos de vida en Microsoft Dynamics 365 Human Resources para dos cambios en los eventos de la vida:</span><span class="sxs-lookup"><span data-stu-id="f9ca1-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="f9ca1-105">Cambios de fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="f9ca1-105">Birthday changes</span></span>
- <span data-ttu-id="f9ca1-106">Cambios en la expiración de la anulación de la regla de idoneidad</span><span class="sxs-lookup"><span data-stu-id="f9ca1-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="f9ca1-107">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de cambios de eventos de vida**.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="f9ca1-108">En el cuadro de diálogo **Ejecutar proceso de cambio de evento de vida**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f9ca1-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="f9ca1-109">Campo</span><span class="sxs-lookup"><span data-stu-id="f9ca1-109">Field</span></span> | <span data-ttu-id="f9ca1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9ca1-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f9ca1-111">Período de inscripción</span><span class="sxs-lookup"><span data-stu-id="f9ca1-111">Enrollment period</span></span> | <span data-ttu-id="f9ca1-112">El periodo de inscripción para procesar cambios de evento de vida.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="f9ca1-113">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="f9ca1-113">Legal entity</span></span> | <span data-ttu-id="f9ca1-114">La entidad jurídica para procesar cambios de evento de vida.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="f9ca1-115">Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f9ca1-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="f9ca1-116">Escriba información para proceso.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="f9ca1-117">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="f9ca1-118">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="f9ca1-119">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-119">Select **OK**.</span></span> <span data-ttu-id="f9ca1-120">El proceso se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="f9ca1-121">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9ca1-121">Select **OK**.</span></span>
