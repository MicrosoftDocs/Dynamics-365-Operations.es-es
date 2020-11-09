---
title: Introducción al complemento de facturación electrónica para México
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para México en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: a30f5a9b585c826222108563ea10ac4194ee441c
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039831"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a><span data-ttu-id="9e18a-103">Introducción al complemento de facturación electrónica para México</span><span class="sxs-lookup"><span data-stu-id="9e18a-103">Get started with the Electronic invoicing add-on for Mexico</span></span>

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="9e18a-104">Es posible que el complemento de facturación electrónica para México no admita actualmente todas las funciones que están disponibles en el documento Comprobante Fiscal Digital por Internet (CFDI) y en la integración relacionada que está integrada en Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9e18a-104">The Electronic invoicing add-on for Mexico might not currently support all the functions that are available in the Comprobante Fiscal Digital por Internet (CFDI) document, and in the related integration that is built into Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="9e18a-105">Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para México.</span><span class="sxs-lookup"><span data-stu-id="9e18a-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Mexico.</span></span> <span data-ttu-id="9e18a-106">Le guía a través de los pasos de configuración que dependen del país o la región en Regulatory Configuration Services (RCS) y Finance.</span><span class="sxs-lookup"><span data-stu-id="9e18a-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="9e18a-107">También lo guía a través de los pasos que debe seguir en Finance para enviar facturas CFDI a través del servicio y explica cómo revisar los resultados del procesamiento y el estado de las facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-107">It also guides you through the steps that you must follow in Finance to submit CFDI invoices through the service, and it explains how to review the processing results and the status of CFDI invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e18a-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e18a-108">Prerequisites</span></span>

<span data-ttu-id="9e18a-109">Antes de completar los pasos de este tema, debe completar los pasos en [Comience con el complemento de facturación electrónica](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="9e18a-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="9e18a-110">Configuración de RCS</span><span class="sxs-lookup"><span data-stu-id="9e18a-110">RCS setup</span></span>

<span data-ttu-id="9e18a-111">Durante la configuración de RCS, completará estas tareas:</span><span class="sxs-lookup"><span data-stu-id="9e18a-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="9e18a-112">Importe la función de facturación electrónica para procesar facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-112">Import the e-Invoicing feature for processing CFDI invoices.</span></span>
2. <span data-ttu-id="9e18a-113">Revise las configuraciones de formato necesarias para generar, enviar y recibir respuestas sobre facturas CFDI y para enviar y recibir respuestas sobre cancelaciones.</span><span class="sxs-lookup"><span data-stu-id="9e18a-113">Review the format configurations that are required to generate, submit, and receive responses about CFDI invoices, and to submit and receive responses about cancellation.</span></span>
3. <span data-ttu-id="9e18a-114">Configure los eventos que soportan los escenarios de envío de facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-114">Configure the events that support the CFDI invoice submission scenarios.</span></span>
4. <span data-ttu-id="9e18a-115">Publique la función de facturación electrónica para facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-115">Publish the e-Invoicing feature for CFDI invoices.</span></span>

> [!NOTE]
> <span data-ttu-id="9e18a-116">"Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para consumir el servidor complementario de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="9e18a-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="9e18a-117">En este caso, las facturas CFDI (MX) son la función de facturación electrónica que configurará.</span><span class="sxs-lookup"><span data-stu-id="9e18a-117">In this case, CFDI invoices (MX) are the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="9e18a-118">Importar la función de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="9e18a-119">Inicie sesión en su cuenta de RCS.</span><span class="sxs-lookup"><span data-stu-id="9e18a-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9e18a-120">En el espacio de trabajo **Características de globalización** , en la sección **Características** , seleccione el mosaico **Facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="9e18a-121">En la página **Funciones de facturación electrónica** , seleccione **Importar** para importar la característica **Facturas CFDI (MX)** del repositorio global.</span><span class="sxs-lookup"><span data-stu-id="9e18a-121">On the **e-Invoicing Features** page, select **Import** to import the **CFDI invoices (MX)** feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e18a-122">Si no ve la función en la lista, seleccione **Sincronizar** y luego repita el paso 3.</span><span class="sxs-lookup"><span data-stu-id="9e18a-122">If you don't see the feature in the list, select **Synchronize** , and then repeat step 3.</span></span>

![Importación de la función de facturas CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

<span data-ttu-id="9e18a-124">Cuando importa la característica **Facturas CFDI (MX)** del repositorio global, también se importan todas las configuraciones de características, incluidas las configuraciones y acciones.</span><span class="sxs-lookup"><span data-stu-id="9e18a-124">When you import the **CFDI invoices (MX)** feature from the Global repository, all the feature settings, including configurations and actions, are also imported.</span></span>

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a><span data-ttu-id="9e18a-125">Cree una nueva versión de la función de facturas CFDI (MX)</span><span class="sxs-lookup"><span data-stu-id="9e18a-125">Create a new version of the CFDI invoices (MX) feature</span></span>

<span data-ttu-id="9e18a-126">Puede crear una nueva versión si, por ejemplo, se deben actualizar las URL.</span><span class="sxs-lookup"><span data-stu-id="9e18a-126">You can create a new version if, for example, URLs must be updated.</span></span> <span data-ttu-id="9e18a-127">Para más información, vea [CFDI de facturación electrónica](tasks/mx-00010-e-invoicing-cfdi.md).</span><span class="sxs-lookup"><span data-stu-id="9e18a-127">For more information, see [E-invoicing CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span></span>

- <span data-ttu-id="9e18a-128">En la página **Funciones de facturación electrónica** , en la pestaña **Versiones** , seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-128">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Agregar una nueva versión de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="9e18a-130">Actualizar la versión de configuración</span><span class="sxs-lookup"><span data-stu-id="9e18a-130">Update the configuration version</span></span>

1. <span data-ttu-id="9e18a-131">En la página **Funciones de facturación electrónica** , en la pestaña **Configuraciones** , seleccione **Agregar** o **Eliminar** para administrar las versiones de configuración (configuraciones de formato de archivo ER).</span><span class="sxs-lookup"><span data-stu-id="9e18a-131">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![Gestión de configuraciones de funciones de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    <span data-ttu-id="9e18a-133">Cuando crea una nueva versión, todas las configuraciones se heredan de la última versión publicada.</span><span class="sxs-lookup"><span data-stu-id="9e18a-133">When you create a new version, all configurations are inherited from the last published version.</span></span> <span data-ttu-id="9e18a-134">Para procesar facturas CFDI, se requieren las siguientes configuraciones:</span><span class="sxs-lookup"><span data-stu-id="9e18a-134">To process CFDI invoices, the following configurations are required:</span></span>

    - <span data-ttu-id="9e18a-135">Factura CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="9e18a-135">CFDI invoice (BusinessDocumentService)</span></span>
    - <span data-ttu-id="9e18a-136">Importación de mensajes de respuesta CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-136">CFDI response message import</span></span>
    - <span data-ttu-id="9e18a-137">Importación del registro de errores de CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-137">CFDI error log import</span></span>
    - <span data-ttu-id="9e18a-138">Solicitud de cancelación de CFDI (MX) (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="9e18a-138">CFDI cancelation request (MX) (BusinessDocumentService)</span></span>
    - <span data-ttu-id="9e18a-139">Factura CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="9e18a-139">CFDI invoice (BusinessDocumentService)</span></span>

2. <span data-ttu-id="9e18a-140">En la lista, seleccione una versión de configuración y luego seleccione **Editar** o **Ver** para abrir la página **Diseñador de formatos** , donde puede editar o ver la configuración.</span><span class="sxs-lookup"><span data-stu-id="9e18a-140">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![Abrir la página Diseñador de formato](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. <span data-ttu-id="9e18a-142">Utilice la página **Diseñador de formatos** para editar y ver las configuraciones de archivo del formato ER.</span><span class="sxs-lookup"><span data-stu-id="9e18a-142">Use the **Format designer** page to edit and view the ER format file configurations.</span></span> <span data-ttu-id="9e18a-143">Para obtener más información, consulte [Crear configuraciones de documentos electrónicos](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="9e18a-143">For more information, see [Create electronic document configurations](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span></span>

    ![Página de diseñador de formato](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="9e18a-145">Administrar las configuraciones de la función de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-145">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="9e18a-146">En la página **Funciones de facturación electrónica** , en la pestaña **Configuraciones** , seleccione **Agregar** , **Eliminar** o **Editar** para administrar las configuraciones de la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="9e18a-146">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add** , **Delete** , or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Administrar las configuraciones de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

<span data-ttu-id="9e18a-148">Para enviar facturas CFDI para autorización (generar el archivo XML, enviar el archivo XML y procesar la respuesta), se requiere la configuración de función **Factura de venta**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-148">To submit CFDI invoices for authorization (generate the XML file, submit the XML file, and process the response), the **Sales invoice** feature setup is required.</span></span>

<span data-ttu-id="9e18a-149">Para enviar la cancelación de la factura CFDI, se requieren las configuraciones de funciones **Cancelación** y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-149">To submit CFDI invoice cancellation, the **Cancellation** and **Cancel** feature setups are required.</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="9e18a-150">Configurar la configuración de la función de factura de ventas</span><span class="sxs-lookup"><span data-stu-id="9e18a-150">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="9e18a-151">En la página **Funciones de facturación electrónica** , en la pestaña **Configuraciones** , en la columna **Configuración de funciones** , seleccione **Factura de venta**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-151">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="9e18a-152">Seleccione **Editar** para configurar las acciones, reglas de aplicabilidad y variables.</span><span class="sxs-lookup"><span data-stu-id="9e18a-152">Select **Edit** to configure the actions, applicability rules, and variables.</span></span>

    ![Editar la configuración de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="9e18a-154">En la página **Configuración de la versión de función** , seleccione la pestaña **Acciones** para gestionar la lista de acciones.</span><span class="sxs-lookup"><span data-stu-id="9e18a-154">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="9e18a-155">Las acciones definen una lista de operaciones que deben ejecutarse en orden secuencial para lograr la ejecución completa del evento.</span><span class="sxs-lookup"><span data-stu-id="9e18a-155">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Pestaña Acciones](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | <span data-ttu-id="9e18a-157">Id. de acción</span><span class="sxs-lookup"><span data-stu-id="9e18a-157">Action ID</span></span> | <span data-ttu-id="9e18a-158">Acción</span><span class="sxs-lookup"><span data-stu-id="9e18a-158">Action</span></span>                   | <span data-ttu-id="9e18a-159">Nombre de acción</span><span class="sxs-lookup"><span data-stu-id="9e18a-159">Action name</span></span>                                  | <span data-ttu-id="9e18a-160">Descripción de la acción</span><span class="sxs-lookup"><span data-stu-id="9e18a-160">Action description</span></span>                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | <span data-ttu-id="9e18a-161">1</span><span class="sxs-lookup"><span data-stu-id="9e18a-161">1</span></span>         | <span data-ttu-id="9e18a-162">Transformar documento</span><span class="sxs-lookup"><span data-stu-id="9e18a-162">Transform document</span></span>       | <span data-ttu-id="9e18a-163">Genere una factura electrónica CFDI sin señal digital</span><span class="sxs-lookup"><span data-stu-id="9e18a-163">Generate CFDI E-Invoice without digital sign</span></span> | <span data-ttu-id="9e18a-164">Genere la factura electrónica CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-164">Generate the CFDI e-invoice.</span></span>                                |
    | <span data-ttu-id="9e18a-165">2</span><span class="sxs-lookup"><span data-stu-id="9e18a-165">2</span></span>         | <span data-ttu-id="9e18a-166">Firmar documento</span><span class="sxs-lookup"><span data-stu-id="9e18a-166">Sign document</span></span>            | <span data-ttu-id="9e18a-167">Señal digital</span><span class="sxs-lookup"><span data-stu-id="9e18a-167">Digital sign</span></span>                                 | <span data-ttu-id="9e18a-168">Firme digitalmente la factura electrónica para su envío.</span><span class="sxs-lookup"><span data-stu-id="9e18a-168">Digitally sign the e-invoice for submission.</span></span>                |
    | <span data-ttu-id="9e18a-169">3</span><span class="sxs-lookup"><span data-stu-id="9e18a-169">3</span></span>         | <span data-ttu-id="9e18a-170">Llamar al servicio PAC mexicano</span><span class="sxs-lookup"><span data-stu-id="9e18a-170">Call Mexican PAC service</span></span> | <span data-ttu-id="9e18a-171">Enviar factura electrónica CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-171">Submit CFDI E-Invoice</span></span>                        | <span data-ttu-id="9e18a-172">El cliente de Windows Communication Foundation (WCF) envía la factura electrónica CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-172">The Windows Communication Foundation (WCF) client submits the CFDI e-invoice.</span></span> |
    | <span data-ttu-id="9e18a-173">4</span><span class="sxs-lookup"><span data-stu-id="9e18a-173">4</span></span>         | <span data-ttu-id="9e18a-174">Respuesta del proceso</span><span class="sxs-lookup"><span data-stu-id="9e18a-174">Process response</span></span>         | <span data-ttu-id="9e18a-175">Analizar la respuesta del servicio web</span><span class="sxs-lookup"><span data-stu-id="9e18a-175">Analyze web service response</span></span>                 | <span data-ttu-id="9e18a-176">Analice la respuesta del servicio web y devuelva el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="9e18a-176">Analyze the web service response, and return the error log.</span></span> |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a><span data-ttu-id="9e18a-177">Configurar la URL para los servicios web del PAC mexicano</span><span class="sxs-lookup"><span data-stu-id="9e18a-177">Set up the URL for Mexican PAC web services</span></span> 

1. <span data-ttu-id="9e18a-178">En la página **Configuración de la versión de función** , en la pestaña **Acciones** , en la ficha desplegable **Acciones** , seleccione **Llamar al servicio PAC mexicano**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-178">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Mexican PAC service**.</span></span>
2. <span data-ttu-id="9e18a-179">En la ficha desplegable **Parámetros** , en el campo **Dirección URL** , ingrese la URL del servicio web para el envío de facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-179">On the **Parameters** FastTab, in the **URL address** field, enter the URL of the web service for CFDI invoice submission.</span></span>

> [!NOTE]
> <span data-ttu-id="9e18a-180">Siga los mismos pasos para actualizar la URL de la acción **Llamar al servicio PAC mexicano** para las configuraciones de función **Cancelar** y **Solicitud de cancelación**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-180">Use the same steps to update the URL for **Call Mexican PAC service** action for the **Cancel** and **Cancelation request** feature setups.</span></span>

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a><span data-ttu-id="9e18a-181">Asignar la versión borrador a un entorno de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-181">Assign the Draft version to an e-Invoicing environment</span></span>

1. <span data-ttu-id="9e18a-182">En la página **Funciones de facturación electrónica** , en la pestaña **Entornos** , seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-182">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="9e18a-183">En el campo **Entorno** , seleccione el entorno.</span><span class="sxs-lookup"><span data-stu-id="9e18a-183">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="9e18a-184">En el campo **Válido desde** , seleccione la fecha en que el nuevo entorno debe entrar en vigencia.</span><span class="sxs-lookup"><span data-stu-id="9e18a-184">In the **Effective from** field, select the date when the environment should become effective.</span></span>
3. <span data-ttu-id="9e18a-185">Seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-185">Select **Enable**.</span></span>

![Habilitación de un entorno de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a><span data-ttu-id="9e18a-187">Cambiar el estado de la versión a Completado</span><span class="sxs-lookup"><span data-stu-id="9e18a-187">Change the version status to Completed</span></span>

1. <span data-ttu-id="9e18a-188">En la página **Funciones de facturación electrónica** , en la pestaña **Versiones** , seleccione la versión de la función de facturación electrónica que tiene un estado de **Borrador**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-188">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="9e18a-189">Seleccione **Cambiar estado\> Completada**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-189">Select **Change status \> Complete**.</span></span>

## <a name="change-the-version-status-to-published"></a><span data-ttu-id="9e18a-190">Cambiar el estado de la versión a Publicado</span><span class="sxs-lookup"><span data-stu-id="9e18a-190">Change the version status to Published</span></span>

- <span data-ttu-id="9e18a-191">En la página **Funciones de facturación electrónica** , en la pestaña **Versiones** , seleccione **Cambiar Estado \> Publicar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-191">On the **e-Invoicing Features** page, on the **Versions** tab, select **Change status \> Publish**.</span></span>

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="9e18a-192">Publicar la función de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-192">Publish the e-Invoicing feature</span></span>

1. <span data-ttu-id="9e18a-193">En la página **Funciones de facturación electrónica** , seleccione la pestaña **Versiones** para gestionar el estado de la característica **Facturas CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-193">On the **e-Invoicing Features** page, select the **Versions** tab to manage the status of the **CFDI invoices (MX)** feature.</span></span>
2. <span data-ttu-id="9e18a-194">Seleccione **Cambiar estado** para cambiar el estado de la función.</span><span class="sxs-lookup"><span data-stu-id="9e18a-194">Select **Change status** to change the status of the feature.</span></span>

![Cambiar el estado de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="9e18a-196">Configurar la integración del complemento de facturación electrónica en Finance</span><span class="sxs-lookup"><span data-stu-id="9e18a-196">Set up Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="9e18a-197">Para configurar el complemento de facturación electrónica en Finance, completará estas tareas:</span><span class="sxs-lookup"><span data-stu-id="9e18a-197">To set up the Electronic invoicing add-on in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="9e18a-198">Importe el modelo de datos ER, el mapeo del modelo de datos ER y los formatos necesarios para las facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-198">Import the ER data model, the ER data model mapping, and the formats that are required for CFDI invoices.</span></span>
2. <span data-ttu-id="9e18a-199">Configure tipos de respuesta para actualizar las facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-199">Configure response types for updating the CFDI invoices.</span></span> <span data-ttu-id="9e18a-200">Estos tipos de respuesta se utilizan para la respuesta del servidor del proveedor de certificación autorizado (PAC).</span><span class="sxs-lookup"><span data-stu-id="9e18a-200">These response types are used for the response from the authorized certification provider (PAC) server.</span></span>

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a><span data-ttu-id="9e18a-201">Importe el modelo de datos ER, el mapeo del modelo de datos ER y las configuraciones de contexto para facturas CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-201">Import the ER data model, ER data model mapping, and context configurations for CFDI invoices</span></span>

1. <span data-ttu-id="9e18a-202">Iniciar sesión en Finance.</span><span class="sxs-lookup"><span data-stu-id="9e18a-202">Sign in to Finance.</span></span>
2. <span data-ttu-id="9e18a-203">En el espacio de trabajo **Informes electrónicos** , en la sección **Proveedores de configuración** , seleccione el título **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-203">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span> <span data-ttu-id="9e18a-204">Asegúrese de que este proveedor de configuración esté establecido en **Activo**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-204">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="9e18a-205">Para obtener más información sobre cómo establecer un proveedor en **Activo** , vea [Crear proveedores de la configuración y marcarlos como activos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="9e18a-205">For information about how to set a provider to **Active** , see [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span></span>
3. <span data-ttu-id="9e18a-206">Seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-206">Select **Repositories**.</span></span>
4. <span data-ttu-id="9e18a-207">Seleccione **Recurso global \> Abierto**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-207">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="9e18a-208">Importe **Modelo de factura** , **Mapeo del modelo de factura** , **Formato de factura CFDI (MX)** , **Formato de solicitud de cancelación de factura CFDI (MX)** y **Formato de cancelación de factura CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-208">Import **Invoice model** , **Invoice model mapping** , **CFDI invoice format (MX)** , **CFDI invoice cancelation request format (MX)** , and **CFDI invoice cancel format (MX)**.</span></span>

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a><span data-ttu-id="9e18a-209">Activar la función para procesar facturas CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-209">Turn on the feature for processing CFDI invoices</span></span>

1. <span data-ttu-id="9e18a-210">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="9e18a-211">En la pestaña **Características** , seleccione la casilla **Habilitar** en las filas para referencias de características **MX-00010** y **MX-00016**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-211">On the **Features** tab, select the **Enable** check box in the rows for feature references **MX-00010** and **MX-00016**.</span></span>

![Activar las funciones para procesar facturas CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a><span data-ttu-id="9e18a-213">Importar configuraciones de ER y configurar los tipos de respuesta para actualizar las facturas CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-213">Import ER configurations and set up the response types for updating CFDI invoices</span></span>

#### <a name="import-er-configurations"></a><span data-ttu-id="9e18a-214">Importar configuraciones de ER</span><span class="sxs-lookup"><span data-stu-id="9e18a-214">Import ER configurations</span></span>

1. <span data-ttu-id="9e18a-215">En el espacio de trabajo **Informes electrónicos** , en la sección **Proveedores de configuración** , seleccione el título **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-215">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span>
3. <span data-ttu-id="9e18a-216">Seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-216">Select **Repositories**.</span></span>
4. <span data-ttu-id="9e18a-217">Seleccione **Recurso global \> Abierto**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-217">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="9e18a-218">Importe **Modelo de mensaje de respuesta** , **Importación de registro de errores CFDI (MX)** , **Importación de registro de errores CFDI (MX)** e **Importación de mensajes de respuesta CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-218">Import **Response message model** , **CFDI error log import (MX)** , **CFDI error log import (MX)** , and **CFDI response message import (MX)**.</span></span>

#### <a name="set-up-the-response-types"></a><span data-ttu-id="9e18a-219">Configurar los tipos de respuesta</span><span class="sxs-lookup"><span data-stu-id="9e18a-219">Set up the response types</span></span>

1. <span data-ttu-id="9e18a-220">Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-220">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="9e18a-221">En la pestaña **Documento electrónico** haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-221">On the **Electronic document** tab, select **Add**.</span></span>
3. <span data-ttu-id="9e18a-222">Ingrese el diario de facturas del cliente y luego, en el campo **Nombre de la tabla** , seleccione la factura del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e18a-222">Enter the customer invoice journal, and then, in the **Table name** field, select the project invoice.</span></span>
4. <span data-ttu-id="9e18a-223">Para cada tabla, defina un contexto de documento relacionado:</span><span class="sxs-lookup"><span data-stu-id="9e18a-223">For each table, define a related document context:</span></span>

    - <span data-ttu-id="9e18a-224">Para **Diario de facturas del cliente** , introduzca **Contexto de la factura del cliente**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-224">For **Customer invoice journal** , enter **Customer invoice context**.</span></span>
    - <span data-ttu-id="9e18a-225">Para **Factura del proyecto** , introduzca **Contexto de la factura del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-225">For **Project invoice** , enter **Project invoice context**.</span></span>

4. <span data-ttu-id="9e18a-226">Seleccione **Tipos de respuesta** para configurar los tipos de respuesta que pueden devolverse desde el complemento de facturación electrónica e incluirse en un diario de facturas de cliente o factura de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e18a-226">Select **Response types** to configure the response types that can be returned from the Electronic invoicing add-on and included in a customer invoice journal or project invoice.</span></span>
5. <span data-ttu-id="9e18a-227">Seleccione **Nuevo** y, en el campo **Tipo de respuesta** , seleccione **Respuesta**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-227">Select **New** , and then, in the **Response type** field, select **Response**.</span></span>
6. <span data-ttu-id="9e18a-228">En el campo **Estado de envío** , seleccione **Pendiente**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-228">In the **Submission status** field, select **Pending**.</span></span>
7. <span data-ttu-id="9e18a-229">En el campo **Mapeo de modelos** , seleccione **Formato de importación del mensaje de respuesta: mapeo del modelo del mensaje de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-229">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
8. <span data-ttu-id="9e18a-230">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-230">Select **Save**.</span></span>
9. <span data-ttu-id="9e18a-231">Seleccione **Nuevo** y, en el campo **Tipo de respuesta** , seleccione **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-231">Select **New** , and then, in the **Response type** field, select **ResponseData**.</span></span>
10. <span data-ttu-id="9e18a-232">En el campo **Estado de envío** , seleccione **Pendiente**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-232">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="9e18a-233">En el campo **Mapeo de modelos** , seleccione **Formato de importación de datos de respuesta CFDI (detalles) - Importación de datos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-233">In the **Model mapping** field, select **CFDI response data import format (details) – Response data import**.</span></span>
12. <span data-ttu-id="9e18a-234">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-234">Select **Save**.</span></span>

## <a name="process-electronic-invoices-in-finance"></a><span data-ttu-id="9e18a-235">Procesar facturas electrónicas en Finance</span><span class="sxs-lookup"><span data-stu-id="9e18a-235">Process electronic invoices in Finance</span></span> 

<span data-ttu-id="9e18a-236">Durante el procesamiento de facturas CFDI en Finance a través del complemento Facturación electrónica, puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="9e18a-236">During the processing of CFDI invoices in Finance through the Electronic invoicing add-on, you can perform the following tasks:</span></span>

- <span data-ttu-id="9e18a-237">Enviar facturas electrónicas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-237">Submit CFDI invoices.</span></span>
- <span data-ttu-id="9e18a-238">Ver los registros de ejecución de envíos.</span><span class="sxs-lookup"><span data-stu-id="9e18a-238">View the submission execution logs.</span></span>
- <span data-ttu-id="9e18a-239">Presentar la cancelación de una factura CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-239">Submit the cancellation of a CFDI invoice.</span></span>

### <a name="submit-cfdi-invoices"></a><span data-ttu-id="9e18a-240">Enviar facturas electrónicas CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-240">Submit CFDI invoices</span></span>

<span data-ttu-id="9e18a-241">Después de activar la característica **Integración adicional configurable de facturación electrónica** , el proceso **Exportación / Importación factura electrónica** ( **Cuentas por cobrar \> Facturas \> Facturas electrónicas** ) para enviar facturas CFDI ya no se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="9e18a-241">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the **Export/Import electronic invoice** process ( **Accounts receivable \> Invoices \> E-invoices** ) for submitting CFDI invoices can no longer be used.</span></span> <span data-ttu-id="9e18a-242">Es reemplazado por un nuevo proceso que se llama **Presentar documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-242">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="9e18a-243">Antes de usar el nuevo proceso **Presentar documentos electrónicos** , verifique que se haya completado la configuración requerida para las facturas electrónicas mexicanas.</span><span class="sxs-lookup"><span data-stu-id="9e18a-243">Before you use the new **Submit electronic documents** process, verify that the setup that is required for Mexican e-invoices was completed.</span></span> <span data-ttu-id="9e18a-244">Para obtener más información acerca de la conversión, consulte [Versión de diseño CFDI 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span><span class="sxs-lookup"><span data-stu-id="9e18a-244">For more information, see [CFDI layout version 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span></span>

1. <span data-ttu-id="9e18a-245">Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Presentar documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-245">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="9e18a-246">Para el primer envío de cualquier documento, establezca siempre la opción **Reenviar documentos** en **No**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-246">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="9e18a-247">Si debe volver a enviar un documento a través del servicio, configure esta opción en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-247">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="9e18a-248">En la ficha desplegable **Registros para incluir** , seleccione **Filtrar** para abrir el cuadro de diálogo **Investigación** , donde puede crear una consulta para seleccionar los documentos para su envío.</span><span class="sxs-lookup"><span data-stu-id="9e18a-248">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Envío de un documento CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> <span data-ttu-id="9e18a-250">Durante su primer intento de enviar un documento a través del servicio, se le pedirá que confirme la conexión con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="9e18a-250">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="9e18a-251">Seleccione **Haga clic aquí para conectar al servicio de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-251">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-submission-logs"></a><span data-ttu-id="9e18a-252">Ver registros de envío</span><span class="sxs-lookup"><span data-stu-id="9e18a-252">View submission logs</span></span>

<span data-ttu-id="9e18a-253">Puede ver los registros de envío de todos los documentos enviados o solo de un documento enviado.</span><span class="sxs-lookup"><span data-stu-id="9e18a-253">You can view the submission logs for all submitted documents or for just one submitted document.</span></span>

#### <a name="view-all-submission-logs"></a><span data-ttu-id="9e18a-254">Ver todos registros de envío</span><span class="sxs-lookup"><span data-stu-id="9e18a-254">View all submission logs</span></span>

<span data-ttu-id="9e18a-255">Después de activar la función **Integración adicional configurable de facturación electrónica** , una nueva página está disponible que le permite dar seguimiento al proceso de envío de documentos.</span><span class="sxs-lookup"><span data-stu-id="9e18a-255">After you turn on the **Configurable Electronic invoicing add-on integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="9e18a-256">Puede utilizar esta página para ver los registros de envío de todos los documentos enviados.</span><span class="sxs-lookup"><span data-stu-id="9e18a-256">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="9e18a-257">Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-257">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="9e18a-258">En el campo **Tipo de Documento** , seleccione **Diario de facturas del cliente** para filtrar los documentos electrónicos requeridos.</span><span class="sxs-lookup"><span data-stu-id="9e18a-258">In the **Document type** field, select **Customer invoice journal** to filter for the required electronic documents.</span></span>

    ![Seleccionar un tipo de documento para ver los registros de envío](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. <span data-ttu-id="9e18a-260">En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.</span><span class="sxs-lookup"><span data-stu-id="9e18a-260">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Ver los detalles del registro de envío](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

<span data-ttu-id="9e18a-262">La información en los registros de envío se divide en tres fichas desplegables:</span><span class="sxs-lookup"><span data-stu-id="9e18a-262">The information in the submission logs is divided among three FastTabs:</span></span>

- <span data-ttu-id="9e18a-263">**Procesamiento de acciones** - Esta ficha desplegable muestra el registro de ejecución de las acciones configuradas en la versión de función que se configuró en RCS.</span><span class="sxs-lookup"><span data-stu-id="9e18a-263">**Processing actions** – This FastTab shows the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="9e18a-264">La columna **Estado** muestra si la acción se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9e18a-264">The **Status** column shows whether the action was successfully run.</span></span>
- <span data-ttu-id="9e18a-265">**Archivos de acción** - Esta ficha desplegable muestra los archivos intermedios que se generaron durante la ejecución de las acciones.</span><span class="sxs-lookup"><span data-stu-id="9e18a-265">**Action files** – This FastTab shows the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="9e18a-266">Puede seleccionar **Ver** para descargar y ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="9e18a-266">You can select **View** to download and view the file.</span></span>
- <span data-ttu-id="9e18a-267">**Registro de acciones de procesamiento** - Esta ficha desplegable muestra los resultados de la comunicación entre el complemento de facturación electrónica y el servicio web de destino.</span><span class="sxs-lookup"><span data-stu-id="9e18a-267">**Processing action log** – This FastTab shows the results of the communication between the Electronic invoicing add-on and the target web service.</span></span> <span data-ttu-id="9e18a-268">También muestra lo que devolvió el procesamiento desde el servicio web.</span><span class="sxs-lookup"><span data-stu-id="9e18a-268">It also shows what was returned by the processing from the web service.</span></span> <span data-ttu-id="9e18a-269">La columna **Código de error** muestra el código de retorno devuelto por el servicio web de autorización.</span><span class="sxs-lookup"><span data-stu-id="9e18a-269">The **Error code** column shows the return code that was returned by the authorization web service.</span></span>

<span data-ttu-id="9e18a-270">Cuando se autoriza la factura CFDI presentada, su estado se actualiza a **Aprobado**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-270">When the submitted CFDI invoice is authorized, its status is updated to **Approved**.</span></span>

#### <a name="view-submission-logs-from-cfdi-invoices"></a><span data-ttu-id="9e18a-271">Ver registros de envío de facturas CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-271">View submission logs from CFDI invoices</span></span>

<span data-ttu-id="9e18a-272">Después de activar la característica **Integración complementaria de facturación electrónica configurable** , también puede ver los registros de envío de las facturas CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-272">After you turn on the **ConfigurableElectronic invoicing add-on integration** feature, you can also view the submission logs from CFDI invoices.</span></span>

1. <span data-ttu-id="9e18a-273">Vaya a **Clientes \> Consultas e informes \> CFDI (facturas electrónicas)**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-273">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="9e18a-274">Seleccione una factura CFDI que se envió después de activar la característica **Integración adicional configurable de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-274">Select a CFDI invoice that was submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>
3. <span data-ttu-id="9e18a-275">En el panel de acciones, en la pestaña **Historial** , seleccione **Registro de documento electrónico**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-275">On the Action Pane, on the **History** tab, select **Electronic document log**.</span></span>

![Ver registros de envío de facturas CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> <span data-ttu-id="9e18a-277">Para facturas CFDI que se enviaron antes de activar la característica **Integración adicional configurable de facturación electrónica** , el botón **Historial** está disponible.</span><span class="sxs-lookup"><span data-stu-id="9e18a-277">For CFDI invoices that were submitted before the **Configurable Electronic invoicing add-on integration** feature was turned on, the **History** button is available.</span></span> <span data-ttu-id="9e18a-278">El botón **Historial** no está disponible para facturas CFDI que se enviaron después de activar la característica **Integración adicional configurable de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-278">The **History** button isn't available for CFDI invoices that were submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>

### <a name="submit-cancellation-of-cfdi-invoices"></a><span data-ttu-id="9e18a-279">Presentar la cancelación de facturas CFDI</span><span class="sxs-lookup"><span data-stu-id="9e18a-279">Submit cancellation of CFDI invoices</span></span>

<span data-ttu-id="9e18a-280">Después de activar la característica **Integración adicional configurable de facturación electrónica** , el antiguo proceso para cancelar facturas CFDI ya no se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="9e18a-280">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the old process for canceling CFDI invoices can no longer be used.</span></span> <span data-ttu-id="9e18a-281">Se reemplaza por un nuevo proceso de cancelación que está integrado en la página **Registro de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-281">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

1. <span data-ttu-id="9e18a-282">Vaya a **Clientes \> Consultas e informes \> CFDI (facturas electrónicas)**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-282">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="9e18a-283">Si la factura CFDI tiene un estado de **Aprobado** , seleccione **Funciones \> Cancelar CFDI**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-283">If the CFDI invoice has a status of **Approved** , select **Functions \> Cancel CFDI**.</span></span>
3. <span data-ttu-id="9e18a-284">Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-284">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
4. <span data-ttu-id="9e18a-285">Seleccione la factura CFDI y luego seleccione **Funciones \> Enviar envíos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-285">Select the CFDI invoice, and then select **Functions \> Send related submissions**.</span></span>
5. <span data-ttu-id="9e18a-286">Ingrese una descripción para el envío relacionado y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-286">Enter a description for the related submission, and then select **OK**.</span></span>

#### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="9e18a-287">Ver todos registros de envío de cancelación</span><span class="sxs-lookup"><span data-stu-id="9e18a-287">View cancellation submission logs</span></span>

1. <span data-ttu-id="9e18a-288">Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="9e18a-289">En el campo **Tipo de Documento** , seleccione **Diario de facturas del cliente** para filtrar solo los documentos de diario de facturas de cliente.</span><span class="sxs-lookup"><span data-stu-id="9e18a-289">In the **Document type** field, select **Customer invoice journal** to filter for customer invoice journal documents only.</span></span>
3. <span data-ttu-id="9e18a-290">Seleccione la factura CFDI y luego, en el Panel de acciones, seleccione **Consultas \> Envío relacionado**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-290">Select the CFDI invoice, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="9e18a-291">La página **Envíos relacionados** muestra todos los envíos relacionados y su estado de envío para una factura CFDI determinada.</span><span class="sxs-lookup"><span data-stu-id="9e18a-291">The **Related submissions** page shows all related submissions, and their submission status, for a given CFDI invoice.</span></span> <span data-ttu-id="9e18a-292">En la siguiente ilustración, la primera línea representa el envío que solicitó la aprobación de la factura CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-292">In the following illustration, the first line represents the submission that requested approval of the CFDI invoice.</span></span> <span data-ttu-id="9e18a-293">La segunda línea representa el envío que canceló esa factura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="9e18a-293">The second line represents the submission that canceled that CFDI invoice.</span></span>

    ![Ver los registros de envío de cancelación](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. <span data-ttu-id="9e18a-295">En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.</span><span class="sxs-lookup"><span data-stu-id="9e18a-295">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Ver los detalles del registro de envío de cancelación](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="9e18a-297">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="9e18a-297">Privacy notice</span></span>
<span data-ttu-id="9e18a-298">Habilitar las funciones MX-00010 y MX-00016 (Factura CFDI y Cancelación de CFDI) puede requerir el envío de datos limitados, que incluyen el ID de registro fiscal de la organización.</span><span class="sxs-lookup"><span data-stu-id="9e18a-298">Enabling the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="9e18a-299">Este será transmitido a agencias de terceros autorizadas por la autoridad tributaria para propósitos de enviar facturas electrónicas a esta autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno.</span><span class="sxs-lookup"><span data-stu-id="9e18a-299">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="9e18a-300">Un administrador puede habilitar y deshabilitar las funciones MX-00010 y MX-00016 (Factura CFDI y Cancelación de CFDI) navegando a **Administración de la organización \> Preparar \> Parámetros de documentos electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9e18a-300">An administrator can enable and disable the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="9e18a-301">Seleccione la pestaña **Características** , seleccione las filas que contienen las características MX-00010 y MX-00016, y luego haga la selección apropiada.</span><span class="sxs-lookup"><span data-stu-id="9e18a-301">Select the **Features** tab, select the rows containing the MX-00010 and MX-00016 features, and then make the appropriate selection.</span></span> <span data-ttu-id="9e18a-302">Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132).</span><span class="sxs-lookup"><span data-stu-id="9e18a-302">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="9e18a-303">Consulte las secciones de Aviso de privacidad en la documentación de funciones específicas de cada país o región para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9e18a-303">Consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e18a-304">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9e18a-304">Additional resources</span></span>

- [<span data-ttu-id="9e18a-305">Descripción general del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-305">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="9e18a-306">Introducción al complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-306">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="9e18a-307">Configurar el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="9e18a-307">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
