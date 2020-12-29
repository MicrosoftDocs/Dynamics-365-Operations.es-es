---
title: Introducción al complemento de facturación electrónica para Italia
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Italia en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c513141f820c95fe3842478361693701f1e3641b
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2020
ms.locfileid: "4447783"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a><span data-ttu-id="cc838-103">Introducción al complemento de facturación electrónica para Italia</span><span class="sxs-lookup"><span data-stu-id="cc838-103">Get started with the Electronic invoicing add-on for Italy</span></span>

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> <span data-ttu-id="cc838-104">Es posible que el complemento de facturación electrónica para Italia no admita actualmente todas las funciones que están disponibles para las facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="cc838-104">The Electronic invoicing add-on for Italy might not currently support all the functions that are available for electronic invoices in Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="cc838-105">Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Italia.</span><span class="sxs-lookup"><span data-stu-id="cc838-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Italy.</span></span> <span data-ttu-id="cc838-106">Le guía a través de los pasos de configuración que dependen del país o la región en Regulatory Configuration Services (RCS) y Finance.</span><span class="sxs-lookup"><span data-stu-id="cc838-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="cc838-107">También le guía a través del proceso de envío de facturas electrónicas que se generan en el formato **FatturaPA** específico de Italia a través del servicio y explica cómo revisar los resultados del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="cc838-107">It also guides you through the process for submitting electronic invoices that are generated in the Italy-specific **FatturaPA** format through the service, and it explains how to review the results of processing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc838-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cc838-108">Prerequisites</span></span>

<span data-ttu-id="cc838-109">Antes de completar los pasos de este tema, debe completar los pasos en [Comience con el complemento de facturación electrónica](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="cc838-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="cc838-110">Configuración de RCS</span><span class="sxs-lookup"><span data-stu-id="cc838-110">RCS setup</span></span>

<span data-ttu-id="cc838-111">Durante la configuración de RCS, completará estas tareas:</span><span class="sxs-lookup"><span data-stu-id="cc838-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="cc838-112">Importar la función de facturación electrónica para la exportación de facturas electrónicas de clientes en el formato **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="cc838-112">Import the e-Invoicing feature for the export of customer electronic invoices in the **FatturaPA** format.</span></span>
2. <span data-ttu-id="cc838-113">Revisar las configuraciones de formato necesarias para generar, enviar y recibir respuestas sobre facturas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="cc838-113">Review the format configurations that are required to generate, submit, and receive responses about electronic invoices.</span></span>
3. <span data-ttu-id="cc838-114">Configurar los eventos que soportan los escenarios de envío de facturas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="cc838-114">Configure the events that support the electronic invoice submission scenarios.</span></span>
4. <span data-ttu-id="cc838-115">Publicar la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-115">Publish the e-Invoicing feature.</span></span>

> [!NOTE]
> <span data-ttu-id="cc838-116">"Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para consumir el servidor complementario de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="cc838-117">En este caso, la exportación de facturas electrónicas de clientes es la característica de facturación electrónica que va a configurar.</span><span class="sxs-lookup"><span data-stu-id="cc838-117">In this case, the export of customer electronic invoices is the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="cc838-118">Importar la función de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="cc838-119">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="cc838-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="cc838-120">En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="cc838-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="cc838-121">En la página **Funciones de facturación electrónica**, seleccione **Importar** para importar la característica de facturación electrónica del repositorio global.</span><span class="sxs-lookup"><span data-stu-id="cc838-121">On the **e-Invoicing Features** page, select **Import** to import the e-Invoicing feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc838-122">Si no ve la lista de funciones disponibles, seleccione **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="cc838-122">If you don't see the list of available features, select **Synchronize**.</span></span> 

4. <span data-ttu-id="cc838-123">Seleccione la función **Exportación de facturas electrónicas (IT)** y luego seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="cc838-123">Select the **e-Invoices Export (IT)** feature, and then select **Import**.</span></span>

![Importación de la función de exportación de facturas electrónicas (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

<span data-ttu-id="cc838-125">Cuando importa la función **Exportación de facturas electrónicas (IT)** del repositorio global, también se importan todas las configuraciones que se describen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="cc838-125">When you import the **e-Invoices Export (IT)** feature from the Global repository, all the settings that are described in the next sections are also imported.</span></span>

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a><span data-ttu-id="cc838-126">Crear una nueva versión de la función Exportación de facturas electrónicas (IT)</span><span class="sxs-lookup"><span data-stu-id="cc838-126">Create a new version of the e-Invoices Export (IT) feature</span></span>

1. <span data-ttu-id="cc838-127">En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cc838-127">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span> 

    ![Agregar una nueva versión de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    <span data-ttu-id="cc838-129">A continuación, configurará los formatos de informes electrónicos (ER) asociados con la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-129">Next, you will configure the Electronic reporting (ER) formats that are associated with the e-Invoicing feature.</span></span>

2. <span data-ttu-id="cc838-130">En la pestaña **Configuraciones**, seleccione **Agregar** para gestionar las versiones de configuración.</span><span class="sxs-lookup"><span data-stu-id="cc838-130">On the **Configurations** tab, select **Add** to manage the configuration versions.</span></span>

    ![Gestión de versiones de configuración de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    <span data-ttu-id="cc838-132">En este paso, está agregando y configurando los formatos ER de diferentes archivos que se utilizan para exportar facturas electrónicas italianas.</span><span class="sxs-lookup"><span data-stu-id="cc838-132">In this step, you're adding and configuring the ER formats of different files that are used to export Italian e-invoices.</span></span> <span data-ttu-id="cc838-133">Para las facturas electrónicas italianas de FatturaPA, utilice las siguientes configuraciones estándar o las configuraciones personalizadas reales que utiliza para la facturación electrónica:</span><span class="sxs-lookup"><span data-stu-id="cc838-133">For Italian FatturaPA e-invoices, use either the following standard configurations or the actual customized configurations that you use for e-invoicing:</span></span>

    - <span data-ttu-id="cc838-134">Factura de ventas (IT)</span><span class="sxs-lookup"><span data-stu-id="cc838-134">Sales invoice (IT)</span></span>
    - <span data-ttu-id="cc838-135">Factura de proyecto (IT)</span><span class="sxs-lookup"><span data-stu-id="cc838-135">Project invoice (IT)</span></span>

    <span data-ttu-id="cc838-136">Cuando crea una función de facturación electrónica que se deriva de otra función de facturación electrónica, todos los formatos de ER se heredan de la función original.</span><span class="sxs-lookup"><span data-stu-id="cc838-136">When you create an e-Invoicing feature that is derived from another e-Invoicing feature, all ER formats are inherited from the original feature.</span></span>

3. <span data-ttu-id="cc838-137">Seleccione una configuración de archivo de formato ER específico.</span><span class="sxs-lookup"><span data-stu-id="cc838-137">Select a specific ER format file configuration.</span></span>
4. <span data-ttu-id="cc838-138">Seleccione **Editar** o **Ver** para abrir la página **Diseñador de formatos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-138">Select **Edit** or **View** to open the **Format designer** page.</span></span>

    ![Abrir la página Diseñador de formato](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. <span data-ttu-id="cc838-140">Utilice la página **Diseñador de formatos** para editar y ver las configuraciones de archivo del formato ER.</span><span class="sxs-lookup"><span data-stu-id="cc838-140">Use the **Format designer** page to edit and view the ER format file configurations.</span></span>

    ![Página de diseñador de formato](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="cc838-142">Administrar las configuraciones de la función de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-142">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="cc838-143">En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar**, **Eliminar** o **Editar** para administrar las configuraciones de la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-143">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Administrar las configuraciones de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

<span data-ttu-id="cc838-145">En este paso, configura los eventos que son aplicables a las facturas electrónicas, incluida la generación de los archivos de salida XML en formato **FatturaPA** y firma digital (si se requiere).</span><span class="sxs-lookup"><span data-stu-id="cc838-145">In this step, you configure the events that are applicable to electronic invoices, including generation of the XML output files in **FatturaPA** format and digital signing (if required).</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="cc838-146">Configurar la configuración de la función de factura de ventas</span><span class="sxs-lookup"><span data-stu-id="cc838-146">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="cc838-147">En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, en la columna **Configuración de funciones**, seleccione **Factura de venta**.</span><span class="sxs-lookup"><span data-stu-id="cc838-147">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="cc838-148">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cc838-148">Select **Edit**.</span></span>
3. <span data-ttu-id="cc838-149">En la página **Configuración de la versión de función**, seleccione la pestaña **Acciones** para gestionar la lista de acciones.</span><span class="sxs-lookup"><span data-stu-id="cc838-149">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="cc838-150">Las acciones definen una lista de operaciones que deben ejecutarse en orden secuencial para lograr la ejecución completa del evento.</span><span class="sxs-lookup"><span data-stu-id="cc838-150">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Pestaña Acciones](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | <span data-ttu-id="cc838-152">Id. de acción</span><span class="sxs-lookup"><span data-stu-id="cc838-152">Action ID</span></span> | <span data-ttu-id="cc838-153">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="cc838-153">Action name</span></span>        | <span data-ttu-id="cc838-154">Descripción de la acción</span><span class="sxs-lookup"><span data-stu-id="cc838-154">Action description</span></span>                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | <span data-ttu-id="cc838-155">1</span><span class="sxs-lookup"><span data-stu-id="cc838-155">1</span></span>         | <span data-ttu-id="cc838-156">Transformar documento</span><span class="sxs-lookup"><span data-stu-id="cc838-156">Transform document</span></span> | <span data-ttu-id="cc838-157">Cree el archivo XML de factura electrónica en formato **FatturaPA**.</span><span class="sxs-lookup"><span data-stu-id="cc838-157">Create the e-invoice XML file in **FatturaPA** format.</span></span> |
    | <span data-ttu-id="cc838-158">2</span><span class="sxs-lookup"><span data-stu-id="cc838-158">2</span></span>         | <span data-ttu-id="cc838-159">Firmar documento</span><span class="sxs-lookup"><span data-stu-id="cc838-159">Sign document</span></span>      | <span data-ttu-id="cc838-160">Aplicar una firma digital al archivo XML.</span><span class="sxs-lookup"><span data-stu-id="cc838-160">Apply a digital signature to the XML file.</span></span>             |

4. <span data-ttu-id="cc838-161">Seleccione la pestaña **Reglas de aplicabilidad** para ver y mantener las reglas de aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="cc838-161">Select the **Applicability rules** tab to view and maintain the applicability rules.</span></span> <span data-ttu-id="cc838-162">Las reglas de aplicabilidad definen el contexto en el que se ejecutará la acción.</span><span class="sxs-lookup"><span data-stu-id="cc838-162">Applicability rules define the context where the action will be run.</span></span>

    ![Pestaña Reglas de aplicabilidad](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. <span data-ttu-id="cc838-164">Seleccione la pestaña **Variables** para ver y mantener las variables.</span><span class="sxs-lookup"><span data-stu-id="cc838-164">Select the **Variables** tab to view and maintain the variables.</span></span>

    ![Pestaña Variables](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. <span data-ttu-id="cc838-166">Defina las variables públicas necesarias para ejecutar las acciones.</span><span class="sxs-lookup"><span data-stu-id="cc838-166">Define the public variables that are required to run the actions.</span></span>

### <a name="configure-the-project-invoice-feature-setup"></a><span data-ttu-id="cc838-167">Configurar la función de factura de proyecto</span><span class="sxs-lookup"><span data-stu-id="cc838-167">Configure the Project invoice feature setup</span></span> 

<span data-ttu-id="cc838-168">Los pasos y ajustes necesarios para configurar la función **Factura de proyecto** son muy similares a los pasos y configuraciones de la configuración de la función **Factura de venta**.</span><span class="sxs-lookup"><span data-stu-id="cc838-168">The steps and settings that are required to configure the **Project invoice** feature setup are very similar to the steps and settings for the **Sales invoice** feature setup.</span></span> <span data-ttu-id="cc838-169">Cuando trabaje con facturas de proyectos, consulte los procedimientos para facturas de ventas.</span><span class="sxs-lookup"><span data-stu-id="cc838-169">When you work with project invoices, see the procedures for sales invoices.</span></span>

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a><span data-ttu-id="cc838-170">Asignar la función de facturación electrónica al entorno</span><span class="sxs-lookup"><span data-stu-id="cc838-170">Assign the e-Invoicing feature to the environment</span></span>

1. <span data-ttu-id="cc838-171">En la página **Funciones de facturación electrónica**, en la pestaña **Entornos**, seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="cc838-171">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="cc838-172">En el campo **Entorno**, seleccione el entorno.</span><span class="sxs-lookup"><span data-stu-id="cc838-172">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="cc838-173">En el campo **Válido desde**, seleccione la fecha en que el nuevo entorno debe entrar en vigencia.</span><span class="sxs-lookup"><span data-stu-id="cc838-173">In the **Effective from** field, select the date when the environment should become effective.</span></span>
4. <span data-ttu-id="cc838-174">Seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="cc838-174">Select **Enable**.</span></span> 

![Habilitación del entorno de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="cc838-176">Publicar la función de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-176">Publish the e-invoicing feature</span></span>

<span data-ttu-id="cc838-177">Puede publicar la función de facturación electrónica cambiando el estado de la versión a **Terminado** o **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="cc838-177">You can publish the e-Invoicing feature by changing the version status to **Completed** or **Published**.</span></span>

### <a name="change-the-version-status-to-completed"></a><span data-ttu-id="cc838-178">Cambiar el estado de la versión a Completado</span><span class="sxs-lookup"><span data-stu-id="cc838-178">Change the version status to Completed</span></span>

1. <span data-ttu-id="cc838-179">En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado de **Borrador**.</span><span class="sxs-lookup"><span data-stu-id="cc838-179">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="cc838-180">Seleccione **Cambiar estado\> Completada**.</span><span class="sxs-lookup"><span data-stu-id="cc838-180">Select **Change status \> Complete**.</span></span> 

### <a name="change-the-version-status-to-published"></a><span data-ttu-id="cc838-181">Cambiar el estado de la versión a Publicado</span><span class="sxs-lookup"><span data-stu-id="cc838-181">Change the version status to Published</span></span> 

1. <span data-ttu-id="cc838-182">En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado **Completado**.</span><span class="sxs-lookup"><span data-stu-id="cc838-182">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Completed**.</span></span>
2. <span data-ttu-id="cc838-183">Seleccione **Cambiar estado \> Publicar**.</span><span class="sxs-lookup"><span data-stu-id="cc838-183">Select **Change status \> Publish**.</span></span>

![Cambiar el estado de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="cc838-185">Configurar la integración del complemento de facturación electrónica en Finance</span><span class="sxs-lookup"><span data-stu-id="cc838-185">Set up the Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="cc838-186">Durante la configuración de Finance, completará estas tareas:</span><span class="sxs-lookup"><span data-stu-id="cc838-186">During the setup of Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="cc838-187">Importe el modelo de datos ER, el mapeo del modelo de datos ER y las configuraciones de contexto para facturas electrónicas FatturaPA.</span><span class="sxs-lookup"><span data-stu-id="cc838-187">Import the ER data model, the ER data model mapping, and the context configurations for FatturaPA e-invoices.</span></span>
2. <span data-ttu-id="cc838-188">Configure el certificado necesario para firmar digitalmente facturas electrónicas italianas.</span><span class="sxs-lookup"><span data-stu-id="cc838-188">Configure the certificate that is required to digitally sign Italian e-invoices.</span></span>

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a><span data-ttu-id="cc838-189">Importe el modelo de datos ER, el mapeo del modelo de datos y los formatos</span><span class="sxs-lookup"><span data-stu-id="cc838-189">Import the ER data model, data model mapping, and formats</span></span>

1. <span data-ttu-id="cc838-190">En el espacio de trabajo **Informes electrónicos**, verifique que el proveedor de configuración **Servicio de documentos comerciales** está establecido en **Activo**.</span><span class="sxs-lookup"><span data-stu-id="cc838-190">In the **Electronic reporting** workspace, verify that the **Business Document Service** configuration provider is set to **Active**.</span></span>
2. <span data-ttu-id="cc838-191">Seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="cc838-191">Select **Repositories**.</span></span>
3. <span data-ttu-id="cc838-192">Seleccione **Recurso global \> Abierto**.</span><span class="sxs-lookup"><span data-stu-id="cc838-192">Select **Global resource \> Open**.</span></span>
4. <span data-ttu-id="cc838-193">Importar **Modelo de factura**, **Mapeo del modelo de factura** y **Modelo de contexto de factura de cliente**.</span><span class="sxs-lookup"><span data-stu-id="cc838-193">Import **Invoice model**, **Invoice model mapping**, and **Customer invoice context model**.</span></span>

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a><span data-ttu-id="cc838-194">Active la función para exportar facturas electrónicas de clientes para Italia</span><span class="sxs-lookup"><span data-stu-id="cc838-194">Turn on the feature for exporting customer electronic invoices for Italy</span></span>

1. <span data-ttu-id="cc838-195">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-195">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="cc838-196">En la pestaña **Características**, seleccione la casilla **Habilitar** en la fila de la referencia de característica **IT00036**.</span><span class="sxs-lookup"><span data-stu-id="cc838-196">On the **Features** tab, select the **Enabled** check box in the row for feature reference **IT00036**.</span></span>

![Activar la función FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a><span data-ttu-id="cc838-198">Configurar documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="cc838-198">Configure electronic documents</span></span>

1. <span data-ttu-id="cc838-199">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-199">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="cc838-200">En la pestaña **Documento electrónico**, seleccione **Agregar** e introduzca las tablas necesarias para generar facturas electrónicas italianas:</span><span class="sxs-lookup"><span data-stu-id="cc838-200">On the **Electronic document** tab, select **Add**, and enter the tables that are required to generate Italian e-invoices:</span></span>

    - <span data-ttu-id="cc838-201">**Nombre de la tabla**: diario de facturas del cliente</span><span class="sxs-lookup"><span data-stu-id="cc838-201">**Table name:** Customer invoice journal</span></span>
    - <span data-ttu-id="cc838-202">**Nombre de la tabla**: factura del proyecto</span><span class="sxs-lookup"><span data-stu-id="cc838-202">**Table name:** Project invoice</span></span>

3. <span data-ttu-id="cc838-203">Para cada tabla, defina un contexto de documento relacionado:</span><span class="sxs-lookup"><span data-stu-id="cc838-203">For each table, define a related document context:</span></span>

    - <span data-ttu-id="cc838-204">Para **Diario de facturas del cliente**, seleccione **Contexto de la factura del cliente**.</span><span class="sxs-lookup"><span data-stu-id="cc838-204">For **Customer invoice journal**, select **Customer invoice context**.</span></span>
    - <span data-ttu-id="cc838-205">Para **Factura del proyecto**, seleccione **Contexto de la factura del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="cc838-205">For **Project invoice**, select **Project invoice context**.</span></span>

![Configuración de tipos de respuesta](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a><span data-ttu-id="cc838-207">Procesamiento de facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="cc838-207">Electronic invoice processing</span></span>

<span data-ttu-id="cc838-208">Durante el procesamiento en Finance, completará estas tareas:</span><span class="sxs-lookup"><span data-stu-id="cc838-208">During processing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="cc838-209">Genere facturas electrónicas italianas a través del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-209">Generate Italian e-invoices through the Electronic invoicing add-on</span></span>
2. <span data-ttu-id="cc838-210">Ver los registros de ejecución y revisar los resultados del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="cc838-210">View the execution logs and review the results of processing</span></span>

### <a name="generate-electronic-invoices"></a><span data-ttu-id="cc838-211">Generar facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="cc838-211">Generate electronic invoices</span></span>

<span data-ttu-id="cc838-212">Después de activar la función **Integración adicional configurable de facturación electrónica** y activar la característica **IT00036**, el antiguo proceso de Finance para generar facturas electrónicas italianas ya no se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="cc838-212">After you turn on the **Configurable Electronic invoicing add-on integration** feature and activate the **IT00036** feature, the old Finance process for generating Italian e-invoices can no longer be used.</span></span> <span data-ttu-id="cc838-213">Es reemplazado por un nuevo proceso que se llama **Presentar documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-213">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

<span data-ttu-id="cc838-214">Puede enviar los documentos manualmente, según su demanda de documentos de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-214">You can submit the documents manually, based on your demand for e-invoice documents.</span></span>

> [!NOTE]
> <span data-ttu-id="cc838-215">Antes de continuar, verifique que se haya completado la configuración necesaria para las facturas electrónicas italianas.</span><span class="sxs-lookup"><span data-stu-id="cc838-215">Before you continue, verify that the setup that is required for Italian e-invoices was completed.</span></span> <span data-ttu-id="cc838-216">Para obtener más información, consulte [Facturas electrónicas de cliente](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span><span class="sxs-lookup"><span data-stu-id="cc838-216">For more information, see [Customer electronic invoices](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices).</span></span> <span data-ttu-id="cc838-217">Tenga en cuenta que algunos de los pasos de configuración que se describen en ese tema pueden no estar disponibles debido a la activación del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-217">Be aware that some of the setup steps that are described in that topic might be unavailable because of Electronic invoicing add-on activation.</span></span>

1. <span data-ttu-id="cc838-218">Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Presentar documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-218">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="cc838-219">Para el primer envío de cualquier documento, establezca la opción **Reenviar documentos** en **No**.</span><span class="sxs-lookup"><span data-stu-id="cc838-219">For the first submission of any document, set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="cc838-220">Si debe volver a enviar un documento a través del servicio, configure esta opción en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cc838-220">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="cc838-221">En la ficha desplegable **Registros para incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo **Investigación**, donde puede crear una consulta para seleccionar los documentos para su envío.</span><span class="sxs-lookup"><span data-stu-id="cc838-221">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Cuadro de diálogo Enviar documentos electrónicos](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a><span data-ttu-id="cc838-223">Consulta de filtro</span><span class="sxs-lookup"><span data-stu-id="cc838-223">Filter query</span></span>

1. <span data-ttu-id="cc838-224">En el cuadro de diálogo **Investigación**, configure las condiciones de filtrado para facturas de venta y facturas de proyecto, o deje las condiciones en blanco para incluir todas las facturas no enviadas.</span><span class="sxs-lookup"><span data-stu-id="cc838-224">In the **Inquiry** dialog box, configure the filtering conditions for both sales invoices and project invoices, or leave the conditions blank to include all unsubmitted invoices.</span></span>

    ![Configurar criterios de filtro de envío](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. <span data-ttu-id="cc838-226">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cc838-226">Select **OK** to close the **Inquiry** dialog box.</span></span>
3. <span data-ttu-id="cc838-227">Seleccione **Aceptar** para enviar los documentos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="cc838-227">Select **OK** submit the selected documents.</span></span>

> <span data-ttu-id="cc838-228">![NOTA] Durante su primer intento de enviar un documento a través del servicio, se le pedirá que confirme la conexión con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="cc838-228">![NOTE] During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="cc838-229">Seleccione **Haga clic aquí para conectar al servicio de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-229">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

#### <a name="view-submission-logs"></a><span data-ttu-id="cc838-230">Ver registros de envío</span><span class="sxs-lookup"><span data-stu-id="cc838-230">View submission logs</span></span>

<span data-ttu-id="cc838-231">Puede ver los registros de envío de todos los documentos enviados.</span><span class="sxs-lookup"><span data-stu-id="cc838-231">You can view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="cc838-232">Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cc838-232">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="cc838-233">En el campo **Tipo de documento**, seleccione **Diario de facturas del cliente** o **Factura de proyecto** para filtrar los documentos electrónicos requeridos.</span><span class="sxs-lookup"><span data-stu-id="cc838-233">In the **Document type** field, select **Customer invoice journal** or **Project invoice** to filter for the required electronic documents.</span></span>

    ![Seleccionar un tipo de documento para ver los registros de envío](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    <span data-ttu-id="cc838-235">El valor que se muestra en la columna **Estado de presentación** representa el estado del proceso de envío.</span><span class="sxs-lookup"><span data-stu-id="cc838-235">The value that is shown in the **Submission status** column represents the status of the submission process.</span></span> <span data-ttu-id="cc838-236">Indica si el proceso se ejecutó según lo configurado y si se requieren acciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="cc838-236">It indicates whether the process ran as configured and whether additional action is required.</span></span>

3. <span data-ttu-id="cc838-237">En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.</span><span class="sxs-lookup"><span data-stu-id="cc838-237">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Ver los detalles del registro de envío](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. <span data-ttu-id="cc838-239">En la ficha desplegable **Procesamiento de acciones**, puede ver el registro de ejecución de las acciones configuradas en la versión de función que se configuró en RCS.</span><span class="sxs-lookup"><span data-stu-id="cc838-239">On the **Processing actions** FastTab, you can view the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="cc838-240">La columna **Estado** muestra si la acción se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cc838-240">The **Status** column shows whether the action was successfully run.</span></span>
5. <span data-ttu-id="cc838-241">En la ficha desplegable **Archivos de acción**, puede ver los archivos intermedios que se generaron durante la ejecución de las acciones.</span><span class="sxs-lookup"><span data-stu-id="cc838-241">On the **Action files** FastTab, you can view the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="cc838-242">Puede elegir **Ver** para descargar el archivo XML de salida en formato **FatturaPA** y ver su contenido.</span><span class="sxs-lookup"><span data-stu-id="cc838-242">You can select **View** to download the output XML file in **FatturaPA** format and view its content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc838-243">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cc838-243">Related topics</span></span>

- [<span data-ttu-id="cc838-244">Descripción general del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-244">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="cc838-245">Introducción al complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-245">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="cc838-246">Configurar el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="cc838-246">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
