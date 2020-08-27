---
title: Instalar, configurar y actualizar el portal del cliente
description: Este tema proporciona detalles sobre licencias e instrucciones de configuracion del Portal del cliente.
author: dasani-madipalli
manager: tfehr
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 0343100362c4d7bc3e09334fb7890919bdb84941
ms.sourcegitcommit: 7d943499f302298c6ff127f56cecc34af6cee289
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435618"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="1ce1d-103">Instalar, configurar y actualizar el portal del cliente</span><span class="sxs-lookup"><span data-stu-id="1ce1d-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1ce1d-104">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="1ce1d-104">Licensing requirements</span></span>

<span data-ttu-id="1ce1d-105">Para implementar el portal del Cliente, debe tener las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="1ce1d-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="1ce1d-106">**Portales Power Apps**: esta licencia es necesaria para alojar el portal del Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="1ce1d-107">Los portales tienen licencia en función del uso.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="1ce1d-108">Para más información, consulte los [requisitos de licencia de portales Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="1ce1d-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="1ce1d-109">**Doble escritura**: debe tener las licencias necesarias para habilitar la escritura dual para las entidades de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="1ce1d-110">Para obtener más información, consulte los [requisitos del sistema para escritura dual](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="1ce1d-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="1ce1d-111">Dependencias de doble escritura y los portales Power Apps</span><span class="sxs-lookup"><span data-stu-id="1ce1d-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="1ce1d-112">El portal del cliente depende de los portales Power Apps portales y la doble escritura, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

<span data-ttu-id="1ce1d-113">![Dependencias del portal del cliente](media/customer-portal-elements.png "Dependencias del portal del cliente")</span><span class="sxs-lookup"><span data-stu-id="1ce1d-113">![Customer portal dependencies](media/customer-portal-elements.png "Customer portal dependencies")</span></span>

<span data-ttu-id="1ce1d-114">A diferencia de otras características de Supply Chain Management, la plantilla del portal del cliente reside en los portales Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="1ce1d-115">Por lo tanto, el portal del Cliente está limitado por la funcionalidad y las capacidades proporcionadas por los portales Power Apps y las entidades en doble escritura.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="1ce1d-116">Configuración requerida para habilitar el portal del cliente</span><span class="sxs-lookup"><span data-stu-id="1ce1d-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="1ce1d-117">Después de asegurarse de que tiene las licencias requeridas, puede configurar la escritura dual como se describe en [instrucciones de sincronización inicial de doble escritura](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="1ce1d-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="1ce1d-118">Asegúrese de habilitar las siguientes asignaciones de entidades en doble escritura:</span><span class="sxs-lookup"><span data-stu-id="1ce1d-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="1ce1d-119">Encabezado de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="1ce1d-119">Sales Order Header</span></span>
- <span data-ttu-id="1ce1d-120">Detalles de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="1ce1d-120">Sales Order Details</span></span>
- <span data-ttu-id="1ce1d-121">Cuentas</span><span class="sxs-lookup"><span data-stu-id="1ce1d-121">Accounts</span></span>
- <span data-ttu-id="1ce1d-122">Contactos</span><span class="sxs-lookup"><span data-stu-id="1ce1d-122">Contacts</span></span>
- <span data-ttu-id="1ce1d-123">Productos</span><span class="sxs-lookup"><span data-stu-id="1ce1d-123">Products</span></span>

<span data-ttu-id="1ce1d-124">Una vez completada esta configuración, puede aprovisionar la plantilla del portal del Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="1ce1d-125">Aprovisionar el portal del cliente</span><span class="sxs-lookup"><span data-stu-id="1ce1d-125">Provision the Customer portal</span></span>

<span data-ttu-id="1ce1d-126">Antes de comenzar, asegúrese de haber completado la [configuración requerida](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="1ce1d-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="1ce1d-127">Luego, siga estos pasos para aprovisionar el portal del Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="1ce1d-128">Vaya a [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="1ce1d-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="1ce1d-129">Asegúrese de estar utilizando el entorno donde habilitó la escritura dual.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="1ce1d-130">En la pestaña **Crear**, desplácese hacia abajo a la sección **Comenzar desde plantilla** y seleccione la plantilla que se llama **Portal del cliente**.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Customer Portal**.</span></span>
4. <span data-ttu-id="1ce1d-131">Siga las instrucciones en pantalla.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="1ce1d-132">Después de completar el aprovisionamiento, puede acceder al portal del Cliente en la sección **Sus aplicaciones** de la página **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="1ce1d-133">Si la solución de doble escritura no está instalada en el entorno en el que está trabajando, recibirá un mensaje de error y no se aprovisionará el portal del Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="1ce1d-134">Actualizar el portal del cliente</span><span class="sxs-lookup"><span data-stu-id="1ce1d-134">Update the Customer portal</span></span>

<span data-ttu-id="1ce1d-135">Se podría agregar más funcionalidad al portal del Cliente más adelante.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="1ce1d-136">Cualquier cambio que Microsoft realice en los componentes de la solución subyacente aparecerá automáticamente en su entorno.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="1ce1d-137">Sin embargo, el sitio web aprovisionado en su entorno no reflejará automáticamente los cambios realizados en los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="1ce1d-138">Tendrá que aplicar manualmente esos cambios obteniendo el código de la nueva plantilla y fusionándolo con el sitio web aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ce1d-139">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1ce1d-139">Additional resources</span></span>

<span data-ttu-id="1ce1d-140">Para saber cómo puede configurar y personalizar el portal del Cliente, debe comenzar por revisar la siguiente documentación para las tecnologías subyacentes:</span><span class="sxs-lookup"><span data-stu-id="1ce1d-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="1ce1d-141">Documentación de portales Power Apps</span><span class="sxs-lookup"><span data-stu-id="1ce1d-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="1ce1d-142">Documentación de doble escritura</span><span class="sxs-lookup"><span data-stu-id="1ce1d-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="1ce1d-143">Para gestionar eficazmente sus portales, debe conocer los portales Power Apps y el ciclo de vida de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="1ce1d-144">Para obtener más información, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="1ce1d-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="1ce1d-145">Sobre el ciclo de vida del portal</span><span class="sxs-lookup"><span data-stu-id="1ce1d-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="1ce1d-146">Actualizar un portal</span><span class="sxs-lookup"><span data-stu-id="1ce1d-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="1ce1d-147">Migrar la configuración del portal</span><span class="sxs-lookup"><span data-stu-id="1ce1d-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="1ce1d-148">Administración de ciclo de vida de solución: Dynamics 365 para aplicaciones de Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="1ce1d-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)