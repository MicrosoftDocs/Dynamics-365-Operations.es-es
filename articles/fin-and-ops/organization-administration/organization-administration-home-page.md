---
title: "Página principal de administración de la organización"
description: "En este tema se indican recursos que le ayudarán a usar Microsoft Dynamics 365 for Finance and Operations en una organización."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a2c1d846527eac4db0a043c7f1c51da0e73bd796
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="organization-administration-home-page"></a><span data-ttu-id="6c2e1-103">Página principal de administración de la organización</span><span class="sxs-lookup"><span data-stu-id="6c2e1-103">Organization administration home page</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6c2e1-104">En este tema se detalla el contenido que ayudará a los usuarios avanzados y a los administradores a configurar Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-104">This topic points to content that will help power users and administrators configure Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="6c2e1-105">Gracias a este contenido será posible configurar el sistema de su organización y negocio para que funcione de forma rápida y efectiva.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-105">This content will help them configure the system to work smoothly and effectively for your organization and business.</span></span>

<span data-ttu-id="6c2e1-106">La mayor parte del contenido que se detalla aquí se aplica a características del módulo **Administración de organización** .</span><span class="sxs-lookup"><span data-stu-id="6c2e1-106">Much of the content listed here applies to features in the **Organizational administration** module.</span></span> <span data-ttu-id="6c2e1-107">Sin embargo, existen un par de tareas, como la creación y el uso de una plantilla de registro, que se pueden realizar en cualquier módulo y así permitirle perfeccionar el funcionamiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-107">However, there are a couple of tasks, such as creating and using a record template, that can be performed in any module to help your organization run more efficiently.</span></span> 

<a name="number-sequences"></a><span data-ttu-id="6c2e1-108">Secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="6c2e1-108">Number sequences</span></span>
----------------
<span data-ttu-id="6c2e1-109">Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-109">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="6c2e1-110">El registro de datos maestros o de transacciones que necesita un identificador se denomina *referencia*.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-110">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span> <span data-ttu-id="6c2e1-111">Antes de poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-111">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span>

-   [<span data-ttu-id="6c2e1-112">Información general de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="6c2e1-112">Number sequence overview</span></span>](number-sequence-overview.md)
-   <span data-ttu-id="6c2e1-113">[Configurar secuencias numéricas mediante asistente](tasks/set-up-number-sequences-wizard.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-113">[Set up number sequences by using a wizard](tasks/set-up-number-sequences-wizard.md) (Task guide)</span></span>
-   <span data-ttu-id="6c2e1-114">[Configurar secuencias numéricas de manera individual](tasks/set-up-number-sequences-individual-basis.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-114">[Set up number sequences on an individual basis](tasks/set-up-number-sequences-individual-basis.md) (Task guide)</span></span>

## <a name="organizations"></a><span data-ttu-id="6c2e1-115">Organizaciones</span><span class="sxs-lookup"><span data-stu-id="6c2e1-115">Organizations</span></span>
<span data-ttu-id="6c2e1-116">Una organización es un grupo de personas que trabajan juntas para llevar a cabo un proceso empresarial o lograr un objetivo.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-116">An organization is a group of people who are working together to carry out a business process or achieve a goal.</span></span> <span data-ttu-id="6c2e1-117">Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-117">Organizational hierarchies represent the relationships between the organizations that make up your business.</span></span>

<span data-ttu-id="6c2e1-118">Antes de configurar las organizaciones y las jerarquías organizativas en Finance and Operations, asegúrese de tener previsto cómo se modelará la empresa.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-118">Before you set up organizations and organization hierarchies in Finance and Operations, make sure that you plan how your business will be modeled.</span></span> <span data-ttu-id="6c2e1-119">El modelo organizativo tiene un importante efecto en la implementación de Finance and Operations y en los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-119">The organization model has a significant effect on the implementation of Finance and Operations and on business processes.</span></span>

-   [<span data-ttu-id="6c2e1-120">Organizaciones y jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="6c2e1-120">Organizations and organizational hierarchies</span></span>](organizations-organizational-hierarchies.md)
-   [<span data-ttu-id="6c2e1-121">Planificación de su jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="6c2e1-121">Plan your organizational hierarchy</span></span>](plan-organizational-hierarchy.md)
-   <span data-ttu-id="6c2e1-122">[Creación o modificación de una jerarquía organizativa](tasks/create-organization-hierarchy.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-122">[Create an organization hierarchy](tasks/create-organization-hierarchy.md) (Task guide)</span></span>
-   <span data-ttu-id="6c2e1-123">[Creación de una entidad jurídica](tasks/create-legal-entity.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-123">[Create a legal entity](tasks/create-legal-entity.md) (Task guide)</span></span>
-   <span data-ttu-id="6c2e1-124">[Creación o modificación de una unidad operativa](tasks/create-operating-unit.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-124">[Create an operating unit](tasks/create-operating-unit.md) (Task guide)</span></span>

## <a name="address-books"></a><span data-ttu-id="6c2e1-125">Libretas de direcciones</span><span class="sxs-lookup"><span data-stu-id="6c2e1-125">Address books</span></span>
<span data-ttu-id="6c2e1-126">La libreta de direcciones global es un repositorio centralizado de datos maestros que se deben almacenar para todas las personas y organizaciones internas y externas con los que la empresa interactúe.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-126">The global address book is a centralized repository for master data that must be stored for all internal and external persons and organizations that the company interacts with.</span></span> <span data-ttu-id="6c2e1-127">En los datos que se asocian a los registros de parte se incluyen el nombre, la dirección y la información de contacto.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-127">The data that is associated with party records includes the party's name, address, and contact information.</span></span> 

<span data-ttu-id="6c2e1-128">Después de crear la libreta de direcciones global, puede crear libretas de direcciones adicionales como sea necesario, como una libreta de direcciones independiente para cada empresa de su organización o para cada línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-128">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> 

-   [<span data-ttu-id="6c2e1-129">Libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="6c2e1-129">Global address book</span></span>](overview-global-address-book.md)
-   [<span data-ttu-id="6c2e1-130">Plan para saber cómo configurar la libreta de direcciones global y las libretas de direcciones adicionales</span><span class="sxs-lookup"><span data-stu-id="6c2e1-130">Plan how to configure the global address book and additional address books</span></span>](plan-configuration-global-address-book-additional-address-books.md)
- [<span data-ttu-id="6c2e1-131">Configurar la libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="6c2e1-131">Configure the global address book</span></span>](tasks/configure-global-address-book.md)
-   [<span data-ttu-id="6c2e1-132">Preguntas frecuentes sobre libretas de direcciones</span><span class="sxs-lookup"><span data-stu-id="6c2e1-132">Address books FAQ</span></span>](qa-address-books.md)


## <a name="workflow"></a><span data-ttu-id="6c2e1-133">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c2e1-133">Workflow</span></span>
<span data-ttu-id="6c2e1-134">El flujo de trabajo es un sistema que está instalado en Finance and Operations que puede usar para crear flujos de trabajo individuales, o procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-134">Workflow is a system that is installed with Finance and Operations that you can use to create individual workflows, or business processes.</span></span> <span data-ttu-id="6c2e1-135">Al crear un flujo de trabajo, debe especificar cómo fluye o se mueve un documento en el sistema; para ello, debe mostrar quién debe completar una tarea, tomar una decisión o aprobar un documento.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-135">When you create a workflow, you specify how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> 

-   [<span data-ttu-id="6c2e1-136">Visión general del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c2e1-136">Workflow overview</span></span>](overview-workflow-system.md)
-   [<span data-ttu-id="6c2e1-137">Elementos del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c2e1-137">Workflow elements</span></span>](workflow-elements.md)
-   [<span data-ttu-id="6c2e1-138">Acciones de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c2e1-138">Workflow actions</span></span>](workflow-actions.md)
-   [<span data-ttu-id="6c2e1-139">Crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c2e1-139">Create a workflow</span></span>](create-workflow.md)

## <a name="electronic-signatures"></a><span data-ttu-id="6c2e1-140">Firmas electrónicas</span><span class="sxs-lookup"><span data-stu-id="6c2e1-140">Electronic signatures</span></span>
<span data-ttu-id="6c2e1-141">Una firma electrónica confirma la identidad de una persona que va a comenzar o aprobar un proceso informático.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-141">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="6c2e1-142">En algunos sectores, una firma electrónica es tan vinculante legalmente como una firma escrita.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-142">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span> <span data-ttu-id="6c2e1-143">Las firmas electrónicas son un requisito de cumplimiento de directivas para determinados sectores regulados, como el farmacéutico, alimentación, aeroespacial y defensa.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-143">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span>

<span data-ttu-id="6c2e1-144">En Finance and Operations, puede usar firmas electrónicas para procesos empresariales críticos.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-144">In Finance and Operations, you can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="6c2e1-145">Algunos procesos llevan integrada la capacidad de firma electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-145">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="6c2e1-146">También puede crear requisitos de firma personalizados para cualquier tabla o campo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-146">You can also create custom signature requirements for any database table and field.</span></span>

-   [<span data-ttu-id="6c2e1-147">Visión general de la firma electrónica</span><span class="sxs-lookup"><span data-stu-id="6c2e1-147">Electronic signature overview</span></span>](electronic-signature-overview.md)
-   <span data-ttu-id="6c2e1-148">[Configuración de firmas electrónicas](tasks/set-up-electronic-signatures.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-148">[Set up electronic signatures](tasks/set-up-electronic-signatures.md) (Task guide)</span></span>

## <a name="case-management"></a><span data-ttu-id="6c2e1-149">Gestión de casos</span><span class="sxs-lookup"><span data-stu-id="6c2e1-149">Case management</span></span>
<span data-ttu-id="6c2e1-150">Al planificar, seguir y analizar casos, puede desarrollar resoluciones eficaces que se pueden usar para emisiones similares.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-150">By planning, tracking, and analyzing cases, you can develop efficient resolutions that can be used for similar issues.</span></span> <span data-ttu-id="6c2e1-151">Por ejemplo, si un representante de servicio al cliente o un generalista de recursos humanos crean casos, pueden encontrar información en los artículos de conocimientos sobre cómo trabajar con un caso o cómo resolverlo de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-151">For example, when customer service representatives or Human Resources generalists create cases, they can find information in knowledge articles to help them work with or resolve a case more efficiently.</span></span> 

-   [<span data-ttu-id="6c2e1-152">Visión general de la gestión de casos</span><span class="sxs-lookup"><span data-stu-id="6c2e1-152">Case management overview</span></span>](cases.md)
-   [<span data-ttu-id="6c2e1-153">Configurar seguridad, procesos y categorías de casos</span><span class="sxs-lookup"><span data-stu-id="6c2e1-153">Configure case security, processes, and categories</span></span>](plan-case-management.md)

## <a name="record-templates"></a><span data-ttu-id="6c2e1-154">Plantillas de registro</span><span class="sxs-lookup"><span data-stu-id="6c2e1-154">Record templates</span></span>
<span data-ttu-id="6c2e1-155">Las plantillas de registro pueden ayudarle a crear registros más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-155">Record templates can help you to create records more quickly.</span></span> <span data-ttu-id="6c2e1-156">Puede crear plantillas de registro para no tener que especificar los valores de campo que se utilizan a menudo explícitamente para cada registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="6c2e1-156">You can create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> 

-   [<span data-ttu-id="6c2e1-157">Plantillas de registro</span><span class="sxs-lookup"><span data-stu-id="6c2e1-157">Record templates</span></span>](record-templates.md)
- <span data-ttu-id="6c2e1-158">[Crear una plantilla de registro para facilitar la entrada de datos](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-158">[Create a record template to facilitate data entry](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Task guide)</span></span>
- <span data-ttu-id="6c2e1-159">[Usar una plantilla de registro para crear un nuevo registro](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-159">[Use a record template to create a new record](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Task guide)</span></span>

## <a name="general-organization-administration"></a><span data-ttu-id="6c2e1-160">Administración de la organización general</span><span class="sxs-lookup"><span data-stu-id="6c2e1-160">General organization administration</span></span>
-   <span data-ttu-id="6c2e1-161">[Cambiar el encabezado o el logotipo](../get-started/tasks/change-banner-or-logo.md) (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="6c2e1-161">[Change the banner or logo](../get-started/tasks/change-banner-or-logo.md) (Task guide)</span></span>
- [<span data-ttu-id="6c2e1-162">Configurar la gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="6c2e1-162">Configure document management</span></span>](configure-document-management.md)
- [<span data-ttu-id="6c2e1-163">Configurar y enviar correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6c2e1-163">Configure and send email</span></span>](configure-email.md)
-   [<span data-ttu-id="6c2e1-164">Datos de fecha y hora y las zonas horarias</span><span class="sxs-lookup"><span data-stu-id="6c2e1-164">Date/time data and time zones</span></span>](date-time-zones.md)








