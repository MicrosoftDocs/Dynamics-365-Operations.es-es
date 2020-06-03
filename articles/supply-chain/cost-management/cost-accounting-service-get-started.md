---
title: Introducción al servicio de contabilidad de costes (vista previa privada)
description: Este tema proporciona detalles sobre licencias e instrucciones de instalación para el servicio de contabilidad de costes.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: a82af9e8ec1806f470103897389d0316d33a4a06
ms.sourcegitcommit: 7fec9dc5297ed6e687d4a0dff099922d59d6a830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "3372745"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a><span data-ttu-id="bdc42-103">Introducción al servicio de contabilidad de costes (vista previa privada)</span><span class="sxs-lookup"><span data-stu-id="bdc42-103">Get started with the cost accounting service (private preview)</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="bdc42-104">La funcionalidad que se describe en este tema está disponible como parte de una versión preliminar privada.</span><span class="sxs-lookup"><span data-stu-id="bdc42-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="bdc42-105">El contenido de este tema y la funcionalidad que describe están sujetos a cambios.</span><span class="sxs-lookup"><span data-stu-id="bdc42-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="bdc42-106">Para obtener más información acerca las versiones preliminares, consulte [Preguntas frecuentes sobre actualizaciones del servicio de una versión](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="bdc42-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="bdc42-107">El servicio de contabilidad de costos le permite realizar múltiples inventarios en los libros de contabilidad de costos que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="bdc42-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="bdc42-108">Usted asocia cada libro de contabilidad de costos a una *convención*.</span><span class="sxs-lookup"><span data-stu-id="bdc42-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="bdc42-109">Una convención es una colección de los siguientes tipos de directivas contables:</span><span class="sxs-lookup"><span data-stu-id="bdc42-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="bdc42-110">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="bdc42-110">Cost object</span></span>
- <span data-ttu-id="bdc42-111">Base de medida de entrada</span><span class="sxs-lookup"><span data-stu-id="bdc42-111">Input measurement basis</span></span>
- <span data-ttu-id="bdc42-112">Suposición de flujo de costes</span><span class="sxs-lookup"><span data-stu-id="bdc42-112">Cost flow assumption</span></span>
- <span data-ttu-id="bdc42-113">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="bdc42-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="bdc42-114">Incluso después de haber activado el servicio de contabilidad de costos, aún puede hacer contabilidad de inventario en Microsoft Dynamics 365 Supply Chain Management, como siempre.</span><span class="sxs-lookup"><span data-stu-id="bdc42-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="bdc42-115">El servicio de contabilidad de costos es un complemento.</span><span class="sxs-lookup"><span data-stu-id="bdc42-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="bdc42-116">Para que sus funciones estén disponibles, debe instalarlo desde Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="bdc42-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="bdc42-117">Por lo tanto, puede elegir evaluarlo en un entorno de prueba antes de activarlo para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="bdc42-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="bdc42-118">El servicio de contabilidad de costos no admite actualmente todas las funciones de administración de costos integradas en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bdc42-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="bdc42-119">Por lo tanto, es importante que evalúe si el conjunto de funciones que están disponibles actualmente cumplirá sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="bdc42-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a><span data-ttu-id="bdc42-120">Cómo obtener el servicio de contabilidad de costes (vista previa privada)</span><span class="sxs-lookup"><span data-stu-id="bdc42-120">How to get the cost accounting service (private preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdc42-121">Para usar el servicio de contabilidad de costos, debe tener un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox), y debe estar ejecutando Dynamics 365 Supply Chain Management versión 10.0.11 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bdc42-121">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="bdc42-122">Para suscribirse a la vista previa privada del servicio de contabilidad de costes, envíe su id. de entorno LCS por correo electrónico a [Servicio de contabilidad de costes (vista previa privada)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span><span class="sxs-lookup"><span data-stu-id="bdc42-122">To sign up for the cost accounting service private preview, please send your LCS environment ID by email to [Cost accounting service (private preview)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span></span> <span data-ttu-id="bdc42-123">Al admitirle en el programa, le enviaremos un correo electrónico de seguimiento que contendrá una clave beta del servicio de contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="bdc42-123">On approving you for the program, we will send you a follow up email that contains a cost accounting service beta key.</span></span> <span data-ttu-id="bdc42-124">Al recibir la clave beta, puede continuar [instalando el complemento](#install).</span><span class="sxs-lookup"><span data-stu-id="bdc42-124">On receiving the beta key, you can proceed by [installing the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="bdc42-125">Licencias</span><span class="sxs-lookup"><span data-stu-id="bdc42-125">Licensing</span></span>

<span data-ttu-id="bdc42-126">El servicio de contabilidad de costos tiene licencia junto con las funciones estándar de la contabilidad de inventario que están disponibles para Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bdc42-126">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="bdc42-127">No tiene que comprar una licencia adicional para usar el servicio de contabilidad de costos.</span><span class="sxs-lookup"><span data-stu-id="bdc42-127">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="bdc42-128">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="bdc42-128">Install the add-in</span></span>

<span data-ttu-id="bdc42-129">Para usar el servicio de contabilidad de costos, instale el complemento de servicio de contabilidad de costos para Supply Chain Management como se describe en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bdc42-129">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="bdc42-130">[Registrarse](#sign-up) para obtener el servicio de contabilidad de costes (vista previa privada).</span><span class="sxs-lookup"><span data-stu-id="bdc42-130">[Sign up](#sign-up) for the cost accounting service (private preview).</span></span>

1. <span data-ttu-id="bdc42-131">Inicie sesión en LCS.</span><span class="sxs-lookup"><span data-stu-id="bdc42-131">Sign in to LCS.</span></span>

1. <span data-ttu-id="bdc42-132">Vaya a **Administración de funciones de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-132">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="bdc42-133">Seleccione el signo más (**+**).</span><span class="sxs-lookup"><span data-stu-id="bdc42-133">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="bdc42-134">En el campo **Código**, introduzca su clave beta de complemento para el servicio de contabilidad de costos.</span><span class="sxs-lookup"><span data-stu-id="bdc42-134">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="bdc42-135">(Debería haber recibido su clave por correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="bdc42-135">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="bdc42-136">Seleccione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-136">Select **Unblock**.</span></span>

1. <span data-ttu-id="bdc42-137">Abra el entorno LCS donde desea agregar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bdc42-137">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="bdc42-138">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-138">Go to **Full details**.</span></span>

1. <span data-ttu-id="bdc42-139">Desplácese hacia abajo hasta la ficha desplegable **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-139">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="bdc42-140">Seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-140">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="bdc42-141">Seleccione **Servicio de contabilidad de costos**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-141">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="bdc42-142">Siga la guía de instalación y acepte los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="bdc42-142">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="bdc42-143">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-143">Select **Install**.</span></span>

1. <span data-ttu-id="bdc42-144">En la ficha desplegable **Complementos de entorno**, debería ver que se está instalando el servicio de contabilidad de costos.</span><span class="sxs-lookup"><span data-stu-id="bdc42-144">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="bdc42-145">Después de unos minutos, el estado debería cambiar de **Instalando** a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-145">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="bdc42-146">(Es posible que tenga que actualizar la página para ver este cambio). En ese momento, el servicio de contabilidad de costos está listo para usar.</span><span class="sxs-lookup"><span data-stu-id="bdc42-146">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="bdc42-147">Configuración de la integración</span><span class="sxs-lookup"><span data-stu-id="bdc42-147">Set up the integration</span></span>

<span data-ttu-id="bdc42-148">Para configurar la integración entre el servicio de contabilidad de costos y Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="bdc42-148">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="bdc42-149">Vaya a **Administración del sistema > Administración de funciones**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-149">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="bdc42-150">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-150">Select **Check for updates**.</span></span>

1. <span data-ttu-id="bdc42-151">Abra la pestaña **Todas** y busque la función denominada *Servicio de contabilidad de costos*.</span><span class="sxs-lookup"><span data-stu-id="bdc42-151">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="bdc42-152">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-152">Select **Enable now**.</span></span>

1. <span data-ttu-id="bdc42-153">Vaya a **Gestión de costes > Servicio de contabilidad de costes > Configuración > Parámetros del servicio de contabilidad de costes > Parámetros de integración**.</span><span class="sxs-lookup"><span data-stu-id="bdc42-153">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="bdc42-154">En el campo **ID de aplicación**, introduzca el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="bdc42-154">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="bdc42-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="bdc42-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="bdc42-156">En el campo **Punto final del servicio de datos**, introduzca la siguiente URL:</span><span class="sxs-lookup"><span data-stu-id="bdc42-156">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="bdc42-157">En el campo **Punto final de contabilidad de costes**, introduzca la siguiente URL:</span><span class="sxs-lookup"><span data-stu-id="bdc42-157">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="bdc42-158">El servicio de contabilidad de costos ahora está listo para usar.</span><span class="sxs-lookup"><span data-stu-id="bdc42-158">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="bdc42-159">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="bdc42-159">Related resources</span></span>

[<span data-ttu-id="bdc42-160">Página principal del servicio de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="bdc42-160">Cost accounting service home page</span></span>](cost-accounting-service-home.md)
