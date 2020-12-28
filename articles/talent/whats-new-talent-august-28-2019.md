---
title: Novedades y cambios en Dynamics 365 for Talent (27 de agosto de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8965636e539345be5ef0ad591f7017938efd322d
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529813"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a><span data-ttu-id="e37ee-103">Novedades y cambios en Dynamics 365 for Talent (27 de agosto de 2019)</span><span class="sxs-lookup"><span data-stu-id="e37ee-103">What's new or changed in Dynamics 365 for Talent (August 27, 2019)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e37ee-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="e37ee-104">This topic describes features that are either new or changed in Dynamics 365 for Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="e37ee-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="e37ee-105">Changes in Attract</span></span>

<span data-ttu-id="e37ee-106">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="e37ee-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="e37ee-107">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="e37ee-107">Changes in Onboard</span></span>

<span data-ttu-id="e37ee-108">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="e37ee-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="e37ee-109">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="e37ee-109">Changes in Core HR</span></span>

<span data-ttu-id="e37ee-110">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2447.</span><span class="sxs-lookup"><span data-stu-id="e37ee-110">Changes described in this section apply to build number 8.1.2447.</span></span> <span data-ttu-id="e37ee-111">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e37ee-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a><span data-ttu-id="e37ee-112">Las características de la vista previa solo están habilitado en instancias de espacio aislado</span><span class="sxs-lookup"><span data-stu-id="e37ee-112">Preview features are enabled only in sandbox instances</span></span>

<span data-ttu-id="e37ee-113">Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es Producción o Espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="e37ee-113">When you provision a new instance of Talent, you can specify whether the instance type is Production or Sandbox.</span></span> <span data-ttu-id="e37ee-114">Las instancias del tipo Espacio aislado permiten la prueba temprana de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="e37ee-114">Instances of the Sandbox type allow for early testing of new features.</span></span> <span data-ttu-id="e37ee-115">Todas las instancias existentes de Talent se actualizarán el tipo de instancia de Producción.</span><span class="sxs-lookup"><span data-stu-id="e37ee-115">All existing Talent instances will be updated to the Production instance type.</span></span> <span data-ttu-id="e37ee-116">Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="e37ee-116">If you want one of your existing instances to be updated to the Sandbox instance type, contact Support to initiate the change request.</span></span>

<span data-ttu-id="e37ee-117">Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](./provisioning-talent.md).</span><span class="sxs-lookup"><span data-stu-id="e37ee-117">For more information about how changes are published, see [Provision Talent](./provisioning-talent.md).</span></span>

### <a name="view-extended-information-for-performance-in-manager-self-service"></a><span data-ttu-id="e37ee-118">Ver información ampliada para el rendimiento en autoservicio para directores</span><span class="sxs-lookup"><span data-stu-id="e37ee-118">View extended information for performance in manager self-service</span></span>

<span data-ttu-id="e37ee-119">Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados.</span><span class="sxs-lookup"><span data-stu-id="e37ee-119">A new option will let managers view the performance of both their direct reports and their extended reports.</span></span> <span data-ttu-id="e37ee-120">Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones.</span><span class="sxs-lookup"><span data-stu-id="e37ee-120">Currently, line managers can assign and update performance goals and issue new reviews.</span></span> <span data-ttu-id="e37ee-121">Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente.</span><span class="sxs-lookup"><span data-stu-id="e37ee-121">In addition, direct managers and their employees can maintain and update performance journals to help ensure that the performance review process goes smoothly.</span></span> <span data-ttu-id="e37ee-122">Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos.</span><span class="sxs-lookup"><span data-stu-id="e37ee-122">When this change is implemented, managers will be able to view and maintain performance-related information for their extended reports in addition to their direct reports.</span></span>

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a><span data-ttu-id="e37ee-123">Eliminar entidades jurídicas no se permite si existen empleados dentro de la empresa (339849)</span><span class="sxs-lookup"><span data-stu-id="e37ee-123">Deleting legal entities isn't allowed if employees exist within the company (339849)</span></span>

<span data-ttu-id="e37ee-124">Con este cambio, no podrá quitar o eliminar empresas si existen empleados y otros datos relacionados para la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="e37ee-124">With this change, you can't remove or delete companies if employees and other related data exist for the legal entity.</span></span>

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a><span data-ttu-id="e37ee-125">Los análisis de inteligencia empresarial de la gestión de compensación no coinciden en el espacio de trabajo de la compensación (322493)</span><span class="sxs-lookup"><span data-stu-id="e37ee-125">Compensation management business intelligence analytics don't match on the compensation workspace (322493)</span></span>

<span data-ttu-id="e37ee-126">En esta versión, los análisis de compensación se han ajustado para reflejar de forma precisa los planes asignados a los empleados.</span><span class="sxs-lookup"><span data-stu-id="e37ee-126">In this release, compensation analytics have been adjusted to accurately reflect the plans assigned to employees.</span></span>

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a><span data-ttu-id="e37ee-127">El marcador de posición del flujo de trabajo %company% muestra DAT cuando se contratan empleados con el flujo de trabajo (343905)</span><span class="sxs-lookup"><span data-stu-id="e37ee-127">Workflow placeholder %company% displays DAT when hiring employees through workflow (343905)</span></span>

<span data-ttu-id="e37ee-128">Con esta versión, el marcador de posición de la la empresa presenta la entidad jurídica asociada al empleo del nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="e37ee-128">With this release, the company placeholder displays the legal entity that is associated with the employment of the new employee.</span></span>

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a><span data-ttu-id="e37ee-129">La entidad CDSJobPosition muestra un error cuando la está configurada la validez hasta la fecha (349387)</span><span class="sxs-lookup"><span data-stu-id="e37ee-129">The CDSJobPosition entity displays an error when valid to date is set (349387)</span></span>

<span data-ttu-id="e37ee-130">En esta versión, los orígenes de datos **Detalle del puesto** y **Duración del puesto** en la entidad **CDSJobPosition** permiten ediciones de Common Data Service en los campos **Fecha efectiva**.</span><span class="sxs-lookup"><span data-stu-id="e37ee-130">In this release, the **Position detail** and the **Position duration** data sources on the **CDSJobPosition** entity allow for edits from Common Data Service to the **Date effective** fields.</span></span> 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a><span data-ttu-id="e37ee-131">Para el cese del empleado, el último día trabajado se rellena en la fecha de finalización de asignación (332496)</span><span class="sxs-lookup"><span data-stu-id="e37ee-131">For employee termination, the last day worked is populated on Assignment end date (332496)</span></span>

<span data-ttu-id="e37ee-132">En este cambio ahora la **Fecha final de la asignación** del puesto toma como valor predeterminado **Fecha final del empleo**.</span><span class="sxs-lookup"><span data-stu-id="e37ee-132">This change now defaults the position **Assignment end date** to the **Employment end date**.</span></span> <span data-ttu-id="e37ee-133">Puede cambiar estos valores predeterminados a medida que especifica datos.</span><span class="sxs-lookup"><span data-stu-id="e37ee-133">You can change these defaults while entering data.</span></span>

### <a name="legal-entities-arent-limited-with-hire-338871"></a><span data-ttu-id="e37ee-134">Las entidades jurídicas no están limitadas en la contratación (338871)</span><span class="sxs-lookup"><span data-stu-id="e37ee-134">Legal entities aren't limited with hire (338871)</span></span>
 
<span data-ttu-id="e37ee-135">Este cambio limita el proceso de contratación para mostrar sólo las entidades jurídicas a las que el usuario tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="e37ee-135">This change restricts the hiring process to only show those legal entities the user has access to.</span></span>  

## <a name="in-preview"></a><span data-ttu-id="e37ee-136">En vista previa</span><span class="sxs-lookup"><span data-stu-id="e37ee-136">In preview</span></span>

### <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="e37ee-137">Entrada y navegación de empleados optimizadas</span><span class="sxs-lookup"><span data-stu-id="e37ee-137">Streamlined employee entry and navigation</span></span>

<span data-ttu-id="e37ee-138">Esta funcionalidad ya está disponible en los entornos de espacio aislado y prueba.</span><span class="sxs-lookup"><span data-stu-id="e37ee-138">This functionality is now available in sandbox and trial environments.</span></span> <span data-ttu-id="e37ee-139">Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="e37ee-139">To turn this feature on, navigate to **System administration > Links > Setup > System parameters > Preview features**.</span></span> <span data-ttu-id="e37ee-140">Seleccione **Formulario y navegación de trabajador mejorado**.</span><span class="sxs-lookup"><span data-stu-id="e37ee-140">Select **Enhanced worker form and navigation**.</span></span> <span data-ttu-id="e37ee-141">Esto habilita estos cambios para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e37ee-141">This enables these changes for all users.</span></span> <span data-ttu-id="e37ee-142">Puede desactivar esta opción en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e37ee-142">You can turn this option off at any time.</span></span>

<span data-ttu-id="e37ee-143">Para obtener más información, consulte [Entrada y navegación de empleados optimizadas](./streamlined-employee-entry.md).</span><span class="sxs-lookup"><span data-stu-id="e37ee-143">For more information, see [Streamlined employee entry and navigation](./streamlined-employee-entry.md).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="e37ee-144">Próximamente</span><span class="sxs-lookup"><span data-stu-id="e37ee-144">Coming soon</span></span>

### <a name="platform-update-29"></a><span data-ttu-id="e37ee-145">Actualización 29 de la plataforma</span><span class="sxs-lookup"><span data-stu-id="e37ee-145">Platform update 29</span></span>

<span data-ttu-id="e37ee-146">Para obtener más información acerca de la Platform update 29, consulte [Características de vista previa en Dynamics 365 for Finance and Operations platform update 29 (octubre de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).</span><span class="sxs-lookup"><span data-stu-id="e37ee-146">For more details about Platform update 29, see [Preview features in Dynamics 365 for Finance and Operations platform update 29 (October 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).</span></span>
