---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (1 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
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
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f872b0907e0f48e0b734c87f0b8fb1a4cfe20cb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462418"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-1-2018"></a><span data-ttu-id="2df54-103">Novedades y cambios en Dynamics 365 Talent: Core HR (1 de octubre de 2018)</span><span class="sxs-lookup"><span data-stu-id="2df54-103">What's new or changed in Dynamics 365 Talent: Core HR (October 1, 2018)</span></span>

<span data-ttu-id="2df54-104">**Compilación 8.1.1035.0**</span><span class="sxs-lookup"><span data-stu-id="2df54-104">**Build 8.1.1035.0**</span></span>

<span data-ttu-id="2df54-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="2df54-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="turn-off-electronic-payment-validation"></a><span data-ttu-id="2df54-106">Desactiva la validación de pagos electrónicos</span><span class="sxs-lookup"><span data-stu-id="2df54-106">Turn off electronic payment validation</span></span>

<span data-ttu-id="2df54-107">La validación de la información de los pagos electrónicos se produce si se definen desembolsos para depósitos directos a través del espacio de trabajo **Autoservicio para empleados** (ESS) o directamente en el formulario del empleado.</span><span class="sxs-lookup"><span data-stu-id="2df54-107">Electronic payment information validation occurs if you set up disbursements for direct deposit either through **Employee self-service** workspace (ESS) or directly on the employee form.</span></span> <span data-ttu-id="2df54-108">Esta opción le da la flexibilidad para quitar esa validación si no necesita las comprobaciones de validación para los valores de importes y del importe restante.</span><span class="sxs-lookup"><span data-stu-id="2df54-108">This option gives you the flexibility to remove that validation if you do not require the validation checks for amounts and remainder values.</span></span> <span data-ttu-id="2df54-109">Esta función es útil si se está integrando con un sistema de nóminas externo con diferentes requisitos.</span><span class="sxs-lookup"><span data-stu-id="2df54-109">This feature is helpful if you're integrating with an external payroll system that has different requirements.</span></span>

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a><span data-ttu-id="2df54-110">Autoservicio de administrador - Agregar objetivos para los miembros del equipo a través del mosaico de objetivos de rendimiento de equipo</span><span class="sxs-lookup"><span data-stu-id="2df54-110">Manager self-service - Add goals for team members through the Team performance goals tile</span></span>

<span data-ttu-id="2df54-111">Antes de esta versión, los administradores podían agregar objetivos a sus empleados individualmente con los objetivos de rendimiento asociados a cada empleado.</span><span class="sxs-lookup"><span data-stu-id="2df54-111">Prior to this release, managers can add goals to their employees individually through the performance goals associated to each employee.</span></span> <span data-ttu-id="2df54-112">Con esta actualización, los administradores pueden tener acceso al mosaico **Objetivos de rendimiento de equipo** y crear nuevos objetivos seleccionando cualquiera de sus informes directos.</span><span class="sxs-lookup"><span data-stu-id="2df54-112">With this update, managers can access the **Team performance goals** tile and create new goals by selecting any of their direct reports.</span></span>

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a><span data-ttu-id="2df54-113">Autoservicio de administrador - Agregar revisiones para los miembros del equipo a través del mosaico de revisiones de rendimiento de equipo</span><span class="sxs-lookup"><span data-stu-id="2df54-113">Manager self-service - Add reviews for team members through the Team performance reviews tile</span></span>

<span data-ttu-id="2df54-114">Antes de esta versión, los administradores podían agregar revisiones a sus empleados individualmente con los objetivos de revisión asociados a cada empleado.</span><span class="sxs-lookup"><span data-stu-id="2df54-114">Prior to this release, managers can add reviews to their employees individually through the reviews associated to each employee.</span></span> <span data-ttu-id="2df54-115">Con esta actualización, los administradores pueden tener acceso al mosaico **Revisiones de rendimiento de equipo** y crear nuevas revisiones seleccionando cualquiera de sus informes directos.</span><span class="sxs-lookup"><span data-stu-id="2df54-115">With this update, managers can access the **Team performance reviews** tile and create new reviews by selecting any of their direct reports.</span></span>

## <a name="configure-proration-options-by-leave-plan"></a><span data-ttu-id="2df54-116">Configure las opciones de prorrateo en función el plan de licencia</span><span class="sxs-lookup"><span data-stu-id="2df54-116">Configure proration options by leave plan</span></span>

<span data-ttu-id="2df54-117">Las organizaciones conceden tiempo libre de manera diferente basándose en cuándo los empleados se unen y dejan la empresa.</span><span class="sxs-lookup"><span data-stu-id="2df54-117">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="2df54-118">Para algunas organizaciones, se concede a los empleados su asignación completa en su fecha de inicio mientras que otras prorratean la prima.</span><span class="sxs-lookup"><span data-stu-id="2df54-118">For some organizations, employees are awarded their full allocation on their start date while others prorate the award.</span></span> <span data-ttu-id="2df54-119">Las nuevas opciones se proporcionan en esta versión para elegir cómo prorratear las primas y las acumulaciones para los empleados que se unen o dejan una organización.</span><span class="sxs-lookup"><span data-stu-id="2df54-119">New options are provided in this release to choose how to prorate the awards and accruals for joiners and leavers in an organization.</span></span> <span data-ttu-id="2df54-120">Las opciones incluyen: Prorrateo, Acumulación completa y Ninguna acumulación.</span><span class="sxs-lookup"><span data-stu-id="2df54-120">Options include: Prorated, Full accrual, and No accrual.</span></span>

## <a name="other-changes"></a><span data-ttu-id="2df54-121">Otros cambios</span><span class="sxs-lookup"><span data-stu-id="2df54-121">Other changes</span></span>

-   <span data-ttu-id="2df54-122">Entidad de empleado actualizada - Ahora **Personal** se puede actualizar usando el complemento de Excel/administración de datos.</span><span class="sxs-lookup"><span data-stu-id="2df54-122">Employee entity updated - The **Personal** title can now be updated using the Excel add-in/data management.</span></span>

-   <span data-ttu-id="2df54-123">Cambio de seguridad para permitir la eliminación de los botones **Eliminar** y **Desactivar** en el autoservicio del empleado para la información de pagos.</span><span class="sxs-lookup"><span data-stu-id="2df54-123">Security change to allow removal of the **Delete** and **Deactivate** buttons in employee self-service for payment information.</span></span>

## <a name="known-issue"></a><span data-ttu-id="2df54-124">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="2df54-124">Known issue</span></span>

-   <span data-ttu-id="2df54-125">**Problema:** Al agregar nuevos archivos adjuntos a un trabajador, los botones **Nuevo** y **Editar** se atenúan. **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos de la página **Trabajador** estén cerrados.</span><span class="sxs-lookup"><span data-stu-id="2df54-125">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="2df54-126">Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones **Datos adjuntos** se habilitan.</span><span class="sxs-lookup"><span data-stu-id="2df54-126">If the FactBoxes are closed when the **Worker** page is loaded, the **Attachments** buttons will be enabled.</span></span> <span data-ttu-id="2df54-127">(Este problema se corregirá en la siguiente actualización de la plataforma).</span><span class="sxs-lookup"><span data-stu-id="2df54-127">(This issue will be fixed in the next platform update.)</span></span>
