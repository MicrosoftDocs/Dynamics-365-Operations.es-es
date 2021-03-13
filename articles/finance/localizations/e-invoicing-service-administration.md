---
title: Componentes de administración del complemento de facturación electrónica
description: Este tema proporciona información sobre los componentes relacionados con la administración del complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104435"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="a3d9e-103">Componentes de administración del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="a3d9e-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="a3d9e-104">Este tema proporciona información sobre los componentes relacionados con la administración del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="a3d9e-105">También proporciona información sobre cómo configurar el servicio adicional de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="a3d9e-106">Azure</span><span class="sxs-lookup"><span data-stu-id="a3d9e-106">Azure</span></span>

<span data-ttu-id="a3d9e-107">Utilice Microsoft Azure para crear los secretos para el almacén de claves y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="a3d9e-108">Luego utilice los secretos en la configuración del complemento de Facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="a3d9e-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="a3d9e-109">Lifecycle Services</span></span>

<span data-ttu-id="a3d9e-110">Utilice Microsoft Dynamics Lifecycle Services (LCS) para habilitar el complemento de los microservicios para su proyecto de implementación de LCS.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

<span data-ttu-id="a3d9e-111">En LCS, seleccione el mosaico **Gestión de funciones de versión preliminar** y luego active la característica **Servicio de facturación electrónica**.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-111">In LCS, select the **Preview feature management** tile, and then turn on the **e-Invoicing Service** feature.</span></span>

## <a name="regulatory-configuration-services"></a><span data-ttu-id="a3d9e-112">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="a3d9e-112">Regulatory Configuration Services</span></span>

<span data-ttu-id="a3d9e-113">Dynamics 365 Regulatory Configuration Services (RCS) es la interfaz para configurar el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-113">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="a3d9e-114">Los recursos, como los entornos y las funciones de facturación electrónica se crean, mantienen y alojan en RCS.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-114">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="a3d9e-115">Cuando los recursos están listos, se publican en el servicio adicional de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-115">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="a3d9e-116">Para más información sobre RCS, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="a3d9e-116">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="a3d9e-117">Integración con el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="a3d9e-117">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="a3d9e-118">Antes de poder utilizar RCS para configurar facturas electrónicas, debe configurar RCS para permitir la comunicación con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-118">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="a3d9e-119">Complete esta configuración en la pestaña **Complemento de facturación electrónica** de la página **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-119">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="a3d9e-120">Extremo del servicio</span><span class="sxs-lookup"><span data-stu-id="a3d9e-120">Service endpoint</span></span>

<span data-ttu-id="a3d9e-121">La URL del punto de conexión del complemento de facturación electrónica puede variar según la geografía del centro de datos de Azure.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-121">The URL of the Electronic invoicing add-on endpoint can vary according to the Azure datacenter geography.</span></span> <span data-ttu-id="a3d9e-122">La siguiente tabla enumera la disponibilidad por región:</span><span class="sxs-lookup"><span data-stu-id="a3d9e-122">The following table lists the availability per region:</span></span>

| <span data-ttu-id="a3d9e-123">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="a3d9e-123">Azure datacenter geography</span></span> | <span data-ttu-id="a3d9e-124">URL de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="a3d9e-124">Service endpoint URL</span></span>                                                       |
|----------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="a3d9e-125">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-125">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="a3d9e-126">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-126">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="a3d9e-127">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="a3d9e-127">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="a3d9e-128">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="a3d9e-128">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a><span data-ttu-id="a3d9e-129">Id. de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a3d9e-129">Application ID</span></span>

<span data-ttu-id="a3d9e-130">El id. de la aplicación es el id. de la aplicación de complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-130">The application ID is the ID of the Electronic invoicing add-on application.</span></span> <span data-ttu-id="a3d9e-131">En este caso, el valor es fijo: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-131">In this case, the value is fixed: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

#### <a name="lcs-environment-id"></a><span data-ttu-id="a3d9e-132">Id. de entorno LCS</span><span class="sxs-lookup"><span data-stu-id="a3d9e-132">LCS environment ID</span></span>

<span data-ttu-id="a3d9e-133">El id. del entorno de LCS es el id. de la suscripción LCS de su organización.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-133">The LCS environment ID is the ID of your organization's LCS subscription.</span></span>

### <a name="service-environments"></a><span data-ttu-id="a3d9e-134">Entornos de servicio</span><span class="sxs-lookup"><span data-stu-id="a3d9e-134">Service environments</span></span>

<span data-ttu-id="a3d9e-135">Los entornos de servicio son particiones lógicas que se crean para respaldar la ejecución de las funciones de facturación electrónica del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-135">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="a3d9e-136">Los secretos de seguridad y los certificados digitales, y la gobernanza (es decir, los permisos de acceso), deben configurarse en el nivel del entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-136">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="a3d9e-137">Los clientes pueden crear tantos entornos de servicio como deseen.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-137">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="a3d9e-138">Todos los entornos de servicio que crea un cliente son independientes entre sí.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-138">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="a3d9e-139">Los entornos de servicio deben crearse y mantenerse en RCS.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-139">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="a3d9e-140">Cuando los entornos de servicio están listos, deben publicarse en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-140">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="a3d9e-141">Estado de entornos de servicio</span><span class="sxs-lookup"><span data-stu-id="a3d9e-141">Service environment status</span></span>

<span data-ttu-id="a3d9e-142">Los entornos de servicio se pueden gestionar a través del estado.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-142">Service environments can be managed through status.</span></span> <span data-ttu-id="a3d9e-143">Las posibles opciones son:</span><span class="sxs-lookup"><span data-stu-id="a3d9e-143">The possible options are:</span></span>

- <span data-ttu-id="a3d9e-144">**No publicado**: se ha creado el entorno, pero aún no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-144">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="a3d9e-145">**Publicado**: se ha publicado el entorno en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-145">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="a3d9e-146">**Cambiado**: se han cambiado los atributos de un entorno publicado, pero los cambios aún no se han publicado.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-146">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="a3d9e-147">Secretos del cliente</span><span class="sxs-lookup"><span data-stu-id="a3d9e-147">Customer secrets</span></span>

<span data-ttu-id="a3d9e-148">El servicio adicional de facturación electrónica es responsable de almacenar todos sus datos comerciales en los recursos de Azure que son propiedad de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-148">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="a3d9e-149">Para asegurarse de que el servicio funcione correctamente y de que solo el complemento acceda a todos los datos comerciales requeridos y generados por el complemento de facturación electrónica, debe crear dos recursos principales de Azure:</span><span class="sxs-lookup"><span data-stu-id="a3d9e-149">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="a3d9e-150">Una cuenta de almacenamiento de Azure (Blob Storage) que almacenará facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="a3d9e-150">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="a3d9e-151">Un almacén de claves de Azure que almacenará certificados y el identificador uniforme de recursos (URI) de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="a3d9e-151">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="a3d9e-152">Se debe asignar un almacén de claves dedicado y una cuenta de almacenamiento de cliente específicamente para su uso con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-152">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="a3d9e-153">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="a3d9e-153">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="a3d9e-154">Usuarios</span><span class="sxs-lookup"><span data-stu-id="a3d9e-154">Users</span></span>

<span data-ttu-id="a3d9e-155">Cada entorno de servicio debe enumerar los usuarios que pueden conectarse desde Dynamics 365 Finance y Dynamics 365 Supply Chain Management en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-155">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="a3d9e-156">Publicación</span><span class="sxs-lookup"><span data-stu-id="a3d9e-156">Publication</span></span>

<span data-ttu-id="a3d9e-157">Antes de poder utilizarse, los entornos de servicio deben publicarse en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-157">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="a3d9e-158">Finance and Supply Chain Management solo puede acceder a los entornos publicados.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-158">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="a3d9e-159">Además, se debe publicar un entorno de servicio antes de que cualquier actualización de sus atributos entre en vigor en el servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-159">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="a3d9e-160">Solicitudes conectadas</span><span class="sxs-lookup"><span data-stu-id="a3d9e-160">Connected applications</span></span>

<span data-ttu-id="a3d9e-161">Las aplicaciones conectadas son las instancias de Finance y Supply Chain Management a las que quizás desee acceder a través de RCS.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-161">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="a3d9e-162">Además de la URL de la aplicación y su inquilino, una aplicación conectada contiene las credenciales que permiten que RCS se conecte al entorno.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-162">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="a3d9e-163">A través de las aplicaciones conectadas, puede configurar parte de la función de facturación electrónica en Finance y Supply Chain Management para que funcione toda la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-163">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="a3d9e-164">Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a3d9e-164">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="a3d9e-165">Integración con el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="a3d9e-165">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="a3d9e-166">Antes de poder utilizar Finance y Supply Chain Management para emitir facturas electrónicas a través del complemento de facturación electrónica, el complemento debe configurarse para permitir la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-166">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="a3d9e-167">Característica de integración del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="a3d9e-167">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="a3d9e-168">Para habilitar la comunicación entre Finance y Supply Chain Management y el complemento de facturación electrónica, debe activar la característica **Integración complementaria de facturación electrónica** en el espacio de trabajo **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-168">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="a3d9e-169">Extremo del servicio</span><span class="sxs-lookup"><span data-stu-id="a3d9e-169">Service endpoint</span></span>

<span data-ttu-id="a3d9e-170">El punto de conexión de servicio es la URL donde se encuentra el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-170">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="a3d9e-171">Antes de poder emitir facturas electrónicas, el punto de conexión de servicio debe configurarse en Finance y Supply Chain Management para permitir la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-171">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="a3d9e-172">Para configurar el punto de conexión de servicio, vaya a **Administración de la organización \> Preparar \> Parámetro de documento electrónico** y luego, en la pestaña **Servicios de envío**, en el campo **URL del complemento de facturación electrónica**, introduzca la URL como se describe en la sección **Punto de conexión de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-172">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="a3d9e-173">Entornos</span><span class="sxs-lookup"><span data-stu-id="a3d9e-173">Environments</span></span>

<span data-ttu-id="a3d9e-174">El nombre del entorno que se introduce en Finance y Supply Chain Management hace referencia al nombre del entorno que se crea en RCS y se publica en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-174">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="a3d9e-175">El entorno debe configurarse en la pestaña **Servicios de envío** de la página **Parámetro de documento electrónico**, de modo que cada solicitud para emitir facturas electrónicas contenga el entorno donde el complemento de facturación electrónica pueda determinar qué función de facturación electrónica debe procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a3d9e-175">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3d9e-176">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a3d9e-176">Additional resources</span></span>

- [<span data-ttu-id="a3d9e-177">Configurar facturas electrónicas en RCS</span><span class="sxs-lookup"><span data-stu-id="a3d9e-177">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="a3d9e-178">Emitir facturas electrónicas en Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a3d9e-178">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
