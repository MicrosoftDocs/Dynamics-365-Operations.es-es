---
title: Ampliar Talent con Power Apps y Power Automate
description: 'En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Talent: Attract que usan Microsoft Power Apps y Microsoft Power Automate.'
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 1051fa4db16bb94cc9d60a91fc3637d7e5305cc2
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029920"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="e4169-103">Ampliar Talent con Power Apps y Power Automate</span><span class="sxs-lookup"><span data-stu-id="e4169-103">Extend Talent with Power Apps and Power Automate</span></span>

<span data-ttu-id="e4169-104">En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Talent: Attract que usan Microsoft Power Apps y Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="e4169-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="e4169-105">Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e4169-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="e4169-106">Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.</span><span class="sxs-lookup"><span data-stu-id="e4169-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4169-107">Si desea usar las plantillas y la aplicación que se describen en este artículo “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.</span><span class="sxs-lookup"><span data-stu-id="e4169-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="e4169-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e4169-108">Prerequisites</span></span>

- <span data-ttu-id="e4169-109">Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.</span><span class="sxs-lookup"><span data-stu-id="e4169-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="e4169-110">Para exportar o importar aplicaciones, los usuarios deben tener una licencia Power Apps Plan 2 o una licencia de prueba de Power Apps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="e4169-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="e4169-111">Power Automate - Conectar formulario</span><span class="sxs-lookup"><span data-stu-id="e4169-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="e4169-112">La plantilla **Power Automate - Conectar formulario** se puede usar para leer datos de Microsoft Forms y almacenarlos en una entidad de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e4169-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="e4169-113">Esta plantilla puede ser ampliada para que pueda usar otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="e4169-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="e4169-114">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="e4169-114">Here are some examples:</span></span>

- <span data-ttu-id="e4169-115">Captura evaluaciones de candidato.</span><span class="sxs-lookup"><span data-stu-id="e4169-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="e4169-116">Captura resultados de los cuestionarios del curso.</span><span class="sxs-lookup"><span data-stu-id="e4169-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="e4169-117">Compile una biblioteca de las preguntas de la entrevista para los administradores de recursos humanos (HR).</span><span class="sxs-lookup"><span data-stu-id="e4169-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="e4169-118">Captura la evaluación de un candidato del proceso de la entrevista</span><span class="sxs-lookup"><span data-stu-id="e4169-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="e4169-119">En Microsoft Dynamics 365: Attract, puede usar formularios en el portal de candidatos, donde los candidatos pueden completar los detalles.</span><span class="sxs-lookup"><span data-stu-id="e4169-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="e4169-120">Los formularios también se pueden insertar como actividades en una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4169-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="e4169-121">Cuando un candidato envía un formulario, Microsoft Power Automate captura el envío del formulario, lee los datos y los almacena en la entidad Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e4169-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="e4169-122">Para descargar la plantilla **Power Automate - Conectar formulario** y la estructura de entidad personalizada, vaya a [Power Automate - Conectar formulario](https://go.microsoft.com/fwlink/?linkid=2081988) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4169-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="e4169-123">Integración de Power Automate - SharePoint</span><span class="sxs-lookup"><span data-stu-id="e4169-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="e4169-124">La plantilla **Power Automate – Integración con SharePoint** se puede usar para leer datos de una lista de Microsoft SharePoint, comparar la lista con los valores de campo de cualquier entidad de Common Data Service, y enviar los resultados de la comparación como una notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e4169-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="e4169-125">Una organización puede tener un conjunto de aptitudes que necesita con urgencia.</span><span class="sxs-lookup"><span data-stu-id="e4169-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="e4169-126">Estos aptitudes se pueden almacenar en SharePoint como una lista SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e4169-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="e4169-127">Cuando un candidato solicita cualquier trabajo que cuenta con un conjunto de las aptitudes necesarias, si hay una coincidencia significativa entre las aptitudes del candidato y las aptitudes que se almacenan en SharePoint, se envía una notificación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e4169-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="e4169-128">Esto ayuda a ocupar más rápidamente los puestos que se requieren con urgencia, ya que las notificaciones ayudan a los reclutadores a contratar a candidatos en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="e4169-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="e4169-129">Esta plantilla puede ser ampliada para que pueda usar para cualquier escenario que implique la integración con SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e4169-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="e4169-130">Para descargar la plantilla **Integración de Power Automate – SharePoint** con , vaya a Integración de [Power Automate – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4169-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="e4169-131">Aplicación de referencia</span><span class="sxs-lookup"><span data-stu-id="e4169-131">Referral App</span></span>

<span data-ttu-id="e4169-132">Puede usar la aplicación de referencia para agregar candidatos a una reserva de talentos compartida.</span><span class="sxs-lookup"><span data-stu-id="e4169-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="e4169-133">La persona que hace la referencia puede especificar **Nombre**, **Apellidos**, **Correo electrónico** y **Dirección URL de Linkedln**, al registrar un candidato.</span><span class="sxs-lookup"><span data-stu-id="e4169-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="e4169-134">Luego los metadatos de origen del candidato se rellenan con la información de la persona que hace la referencia.</span><span class="sxs-lookup"><span data-stu-id="e4169-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="e4169-135">Puede insertar esta aplicación en el autoservicio para empleados para enviar referencias o puede usarla como hipervínculo en el portal corporativo y ejecutarla como aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="e4169-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="e4169-136">Para descargar **Aplicación de referencia**, [solución de extensibilidad de Dynamics 365 Talent: Aplicación de referencia](https://www.microsoft.com/download/details.aspx?id=58497) en al Centro de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4169-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="e4169-137">Puede importar esta aplicación y personalizarla para agregar una funcionalidad adicional.</span><span class="sxs-lookup"><span data-stu-id="e4169-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4169-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e4169-138">Additional resources</span></span>

[<span data-ttu-id="e4169-139">La Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="e4169-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="e4169-140">Migrar la aplicación entre arrendatarios y entornos</span><span class="sxs-lookup"><span data-stu-id="e4169-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
