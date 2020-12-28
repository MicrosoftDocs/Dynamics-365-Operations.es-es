---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (16 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
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
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d5f2aea5fcc81d0b4c1d8a392a3e56c888440a94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462444"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-16-2018"></a><span data-ttu-id="4ff25-103">Novedades y cambios en Dynamics 365 Talent - Core HR (16 de octubre de 2018)</span><span class="sxs-lookup"><span data-stu-id="4ff25-103">What's new or changed in Dynamics 365 Talent - Core HR (October 16, 2018)</span></span>

<span data-ttu-id="4ff25-104">**Compilación 8.1.1067**</span><span class="sxs-lookup"><span data-stu-id="4ff25-104">**Build 8.1.1067**</span></span>

<span data-ttu-id="4ff25-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="4ff25-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-managers-to-update-time-off-requests"></a><span data-ttu-id="4ff25-106">Permitir que los administradores actualicen solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="4ff25-106">Allow managers to update time off requests</span></span>

<span data-ttu-id="4ff25-107">Las solicitudes de licencia de los empleados es posible que necesiten actualizarse después de que se aprueben con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4ff25-107">Employee time off requests may need to be updated after they are approved through the workflow.</span></span> <span data-ttu-id="4ff25-108">En muchos casos, el administrador se encarga de estas actualizaciones en nombre del empleado.</span><span class="sxs-lookup"><span data-stu-id="4ff25-108">In many cases, the manager makes these updates on the employee’s behalf.</span></span> <span data-ttu-id="4ff25-109">Esta nueva característica permite a los administradores actualizar las solicitudes de licencia o cancelarlas en nombre de sus empleados.</span><span class="sxs-lookup"><span data-stu-id="4ff25-109">This new feature provides the ability for managers to update time off or cancel time off requests on behalf of their employees.</span></span> <span data-ttu-id="4ff25-110">Esta capacidad se controla mediante el parámetro **Trabajo en nombre de** que se establece en la página **Parámetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="4ff25-110">This capability is controlled by the **Work on behalf** parameter that can be set on the **Human Resource Parameters** page.</span></span> 
 
## <a name="allow-hr-to-update-time-off-requests"></a><span data-ttu-id="4ff25-111">Permitir que HH. RR. actualice solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="4ff25-111">Allow HR to update time off requests</span></span>

<span data-ttu-id="4ff25-112">Similar a la función anterior, es posible que RR. HH. tenga que actualizar las solicitudes de licencia de los empleados después de que se hayan aprobado anteriormente con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4ff25-112">Similar to the feature above, employee time off requests may need to be updated by HR after they have been previously approved through the workflow.</span></span> <span data-ttu-id="4ff25-113">Esta característica proporciona la capacidad a los usuarios de RR. HH. de actualizar las solicitudes de licencia.</span><span class="sxs-lookup"><span data-stu-id="4ff25-113">This feature provides the ability for HR users to update time off requests.</span></span> <span data-ttu-id="4ff25-114">La capacidad se habilita en el área de trabajo **Personas** y en la página **Trabajador** , mediante una nueva opción denominada **Ver licencia**.</span><span class="sxs-lookup"><span data-stu-id="4ff25-114">The capability is enabled in the **People** workspace and on the **Worker** page, using a new option called **View time off**.</span></span> <span data-ttu-id="4ff25-115">En tales páginas, los usuarios de RR. HH. pueden ver solicitudes y actualizar las transacciones de licencia, igual a cómo los administradores pueden realizar estas acciones.</span><span class="sxs-lookup"><span data-stu-id="4ff25-115">On those pages, HR users can view requests and update time off transactions, similar to how managers can perform these actions.</span></span>

<span data-ttu-id="4ff25-116">El derecho de seguridad que controla el acceso a esta función es:</span><span class="sxs-lookup"><span data-stu-id="4ff25-116">The security duty that controls access to this functionality is:</span></span>
- <span data-ttu-id="4ff25-117">Derecho: Mantener procesos de bajas y ausencias específicos de trabajador.</span><span class="sxs-lookup"><span data-stu-id="4ff25-117">Duty: Maintain worker-specific leave and absence processes.</span></span>
- <span data-ttu-id="4ff25-118">Privilegio: Mantener solicitudes de baja y de ausencia para todos los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="4ff25-118">Privilege: Maintain leave and absence requests for all workers.</span></span>

## <a name="other-changes"></a><span data-ttu-id="4ff25-119">Otros cambios</span><span class="sxs-lookup"><span data-stu-id="4ff25-119">Other changes</span></span>
<span data-ttu-id="4ff25-120">Las actualizaciones siguientes se han creado en esta versión:</span><span class="sxs-lookup"><span data-stu-id="4ff25-120">The following updates have been made in this release:</span></span>
- <span data-ttu-id="4ff25-121">Cambios en las acciones de contratación del trabajador que ya no están "atascados" en el estado **Flujo de trabajo completado**.</span><span class="sxs-lookup"><span data-stu-id="4ff25-121">Changes to worker hire actions so that they are no longer "stuck" in **Workflow complete** state.</span></span>
- <span data-ttu-id="4ff25-122">Ahora se puede crear un registro de empleo sin una fecha de inicio del empleo.</span><span class="sxs-lookup"><span data-stu-id="4ff25-122">Employment record can now be created without an employment start date.</span></span>
- <span data-ttu-id="4ff25-123">Ahora la fecha del registro de Dynamics 365 Talent para un curso mostrado en autoservicio de empleados aplica la diferencia de zona horaria a la fecha.</span><span class="sxs-lookup"><span data-stu-id="4ff25-123">The Dynamics 365 Talent registration date for a course shown in Employee self-service now applies the time zone offset to the date.</span></span>
- <span data-ttu-id="4ff25-124">Los archivos Excel se pueden importar varias veces sin errores con **Entidad del empleado**.</span><span class="sxs-lookup"><span data-stu-id="4ff25-124">Excel files can be imported multiple times without any errors using **Employee Entity**.</span></span>

## <a name="known-issue"></a><span data-ttu-id="4ff25-125">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="4ff25-125">Known issue</span></span>

- <span data-ttu-id="4ff25-126">**Emisión**: Al agregar un nuevo archivo adjunto a un trabajador, los botones **Nuevo** y **Editar** se atenúan.</span><span class="sxs-lookup"><span data-stu-id="4ff25-126">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="4ff25-127">**Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos en la página **Trabajador** estén cerrados.</span><span class="sxs-lookup"><span data-stu-id="4ff25-127">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="4ff25-128">Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan.</span><span class="sxs-lookup"><span data-stu-id="4ff25-128">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="4ff25-129">(Este problema se corregirá en la siguiente actualización de la plataforma).</span><span class="sxs-lookup"><span data-stu-id="4ff25-129">(This issue will be fixed in the next platform update.)</span></span>
