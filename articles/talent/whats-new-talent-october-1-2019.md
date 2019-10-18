---
title: Novedades y cambios en Dynamics 365 Talent (1 de octubre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 86d8ce59ea67f42bc6e3abea50788bd3bc085e33
ms.sourcegitcommit: 0dd8d0510214f92936a9dd214b404c5c8103587b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "2419347"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-01-2019"></a><span data-ttu-id="55798-103">Novedades y cambios en Dynamics 365 Talent (01 de octubre de 2019)</span><span class="sxs-lookup"><span data-stu-id="55798-103">What's new or changed in Dynamics 365 Talent (October 01, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="55798-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="55798-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="55798-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="55798-105">Changes in Attract</span></span>

<span data-ttu-id="55798-106">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="55798-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="55798-107">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="55798-107">Changes in Onboard</span></span>

<span data-ttu-id="55798-108">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="55798-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="55798-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="55798-109">Changes in Core HR</span></span>

<span data-ttu-id="55798-110">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2509.</span><span class="sxs-lookup"><span data-stu-id="55798-110">Changes described in this section apply to build number 8.1.2509.</span></span> <span data-ttu-id="55798-111">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="55798-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="55798-112">Entrada y navegación de empleados optimizadas</span><span class="sxs-lookup"><span data-stu-id="55798-112">Streamlined employee entry and navigation</span></span>

<span data-ttu-id="55798-113">Esta funcionalidad ya está disponible en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="55798-113">This functionality is now available in all environments.</span></span> <span data-ttu-id="55798-114">Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="55798-114">To turn this feature on, navigate to **System administration > Links > Setup > System parameters > Preview features**.</span></span> <span data-ttu-id="55798-115">Seleccione **Formulario y navegación de trabajador mejorado**.</span><span class="sxs-lookup"><span data-stu-id="55798-115">Select **Enhanced worker form and navigation**.</span></span> <span data-ttu-id="55798-116">Esto habilita estos cambios para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55798-116">This enables these changes for all users.</span></span> <span data-ttu-id="55798-117">Puede desactivar esta opción en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="55798-117">You can turn this option off at any time.</span></span>

<span data-ttu-id="55798-118">Para obtener más información, consulte [Entrada y navegación de empleados optimizadas](./streamlined-employee-entry.md).</span><span class="sxs-lookup"><span data-stu-id="55798-118">For more information, see [Streamlined employee entry and navigation](./streamlined-employee-entry.md).</span></span> <span data-ttu-id="55798-119">Para ver un vídeo de estos cambios, consulte [Dynamics 365 for Talent 2019 resumen general de liberar oleada 2](https://aka.ms/ROGT19RW2ROV).</span><span class="sxs-lookup"><span data-stu-id="55798-119">To watch a video of these changes, see [Dynamics 365 for Talent 2019 release wave 2 overview](https://aka.ms/ROGT19RW2ROV).</span></span>

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a><span data-ttu-id="55798-120">Puede habilitar las características de vista previa en los entornos tanto de prueba como de entorno cerrado</span><span class="sxs-lookup"><span data-stu-id="55798-120">You can enable preview features in Sandbox and Trial environments</span></span>

<span data-ttu-id="55798-121">Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es Producción o Espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="55798-121">When you provision a new instance of Talent, you can specify whether the instance type is Production or Sandbox.</span></span> <span data-ttu-id="55798-122">Las instancias del tipo Espacio aislado permiten la prueba temprana de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="55798-122">Instances of the Sandbox type allow for early trial of new features.</span></span> <span data-ttu-id="55798-123">Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="55798-123">If you want one of your existing instances to be updated to the Sandbox instance type, contact Support to initiate the change request.</span></span>

<span data-ttu-id="55798-124">Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](./provisioning-talent.md).</span><span class="sxs-lookup"><span data-stu-id="55798-124">For more information about how changes are published, see [Provision Talent](./provisioning-talent.md).</span></span>

### <a name="compensation-date-defaults-to-a-different-date-than-the-position-assignment-337694"></a><span data-ttu-id="55798-125">La fecha de compensación se predetermina a una fecha distinta que la asignación de posición (337694)</span><span class="sxs-lookup"><span data-stu-id="55798-125">Compensation date defaults to a different date than the position assignment (337694)</span></span>

<span data-ttu-id="55798-126">Con este cambio la fecha inicial de compensación se predetermina a la fecha inicial de la posición de asignación.</span><span class="sxs-lookup"><span data-stu-id="55798-126">With this change, the compensation start date defaults to the position assignment start date.</span></span>

### <a name="not-able-to-end-compensation-along-with-its-position-assignment-328993"></a><span data-ttu-id="55798-127">No poder finalizar la compensación junto con su asignación de puesto (328993)</span><span class="sxs-lookup"><span data-stu-id="55798-127">Not able to end compensation along with its position assignment (328993)</span></span>

<span data-ttu-id="55798-128">Con este cambio, puede finalizar la compensación cuando termina la asignación de puesto usando **Finalizar asignaciónl** en la página **Asignaciones de puesto del trabajador** con acciones del personal activas.</span><span class="sxs-lookup"><span data-stu-id="55798-128">With this change, you can end compensation when you end the position assignment by using **End assignment** in the **Worker position assignments** page with personnel actions turned on.</span></span>

### <a name="bank-account-validation-requires-routing-and-account-numbers-in-all-locations-340403"></a><span data-ttu-id="55798-129">La validación de la cuenta bancaria requiere el enrutamiento y los números de cuenta en todas las ubicaciones (340403)</span><span class="sxs-lookup"><span data-stu-id="55798-129">Bank account validation requires routing and account numbers in all locations (340403)</span></span>

<span data-ttu-id="55798-130">Con los cambios de esta semana, se ha agregado una nueva opción de configuración para deshabilitar la validación requerida de **Número de ruta** y **Número de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="55798-130">With this week's changes, a new configuration option has been added to disable **Routing number** and **Account number** required validation.</span></span> 

### <a name="attachments-are-not-enabled-in-mss-performance-journals-for-performance-feedback-341794"></a><span data-ttu-id="55798-131">Los datos adjuntos no están habilitados en los diarios de rendimiento de MSS para realimentación de rendimiento (341794)</span><span class="sxs-lookup"><span data-stu-id="55798-131">Attachments are not enabled in MSS performance journals for performance feedback (341794)</span></span>

<span data-ttu-id="55798-132">Con la versión de esta semana, los datos adjuntos se habilitan para los artículos de realimentación en la página del diario de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="55798-132">With this week's release, attachments are enabled for feedback items in the performance journal page.</span></span>

### <a name="leave-request-details-dont-sync-from-common-data-service-to-talent-369608"></a><span data-ttu-id="55798-133">Los detalles de la solicitud de la licencia no se sincronizan de Common Data Service a Talent (369608)</span><span class="sxs-lookup"><span data-stu-id="55798-133">Leave request details don't sync from Common Data Service to Talent (369608)</span></span>

<span data-ttu-id="55798-134">Con estos cambios, los detalles de la solicitud de la licencia que se actualizan en Common Data Service sincronización de nuevo con Talent.</span><span class="sxs-lookup"><span data-stu-id="55798-134">With these changes, leave request details that are updated in Common Data Service will sync back to Talent.</span></span>

### <a name="job-description-doesnt-display-for-the-job-in-the-skill-gap-analysis-page-369398"></a><span data-ttu-id="55798-135">La descripción del trabajo no aparece para el trabajo en la página del análisis de lagunas de aptitudes (369398)</span><span class="sxs-lookup"><span data-stu-id="55798-135">Job description doesn't display for the job in the Skill gap analysis page (369398)</span></span>

<span data-ttu-id="55798-136">En la versión de esta semana, la descripción mostrará al seleccionar el trabajo en la página **Análisis de lagunas de aptitudes** .</span><span class="sxs-lookup"><span data-stu-id="55798-136">In this week's build, the description will display when selecting the job in the **Skill gap analysis** page.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="55798-137">Próximamente</span><span class="sxs-lookup"><span data-stu-id="55798-137">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="55798-138">Imprimir evaluaciones del rendimiento</span><span class="sxs-lookup"><span data-stu-id="55798-138">Print performance reviews</span></span>

<span data-ttu-id="55798-139">Los empleados, los administradores y profesionales de RR. HH. podrán imprimir la evaluación del rendimiento de un empleado.</span><span class="sxs-lookup"><span data-stu-id="55798-139">Employees, managers, and HR professionals will be able to print an employee's performance review.</span></span>
