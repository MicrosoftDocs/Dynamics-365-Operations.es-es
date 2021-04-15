---
title: Configurar parámetros de Human Resources
description: Este tema explica cómo configurar parámetros específicos de la empresa en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 74bdf891ffa7a9d875e23cf46aeee1dbaf86db48
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802416"
---
# <a name="configure-human-resources-parameters"></a><span data-ttu-id="56eb4-103">Configurar parámetros de Human Resources</span><span class="sxs-lookup"><span data-stu-id="56eb4-103">Configure Human resources parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="56eb4-104">La configuración de algunos parámetros de Recursos Humanos se comparten entre empresas, mientras que la configuración de otros parámetros son específicos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="56eb4-104">The settings of some Human resources parameters are shared across companies, while the settings of other parameters are company-specific.</span></span> <span data-ttu-id="56eb4-105">Este tema explica cómo configurar parámetros de recursos humanos específicos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="56eb4-105">This topic explains how to set up company-specific Human resources parameters.</span></span>

<span data-ttu-id="56eb4-106">Se usan dos páginas para definir los parámetros de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="56eb4-106">Two pages are used to set Human resources parameters.</span></span> <span data-ttu-id="56eb4-107">Para los parámetros que se comparten entre las empresas, se usa la página **Parámetros compartidos de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="56eb4-107">For parameters that are shared across companies, you use the **Human resources shared parameters** page.</span></span> <span data-ttu-id="56eb4-108">Para los parámetros que son específicos de la empresa (es decir, los ajustes se aplican a una sola empresa), se usa la página **Parámetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="56eb4-108">For parameters that are company-specific (in other words, the settings apply to a single company), you use the **Human resource parameters** page.</span></span>

![Ir a Parámetros de recursos humanos](./media/hr-employee-self-service-human-resources-parameters.png)

<span data-ttu-id="56eb4-110">En la página **Parámetros de recursos humanos**, los ajustes se dividen en seis pestañas:</span><span class="sxs-lookup"><span data-stu-id="56eb4-110">On the **Human resources parameters** page, the settings are divided among six tabs:</span></span>

- <span data-ttu-id="56eb4-111">**General**</span><span class="sxs-lookup"><span data-stu-id="56eb4-111">**General**</span></span>
- <span data-ttu-id="56eb4-112">**Contratación** (esta pestaña no se incluye en Dynamics 365 Human Resources)</span><span class="sxs-lookup"><span data-stu-id="56eb4-112">**Recruitment** (this tab isn't included in Dynamics 365 Human Resources)</span></span>
- <span data-ttu-id="56eb4-113">**Compensación**</span><span class="sxs-lookup"><span data-stu-id="56eb4-113">**Compensation**</span></span>
- <span data-ttu-id="56eb4-114">**Secuencias numéricas**</span><span class="sxs-lookup"><span data-stu-id="56eb4-114">**Number sequences**</span></span>
- <span data-ttu-id="56eb4-115">**FMLA (Ley de permiso por motivos familiares y médicos)**</span><span class="sxs-lookup"><span data-stu-id="56eb4-115">**FMLA**</span></span>
- <span data-ttu-id="56eb4-116">**Autoservicio para empleados**</span><span class="sxs-lookup"><span data-stu-id="56eb4-116">**Employee self service**</span></span>
- <span data-ttu-id="56eb4-117">**Autoservicio para directores**</span><span class="sxs-lookup"><span data-stu-id="56eb4-117">**Manager self service**</span></span>
- <span data-ttu-id="56eb4-118">**Administración de prestaciones**</span><span class="sxs-lookup"><span data-stu-id="56eb4-118">**Benefits management**</span></span>
- <span data-ttu-id="56eb4-119">**Bajas y ausencias**</span><span class="sxs-lookup"><span data-stu-id="56eb4-119">**Leave and absence**</span></span>
- <span data-ttu-id="56eb4-120">**Métodos de pago**</span><span class="sxs-lookup"><span data-stu-id="56eb4-120">**Payment methods**</span></span>

<span data-ttu-id="56eb4-121">Cada pestaña contiene información que pertenece a una sola empresa.</span><span class="sxs-lookup"><span data-stu-id="56eb4-121">Each tab contains information that pertains to a single company.</span></span>

## <a name="general"></a><span data-ttu-id="56eb4-122">General</span><span class="sxs-lookup"><span data-stu-id="56eb4-122">General</span></span>

<span data-ttu-id="56eb4-123">Los ajustes en la pestaña **General** definen el aspecto de la información acerca de ausencia, lesión y enfermedad, y los nuevos trabajadores.</span><span class="sxs-lookup"><span data-stu-id="56eb4-123">The settings on the **General** tab define the appearance of information about absence, injury and illness, and new hires.</span></span> <span data-ttu-id="56eb4-124">Los ajustes de esta pestaña también definen algunas entradas predeterminadas que aparecen mientras trabaja.</span><span class="sxs-lookup"><span data-stu-id="56eb4-124">The settings on this tab also define some default entries that appear as you work.</span></span> <span data-ttu-id="56eb4-125">Específicamente, esta pestaña le permite:</span><span class="sxs-lookup"><span data-stu-id="56eb4-125">Specifically, this tab lets you:</span></span>

- <span data-ttu-id="56eb4-126">Seleccionar un color para aplicarlo a transacciones de ausencia abiertas</span><span class="sxs-lookup"><span data-stu-id="56eb4-126">Select a color to apply to open absence transactions</span></span>
- <span data-ttu-id="56eb4-127">Especificar la hoja de estilo que se utilizará para los informes</span><span class="sxs-lookup"><span data-stu-id="56eb4-127">Specify the style sheet to use for reports</span></span>
- <span data-ttu-id="56eb4-128">Habilitar la integración entre los cursos de formación y el registro de ausencias</span><span class="sxs-lookup"><span data-stu-id="56eb4-128">Enable the integration between training courses and absence registration</span></span>
- <span data-ttu-id="56eb4-129">Seleccionar el código de ausencia que se utiliza para controlar esta integración</span><span class="sxs-lookup"><span data-stu-id="56eb4-129">Select the absence code that is used to control this integration.</span></span>
- <span data-ttu-id="56eb4-130">Indicar cuánto tiempo se deben conservar los incidentes de casos de lesiones y enfermedades</span><span class="sxs-lookup"><span data-stu-id="56eb4-130">Indicate how long to keep injury and illness case incidents.</span></span>
- <span data-ttu-id="56eb4-131">Especificar el número de identificación predeterminado que se muestra cuando se contrata a un nuevo trabajador.</span><span class="sxs-lookup"><span data-stu-id="56eb4-131">Specify the default identification number shown when a new worker is hired.</span></span>

![Pestaña General](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a><span data-ttu-id="56eb4-133">Contratación</span><span class="sxs-lookup"><span data-stu-id="56eb4-133">Recruitment</span></span>

<span data-ttu-id="56eb4-134">Los ajustes en la pestaña **Reclutamiento** definen los tipos de documentos utilizados para la correspondencia enviada automáticamente a los solicitantes.</span><span class="sxs-lookup"><span data-stu-id="56eb4-134">The settings on the **Recruitment** tab define the document types used for correspondence automatically sent to applicants.</span></span> <span data-ttu-id="56eb4-135">También puede indicar el proyecto de contratación utilizado para solicitudes no solicitadas.</span><span class="sxs-lookup"><span data-stu-id="56eb4-135">You can also indicate the recruitment project used for unsolicited applications.</span></span>

<span data-ttu-id="56eb4-136">El período definido para el vencimiento del proyecto de contratación determina los proyectos de contratación que se incluyen en el icono **Proyectos en vencimiento** en el espacio de trabajo **Gestión de contratación**.</span><span class="sxs-lookup"><span data-stu-id="56eb4-136">The period defined for recruitment project aging determines the recruitment projects included on the **Aging projects** tile in the **Recruitment management** workspace.</span></span> <span data-ttu-id="56eb4-137">El período definido para la advertencia del plazo de solicitud se usa para mostrar los proyectos de contratación que se están acercando al plazo de la solicitud en el mosaico **Se acerca el plazo de la solicitud** en el espacio de trabajo **Contratación**.</span><span class="sxs-lookup"><span data-stu-id="56eb4-137">The period defined for the application deadline warning is used to display recruitment projects that are approaching their application deadline on the **Application deadline approaching** tile in the **Recruitment** workspace.</span></span>

<span data-ttu-id="56eb4-138">Para obtener más información sobre la contratación, consulte [Reclutar candidatos para el trabajo](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-138">For more information about recruiting, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="compensation"></a><span data-ttu-id="56eb4-139">Compensación</span><span class="sxs-lookup"><span data-stu-id="56eb4-139">Compensation</span></span>

<span data-ttu-id="56eb4-140">En Dynamics 365 Finance, los ajustes en la pestaña **Compensación** definen si los usuarios deben confirmar que desean guardar la información de un plan fijo o de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="56eb4-140">In Dynamics 365 Finance, the settings on the **Compensation** tab define whether users must confirm that they want to save information for a fixed or variable compensation plan.</span></span> <span data-ttu-id="56eb4-141">Si activa la casilla **Habilitar guardar la validación**, cuando los usuarios cierren una página relacionada con la compensación, reciben un mensaje que les pregunta si desean guardar el registro.</span><span class="sxs-lookup"><span data-stu-id="56eb4-141">If you select **Enable save validation**, when users close a compensation-related page, they receive a message that asks whether they want to save the record.</span></span> <span data-ttu-id="56eb4-142">Algunas páginas en la gestión de Compensación no permiten a los usuarios eliminar la información.</span><span class="sxs-lookup"><span data-stu-id="56eb4-142">Some pages in Compensation management don't let users delete information.</span></span> <span data-ttu-id="56eb4-143">Al preguntar al usuario que verifique que desea guardar información, podría ser capaz de limitar el importe de información que se guarda pero, por otro lado, no se podrá eliminar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="56eb4-143">By prompting users to verify that they want to save information, you might be able to limit the amount of information that is saved but can't be deleted later.</span></span> <span data-ttu-id="56eb4-144">Si la casilla **Habilitar guardar validación** se desactiva, los registros se guardan inmediatamente, probablemente antes de que el usuario esté listo.</span><span class="sxs-lookup"><span data-stu-id="56eb4-144">If you clear **Enable save validation**, records save immediately, possibly before the user is ready.</span></span> <span data-ttu-id="56eb4-145">Si se usa la gestión de Rendimiento, la pestaña **Compensación** también le permite seleccionar un modelo de tasación para usarlo en lugar del modelo que está asignado a los planes de compensación al evaluar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="56eb4-145">If you're using Performance management, the **Compensation** tab also lets you select a rating model to use instead of the model assigned to compensation plans when rating performance.</span></span>

<span data-ttu-id="56eb4-146">En Human Resources, puede utilizar la pesetaña **Compensación** para elegir restringir el acceso a los planes de compensación y establecer una moneda predeterminada.</span><span class="sxs-lookup"><span data-stu-id="56eb4-146">In Human Resources, you can use the **Compensation** tab to choose to restrict access to compensation plans and to set a default currency.</span></span>

<span data-ttu-id="56eb4-147">Para obtener más información acerca de los panes de compensación, consulte [Información general de planes de compensación](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-147">For more information about compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Pestaña Compensación](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a><span data-ttu-id="56eb4-149">Secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="56eb4-149">Number sequences</span></span>

<span data-ttu-id="56eb4-150">Los ajustes en la pestaña **Secuencia numérica** determinan las secuencias utilizadas para asignar automáticamente ID a elementos en Recursos Humanos, como:</span><span class="sxs-lookup"><span data-stu-id="56eb4-150">The settings on the **Number sequence** tab determine the sequences used to automatically assign IDs to items in Human Resources, such as:</span></span>

- <span data-ttu-id="56eb4-151">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="56eb4-151">Applications</span></span>
- <span data-ttu-id="56eb4-152">Registros de ausencias</span><span class="sxs-lookup"><span data-stu-id="56eb4-152">Absence registrations</span></span>
- <span data-ttu-id="56eb4-153">Resultados de proceso de compensación</span><span class="sxs-lookup"><span data-stu-id="56eb4-153">Compensation process results</span></span>
- <span data-ttu-id="56eb4-154">Números de caso</span><span class="sxs-lookup"><span data-stu-id="56eb4-154">Case numbers</span></span>
- <span data-ttu-id="56eb4-155">Cursos</span><span class="sxs-lookup"><span data-stu-id="56eb4-155">Courses</span></span>
- <span data-ttu-id="56eb4-156">Programas del curso</span><span class="sxs-lookup"><span data-stu-id="56eb4-156">Course agendas</span></span>

<span data-ttu-id="56eb4-157">Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas** (seleccione **Administración de la organización > Secuencias numéricas > Secuencias numéricas**).</span><span class="sxs-lookup"><span data-stu-id="56eb4-157">To maintain number sequence references and codes, use the **Number sequences** list page (select **Organization administration > Number sequences > Number sequences**).</span></span>

<span data-ttu-id="56eb4-158">Para obtener más información, consulte [Información general de secuencias numéricas](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="56eb4-158">For more information, see [Number sequences overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span></span>

> [!NOTE]
> <span data-ttu-id="56eb4-159">El número de horas que se trabaja no puede superar 1250, y la duración del empleo no puede superar 12 meses.</span><span class="sxs-lookup"><span data-stu-id="56eb4-159">The number of hours that are worked can't exceed 1,250, and the length of employment can't exceed 12 months.</span></span> <span data-ttu-id="56eb4-160">Estos valores máximos están de acuerdo con la legislación federal en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="56eb4-160">These maximum values are in accordance with federal law in the United States.</span></span>

![Ficha Secuencias numéricas](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a><span data-ttu-id="56eb4-162">FMLA</span><span class="sxs-lookup"><span data-stu-id="56eb4-162">FMLA</span></span>

<span data-ttu-id="56eb4-163">En la pestaña FMLA, establece los requisitos de elegibilidad de FMLA y las horas de derecho de FMLA.</span><span class="sxs-lookup"><span data-stu-id="56eb4-163">On the FMLA tab, you set FMLA eligibility requirements and FMLA entitlement hours.</span></span> <span data-ttu-id="56eb4-164">Para más información, consulte [Configurar parámetros de bajas y ausencias](hr-leave-and-absence-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-164">For more information, see [Configure leave and absence parameters](hr-leave-and-absence-parameters.md).</span></span>

![Ficha FMLA](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a><span data-ttu-id="56eb4-166">Autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="56eb4-166">Employee self service</span></span>

<span data-ttu-id="56eb4-167">Los ajustes en la pestaña **Autoservicio para los empleados** afectan la apariencia del autoservicio de los empleados para los empleados.</span><span class="sxs-lookup"><span data-stu-id="56eb4-167">The settings on the **Employee self service** tab affect how Employee self service appears to employees.</span></span> <span data-ttu-id="56eb4-168">En esta pestaña, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56eb4-168">On this tab, you can:</span></span>

- <span data-ttu-id="56eb4-169">Introducir un nombre para el espacio de trabajo de autoservicio para el empleado</span><span class="sxs-lookup"><span data-stu-id="56eb4-169">Enter a name for the Employee self service workspace</span></span>
- <span data-ttu-id="56eb4-170">Seleccione qué información puede ingresar un gerente para los empleados</span><span class="sxs-lookup"><span data-stu-id="56eb4-170">Select which information a manager can enter for employees</span></span>
- <span data-ttu-id="56eb4-171">Agregue enlaces útiles para los empleados</span><span class="sxs-lookup"><span data-stu-id="56eb4-171">Add useful links for employees</span></span>
- <span data-ttu-id="56eb4-172">Restrinja a los empleados para que no agreguen o editen los detalles de los contactos comerciales.</span><span class="sxs-lookup"><span data-stu-id="56eb4-172">Restrict employees from adding or editing business contact details.</span></span> <span data-ttu-id="56eb4-173">Para más información, vea [Restringir la edición de información personal](hr-employee-self-service-restrict-editing.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-173">For more information, see [Restrict editing of personal information](hr-employee-self-service-restrict-editing.md).</span></span>

<span data-ttu-id="56eb4-174">Para obtener más información sobre cómo configurar el autoservicio para empleados, consulte [Descripción general del autoservicio para empleados y gerentes ](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-174">For more information about setting up Employee self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Pestaña Autoservicio para empleados](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a><span data-ttu-id="56eb4-176">Autoservicio para directores</span><span class="sxs-lookup"><span data-stu-id="56eb4-176">Manager self service</span></span>

<span data-ttu-id="56eb4-177">Los ajustes en la pestaña **Autoservicio para gerentes** afectan lo que ven los gerentes en el autoservicio de gerentes.</span><span class="sxs-lookup"><span data-stu-id="56eb4-177">The settings on the **Manager self service** tab affect what managers see in Manager self service.</span></span> <span data-ttu-id="56eb4-178">En esta pestaña, puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="56eb4-178">On this tab, you can configure the following options:</span></span>

- <span data-ttu-id="56eb4-179">El rango de registros que caducan</span><span class="sxs-lookup"><span data-stu-id="56eb4-179">The range for expiring records</span></span>
- <span data-ttu-id="56eb4-180">Los administradores de información pueden ver los registros que vencen</span><span class="sxs-lookup"><span data-stu-id="56eb4-180">Information managers can view in expiring records</span></span>
- <span data-ttu-id="56eb4-181">Si los gerentes pueden ver las posiciones abiertas para informes extendidos</span><span class="sxs-lookup"><span data-stu-id="56eb4-181">Whether managers can view open positions for extended reports</span></span>
- <span data-ttu-id="56eb4-182">Vistas de los trabajadores que salen</span><span class="sxs-lookup"><span data-stu-id="56eb4-182">Views of exiting workers</span></span>
- <span data-ttu-id="56eb4-183">Enlaces útiles para gerentes</span><span class="sxs-lookup"><span data-stu-id="56eb4-183">Useful links for managers</span></span>

<span data-ttu-id="56eb4-184">Para obtener más información sobre cómo configurar el autoservicio para gerenets, consulte [Descripción general del autoservicio para empleados y gerentes](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-184">For more information about setting up Manager self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Pestaña Autoservicio para directores](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a><span data-ttu-id="56eb4-186">Administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="56eb4-186">Benefits management</span></span>

<span data-ttu-id="56eb4-187">En la pestaña Administración de beneficios, puede configurar las opciones de correo electrónico para la administración de Beneficios.</span><span class="sxs-lookup"><span data-stu-id="56eb4-187">On the Benefits management tab, you can configure email options for Benefits management.</span></span> <span data-ttu-id="56eb4-188">Para obtener más información sobre la configuración y el uso de la administración de beneficios, consulte [Resumen de gestión de beneficios](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-188">For information about setting up and using Benefits management, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

![Pestaña Administración de prestaciones](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a><span data-ttu-id="56eb4-190">Bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="56eb4-190">Leave and absence</span></span>

<span data-ttu-id="56eb4-191">Para obtener más información acerca de la configuración y el uso de Bajas y ausencias, consulte [Vista general de bajas y de ausencias](hr-leave-and-absence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-191">For information about setting up and using Leave and absence, see [Leave and absence overview](hr-leave-and-absence-overview.md).</span></span>

## <a name="payment-methods"></a><span data-ttu-id="56eb4-192">Métodos de pago</span><span class="sxs-lookup"><span data-stu-id="56eb4-192">Payment methods</span></span>

<span data-ttu-id="56eb4-193">Sobre la pestaña **Métodos de pago**, puede seleccionar los métodos de pago admitidos por su organización.</span><span class="sxs-lookup"><span data-stu-id="56eb4-193">On the **Payment methods** tab, you can select the payment methods supported by your organization.</span></span> <span data-ttu-id="56eb4-194">Para obtener más información acerca de la configuración de la compensación, consulte [Información general de planes de compensación](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56eb4-194">For more information about configuring compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Ficha Métodos de pago](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]