---
title: Novedades y cambios en Dynamics 365 Talent (6 de mayo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f06d989ea4e927111729dfbd4bb7700745a16a54
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897520"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-6-2019"></a><span data-ttu-id="a5926-103">Novedades y cambios en Dynamics 365 Talent (6 de mayo de 2019)</span><span class="sxs-lookup"><span data-stu-id="a5926-103">What's new or changed in Dynamics 365 Talent (May 6, 2019)</span></span>

<span data-ttu-id="a5926-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="a5926-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="a5926-105">Cambios en Attract</span><span class="sxs-lookup"><span data-stu-id="a5926-105">Changes in Attract</span></span>

### <a name="select-optional-documents-upon-offer-creation"></a><span data-ttu-id="a5926-106">Seleccione documentos al crear la oferta</span><span class="sxs-lookup"><span data-stu-id="a5926-106">Select optional documents upon offer creation</span></span>

<span data-ttu-id="a5926-107">Al seleccionar una plantilla de paquete de la propuesta, ahora Attract le solicita para seleccionar los documentos opcionales, aplicables de esa plantilla de paquete.</span><span class="sxs-lookup"><span data-stu-id="a5926-107">When you select an offer package template, Attract now prompts you to select the applicable, optional documents from that package template.</span></span> <span data-ttu-id="a5926-108">Puede agregar otros documentos opcionales mientras prepara la propuesta.</span><span class="sxs-lookup"><span data-stu-id="a5926-108">You can add other optional documents while preparing the offer.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="a5926-109">Cambios en Onboard</span><span class="sxs-lookup"><span data-stu-id="a5926-109">Changes in Onboard</span></span>

<span data-ttu-id="a5926-110">Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="a5926-110">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="a5926-111">Cambios en Core HR</span><span class="sxs-lookup"><span data-stu-id="a5926-111">Changes in Core HR</span></span>

<span data-ttu-id="a5926-112">Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2282.</span><span class="sxs-lookup"><span data-stu-id="a5926-112">Changes described in this section apply to build number 8.1.2282.</span></span> <span data-ttu-id="a5926-113">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a5926-113">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="platform-update-26-for-finance-and-operations"></a><span data-ttu-id="a5926-114">Platform update 26 para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a5926-114">Platform update 26 for Finance and Operations</span></span>

<span data-ttu-id="a5926-115">Para obtener más información acerca de la Platform update 26 para Finance and Operations, consulte [Características de vista previa en Dynamics 365 Finance and Operations platform update 26 (mayo de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span><span class="sxs-lookup"><span data-stu-id="a5926-115">For additional details about Platform update 26 for Finance and Operations, see [Preview features in Dynamics 365 Finance and Operations platform update 26 (May 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span></span> 

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="a5926-116">Soporte de la entidad de Common Data Service para los campos personalizados</span><span class="sxs-lookup"><span data-stu-id="a5926-116">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="a5926-117">En la versión de esta semana, las entidades siguientes ahora admiten campos personalizados: Cálculo de frecuencia de prestación, Cálculo de tasa de prestación, Tipo de Prestación, calendario laboral, calendario festivo laboral, Ciclo de pago y tipos de identificación del trabajador.</span><span class="sxs-lookup"><span data-stu-id="a5926-117">In this week's release, the following entities now support custom fields: Benefit calc frequency, Benefit calc rate, Benefit type, Work calendar, Work calendar holiday, Pay cycle, and Worker identification types.</span></span>

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a><span data-ttu-id="a5926-118">Dejar inscripción masiva, cambiar la función del nivel “Fecha de antigüedad” no actualiza la tasa de inicio de la acumulación (318526)</span><span class="sxs-lookup"><span data-stu-id="a5926-118">Leave mass enrollment, changing the tier basis to "Seniority date" doesn't refresh the initial accrual rate (318526)</span></span>

<span data-ttu-id="a5926-119">Al inscribir en masa a empleados y cambiar la función del nivel, la acumulación inicial ahora refleja la base del nivel seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a5926-119">When you mass enroll employees and change the tier basis, the initial accrual now reflects the tier basis that you selected.</span></span>

### <a name="workflow-showing-duplicate-place-holders-313636"></a><span data-ttu-id="a5926-120">El flujo de trabajo muestra marcadores de posición duplicados (313636)</span><span class="sxs-lookup"><span data-stu-id="a5926-120">Workflow showing duplicate place holders (313636)</span></span>

<span data-ttu-id="a5926-121">Los cambios en esta versión eliminan la duplicación de marcadores de duplicación cuando se envían las notificaciones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5926-121">Changes in this release eliminate duplication of placeholders when workflow notifications are sent.</span></span>

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a><span data-ttu-id="a5926-122">Los campos de dimensiones no se actualizan al utilizar “Abrir en Excel” (176261)</span><span class="sxs-lookup"><span data-stu-id="a5926-122">Dimension fields aren't updated when using "Open in Excel" (176261)</span></span>

<span data-ttu-id="a5926-123">Con esta versión, ahora puede actualizar la dimensión financiera usando **Abrir en Excel** de la página **Trabajador** .</span><span class="sxs-lookup"><span data-stu-id="a5926-123">With this release, you can now update financial dimension using **Open in Excel** from the **Worker** page.</span></span> 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a><span data-ttu-id="a5926-124">La dirección del trabajador creada en Common Data Service no se sincroniza con Talent (317555)</span><span class="sxs-lookup"><span data-stu-id="a5926-124">Worker address created in Common Data Service isn't synced to Talent (317555)</span></span>

<span data-ttu-id="a5926-125">Con este cambio, las direcciones creadas en Common Data Service se actualizan en Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="a5926-125">With this change, addresses created in Common Data Service are updated in Talent: Core HR.</span></span>


## <a name="in-preview"></a><span data-ttu-id="a5926-126">En vista previa</span><span class="sxs-lookup"><span data-stu-id="a5926-126">In preview</span></span>

### <a name="new-page-to-validate-position-hierarchy-data"></a><span data-ttu-id="a5926-127">Nueva página para validar datos de la jerarquía de puestos</span><span class="sxs-lookup"><span data-stu-id="a5926-127">New page to validate position hierarchy data</span></span>

<span data-ttu-id="a5926-128">Los recursos humanos (HR) y los administradores ahora pueden validar la jerarquía directiva para cualquier referencia circular que podría haber sido importada de forma inadvertida.</span><span class="sxs-lookup"><span data-stu-id="a5926-128">Human resources (HR) and administrators can now validate the managerial hierarchy for any circular references that might have inadvertently been imported.</span></span> <span data-ttu-id="a5926-129">Puede obtener acceso a esta nueva página desde **Administración de organización > Vínculos > Puestos > Validación de la jerarquía de puestos**.</span><span class="sxs-lookup"><span data-stu-id="a5926-129">You can access this new page from **Organizational administration > Links > Positions > Position hierarchy validation**.</span></span>

### <a name="specify-reason-codes-on-leave-types"></a><span data-ttu-id="a5926-130">Especificar códigos de motivo en tipos de baja</span><span class="sxs-lookup"><span data-stu-id="a5926-130">Specify reason codes on leave types</span></span>

<span data-ttu-id="a5926-131">Las organizaciones pueden requerir información adicional sobre las solicitudes de indisponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a5926-131">Organizations might require additional information about time-off requests.</span></span> <span data-ttu-id="a5926-132">Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a5926-132">You can now specify reason codes for leave types and let employees select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a><span data-ttu-id="a5926-133">Requerir códigos de motivo para tipos de baja específicos y solicitudes de indisponibilidad</span><span class="sxs-lookup"><span data-stu-id="a5926-133">Require reason codes for specific leave types on time-off requests</span></span>

<span data-ttu-id="a5926-134">Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados envíen solicitudes de indisponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a5926-134">Organizations might require reason codes for specific leave types when employees submit time-off requests.</span></span> <span data-ttu-id="a5926-135">Este requisito podría existir debido a la directiva de la empresa o normas legales.</span><span class="sxs-lookup"><span data-stu-id="a5926-135">This requirement might exist because of company policy or regulatory requirements.</span></span> <span data-ttu-id="a5926-136">Ahora puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a5926-136">You can now specify which leave types require a reason code, and you can require that employees provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="a5926-137">Proporcionar una lista de baja y la transacción de ausencia para recursos humanos</span><span class="sxs-lookup"><span data-stu-id="a5926-137">Provide a leave and absence transaction list for HR</span></span>

<span data-ttu-id="a5926-138">La capacidad de seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos (RR.HH) a contestar las preguntas del empleado, también ayuda a garantizar proporcionar el tiempo de indisponibilidad preciso a los empleados.</span><span class="sxs-lookup"><span data-stu-id="a5926-138">The ability to track employee time off and understand how time off is calculated not only helps HR answer employee questions, but also helps ensure accurate time-off awards for employees.</span></span> <span data-ttu-id="a5926-139">Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para que el personal de RR.HH. pueda ver las razones detrás de los saldos.</span><span class="sxs-lookup"><span data-stu-id="a5926-139">HR now has a new view into the transactions (grants, accruals, adjustments, and requests), so that HR staff can view the reasons behind balances.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a5926-140">Próximamente</span><span class="sxs-lookup"><span data-stu-id="a5926-140">Coming soon</span></span>

### <a name="indicate-instance-type-when-provisioning-talent"></a><span data-ttu-id="a5926-141">Indicar el tipo de instancia al aprovisionar Talent</span><span class="sxs-lookup"><span data-stu-id="a5926-141">Indicate instance type when provisioning Talent</span></span>

<span data-ttu-id="a5926-142">Al aprovisionar una nueva instancia de Talent, podrá indicar si el tipo de instancia es **Producción** o **Espacio aislado**, permitiendo la prueba temprana de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="a5926-142">When provisioning a new instance of Talent, you will be able to indicate whether the instance type is **Production** or **Sandbox**, allowing for early testing of new features.</span></span> <span data-ttu-id="a5926-143">Todas las instancias existentes de Talent se actualizarán el tipo de instancia de la producción.</span><span class="sxs-lookup"><span data-stu-id="a5926-143">All existing Talent instances will be updated to the Production instance type.</span></span> <span data-ttu-id="a5926-144">Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="a5926-144">If you want one of your existing instances to be updated to the Sandbox instance type, please contact Support to initiate the change request.</span></span>
