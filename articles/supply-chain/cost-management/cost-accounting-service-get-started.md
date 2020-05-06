---
title: Introducción al servicio de contabilidad de costes
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
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276960"
---
# <a name="get-started-with-the-cost-accounting-service"></a><span data-ttu-id="b1696-103">Introducción al servicio de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="b1696-103">Get started with the cost accounting service</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="b1696-104">La funcionalidad que se describe en este tema está disponible como parte de una versión preliminar privada.</span><span class="sxs-lookup"><span data-stu-id="b1696-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="b1696-105">El contenido de este tema y la funcionalidad que describe están sujetos a cambios.</span><span class="sxs-lookup"><span data-stu-id="b1696-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="b1696-106">Para obtener más información acerca las versiones preliminares, consulte [Preguntas frecuentes sobre actualizaciones del servicio de una versión](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="b1696-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="b1696-107">El servicio de contabilidad de costos le permite realizar múltiples inventarios en los libros de contabilidad de costos que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="b1696-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="b1696-108">Usted asocia cada libro de contabilidad de costos a una *convención*.</span><span class="sxs-lookup"><span data-stu-id="b1696-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="b1696-109">Una convención es una colección de los siguientes tipos de políticas contables:</span><span class="sxs-lookup"><span data-stu-id="b1696-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="b1696-110">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="b1696-110">Cost object</span></span>
- <span data-ttu-id="b1696-111">Base de medida de entrada</span><span class="sxs-lookup"><span data-stu-id="b1696-111">Input measurement basis</span></span>
- <span data-ttu-id="b1696-112">Suposición de flujo de costes</span><span class="sxs-lookup"><span data-stu-id="b1696-112">Cost flow assumption</span></span>
- <span data-ttu-id="b1696-113">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="b1696-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="b1696-114">Incluso después de haber activado el servicio de contabilidad de costos, aún puede hacer contabilidad de inventario en Microsoft Dynamics 365 Supply Chain Management, como siempre.</span><span class="sxs-lookup"><span data-stu-id="b1696-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="b1696-115">El servicio de contabilidad de costos es un complemento.</span><span class="sxs-lookup"><span data-stu-id="b1696-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="b1696-116">Para que sus funciones estén disponibles, debe instalarlo desde Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b1696-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b1696-117">Por lo tanto, puede elegir evaluarlo en un entorno de prueba antes de activarlo para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="b1696-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="b1696-118">El servicio de contabilidad de costos no admite actualmente todas las funciones de administración de costos integradas en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b1696-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b1696-119">Por lo tanto, es importante que evalúe si el conjunto de funciones que están disponibles actualmente cumplirá sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="b1696-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="b1696-120">Licencias</span><span class="sxs-lookup"><span data-stu-id="b1696-120">Licensing</span></span>

<span data-ttu-id="b1696-121">El servicio de contabilidad de costos tiene licencia junto con las características estándar de la contabilidad de inventario que están disponibles para Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b1696-121">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="b1696-122">No tiene que comprar una licencia adicional para usar el servicio de contabilidad de costos.</span><span class="sxs-lookup"><span data-stu-id="b1696-122">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><span data-ttu-id="b1696-123">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="b1696-123">Install the add-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1696-124">Para usar el servicio de contabilidad de costos, debe tener un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox), y debe estar ejecutando Dynamics 365 Supply Chain Management versión 10.0.11 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b1696-124">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="b1696-125">Para usar el servicio de contabilidad de costos, instale el complemento de servicio de contabilidad de costos para Supply Chain Management como se describe en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b1696-125">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="b1696-126">Inicie sesión en LCS.</span><span class="sxs-lookup"><span data-stu-id="b1696-126">Sign in to LCS.</span></span>

1. <span data-ttu-id="b1696-127">Vaya a **Administración de características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="b1696-127">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="b1696-128">Seleccione el signo más (**+**).</span><span class="sxs-lookup"><span data-stu-id="b1696-128">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="b1696-129">En el campo **Código**, ingrese su clave beta de complemento para el servicio de contabilidad de costos.</span><span class="sxs-lookup"><span data-stu-id="b1696-129">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="b1696-130">(Debería haber recibido su clave por correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="b1696-130">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="b1696-131">Seleccione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="b1696-131">Select **Unblock**.</span></span>

1. <span data-ttu-id="b1696-132">Abra el entorno LCS donde desea agregar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b1696-132">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="b1696-133">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="b1696-133">Go to **Full details**.</span></span>

1. <span data-ttu-id="b1696-134">Desplácese hacia abajo hasta la ficha desplegable **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="b1696-134">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="b1696-135">Seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="b1696-135">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="b1696-136">Seleccione **Servicio de contabilidad de costos**.</span><span class="sxs-lookup"><span data-stu-id="b1696-136">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="b1696-137">Siga la guía de instalación y acepte los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="b1696-137">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="b1696-138">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b1696-138">Select **Install**.</span></span>

1. <span data-ttu-id="b1696-139">En la ficha desplegable **Complementos de entorno**, debería ver que se está instalando el servicio de contabilidad de costos.</span><span class="sxs-lookup"><span data-stu-id="b1696-139">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="b1696-140">Después de unos minutos, el estado debería cambiar de **Instalando** a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="b1696-140">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="b1696-141">(Es posible que tenga que actualizar la página para ver este cambio). En ese momento, el servicio de contabilidad de costos está listo para usar.</span><span class="sxs-lookup"><span data-stu-id="b1696-141">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="b1696-142">Configuración de la integración</span><span class="sxs-lookup"><span data-stu-id="b1696-142">Set up the integration</span></span>

<span data-ttu-id="b1696-143">Para configurar la integración entre el servicio de contabilidad de costos y Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="b1696-143">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="b1696-144">Vaya a **Administración del sistema > Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="b1696-144">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="b1696-145">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="b1696-145">Select **Check for updates**.</span></span>

1. <span data-ttu-id="b1696-146">Abra la pestaña **Todas** y busque la función denominada *Servicio de contabilidad de costos*.</span><span class="sxs-lookup"><span data-stu-id="b1696-146">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="b1696-147">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="b1696-147">Select **Enable now**.</span></span>

1. <span data-ttu-id="b1696-148">Vaya a **Gestión de costes > Servicio de contabilidad de costes > Configuración > Parámetros del servicio de contabilidad de costes > Parámetros de integración**.</span><span class="sxs-lookup"><span data-stu-id="b1696-148">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="b1696-149">En el campo **ID de aplicación**, ingrese el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b1696-149">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="b1696-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="b1696-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="b1696-151">En el campo **Punto final del servicio de datos**, ingrese la siguiente URL:</span><span class="sxs-lookup"><span data-stu-id="b1696-151">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="b1696-152">En el campo **Punto final de contabilidad de costes**, ingrese la siguiente URL:</span><span class="sxs-lookup"><span data-stu-id="b1696-152">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="b1696-153">El servicio de contabilidad de costos ahora está listo para usar.</span><span class="sxs-lookup"><span data-stu-id="b1696-153">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="b1696-154">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="b1696-154">Related resources</span></span>

[<span data-ttu-id="b1696-155">Página principal del servicio de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="b1696-155">Cost accounting service home page</span></span>](cost-accounting-service-home.md)
