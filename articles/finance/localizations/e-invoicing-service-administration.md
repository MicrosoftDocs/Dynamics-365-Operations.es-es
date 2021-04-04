---
title: Componentes de administración del complemento de facturación electrónica
description: Este tema proporciona información sobre los componentes relacionados con la administración del complemento de facturación electrónica.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 70ef47dd45200a14c9d780f3c280c554d0e52ac3
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592583"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="83491-103">Componentes de administración del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="83491-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="83491-104">Este tema proporciona información sobre los componentes relacionados con la administración del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="83491-105">También proporciona información sobre cómo configurar el servicio adicional de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="83491-106">Azure</span><span class="sxs-lookup"><span data-stu-id="83491-106">Azure</span></span>

<span data-ttu-id="83491-107">Utilice Microsoft Azure para crear los secretos para el almacén de claves y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="83491-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="83491-108">Luego utilice los secretos en la configuración del complemento de Facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="83491-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="83491-109">Lifecycle Services</span></span>

<span data-ttu-id="83491-110">Utilice Microsoft Dynamics Lifecycle Services (LCS) para habilitar el complemento de los microservicios para su proyecto de implementación de LCS.</span><span class="sxs-lookup"><span data-stu-id="83491-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="83491-111">La instalación del complemento de microservicio en LCS requiere al menos una máquina virtual de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="83491-111">The installation of the microservice add-on in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="83491-112">Para obtener más información sobre planificación de ambientes, consulte [Planificación de ambientes](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="83491-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="83491-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="83491-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="83491-114">Dynamics 365 Regulatory Configuration Services (RCS) es la interfaz para configurar el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="83491-115">Los recursos, como los entornos y las funciones de facturación electrónica se crean, mantienen y alojan en RCS.</span><span class="sxs-lookup"><span data-stu-id="83491-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="83491-116">Cuando los recursos están listos, se publican en el servicio adicional de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-116">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="83491-117">Para registrarse en RCS, consulte [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="83491-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="83491-118">Para más información sobre RCS, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="83491-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="83491-119">Integración con el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="83491-119">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="83491-120">Antes de poder utilizar RCS para configurar facturas electrónicas, debe configurar RCS para permitir la comunicación con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="83491-121">Complete esta configuración en la pestaña **Complemento de facturación electrónica** de la página **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="83491-121">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="83491-122">Extremo del servicio</span><span class="sxs-lookup"><span data-stu-id="83491-122">Service endpoint</span></span>

<span data-ttu-id="83491-123">El complemento de facturación electrónica está disponible en diversas geografías de centros de datos de Azure.</span><span class="sxs-lookup"><span data-stu-id="83491-123">The Electronic invoicing add-on is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="83491-124">La siguiente tabla enumera la disponibilidad por región.</span><span class="sxs-lookup"><span data-stu-id="83491-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="83491-125">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="83491-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="83491-126">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="83491-126">East US</span></span>                    |
| <span data-ttu-id="83491-127">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="83491-127">West US</span></span>                    |
| <span data-ttu-id="83491-128">Norte de la UE</span><span class="sxs-lookup"><span data-stu-id="83491-128">North EU</span></span>                   |
| <span data-ttu-id="83491-129">Oeste de la UE</span><span class="sxs-lookup"><span data-stu-id="83491-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="83491-130">Entornos de servicio</span><span class="sxs-lookup"><span data-stu-id="83491-130">Service environments</span></span>

<span data-ttu-id="83491-131">Los entornos de servicio son particiones lógicas que se crean para respaldar la ejecución de las funciones de facturación electrónica del complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="83491-132">Los secretos de seguridad y los certificados digitales, y la gobernanza (es decir, los permisos de acceso), deben configurarse en el nivel del entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="83491-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="83491-133">Los clientes pueden crear tantos entornos de servicio como deseen.</span><span class="sxs-lookup"><span data-stu-id="83491-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="83491-134">Todos los entornos de servicio que crea un cliente son independientes entre sí.</span><span class="sxs-lookup"><span data-stu-id="83491-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="83491-135">Los entornos de servicio deben crearse y mantenerse en RCS.</span><span class="sxs-lookup"><span data-stu-id="83491-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="83491-136">Cuando los entornos de servicio están listos, deben publicarse en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-136">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="83491-137">Estado de entornos de servicio</span><span class="sxs-lookup"><span data-stu-id="83491-137">Service environment status</span></span>

<span data-ttu-id="83491-138">Los entornos de servicio se pueden gestionar a través del estado.</span><span class="sxs-lookup"><span data-stu-id="83491-138">Service environments can be managed through status.</span></span> <span data-ttu-id="83491-139">Las posibles opciones son:</span><span class="sxs-lookup"><span data-stu-id="83491-139">The possible options are:</span></span>

- <span data-ttu-id="83491-140">**No publicado**: se ha creado el entorno, pero aún no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="83491-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="83491-141">**Publicado**: se ha publicado el entorno en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-141">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="83491-142">**Cambiado**: se han cambiado los atributos de un entorno publicado, pero los cambios aún no se han publicado.</span><span class="sxs-lookup"><span data-stu-id="83491-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="83491-143">Secretos del cliente</span><span class="sxs-lookup"><span data-stu-id="83491-143">Customer secrets</span></span>

<span data-ttu-id="83491-144">El servicio adicional de facturación electrónica es responsable de almacenar todos sus datos comerciales en los recursos de Azure que son propiedad de su empresa.</span><span class="sxs-lookup"><span data-stu-id="83491-144">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="83491-145">Para asegurarse de que el servicio funcione correctamente y de que solo el complemento acceda a todos los datos comerciales requeridos y generados por el complemento de facturación electrónica, debe crear dos recursos principales de Azure:</span><span class="sxs-lookup"><span data-stu-id="83491-145">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="83491-146">Una cuenta de almacenamiento de Azure (Blob Storage) que almacenará facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="83491-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="83491-147">Un almacén de claves de Azure que almacenará certificados y el identificador uniforme de recursos (URI) de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="83491-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="83491-148">Se debe asignar un almacén de claves dedicado y una cuenta de almacenamiento de cliente específicamente para su uso con el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="83491-149">Para más información, consulte [Crear cuenta de almacenamiento de Azure y un almacén de claves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="83491-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="83491-150">Usuarios</span><span class="sxs-lookup"><span data-stu-id="83491-150">Users</span></span>

<span data-ttu-id="83491-151">Cada entorno de servicio debe enumerar los usuarios que pueden conectarse desde Dynamics 365 Finance y Dynamics 365 Supply Chain Management en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="83491-152">Publicación</span><span class="sxs-lookup"><span data-stu-id="83491-152">Publication</span></span>

<span data-ttu-id="83491-153">Antes de poder utilizarse, los entornos de servicio deben publicarse en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-153">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="83491-154">Finance and Supply Chain Management solo puede acceder a los entornos publicados.</span><span class="sxs-lookup"><span data-stu-id="83491-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="83491-155">Además, se debe publicar un entorno de servicio antes de que cualquier actualización de sus atributos entre en vigor en el servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="83491-156">Solicitudes conectadas</span><span class="sxs-lookup"><span data-stu-id="83491-156">Connected applications</span></span>

<span data-ttu-id="83491-157">Las aplicaciones conectadas son las instancias de Finance y Supply Chain Management a las que quizás desee acceder a través de RCS.</span><span class="sxs-lookup"><span data-stu-id="83491-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="83491-158">Además de la URL de la aplicación y su inquilino, una aplicación conectada contiene las credenciales que permiten que RCS se conecte al entorno.</span><span class="sxs-lookup"><span data-stu-id="83491-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="83491-159">A través de las aplicaciones conectadas, puede configurar parte de la función de facturación electrónica en Finance y Supply Chain Management para que funcione toda la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="83491-160">Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="83491-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="83491-161">Integración con el complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="83491-161">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="83491-162">Antes de poder utilizar Finance y Supply Chain Management para emitir facturas electrónicas a través del complemento de facturación electrónica, el complemento debe configurarse para permitir la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="83491-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="83491-163">Característica de integración del complemento de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="83491-163">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="83491-164">Para habilitar la comunicación entre Finance y Supply Chain Management y el complemento de facturación electrónica, debe activar la característica **Integración complementaria de facturación electrónica** en el espacio de trabajo **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="83491-164">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="83491-165">Extremo del servicio</span><span class="sxs-lookup"><span data-stu-id="83491-165">Service endpoint</span></span>

<span data-ttu-id="83491-166">El punto de conexión de servicio es la URL donde se encuentra el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-166">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="83491-167">Antes de poder emitir facturas electrónicas, el punto de conexión de servicio debe configurarse en Finance y Supply Chain Management para permitir la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="83491-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="83491-168">Para configurar el punto de conexión de servicio, vaya a **Administración de la organización \> Preparar \> Parámetro de documento electrónico** y luego, en la pestaña **Servicios de envío**, en el campo **URL del complemento de facturación electrónica**, introduzca la URL como se describe en la sección **Punto de conexión de servicio**.</span><span class="sxs-lookup"><span data-stu-id="83491-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="83491-169">Entornos</span><span class="sxs-lookup"><span data-stu-id="83491-169">Environments</span></span>

<span data-ttu-id="83491-170">El nombre del entorno que se introduce en Finance y Supply Chain Management hace referencia al nombre del entorno que se crea en RCS y se publica en el complemento de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="83491-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="83491-171">El entorno debe configurarse en la pestaña **Servicios de envío** de la página **Parámetro de documento electrónico**, de modo que cada solicitud para emitir facturas electrónicas contenga el entorno donde el complemento de facturación electrónica pueda determinar qué función de facturación electrónica debe procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="83491-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83491-172">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="83491-172">Additional resources</span></span>

- [<span data-ttu-id="83491-173">Configurar facturas electrónicas en RCS</span><span class="sxs-lookup"><span data-stu-id="83491-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="83491-174">Emitir facturas electrónicas en Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="83491-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
