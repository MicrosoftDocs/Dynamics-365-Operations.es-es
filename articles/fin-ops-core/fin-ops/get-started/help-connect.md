---
title: Configurar la experiencia de ayuda para aplicaciones de Finance and Operations
description: Este tema proporciona información sobre los componentes del sistema de ayuda para algunas aplicaciones Microsoft Dynamics 365. También explica cómo conectar esas aplicaciones y proporciona un resumen del proceso para crear ayuda personalizada.
author: margoc
manager: AnnBe
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0495bbc008ed1760b98c2c1ace63fc4a8b1ab5cc
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694430"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a><span data-ttu-id="423f8-104">Configurar la experiencia de ayuda para aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="423f8-104">Configure the Help experience for Finance and Operations apps</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="423f8-105">En este tema, encontrará una descripción general de los componentes del sistema de ayuda para aplicaciones de Finance and Operations, como Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce y Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="423f8-105">In this topic, you will find an overview of the components of the Help system for Finance and Operations apps, such as Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources.</span></span> <span data-ttu-id="423f8-106">El tema también explica cómo conectar estos componentes y proporciona un resumen del proceso para crear ayuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="423f8-106">The topic also explains how to connect these components and provides a summary of the process for creating custom Help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="423f8-107">Arquitectura de la Ayuda</span><span class="sxs-lookup"><span data-stu-id="423f8-107">Help architecture</span></span>

<span data-ttu-id="423f8-108">Las aplicaciones de Finance and Operations incluyen descripciones generales conceptuales y otros temas que se publican en el sitio [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="423f8-108">Finance and Operations apps include conceptual overviews and other topics that are published to the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span> <span data-ttu-id="423f8-109">Se puede acceder a este contenido desde el panel **Ayuda** del producto.</span><span class="sxs-lookup"><span data-stu-id="423f8-109">This content can then be accessed from the in-product **Help** pane.</span></span> <span data-ttu-id="423f8-110">En el ejemplo siguiente se muestra las partes del sistema de Ayuda.</span><span class="sxs-lookup"><span data-stu-id="423f8-110">The following illustration shows the parts of the Help system.</span></span>

<span data-ttu-id="423f8-111">[![Arquitectura de la Ayuda](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="423f8-111">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

<span data-ttu-id="423f8-112">El sistema de ayuda integrado en el producto extrae artículos de docs.microsoft.com y otros sitios web conectados.</span><span class="sxs-lookup"><span data-stu-id="423f8-112">The in-product Help system pulls articles from docs.microsoft.com and other connected websites.</span></span> <span data-ttu-id="423f8-113">También extrae guías de tareas que se almacenan en Modelador de procesos empresariales (BPM), en Lifecycle Services de Microsoft Dynamics (LCS).</span><span class="sxs-lookup"><span data-stu-id="423f8-113">It also pulls in task guides that are stored in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="adding-task-guides"></a><span data-ttu-id="423f8-114">Adición de guías de tareas</span><span class="sxs-lookup"><span data-stu-id="423f8-114">Adding task guides</span></span>

> [!NOTE]
> <span data-ttu-id="423f8-115">La pestaña **Guías de tareas** no está actualmente en Recursos Humanos ni en Commerce.</span><span class="sxs-lookup"><span data-stu-id="423f8-115">The **Task guides** tab isn't currently available in Human Resources or Commerce.</span></span> <!--We are currently working to enable this functionality in a future release.--> <span data-ttu-id="423f8-116">Sin embargo, las guías de tareas de la experiencia Introducción en Recursos humanos seguirán disponibles para cubrir las funcionalidades básicas.</span><span class="sxs-lookup"><span data-stu-id="423f8-116">However, the task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="423f8-117">Tanto para Recursos Humanos como para Commerce, la ayuda de procedimiento está disponible en el sitio [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="423f8-117">For both Human Resources and Commerce, procedural Help is available on the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span>

<span data-ttu-id="423f8-118">En la página **Parámetros del sistema**, los administradores del sistema pueden configurar el acceso a las bibliotecas de guías de tareas relevantes para una implementación.</span><span class="sxs-lookup"><span data-stu-id="423f8-118">On the **System parameters** page, system admins can configure access to the relevant task guide libraries for an implementation.</span></span>

> [!NOTE]
> - <span data-ttu-id="423f8-119">Para configurar Ayuda, debe iniciar sesión con una cuenta en el mismo inquilino que el inquilino en el que se implementa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="423f8-119">To configure Help, you must sign in by using an account in the same tenant as the tenant where the app is deployed.</span></span>
> - <span data-ttu-id="423f8-120">No es posible conectar una biblioteca LCS desde una instancia de la aplicación que se ejecute en un disco duro virtual (VHD) local.</span><span class="sxs-lookup"><span data-stu-id="423f8-120">An LCS library can't be connected from an instance of the app that is running on a local virtual hard drive (VHD).</span></span>

<span data-ttu-id="423f8-121">[![Formulario Parámetros del sistema con configuración de Ayuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="423f8-121">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="423f8-122">Para configurar guías de tareas para una solución, siga estos pasos en la página **Parámetros del sistema**.</span><span class="sxs-lookup"><span data-stu-id="423f8-122">To configure task guides for a solution, follow these steps on the **System parameters** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="423f8-123">La primera vez que abra la ficha **Ayuda** debe conectarse a Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="423f8-123">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="423f8-124">Asegúrese de seleccionar el vínculo que está en la mitad del formulario, espere a la conexión, cierre el cuadro de diálogo y luego seleccione **Aceptar** para obtener la página **Parámetros del sistema**.</span><span class="sxs-lookup"><span data-stu-id="423f8-124">Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="423f8-125">[![Conectarse a LCS](./media/connect-to-lcs-crop-1024x365.png "Conectarse a LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="423f8-125">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="423f8-126">Seleccione el proyecto de Lifecycle Services al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="423f8-126">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="423f8-127">Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.</span><span class="sxs-lookup"><span data-stu-id="423f8-127">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="423f8-128">Establezca el orden de visualización de las bibliotecas de BPM.</span><span class="sxs-lookup"><span data-stu-id="423f8-128">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="423f8-129">El orden de visualización define el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="423f8-129">The display order defines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="423f8-130">Una vez completados estos pasos, puede abrir el panel **Ayuda** y seleccionar la pestaña **Guías de tareas**. Verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en las aplicaciones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="423f8-130">After you complete these steps, you can open the **Help** pane and select the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="423f8-131">Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="423f8-131">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="423f8-132">Mostrar guías de tareas traducidas</span><span class="sxs-lookup"><span data-stu-id="423f8-132">Showing translated task guides</span></span>

<span data-ttu-id="423f8-133">Las guías de tareas traducidas se distribuyeron por primera vez en la Biblioteca unificada APQC de mayo de 2016 y en la biblioteca Introducción.</span><span class="sxs-lookup"><span data-stu-id="423f8-133">Translated task guides were first released in the May 2016 APQC Unified Library and in the Getting Started library.</span></span> <span data-ttu-id="423f8-134">Para ver la ayuda de la guía de tareas localizada, asegúrese de que su solución Dynamics 365 está conectada a la biblioteca de mayo de 2016.</span><span class="sxs-lookup"><span data-stu-id="423f8-134">To view localized task guide Help, make sure that your Dynamics 365 solution is connected to the May 2016 library.</span></span> <span data-ttu-id="423f8-135">Los usuarios pueden cambiar el idioma en el que aparece una guía de tareas cambiando la configuración de idioma en **Opciones** &gt; **Preferencias**.</span><span class="sxs-lookup"><span data-stu-id="423f8-135">Users can change the language that a task guide appears in by changing the language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="423f8-136">Pese a que se han traducido muchas guías de tareas, actualmente el cliente no muestra los nombres traducidos de las guías de tareas.</span><span class="sxs-lookup"><span data-stu-id="423f8-136">Although many task guides have been translated, the client doesn't currently show the translated task guide names.</span></span> <span data-ttu-id="423f8-137">Además, en la biblioteca de mayo de 2016, solo están disponibles traducciones para las guías de tareas que se publicaron en febrero de 2016.</span><span class="sxs-lookup"><span data-stu-id="423f8-137">Additionally, in the May 2016 library, translations are available only for the task guides that were released in February 2016.</span></span> <span data-ttu-id="423f8-138">Microsoft publicará una biblioteca actualizada que incluye traducciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="423f8-138">Microsoft will release an updated library that includes additional translations.</span></span>
>
> - <span data-ttu-id="423f8-139">Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="423f8-139">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="423f8-140">Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="423f8-140">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="adding-custom-help"></a><span data-ttu-id="423f8-141">Adición de ayuda personalizada</span><span class="sxs-lookup"><span data-stu-id="423f8-141">Adding custom Help</span></span>

<span data-ttu-id="423f8-142">Puede usar las guías de tareas para crear ayuda personalizada o puede conectar un sitio web de ayuda personalizada al panel **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="423f8-142">You can use task guides to create custom Help, or you can connect a custom Help website to the **Help** pane.</span></span>

### <a name="create-custom-help-by-using-task-guides"></a><span data-ttu-id="423f8-143">Creación de ayuda personalizada mediante guías de tareas</span><span class="sxs-lookup"><span data-stu-id="423f8-143">Create custom Help by using task guides</span></span>

<span data-ttu-id="423f8-144">Puede crear ayuda personalizada para las aplicaciones soportadas, creando grabaciones de tareas que reflejen su implementación y luego guardándolas en una biblioteca de proceso empresarial en LCS.</span><span class="sxs-lookup"><span data-stu-id="423f8-144">You can create custom Help for the supported apps by creating task recordings that reflect your implementation and then saving them to a Business process library in LCS.</span></span> <span data-ttu-id="423f8-145">No puede crear guías de tareas personalizadas para Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="423f8-145">You can't create custom task guides for Human Resources.</span></span>

<span data-ttu-id="423f8-146">Si es socio y promociona una biblioteca para que sea biblioteca corporativa e incluirla en una solución, esta quedará a disposición de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="423f8-146">If you're a partner, and you promote a library to a corporate library and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="423f8-147">También puede realizar una copia de la biblioteca unificada APQC y luego abrir las grabaciones de tareas en la copia, editarlas y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="423f8-147">You can also make a copy of the APQC Unified Library, and then open the task recordings in the copy, edit them, and save your changes.</span></span> <span data-ttu-id="423f8-148">Para obtener más información, consulte [Recursos del grabador de tareas](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="423f8-148">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-help-site"></a><span data-ttu-id="423f8-149">Conectar un sitio de ayuda personalizada</span><span class="sxs-lookup"><span data-stu-id="423f8-149">Connect a custom Help site</span></span>

<span data-ttu-id="423f8-150">Las aplicaciones Finance and Operations rara vez se usan en su forma original.</span><span class="sxs-lookup"><span data-stu-id="423f8-150">Finance and Operations apps are rarely used in their out-of-box form.</span></span> <span data-ttu-id="423f8-151">En su lugar, la solución se personaliza y se extiende para satisfacer las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="423f8-151">Instead, the solution is customized and extended to fit the organization's needs.</span></span> <span data-ttu-id="423f8-152">También puede personalizar y ampliar la experiencia de Ayuda.</span><span class="sxs-lookup"><span data-stu-id="423f8-152">You can also customize and extend the Help experience.</span></span> <span data-ttu-id="423f8-153">Por ejemplo, puede agregar ayuda personalizada al panel **Ayuda** integrado del producto.</span><span class="sxs-lookup"><span data-stu-id="423f8-153">For example, you can add custom Help to the in-product **Help** pane.</span></span>

<span data-ttu-id="423f8-154">Microsoft ha proporcionado un kit de herramientas para ayudarle a implementar y conectar ayuda personalizada al panel **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="423f8-154">Microsoft has provided a toolkit to help you deploy and connect custom Help to the **Help** pane.</span></span> <span data-ttu-id="423f8-155">Para obtener información acerca de cómo puede configurar una solución de ayuda personalizada que esté conectada al panel **Ayuda**, consulte [Resumen de ayuda personalizada](../../dev-itpro/help/custom-help-overview.md).</span><span class="sxs-lookup"><span data-stu-id="423f8-155">For information about how you can set up a custom Help solution that is connected to the **Help** pane, see [Custom Help overview](../../dev-itpro/help/custom-help-overview.md).</span></span>

<span data-ttu-id="423f8-156">Si desea colaborar con Microsoft en herramientas y procesos para personalizar la ayuda, complete el formulario en [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span><span class="sxs-lookup"><span data-stu-id="423f8-156">If you want to collaborate with Microsoft on tools and processes for customizing Help, fill in the form at [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span></span>

## <a name="see-also"></a><span data-ttu-id="423f8-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="423f8-157">See also</span></span>

[<span data-ttu-id="423f8-158">Sistema de ayuda</span><span class="sxs-lookup"><span data-stu-id="423f8-158">Help system</span></span>](help-overview.md)  
[<span data-ttu-id="423f8-159">Resumen de ayuda personalizada</span><span class="sxs-lookup"><span data-stu-id="423f8-159">Custom Help overview</span></span>](../../dev-itpro/help/custom-help-overview.md)  
[<span data-ttu-id="423f8-160">Recursos del Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="423f8-160">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)  
[<span data-ttu-id="423f8-161">Crear documentación o formación con el Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="423f8-161">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[<span data-ttu-id="423f8-162">Repositorio GitHub de ayuda personalizada</span><span class="sxs-lookup"><span data-stu-id="423f8-162">Custom Help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)  
