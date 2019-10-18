---
title: Novedades y cambios en Dynamics 365 Talent (31 de enero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6dcdb37ba7a423e54a641c1d123f563a59648d46
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010323"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a><span data-ttu-id="971c5-103">Novedades y cambios en Dynamics 365 Talent (31 de enero de 2019)</span><span class="sxs-lookup"><span data-stu-id="971c5-103">What's new or changed in Dynamics 365 Talent (January 31, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="971c5-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="971c5-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

<span data-ttu-id="971c5-105">**Compilación 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="971c5-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="971c5-106">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="971c5-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="971c5-107">El tiempo de licencia tomado en la tarjeta de las personas de la licencia no tiene en cuenta las fechas del plan de la licencia</span><span class="sxs-lookup"><span data-stu-id="971c5-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="971c5-108">Para aquellas personas que tienen planes de licencia que no se ejecuten en un año natural, ahora la una tarjeta **Procedente** muestra el tiempo de licencia que se ha tomado en el año de licencia definido en el plan.</span><span class="sxs-lookup"><span data-stu-id="971c5-108">For those that have leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="971c5-109">Por ejemplo, si el año de la licencia de una organización está incluido entre el 1 de junio y el 30 de mayo y un empleado ha tomado 3 días libres en diciembre, la tarjeta **Procedente** mostrará 3 días el 15 de enero.</span><span class="sxs-lookup"><span data-stu-id="971c5-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken 3 days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="971c5-110">Los importes de acumulación no coinciden con la base de fecha del nivel</span><span class="sxs-lookup"><span data-stu-id="971c5-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="971c5-111">Se han agregado nuevas opciones para licencias y ausencias (parámetros**Recursos humanos**) para habilitar a los clientes para que determinen cuándo los meses de servicio de los empleados entran en vigor.</span><span class="sxs-lookup"><span data-stu-id="971c5-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="971c5-112">Para algunas organizaciones, la fecha es el final del mes, pero para otros puede ser el inicio del mes siguiente.</span><span class="sxs-lookup"><span data-stu-id="971c5-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="971c5-113">Por ejemplo, una organización puede conceder tiempo libre el 31 de diciembre, mientras que otra puede concederlo el 1 de enero.</span><span class="sxs-lookup"><span data-stu-id="971c5-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="971c5-114">Esta opción le permitirá decidir cuando debe realizarse la concesión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="971c5-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="971c5-115">Las acciones de contratación del trabajador se bloquean en el estado “flujo de trabajo completo”</span><span class="sxs-lookup"><span data-stu-id="971c5-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="971c5-116">Se han realizado cambios para corregir un problema en el que una pequeña cantidad de flujos de trabajo terminaban con un estado “flujo de trabajo completo”.</span><span class="sxs-lookup"><span data-stu-id="971c5-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="971c5-117">Los nuevos flujos de trabajo ahora pasan al estado “completado” cuando finaliza del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="971c5-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="971c5-118">Cualquier flujo de trabajo que tenga un estado completado del flujo de trabajo se pasará al estado de error para permitir su actualización o eliminación si procede.</span><span class="sxs-lookup"><span data-stu-id="971c5-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
