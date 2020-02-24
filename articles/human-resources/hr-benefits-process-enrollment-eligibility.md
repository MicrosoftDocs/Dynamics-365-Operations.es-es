---
title: Proceso de idoneidad para inscripción
description: Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.
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
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010413"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="49a44-103">Proceso de idoneidad para inscripción</span><span class="sxs-lookup"><span data-stu-id="49a44-103">Process enrollment eligibility</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="49a44-104">Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="49a44-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="49a44-105">En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de idoneidad para inscripción**.</span><span class="sxs-lookup"><span data-stu-id="49a44-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="49a44-106">En el cuadro de diálogo **Ejecutar proceso de idoneidad para la inscripción en prestaciones**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="49a44-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="49a44-107">Campo</span><span class="sxs-lookup"><span data-stu-id="49a44-107">Field</span></span> | <span data-ttu-id="49a44-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="49a44-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="49a44-109">Período de inscripción</span><span class="sxs-lookup"><span data-stu-id="49a44-109">Enrollment period</span></span> | <span data-ttu-id="49a44-110">El periodo de inscripción para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="49a44-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="49a44-111">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="49a44-111">Legal entity</span></span> | <span data-ttu-id="49a44-112">La entidad jurídica para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="49a44-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="49a44-113">Trabajador</span><span class="sxs-lookup"><span data-stu-id="49a44-113">Worker</span></span> | <span data-ttu-id="49a44-114">El trabajador para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="49a44-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="49a44-115">Si deja este campo en blanco, la idoneidad de inscripción se procesará para todos los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="49a44-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="49a44-116">Plan de prestaciones</span><span class="sxs-lookup"><span data-stu-id="49a44-116">Benefit plan</span></span> | <span data-ttu-id="49a44-117">El plan de prestaciones para procesar la idoneidad de inscripción.</span><span class="sxs-lookup"><span data-stu-id="49a44-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="49a44-118">Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="49a44-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="49a44-119">Escriba información para proceso.</span><span class="sxs-lookup"><span data-stu-id="49a44-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="49a44-120">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49a44-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="49a44-121">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49a44-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="49a44-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49a44-122">Select **OK**.</span></span> <span data-ttu-id="49a44-123">El proceso se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="49a44-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="49a44-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49a44-124">Select **OK**.</span></span>
