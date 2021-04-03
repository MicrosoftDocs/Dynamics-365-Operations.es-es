---
title: Configurar eventos de vida futuros
description: Puede programar eventos de vida futuros en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d390bf2e9b25c50e913967ea51fcfadd4a1120b8
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464359"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="7e574-103">Configurar eventos de vida futuros</span><span class="sxs-lookup"><span data-stu-id="7e574-103">Configure future life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7e574-104">Puede programar eventos de vida futuros en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e574-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="7e574-105">En el espacio de trabajo de **Administración de prestaciones**, en **Configuración**, seleccione **Eventos de vida futuros**.</span><span class="sxs-lookup"><span data-stu-id="7e574-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="7e574-106">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7e574-106">Select **New**.</span></span>

3. <span data-ttu-id="7e574-107">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7e574-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7e574-108">Campo</span><span class="sxs-lookup"><span data-stu-id="7e574-108">Field</span></span> | <span data-ttu-id="7e574-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e574-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7e574-110">Fecha de evento de vida</span><span class="sxs-lookup"><span data-stu-id="7e574-110">Life event date</span></span> | <span data-ttu-id="7e574-111">El sistema procesa todos los eventos durante el periodo de inscripción que ocurren hasta esta fecha.</span><span class="sxs-lookup"><span data-stu-id="7e574-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="7e574-112">Evento de vida registrado</span><span class="sxs-lookup"><span data-stu-id="7e574-112">Life event logged</span></span> | <span data-ttu-id="7e574-113">Se registra la fecha y la hora del evento de vida.</span><span class="sxs-lookup"><span data-stu-id="7e574-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="7e574-114">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="7e574-114">Log type</span></span> | <span data-ttu-id="7e574-115">Muestra si la acción es una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e574-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="7e574-116">- **Actualizar**: un cambio en un registro existente que sigue eventos de vida</span><span class="sxs-lookup"><span data-stu-id="7e574-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="7e574-117">- **Insertar**: la creación de un nuevo registro de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="7e574-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="7e574-118">Identificador del tipo de evento de vida</span><span class="sxs-lookup"><span data-stu-id="7e574-118">Life event type ID</span></span> | <span data-ttu-id="7e574-119">El identificador único del tipo de evento de vida.</span><span class="sxs-lookup"><span data-stu-id="7e574-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="7e574-120">Tipo de evento de vida</span><span class="sxs-lookup"><span data-stu-id="7e574-120">Life event type</span></span> | <span data-ttu-id="7e574-121">Un catalizador para actualizar la inscripción de prestaciones de un empleado.</span><span class="sxs-lookup"><span data-stu-id="7e574-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="7e574-122">Para obtener más detalles, consulte la sección de activadores de eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="7e574-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="7e574-123">Estado</span><span class="sxs-lookup"><span data-stu-id="7e574-123">Status</span></span> | <span data-ttu-id="7e574-124">Si se ha procesado el evento de vida o no.</span><span class="sxs-lookup"><span data-stu-id="7e574-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="7e574-125">Línea</span><span class="sxs-lookup"><span data-stu-id="7e574-125">Line</span></span> | <span data-ttu-id="7e574-126">El número de línea del evento de vida futuro.</span><span class="sxs-lookup"><span data-stu-id="7e574-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="7e574-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e574-127">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]