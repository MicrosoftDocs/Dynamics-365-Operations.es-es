---
title: Componentes de administración de facturación electrónica
description: Este tema proporciona información sobre los componentes relacionados con la administración de la facturación electrónica.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 081d23c85d3555210b54597920a49e800ffe284b
ms.sourcegitcommit: 35fdcc6501e099c54a58583b1e3aba16f02a5ccc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5980933"
---
# <a name="electronic-invoicing-administration-components"></a><span data-ttu-id="6c0ff-103">Componentes de administración de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="6c0ff-103">Electronic invoicing administration components</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6c0ff-104">Este tema proporciona información sobre los componentes relacionados con la administración de la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-104">This topic provides information about the components that are related to administration of Electronic invoicing.</span></span> <span data-ttu-id="6c0ff-105">También proporciona información sobre cómo configurar el servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-105">It also provides information about how to configure the Electronic invoicing service.</span></span>

## <a name="azure"></a><span data-ttu-id="6c0ff-106">Azure</span><span class="sxs-lookup"><span data-stu-id="6c0ff-106">Azure</span></span>

<span data-ttu-id="6c0ff-107">Utilice Microsoft Azure para crear los secretos para el Key Vault y la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-107">Use Microsoft Azure to create the secrets for the Key Vault and storage account.</span></span> <span data-ttu-id="6c0ff-108">Luego, utilice los secretos de la configuración de la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-108">Then use the secrets in the configuration of Electronic invoicing.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="6c0ff-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="6c0ff-109">Lifecycle Services</span></span>

<span data-ttu-id="6c0ff-110">Utilice Microsoft Dynamics Lifecycle Services (LCS) para habilitar los microservicios para su proyecto de implementación de LCS.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="6c0ff-111">La instalación del microservicio en LCS requiere al menos una máquina virtual de nivel 2.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-111">The installation of the microservice in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="6c0ff-112">Para obtener más información sobre planificación de ambientes, consulte [Planificación de ambientes](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="6c0ff-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="6c0ff-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="6c0ff-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="6c0ff-114">Dynamics 365 Regulatory Configuration Services (RCS) es la interfaz que se utiliza para configurar la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure Electronic invoicing.</span></span> <span data-ttu-id="6c0ff-115">Los recursos, como los entornos y las funciones de facturación electrónica se crean, mantienen y alojan en RCS.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="6c0ff-116">Cuando los recursos están listos, se publican en el servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-116">When the resources are ready, they are published to Electronic invoicing service.</span></span>

<span data-ttu-id="6c0ff-117">Para registrarse en RCS, consulte [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="6c0ff-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="6c0ff-118">Para más información sobre RCS, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="6c0ff-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="6c0ff-119">Integración con la facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="6c0ff-119">Integration with Electronic invoicing</span></span> 

<span data-ttu-id="6c0ff-120">Antes de poder utilizar RCS para configurar facturas electrónicas, debe configurar RCS para permitir la comunicación con la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with Electronic invoicing.</span></span> <span data-ttu-id="6c0ff-121">Puede completar esta configuración en la pestaña **Facturación electrónica** de la página **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-121">You complete this configuration on the **Electronic invoicing** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="6c0ff-122">Extremo del servicio</span><span class="sxs-lookup"><span data-stu-id="6c0ff-122">Service endpoint</span></span>

<span data-ttu-id="6c0ff-123">La facturación electrónica está disponible en diversas geografías de centros de datos de Azure.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-123">Electronic invoicing is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="6c0ff-124">La siguiente tabla enumera la disponibilidad por región.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="6c0ff-125">Geografía de centros de datos de Azure</span><span class="sxs-lookup"><span data-stu-id="6c0ff-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="6c0ff-126">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="6c0ff-126">United States</span></span>              |
| <span data-ttu-id="6c0ff-127">Europa</span><span class="sxs-lookup"><span data-stu-id="6c0ff-127">Europe</span></span>                     |
| <span data-ttu-id="6c0ff-128">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="6c0ff-128">United Kingdom</span></span>             |
| <span data-ttu-id="6c0ff-129">Asia</span><span class="sxs-lookup"><span data-stu-id="6c0ff-129">Asia</span></span>                       |

### <a name="service-environments"></a><span data-ttu-id="6c0ff-130">Entornos de servicio</span><span class="sxs-lookup"><span data-stu-id="6c0ff-130">Service environments</span></span>

<span data-ttu-id="6c0ff-131">Los entornos de servicio son particiones lógicas que se crean para respaldar la ejecución de las características de facturación electrónica en la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in Electronic invoicing.</span></span> <span data-ttu-id="6c0ff-132">Los secretos de seguridad y los certificados digitales, y la gobernanza (es decir, los permisos de acceso), deben configurarse en el nivel del entorno de servicio.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="6c0ff-133">Los clientes pueden crear tantos entornos de servicio como deseen.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="6c0ff-134">Todos los entornos de servicio que crea un cliente son independientes entre sí.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="6c0ff-135">Los entornos de servicio deben crearse y mantenerse en RCS.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="6c0ff-136">Cuando los ambientes de servicio están listos, deben publicarse en la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-136">When the service environments are ready, they must be published to Electronic invoicing.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="6c0ff-137">Estado de entornos de servicio</span><span class="sxs-lookup"><span data-stu-id="6c0ff-137">Service environment status</span></span>

<span data-ttu-id="6c0ff-138">Los entornos de servicio se pueden gestionar a través del estado.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-138">Service environments can be managed through status.</span></span> <span data-ttu-id="6c0ff-139">Las posibles opciones son:</span><span class="sxs-lookup"><span data-stu-id="6c0ff-139">The possible options are:</span></span>

- <span data-ttu-id="6c0ff-140">**No publicado**: se ha creado el entorno, pero aún no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="6c0ff-141">**Publicado**: se ha publicado el ambiente en la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-141">**Published** – The environment has been published to Electronic invoicing .</span></span>
- <span data-ttu-id="6c0ff-142">**Cambiado**: se han cambiado los atributos de un entorno publicado, pero los cambios aún no se han publicado.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="6c0ff-143">Secretos del cliente</span><span class="sxs-lookup"><span data-stu-id="6c0ff-143">Customer secrets</span></span>

<span data-ttu-id="6c0ff-144">El servicio de facturación electrónica es responsable de almacenar todos sus datos comerciales en los recursos de Azure que son propiedad de su empresa.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-144">The Electronic invoicing service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="6c0ff-145">Para asegurarse de que el servicio funcione correctamente y de que solo la facturación electrónica acceda a todos los datos comerciales necesarios y generados por ella, debe crear dos recursos principales de Azure:</span><span class="sxs-lookup"><span data-stu-id="6c0ff-145">To ensure that the service works correctly, and that all the business data that is required for and generated by Electronic invoicing is accessed appropriately, you must create two main Azure resources:</span></span>

- <span data-ttu-id="6c0ff-146">Una cuenta de almacenamiento de Azure (Blob Storage) que almacenará facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="6c0ff-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="6c0ff-147">Un Azure Key Vault que almacenará certificados y el identificador uniforme de recursos (URI) de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6c0ff-147">An Azure Key Vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>


<span data-ttu-id="6c0ff-148">Se debe asignar un Key Vault dedicado y una cuenta de almacenamiento de cliente específicamente para su uso con la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-148">A dedicated Key Vault and customer storage account must be allocated specifically for use with Electronic Invoicing.</span></span> <span data-ttu-id="6c0ff-149">Para más información, consulte [Crear una cuenta de almacenamiento de Azure y un Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="6c0ff-149">For more information, see [Create an Azure storage account and a Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

<span data-ttu-id="6c0ff-150">Para supervisar el estado de su Key Vault y recibir alertas, configure Azure Monitor para Key Vault.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-150">To monitor the health of your Key Vault and receive alerts, configure the Azure Monitor for key Vault.</span></span> <span data-ttu-id="6c0ff-151">Al habilitar el registro de Key Vault, puede controlar cómo, cuándo y quién accede a sus Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-151">By enabling Key Vault logging, you can monitor how, when, and by whom your Key Vaults are accessed.</span></span> <span data-ttu-id="6c0ff-152">Para más información, consulte [Supervisión y alerta para Azure Key Vault](/azure/key-vault/general/alert) y [Cómo habilitar el registro de Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).</span><span class="sxs-lookup"><span data-stu-id="6c0ff-152">For more information, see [Monitoring and alerting for Azure Key Vault](/azure/key-vault/general/alert) and [How to enable Key Vault logging](/azure/key-vault/general/howto-logging?tabs=azure-cli).</span></span>

<span data-ttu-id="6c0ff-153">Como práctica recomendada, rote periódicamente los secretos.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-153">As a best practice, periodically rotate the secrets.</span></span> <span data-ttu-id="6c0ff-154">Para obtener más información, consulte [Documentación de secretos](/azure/key-vault/secrets/).</span><span class="sxs-lookup"><span data-stu-id="6c0ff-154">For more information, see [Secrets documentation](/azure/key-vault/secrets/).</span></span>

#### <a name="users"></a><span data-ttu-id="6c0ff-155">Usuarios</span><span class="sxs-lookup"><span data-stu-id="6c0ff-155">Users</span></span>

<span data-ttu-id="6c0ff-156">Cada entorno de servicio debe enumerar los usuarios que pueden conectarse desde Dynamics 365 Finance y Dynamics 365 Supply Chain Management en la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-156">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in Electronic invoicing.</span></span>

#### <a name="publication"></a><span data-ttu-id="6c0ff-157">Publicación</span><span class="sxs-lookup"><span data-stu-id="6c0ff-157">Publication</span></span>

<span data-ttu-id="6c0ff-158">Antes de poder utilizarse, los entornos de servicio deben publicarse en la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-158">Service environments must be published to Electronic invoicing before they can be used.</span></span> <span data-ttu-id="6c0ff-159">Finance and Supply Chain Management solo puede acceder a los entornos publicados.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-159">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="6c0ff-160">Además, se debe publicar un entorno de servicio antes de que cualquier actualización de sus atributos entre en vigor en el servicio de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-160">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="6c0ff-161">Solicitudes conectadas</span><span class="sxs-lookup"><span data-stu-id="6c0ff-161">Connected applications</span></span>

<span data-ttu-id="6c0ff-162">Las aplicaciones conectadas son las instancias de Finance y Supply Chain Management a las que quizás desee acceder a través de RCS.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-162">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="6c0ff-163">Además de la URL de la aplicación y su inquilino, una aplicación conectada contiene las credenciales que permiten que RCS se conecte al entorno.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-163">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="6c0ff-164">A través de las aplicaciones conectadas, puede configurar parte de la función de facturación electrónica en Finance y Supply Chain Management para que funcione toda la función de facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-164">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="6c0ff-165">Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6c0ff-165">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="6c0ff-166">Integración con la facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="6c0ff-166">Integration with Electronic invoicing</span></span>

<span data-ttu-id="6c0ff-167">Antes de poder utilizar Finance y Supply Chain Management para emitir facturas electrónicas a través de la facturación electrónica, esta debe configurarse para permitir la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-167">Before you can use Finance and Supply Chain Management to issue electronic invoices through Electronic invoicing, it must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-integration-feature"></a><span data-ttu-id="6c0ff-168">Característica de integración de facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="6c0ff-168">Electronic invoicing integration feature</span></span>

<span data-ttu-id="6c0ff-169">Para habilitar la comunicación entre Finance y Supply Chain Management y la facturación electrónica, debe activar la característica **Integración de facturación electrónica** en el espacio de trabajo **Gestión de características**.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-169">To enable communication between Finance and Supply Chain Management and Electronic invoicing, you must turn on the **Electronic Invoicing integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="6c0ff-170">Extremo del servicio</span><span class="sxs-lookup"><span data-stu-id="6c0ff-170">Service endpoint</span></span>

<span data-ttu-id="6c0ff-171">El punto de conexión de servicio es la URL donde se encuentra la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-171">The service endpoint is the URL where Electronic invoicing is located.</span></span> <span data-ttu-id="6c0ff-172">Antes de poder emitir facturas electrónicas, el punto de conexión de servicio debe configurarse en Finance y Supply Chain Management para permitir la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-172">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="6c0ff-173">Para configurar el punto de conexión de servicio, vaya a **Administración de la organización \> Configurar \> Parámetro de documento electrónico** y luego, en la pestaña **Servicios de envío**, en el campo **URL de facturación electrónica**, introduzca la URL como se describe en la sección **Punto de conexión de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-173">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="6c0ff-174">Entornos</span><span class="sxs-lookup"><span data-stu-id="6c0ff-174">Environments</span></span>

<span data-ttu-id="6c0ff-175">El nombre del entorno que se introduce en Finance y Supply Chain Management hace referencia al nombre del entorno que se crea en RCS y se publica en la facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-175">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to Electronic invoicing.</span></span>

<span data-ttu-id="6c0ff-176">El ambiente debe configurarse en la pestaña **Servicios de envío** de la página **Parámetro de documento electrónico**, de modo que cada solicitud para emitir facturas electrónicas contenga el ambiente donde la facturación electrónica pueda determinar qué característica de facturación electrónica debe procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6c0ff-176">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where Electronic invoicing can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c0ff-177">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6c0ff-177">Additional resources</span></span>

- [<span data-ttu-id="6c0ff-178">Configurar facturas electrónicas en RCS</span><span class="sxs-lookup"><span data-stu-id="6c0ff-178">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="6c0ff-179">Emitir facturas electrónicas en Finance y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6c0ff-179">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
