---
title: Conectar el sistema de ayuda
description: Este tema describe los componentes del sistema de Ayuda para Microsoft Dynamics 365 for Finance and Operations y proporciona una visión general de cómo conectar los y un resumen de cómo crear la ayuda personalizada.
author: margoc
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 929e453987c6e2773d1886d03a4393a68033566b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850910"
---
# <a name="connect-the-help-system"></a><span data-ttu-id="f188a-103">Conectar el sistema de ayuda</span><span class="sxs-lookup"><span data-stu-id="f188a-103">Connect the Help system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f188a-104">Este tema describe los componentes del sistema de ayuda de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f188a-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f188a-105">Ofrece una visión general de cómo conectar estos componentes y un resumen de cómo crear una ayuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="f188a-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="f188a-106">Arquitectura de la Ayuda</span><span class="sxs-lookup"><span data-stu-id="f188a-106">Help architecture</span></span>

<span data-ttu-id="f188a-107">En la ilustración siguiente se muestran las partes del sistema de Ayuda de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f188a-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="f188a-108">El sistema de Ayuda del producto extrae artículos del sitio de Finance and Operations en https://docs.microsoft.com, además de guías de tareas guardadas en el Modelador de procesos empresariales de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f188a-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span>

> [!NOTE]
> <span data-ttu-id="f188a-109">Las características que aparecen en el diagrama con un asterisco (\*) están planificadas, pero aún no se encuentran disponibles.</span><span class="sxs-lookup"><span data-stu-id="f188a-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span>

<span data-ttu-id="f188a-110">[![Arquitectura de la Ayuda](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="f188a-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

## <a name="connecting-the-help-system"></a><span data-ttu-id="f188a-111">Conexión con el sistema de Ayuda</span><span class="sxs-lookup"><span data-stu-id="f188a-111">Connecting the Help system</span></span>

> [!NOTE]
> <span data-ttu-id="f188a-112">La pestaña **Guías de la tarea** no está actualmente disponible en Microsoft Dynamics 365 for Talent y Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f188a-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="f188a-113">Estamos trabajando actualmente para permitir esta funcionalidad en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="f188a-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="f188a-114">Las Guías de tareas para la Introducción a Talent seguirán disponibles para cubrir las funcionalidades básicas.</span><span class="sxs-lookup"><span data-stu-id="f188a-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="f188a-115">La ayuda de procedimientos también está disponible en el sitio de docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) para Retail y Talent.</span><span class="sxs-lookup"><span data-stu-id="f188a-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>

<span data-ttu-id="f188a-116">Con el formulario **Parámetros del sistema**, los administradores del sistema conectan las piezas del sistema de Ayuda para una implementación.</span><span class="sxs-lookup"><span data-stu-id="f188a-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span>

<span data-ttu-id="f188a-117">[![Formulario Parámetros del sistema con configuración de Ayuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="f188a-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="f188a-118">En la página **Parámetros del sistema**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f188a-118">On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f188a-119">La primera vez que abra la ficha **Ayuda** debe conectarse a Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="f188a-119">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="f188a-120">Asegúrese de hacer clic en el vínculo que hay en el medio del formulario, espere por la conexión, cierre el cuadro de diálogo y haga clic en **Aceptar** para obtener la página **Parámetros del sistema**.</span><span class="sxs-lookup"><span data-stu-id="f188a-120">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="f188a-121">[![Conectar a LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar a LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="f188a-121">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="f188a-122">Seleccione el proyecto de Lifecycle Services al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="f188a-122">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="f188a-123">Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.</span><span class="sxs-lookup"><span data-stu-id="f188a-123">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>

    - <span data-ttu-id="f188a-124">En cuanto a Finance and Operations, para el contenido de Microsoft, seleccione la Biblioteca unificada APQC más reciente para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f188a-124">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span>
    - <span data-ttu-id="f188a-125">Para Retail, lanzaremos al mercado una biblioteca en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="f188a-125">For Retail, we will be releasing a library in the near future.</span></span>
    - <span data-ttu-id="f188a-126">No necesita seleccionar una biblioteca para Talent, la conexión para la biblioteca correcta se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f188a-126">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span>

3. <span data-ttu-id="f188a-127">Establezca el orden de visualización de las bibliotecas de BPM.</span><span class="sxs-lookup"><span data-stu-id="f188a-127">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="f188a-128">Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="f188a-128">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="f188a-129">Una vez complete estos pasos, puede abrir el panel de **Ayuda** y hacer clic en la pestaña **Guías de tareas**. Verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f188a-129">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations.</span></span> <span data-ttu-id="f188a-130">Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f188a-130">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="f188a-131">Mostrar guías de tareas traducidas</span><span class="sxs-lookup"><span data-stu-id="f188a-131">Showing translated task guides</span></span>

<span data-ttu-id="f188a-132">Las guías de tareas traducidas se incluyeron por primera vez en la biblioteca unificada APQC de mayo de 2016 y en la biblioteca de introducción.</span><span class="sxs-lookup"><span data-stu-id="f188a-132">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="f188a-133">En Finance and Operations, para ver la ayuda de la guía de tareas localizada, asegúrese de que está conectado a la biblioteca de mayo.</span><span class="sxs-lookup"><span data-stu-id="f188a-133">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="f188a-134">El idioma en el que aparece una guía de tareas se controla para cada usuario mediante la configuración de idioma en **Opciones** &gt; **Preferencias**.</span><span class="sxs-lookup"><span data-stu-id="f188a-134">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="f188a-135">Aunque se hayan traducido muchas guías de tareas, actualmente el cliente de Finance and Operations no muestra los nombres traducidos de las guías de tareas.</span><span class="sxs-lookup"><span data-stu-id="f188a-135">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="f188a-136">Además, en la biblioteca de mayo de solo están disponibles en este momento las guías de tareas que se publicaron en febrero de 2016.</span><span class="sxs-lookup"><span data-stu-id="f188a-136">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="f188a-137">Publicaremos una biblioteca actualizada con traducciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="f188a-137">We will release an updated library with additional translations.</span></span>
>
> - <span data-ttu-id="f188a-138">Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f188a-138">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="f188a-139">Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f188a-139">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="f188a-140">Creación de ayuda personalizada</span><span class="sxs-lookup"><span data-stu-id="f188a-140">Creating custom help</span></span>

<span data-ttu-id="f188a-141">Puede usar las guías de tareas para crear ayuda personalizada, o para conectar una página Web al panel de la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="f188a-141">You can use task guides to create custom help, or connect a website to the Help pane.</span></span>

### <a name="create-custom-help-with-task-guides"></a><span data-ttu-id="f188a-142">Creación de ayuda personalizada mediante guías de tareas</span><span class="sxs-lookup"><span data-stu-id="f188a-142">Create custom help with task guides</span></span>

<span data-ttu-id="f188a-143">Puede crear ayuda personalizada para su implementación de Finance and Operations y para Retail creando grabaciones de tareas que reflejan su implementación y guardándolos en una Biblioteca de proceso empresarial LCS.</span><span class="sxs-lookup"><span data-stu-id="f188a-143">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="f188a-144">No puede crear guías de tareas personalizadas para Talent.</span><span class="sxs-lookup"><span data-stu-id="f188a-144">You cannot create custom task guides for Talent.</span></span>

<span data-ttu-id="f188a-145">Para socios, si promociona una biblioteca para que sea una biblioteca corporativa, e incluirla en una solución, esta estará disponible para sus clientes.</span><span class="sxs-lookup"><span data-stu-id="f188a-145">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="f188a-146">También puede realizar una copia de la biblioteca global unificada APQC y, a continuación abrir su copia, abrir grabaciones de tareas desde allí, modificarlas y guardar las grabaciones con sus cambios.</span><span class="sxs-lookup"><span data-stu-id="f188a-146">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="f188a-147">Para obtener más información, consulte el tema [Cómo crear una grabación de tareas para usarla como documentación o formación](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="f188a-147">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-site"></a><span data-ttu-id="f188a-148">Conectar un sitio personalizado</span><span class="sxs-lookup"><span data-stu-id="f188a-148">Connect a custom site</span></span>

<span data-ttu-id="f188a-149">Microsoft ha proporcionado documentación técnica y código de muestra que describen cómo crear y conectar un sitio personalizado de la ayuda al panel de la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="f188a-149">Microsoft has provided a white paper and sample code that describe how to create and connect a custom help site to the Help pane.</span></span> <span data-ttu-id="f188a-150">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="f188a-150">For more information, see:</span></span>

- [<span data-ttu-id="f188a-151">Crear Ayuda personalizada para Finance and Operations (documentación técnica)</span><span class="sxs-lookup"><span data-stu-id="f188a-151">Create Custom Help for Finance and Operations (white paper)</span></span>](https://go.microsoft.com/fwlink/?linkid=2041185)
- [<span data-ttu-id="f188a-152">Repositorio GitHub de ayuda personalizada</span><span class="sxs-lookup"><span data-stu-id="f188a-152">Custom help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a><span data-ttu-id="f188a-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f188a-153">Additional resources</span></span>

[<span data-ttu-id="f188a-154">Visión general de la ayuda</span><span class="sxs-lookup"><span data-stu-id="f188a-154">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="f188a-155">Visión general del Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="f188a-155">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="f188a-156">Cómo crear una grabación de tareas para usarla como documentación o formación</span><span class="sxs-lookup"><span data-stu-id="f188a-156">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)
