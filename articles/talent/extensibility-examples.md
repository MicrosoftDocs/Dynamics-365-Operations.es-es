---
title: Extender Talent mediante PowerApps y Microsoft Flow - escenarios de ejemplo
description: En este tema se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 for Talent que usan Microsoft PowerApps y Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519006"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a><span data-ttu-id="aea3d-103">Extender Talent mediante PowerApps y Microsoft Flow - escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aea3d-103">Extend Talent by using PowerApps and Microsoft Flow - Example scenarios</span></span>

<span data-ttu-id="aea3d-104">En este tema se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 for Talent que usan Microsoft PowerApps y Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="aea3d-104">This topic describes some examples of extensibility scenarios for Microsoft Dynamics 365 for Talent that use Microsoft PowerApps and Microsoft Flow.</span></span> <span data-ttu-id="aea3d-105">Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de PowerApps.</span><span class="sxs-lookup"><span data-stu-id="aea3d-105">You can import the solution package that is associated with each example into your PowerApps environment.</span></span> <span data-ttu-id="aea3d-106">Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.</span><span class="sxs-lookup"><span data-stu-id="aea3d-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aea3d-107">Si desea usar las plantillas y la aplicación que se describen en este tema “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.</span><span class="sxs-lookup"><span data-stu-id="aea3d-107">If you want to use the templates and app that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="aea3d-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aea3d-108">Prerequisites</span></span>

- <span data-ttu-id="aea3d-109">Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.</span><span class="sxs-lookup"><span data-stu-id="aea3d-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="aea3d-110">Para exportar o importar aplicaciones, los usuarios deben tener una licencia PowerApps Plan 2 o una licencia de prueba de PowerApps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="aea3d-110">To export or import apps, users must have a PowerApps Plan 2 license or a PowerApps Plan 2 trial license.</span></span>

## <a name="flow--form-connect"></a><span data-ttu-id="aea3d-111">Flow - Conectar formulario</span><span class="sxs-lookup"><span data-stu-id="aea3d-111">Flow – Form Connect</span></span>

<span data-ttu-id="aea3d-112">La plantilla **Flow - Conectar formulario** se puede usar para leer datos de Microsoft Forms y almacenarlos en una entidad Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aea3d-112">The **Flow – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="aea3d-113">Esta plantilla puede ser ampliada para que pueda usar otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="aea3d-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="aea3d-114">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="aea3d-114">Here are some examples:</span></span>

- <span data-ttu-id="aea3d-115">Captura evaluaciones de candidato.</span><span class="sxs-lookup"><span data-stu-id="aea3d-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="aea3d-116">Captura resultados de los cuestionarios del curso.</span><span class="sxs-lookup"><span data-stu-id="aea3d-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="aea3d-117">Compile una biblioteca de las preguntas de la entrevista para los administradores de recursos humanos (HR).</span><span class="sxs-lookup"><span data-stu-id="aea3d-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="aea3d-118">Captura la evaluación de un candidato del proceso de la entrevista</span><span class="sxs-lookup"><span data-stu-id="aea3d-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="aea3d-119">En Microsoft Dynamics 365: Attract, los formularios pueden aparecer en portal del candidato y los candidatos pueden completar los detalles.</span><span class="sxs-lookup"><span data-stu-id="aea3d-119">In Microsoft Dynamics 365: Attract, forms can appear in Candidate portal, and candidates can fill in details.</span></span> <span data-ttu-id="aea3d-120">Los formularios también se pueden insertar como actividades en una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="aea3d-120">Forms can also be embedded as activities in a job template.</span></span>

<span data-ttu-id="aea3d-121">Cuando un candidato envía un formulario, Microsoft Flow captura el envío del formulario, lee los datos y los almacena en la entidad Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aea3d-121">When a candidate submits a form, Microsoft Flow captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="aea3d-122">Para descargar la plantilla **Flow - Conectar formulario** y la estructura de entidad personalizada, vaya a [Flow - Conectar formulario](https://go.microsoft.com/fwlink/?linkid=2081988) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-122">To download the **Flow – Form Connect** template and Custom Entity Structure, go to [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a><span data-ttu-id="aea3d-123">Iniciar y extraer parámetros pasados a PowerApps</span><span class="sxs-lookup"><span data-stu-id="aea3d-123">Initiate and Extract Parameters Passed to Powerapps</span></span>

<span data-ttu-id="aea3d-124">La plantilla **Iniciar y extraer parámetros pasados a PowerApps** se puede usar como punto de partida para cualquier escenario de PowerApps que sea específico de Attract.</span><span class="sxs-lookup"><span data-stu-id="aea3d-124">The **Initiate and Extract Parameters Passed to Powerapps** template can be used as a starting point for any PowerApps scenario that is specific to Attract.</span></span> <span data-ttu-id="aea3d-125">Incluye todos los parámetros predeterminados que son pasados por Attract, por ejemplo, **Solicitud de trabajo**, **Identificador del candidato** y **JobID**.</span><span class="sxs-lookup"><span data-stu-id="aea3d-125">It includes all the default parameters that are passed by Attract, such as **Job Application**, **Candidate ID**, and **JobID**.</span></span>

<span data-ttu-id="aea3d-126">Esta plantilla se puede usar para recuperar un formulario de evaluación del candidato, de modo que un director de contratación puede ver la evaluación que completó un candidato.</span><span class="sxs-lookup"><span data-stu-id="aea3d-126">This template can be used to retrieve a candidate assessment form, so that a hiring manager can view the assessment that a candidate filled in.</span></span>

<span data-ttu-id="aea3d-127">Las aplicaciones que se crean mediante PowerApps se pueden insertar en la plantilla de trabajo en Attract.</span><span class="sxs-lookup"><span data-stu-id="aea3d-127">Apps that are created by using PowerApps can be embedded into the job template in Attract.</span></span>

<span data-ttu-id="aea3d-128">Para descargar la estructura de la plantilla **Iniciar y extraer parámetros pasados a PowerApps** y la estructura de entidad personalizada, vaya a [Iniciar y extraer parámetros pasados a PowerApps](https://go.microsoft.com/fwlink/?linkid=2081991) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-128">To download the **Initiate and Extract Parameters Passed to Powerapps** template and Custom Entity Structure, go to [Initiate and Extract Parameters Passed to Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) on the Microsoft Download Center.</span></span>

## <a name="integration-with-office-365"></a><span data-ttu-id="aea3d-129">Integración con Office 365</span><span class="sxs-lookup"><span data-stu-id="aea3d-129">Integration with Office 365</span></span>

<span data-ttu-id="aea3d-130">La aplicación **Integración con Office 365** se puede utilizar para extraer información de equipos para usuarios registrados desde Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="aea3d-130">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="aea3d-131">Hace referencia a trabajadores en Talent para extraer los datos de entrada y salida y los registros de excepción.</span><span class="sxs-lookup"><span data-stu-id="aea3d-131">It references workers in Talent to extract clock-in and clock-out details and exception recordings.</span></span> <span data-ttu-id="aea3d-132">Los detalles de hora de entrada y de salida se almacenan en entidades Common Data Service personalizadas.</span><span class="sxs-lookup"><span data-stu-id="aea3d-132">Clock-in and Clock-out details are stored in custom Common Data Service entities.</span></span> <span data-ttu-id="aea3d-133">Se asume que estos detalles se completan desde sistemas de terceros mediante la integración.</span><span class="sxs-lookup"><span data-stu-id="aea3d-133">The assumption is that these details are filled in from third-party systems via integration.</span></span>

<span data-ttu-id="aea3d-134">Esta aplicación puede ser ampliada para que pueda usar otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="aea3d-134">This app can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="aea3d-135">Por ejemplo, se puede usar para mostrar la información de las vacaciones del equipo, eventos de calendario y cualquier evento específico del equipo.</span><span class="sxs-lookup"><span data-stu-id="aea3d-135">For example, it can be used to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="aea3d-136">Para descargar la aplicación **Integración con Office 365** y la estructura de entidad personalizada, vaya a [Integración con Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-136">To download the **Integration with Office 365** app and Custome Entity Structure, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="flow--email-notification"></a><span data-ttu-id="aea3d-137">Flow - Notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="aea3d-137">Flow – Email Notification</span></span>

<span data-ttu-id="aea3d-138">La plantilla **Flow – Notificación por correo electrónico** se puede usar para los escenarios de la notificación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="aea3d-138">The **Flow – Email Notification** template can be used for email notification scenarios.</span></span> <span data-ttu-id="aea3d-139">Puede ser utilizada para activar correos electrónicos de notificación a los candidatos que el equipo de contratación rechaza durante cualquier fase del proceso de contratación.</span><span class="sxs-lookup"><span data-stu-id="aea3d-139">It can be used to trigger notification emails to candidates that the hiring team rejects during any stage of the recruiting process.</span></span>

<span data-ttu-id="aea3d-140">Esta plantilla puede ser ampliada para hacer un seguimiento de los cambios a la etapa del candidato en el proceso de contratación y enviar notificaciones al equipo de contratación y al candidato.</span><span class="sxs-lookup"><span data-stu-id="aea3d-140">This template can be extended to track changes to the candidate stage throughout the recruiting process, and to send notifications to the hiring team and candidate.</span></span>

<span data-ttu-id="aea3d-141">Normalmente, para las entidades que se almacenan en Common Data Service, los flujos se pueden configurar para enviar las notificaciones para los eventos que se producen en Core HR, Attract o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="aea3d-141">In general, for entities that are stored in Common Data Service, flows can be set up to send notifications for events that occur in Core HR, Attract, or Dynamics 365 Talent: Onboard.</span></span>

<span data-ttu-id="aea3d-142">Para descargar la plantilla **Flow – Notificación por correo electrónico**, vaya a [Flow – Notificación por correo electrónico](https://go.microsoft.com/fwlink/?linkid=2082103) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-142">To download the **Flow – Email Notification** template, go to [Flow – Email Notification](https://go.microsoft.com/fwlink/?linkid=2082103) on the Microsoft Download Center.</span></span>

## <a name="flow--sql-connect-and-execute"></a><span data-ttu-id="aea3d-143">Flow – Conectar y ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="aea3d-143">Flow – SQL Connect and execute</span></span>

<span data-ttu-id="aea3d-144">La plantilla **Flow - Conectar y ejecutar SQL** se conecta a Microsoft SQL Server y activa la ejecución de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="aea3d-144">The **Flow – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="aea3d-145">Aunque esta plantilla se designa para leer y las tablas SQL actualizadas, puede ser ampliada para que pueda usarse para otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="aea3d-145">Although this template is designed to read and update SQL tables, it can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="aea3d-146">Por ejemplo, se puede usar para rellenar una tabla de ensayo de Common Data Service con registros de SQL Server, y para sincronizar periódicamente la tabla de ensayo mediante una inserción incremental de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aea3d-146">For example, it can be used to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="aea3d-147">Para descargar la plantilla **Flow - Conectar y ejecutar SQL**, vaya a [Flow - Conectar y ejecutar SQL](https://go.microsoft.com/fwlink/?linkid=2081789) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-147">To download the **Flow – SQL Connect and execute** template, go to [Flow – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="flow--sharepoint-integration"></a><span data-ttu-id="aea3d-148">Flow - Integración con SharePoint</span><span class="sxs-lookup"><span data-stu-id="aea3d-148">Flow – SharePoint Integration</span></span>

<span data-ttu-id="aea3d-149">La plantilla **Flow – Integración con SharePoint** se puede usar para leer datos de una lista de Microsoft SharePoint , comparar la lista con los valores de campo de cualquier entidad Common Data Service , y enviar los resultados de la comparación como una notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="aea3d-149">The **Flow – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="aea3d-150">Una organización puede tener un conjunto de aptitudes que necesita con urgencia.</span><span class="sxs-lookup"><span data-stu-id="aea3d-150">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="aea3d-151">Estos aptitudes se pueden almacenar en SharePoint como una lista SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aea3d-151">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="aea3d-152">Cuando un candidato solicita cualquier trabajo que cuenta con un conjunto de las aptitudes necesarias, si hay una coincidencia significativa entre las aptitudes del candidato y las aptitudes que se almacenan en SharePoint, se envía una notificación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="aea3d-152">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="aea3d-153">De esta manera, los puestos que se requieren con urgencia se ocupan antes, ya que las notificaciones ayudan a los reclutadores a contactar y contratar a candidatos a lo largo de la organización.</span><span class="sxs-lookup"><span data-stu-id="aea3d-153">In this way, positions that are urgently required are filled faster, because the notifications help recruiters reach out and cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="aea3d-154">Esta plantilla puede ser ampliada para que pueda usar para cualquier escenario que implique la integración con SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aea3d-154">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="aea3d-155">Para descargar la plantilla **Flow – Integración con SharePoint**, vaya a [Flow – Integración con SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-155">To download the **Flow – SharePoint Integration** template, go to [Flow – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="admin-console-to-manage-talent-pools"></a><span data-ttu-id="aea3d-156">Consola de administración para administrar las reservas de talentos</span><span class="sxs-lookup"><span data-stu-id="aea3d-156">Admin console to manage talent pools</span></span>

<span data-ttu-id="aea3d-157">Si habilita la integración con LinkedIn, Attract automáticamente crea una reserva de talentos de LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="aea3d-157">When you enable integration with LinkedIn, Attract automatically createas a LinkedIn talent pool.</span></span> <span data-ttu-id="aea3d-158">Cuando un reclutador intercambia InMail con un empleado nuevo mediante LinkedIn, Attract crea un perfil para el empleado nuevo, y este se hace miembro de la reserva de talentos de LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="aea3d-158">When a recruiter exchanges InMail with a recruit through LinkedIn, Attract creates a profile for the recruit, and the recruit becomes a member of the LinkedIn talent pool.</span></span> <span data-ttu-id="aea3d-159">Esta aplicación de PowerApps es útil para reorganizar candidatos en las reservas de talentos basadas en aptitudes.</span><span class="sxs-lookup"><span data-stu-id="aea3d-159">This PowerApps app is useful for reorganizing candidates in talent pools based on skill.</span></span>

<span data-ttu-id="aea3d-160">Ejecute esta aplicación de PowerApps como consola de administración para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="aea3d-160">Run this PowerApps app as an admin console to perform the following tasks:</span></span>

- <span data-ttu-id="aea3d-161">Listar candidatos en un grupo de talentos</span><span class="sxs-lookup"><span data-stu-id="aea3d-161">List candidates in a talent pool</span></span>
- <span data-ttu-id="aea3d-162">Agregar y eliminar candidatos de un grupo de talentos</span><span class="sxs-lookup"><span data-stu-id="aea3d-162">Add and remove candidates from a talent pool</span></span>
- <span data-ttu-id="aea3d-163">Trasladar a los candidatos de una reserva de talentos a otra</span><span class="sxs-lookup"><span data-stu-id="aea3d-163">Move candidates from one talent pool to another</span></span>
- <span data-ttu-id="aea3d-164">Determinar si los candidatos ya son parte de una reserva de talentos antes de moverlos</span><span class="sxs-lookup"><span data-stu-id="aea3d-164">Determine whether candidates are already part of a talent pool before moving them</span></span>
- <span data-ttu-id="aea3d-165">Comprobar las aptitudes de los candidatos antes de moverlos a otras reservas de talentos</span><span class="sxs-lookup"><span data-stu-id="aea3d-165">Check the skills of candidates before moving them to other talent pools</span></span>

<span data-ttu-id="aea3d-166">Esta aplicación de PowerApps usa relaciones de varios a varios, por lo que puede usarla como plantilla para otros escenarios donde debe extraer los registros con relaciones de varios a varios.</span><span class="sxs-lookup"><span data-stu-id="aea3d-166">This PowerApps app uses many-to-many relationships, so you can use it as a template for other scenarios where you need to extract records that have many-to-many relationships.</span></span>

<span data-ttu-id="aea3d-167">Para descargar la plantilla **Consola de administración administrar las reservas de talentos** vaya a la [Consola de administración administrar las reservas de talentos](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aea3d-167">To download the **Admin console to manage talent pools** template,  go to [Admin console to manage talent pools](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aea3d-168">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aea3d-168">Additional resources</span></span>

[<span data-ttu-id="aea3d-169">La Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="aea3d-169">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[<span data-ttu-id="aea3d-170">Migrar la aplicación entre arrendatarios y entornos</span><span class="sxs-lookup"><span data-stu-id="aea3d-170">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)