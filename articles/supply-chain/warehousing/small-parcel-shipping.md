---
title: Envío de paquetes pequeños
description: Este tema proporciona información acerca de la función de envío de paquetes pequeños (SPS). Esta característica permite a Microsoft Dynamics 365 Supply Chain Management enviar detalles sobre un contenedor empaquetado al transportista y luego recibir una etiqueta de envío, tarifa de envío y número de seguimiento de ese transportista.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3e72959d79e9b3b03e061a0f26750e3bd025219e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910218"
---
# <a name="small-parcel-shipping"></a><span data-ttu-id="81de2-104">Envío de paquetes pequeños</span><span class="sxs-lookup"><span data-stu-id="81de2-104">Small parcel shipping</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="81de2-105">La función de envío de paquetes pequeños (SPS) permite a Microsoft Dynamics 365 Supply Chain Management interactuar directamente con los transportistas proporcionando un marco para la comunicación a través de las API del transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-105">The small parcel shipping (SPS) feature enables Microsoft Dynamics 365 Supply Chain Management to interact directly with shipping carriers by providing a framework for communication through carrier APIs.</span></span> <span data-ttu-id="81de2-106">Esta funcionalidad es útil cuando envía pedidos de venta individuales a través de transportistas comerciales en lugar de utilizar el envío con contenedores o el envío inferior a clases de camión (LTL).</span><span class="sxs-lookup"><span data-stu-id="81de2-106">This functionality is useful when you're shipping individual sales orders via commercial shipping carriers instead of using container shipping or less-than-truckload (LTL) shipping.</span></span>

<span data-ttu-id="81de2-107">La función SPS interactúa con su transportista a través de un *motor de tarifas* dedicado.</span><span class="sxs-lookup"><span data-stu-id="81de2-107">The SPS feature interacts with your shipping carrier through a dedicated *rate engine*.</span></span> <span data-ttu-id="81de2-108">Su organización debe desarrollar este motor de tarifas en colaboración con su operador o servicio del centro de operador.</span><span class="sxs-lookup"><span data-stu-id="81de2-108">Your organization must develop this rate engine in collaboration with your carrier or carrier hub service.</span></span> <span data-ttu-id="81de2-109">El motor de tarifas permite a Supply Chain Management enviar detalles sobre un contenedor empaquetado a su transportista, y luego recibir una etiqueta de envío, tarifa de envío y número de seguimiento de ese transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-109">The rate engine enables Supply Chain Management to submit details about a packed container to your carrier, and then receive a shipping label, shipping rate, and tracking number back from that carrier.</span></span>

<span data-ttu-id="81de2-110">La tarifa de envío que se devuelve se agrega al pedido de venta asociado como cargos varios.</span><span class="sxs-lookup"><span data-stu-id="81de2-110">The shipping rate that is returned is added to the associated sales order as a miscellaneous charge.</span></span> <span data-ttu-id="81de2-111">La etiqueta de envío que se devuelve puede entonces imprimirse automáticamente mediante una impresora de lenguaje de programación Zebra (ZPL) y aplicarse al envío.</span><span class="sxs-lookup"><span data-stu-id="81de2-111">The shipping label that is returned can then automatically be printed by using a Zebra Programming Language (ZPL) printer and applied to the shipment.</span></span> <span data-ttu-id="81de2-112">El transportista escaneará esta etiqueta de envío cuando recoja los paquetes en su almacén.</span><span class="sxs-lookup"><span data-stu-id="81de2-112">The carrier will scan this shipping label when it picks up the packages at your warehouse.</span></span>

## <a name="prepare-your-system-to-support-sps"></a><span data-ttu-id="81de2-113">Preparar el sistema para admitir SPS</span><span class="sxs-lookup"><span data-stu-id="81de2-113">Prepare your system to support SPS</span></span>

<span data-ttu-id="81de2-114">Para poder empezar a usar la funcionalidad SPS, debe activar la característica SPS en la administración de funciones, agregar su motor de tarifas y configurar los módulos **Administración de transporte** y **Administración de características** para admitirla.</span><span class="sxs-lookup"><span data-stu-id="81de2-114">Before you can start to use SPS functionality, you must turn on the SPS feature in Feature management, add your rate engine, and set up the **Transportation management** and **Warehouse management** modules to support it.</span></span>

### <a name="turn-on-the-sps-feature"></a><span data-ttu-id="81de2-115">Activar la característica SPS</span><span class="sxs-lookup"><span data-stu-id="81de2-115">Turn on the SPS feature</span></span>

<span data-ttu-id="81de2-116">Antes de poder usar la característica SPS, debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="81de2-116">Before you can use the SPS feature, it must be turned on in your system.</span></span> <span data-ttu-id="81de2-117">Los administradores pueden usar el espacio de trabajo [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="81de2-117">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="81de2-118">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="81de2-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="81de2-119">**Módulo**: *Administración de transporte*</span><span class="sxs-lookup"><span data-stu-id="81de2-119">**Module:** *Transportation management*</span></span>
- <span data-ttu-id="81de2-120">**Nombre de característica**: *Envío de paquetes pequeños*</span><span class="sxs-lookup"><span data-stu-id="81de2-120">**Feature name:** *Small parcel shipping*</span></span>

### <a name="deploy-and-set-up-rate-engines"></a><span data-ttu-id="81de2-121">Implementar y configurar motores de tarifas</span><span class="sxs-lookup"><span data-stu-id="81de2-121">Deploy and set up rate engines</span></span>

<span data-ttu-id="81de2-122">Supply Chain Management no incluye motores de tarifas.</span><span class="sxs-lookup"><span data-stu-id="81de2-122">Supply Chain Management doesn't include any rate engines.</span></span> <span data-ttu-id="81de2-123">Debe obtener o crear los motores de tarifas que necesite, y luego agregarlos a su sistema.</span><span class="sxs-lookup"><span data-stu-id="81de2-123">You must obtain or create any rate engines that you require, and then add them to your system.</span></span> <span data-ttu-id="81de2-124">Sin embargo, Microsoft proporciona un motor de tarifas de demostración que puede utilizar para realizar pruebas.</span><span class="sxs-lookup"><span data-stu-id="81de2-124">However, Microsoft provides a demo rate engine that you can use for testing.</span></span>

#### <a name="download-and-deploy-the-demo-rate-engine"></a><span data-ttu-id="81de2-125">Descargar e implementar el motor de tarifas de demostración</span><span class="sxs-lookup"><span data-stu-id="81de2-125">Download and deploy the demo rate engine</span></span>

<span data-ttu-id="81de2-126">Siga estos pasos para obtener el motor de tarifas de demostración.</span><span class="sxs-lookup"><span data-stu-id="81de2-126">Follow these steps to get the demo rate engine.</span></span>

1. <span data-ttu-id="81de2-127">En GitHub, descargue la [ biblioteca de vínculos dinámicos (DLL) para el motor de tarifas de demostración](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span><span class="sxs-lookup"><span data-stu-id="81de2-127">On GitHub, download the [dynamic-link library (DLL) for the demo rate engine](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).</span></span>
1. <span data-ttu-id="81de2-128">En su servidor de Supply Chain Management, guarde la DLL en la carpeta **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.</span><span class="sxs-lookup"><span data-stu-id="81de2-128">On your Supply Chain Management server, save the DLL in the **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin** folder.</span></span>

#### <a name="create-and-deploy-functional-rate-engines"></a><span data-ttu-id="81de2-129">Crear e implementar motores de tarifas funcionales</span><span class="sxs-lookup"><span data-stu-id="81de2-129">Create and deploy functional rate engines</span></span>

<span data-ttu-id="81de2-130">Para obtener información sobre cómo crear e implementar motores de tarifas funcionales para que se puedan usar en un entorno de producción o de prueba, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="81de2-130">For information about how to create and deploy functional rate engines so that they can be used in a production or test environment, see the following topics:</span></span>

- [<span data-ttu-id="81de2-131">Crear un nuevo motor de administración de transporte</span><span class="sxs-lookup"><span data-stu-id="81de2-131">Create a new transportation management engine</span></span>](../transportation/create-new-transportation-management-engine.md)
- [<span data-ttu-id="81de2-132">Configurar motores de administración de transporte</span><span class="sxs-lookup"><span data-stu-id="81de2-132">Set up transportation management engines</span></span>](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

<span data-ttu-id="81de2-133">Para obtener más información sobre cómo crear un motor de tarifas SPS, consulte la siguiente entrada de blog: [Envío de paquetes pequeños: cómo aprovechar la funcionalidad de envío de paquetes pequeños en Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span><span class="sxs-lookup"><span data-stu-id="81de2-133">For more information about how to create an SPS rate engine, see the following blog post: [Small Parcel Shipping: How to leverage small parcel shipping functionality in Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).</span></span>

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a><span data-ttu-id="81de2-134">Configurar un motor de tarifas en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="81de2-134">Set up a rate engine in Supply Chain Management</span></span>

<span data-ttu-id="81de2-135">Una vez que haya creado e implementado un motor de tarifas para SPS, siga estos pasos para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="81de2-135">After you've created and deployed a rate engine for SPS, follow these steps to set it up.</span></span>

1. <span data-ttu-id="81de2-136">Vaya a **Administración de transporte \> Configuración \> Motores \> Motor de tarifas**.</span><span class="sxs-lookup"><span data-stu-id="81de2-136">Go to **Transportation management \> Setup \> Engines \> Rate engine**.</span></span>
1. <span data-ttu-id="81de2-137">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="81de2-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="81de2-138">Establezca los siguientes campos en la fila nueva.</span><span class="sxs-lookup"><span data-stu-id="81de2-138">In the new row, set the following fields:</span></span>

    - <span data-ttu-id="81de2-139">**Motor de clasificación**: introduzca un nombre único para el motor de tarifas.</span><span class="sxs-lookup"><span data-stu-id="81de2-139">**Rating engine** – Enter a unique name for the rate engine.</span></span> <span data-ttu-id="81de2-140">Si está usando el motor de tarifas de demostración, introduzca *Motor de tarifas de demostración*.</span><span class="sxs-lookup"><span data-stu-id="81de2-140">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="81de2-141">**Nombre**: escriba una breve descripción del motor de tarifas.</span><span class="sxs-lookup"><span data-stu-id="81de2-141">**Name** – Enter a short description of the rate engine.</span></span> <span data-ttu-id="81de2-142">Si está usando el motor de tarifas de demostración, introduzca *Motor de tarifas de demostración*.</span><span class="sxs-lookup"><span data-stu-id="81de2-142">If you're using the demo rate engine, enter *Demo rate engine*.</span></span>
    - <span data-ttu-id="81de2-143">**Id. de metadatos de calificación**: seleccione la base que se debe usar para calcular su tarifa.</span><span class="sxs-lookup"><span data-stu-id="81de2-143">**Rating metadata ID** – Select the basis that should be used to calculate your rate.</span></span> <span data-ttu-id="81de2-144">Por ejemplo, su tarifa podría calcularse en función de la distancia.</span><span class="sxs-lookup"><span data-stu-id="81de2-144">For example, your rate might be calculated based on distance.</span></span> <span data-ttu-id="81de2-145">Si está utilizando el motor de tarifas de demostración, puede dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="81de2-145">If you're using the demo rate engine, you can leave this field blank.</span></span>
    - <span data-ttu-id="81de2-146">**Ensamblado de motores**: introduzca el nombre de archivo del paquete DLL ha que implementado.</span><span class="sxs-lookup"><span data-stu-id="81de2-146">**Engine assembly** – Enter the file name of the DLL package that you deployed.</span></span> <span data-ttu-id="81de2-147">Si está usando el motor de tarifas de demostración, introduzca *TMSSmallParcelShippingEngine.dll*.</span><span class="sxs-lookup"><span data-stu-id="81de2-147">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.dll*.</span></span>
    - <span data-ttu-id="81de2-148">**Clase de motor**: escriba el nombre de la clase que se estableció para su motor de tarifas.</span><span class="sxs-lookup"><span data-stu-id="81de2-148">**Engine class** – Enter the class name that was established for your rate engine.</span></span> <span data-ttu-id="81de2-149">Si está usando el motor de tarifas de demostración, introduzca *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span><span class="sxs-lookup"><span data-stu-id="81de2-149">If you're using the demo rate engine, enter *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="81de2-150">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="81de2-150">Example scenario</span></span>

<span data-ttu-id="81de2-151">Este escenario de ejemplo muestra cómo configurar y usar SPS después de haber preparado su sistema como se ha descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="81de2-151">This example scenario shows how to set up and use SPS after you've prepared your system as described earlier in this topic.</span></span> <span data-ttu-id="81de2-152">Este escenario utiliza el motor de tarifas de demostración mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="81de2-152">This scenario uses the previously mentioned demo rate engine.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="81de2-153">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="81de2-153">Make demo data available</span></span>

<span data-ttu-id="81de2-154">Para trabajar en este escenario mediante el uso de los registros y valores de demostración que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="81de2-154">To work through this scenario by using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="81de2-155">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="81de2-155">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="81de2-156">Configuración el escenario</span><span class="sxs-lookup"><span data-stu-id="81de2-156">Set up the scenario</span></span>

<span data-ttu-id="81de2-157">Para este escenario de ejemplo, debe tener un transportista de demostración, un grupo de transportistas, una directiva de embalaje y un perfil de embalaje.</span><span class="sxs-lookup"><span data-stu-id="81de2-157">For this example scenario, you must have a demo carrier, carrier group, packing policy, and packing profile.</span></span> <span data-ttu-id="81de2-158">En las siguientes subsecciones se explica cómo preparar los registros necesarios para el escenario.</span><span class="sxs-lookup"><span data-stu-id="81de2-158">The following subsections explain how to prepare the records that are required for the scenario.</span></span> <span data-ttu-id="81de2-159">En un escenario de producción, el proceso de configuración suele parecerse al proceso que se describe aquí.</span><span class="sxs-lookup"><span data-stu-id="81de2-159">In a production scenario, the setup process typically resembles the process that is described here.</span></span> <span data-ttu-id="81de2-160">Sin embargo, establecerá valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="81de2-160">However, you will set different values.</span></span>

#### <a name="set-up-carriers"></a><span data-ttu-id="81de2-161">Configurar transportistas</span><span class="sxs-lookup"><span data-stu-id="81de2-161">Set up carriers</span></span>

<span data-ttu-id="81de2-162">Siga estos pasos para configurar un transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-162">Follow these steps to set up a carrier.</span></span>

1. <span data-ttu-id="81de2-163">Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.</span><span class="sxs-lookup"><span data-stu-id="81de2-163">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="81de2-164">En el Panel de acciones, seleccione **Nuevo** para agregar un transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-164">On the Action Pane, select **New** to add a carrier.</span></span>
1. <span data-ttu-id="81de2-165">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="81de2-165">On the header, set the following values:</span></span>

    - <span data-ttu-id="81de2-166">**Transportista de envío:** *Transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-166">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="81de2-167">**Nombre:** *Transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-167">**Name:** *Demo Carrier*</span></span>
    - <span data-ttu-id="81de2-168">**Modo:** *Tierra*</span><span class="sxs-lookup"><span data-stu-id="81de2-168">**Mode:** *Ground*</span></span>

1. <span data-ttu-id="81de2-169">En la ficha desplegable **Visión general**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="81de2-169">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="81de2-170">**Activación de interfaces de transportistas de envío:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="81de2-170">**Activate shipping carrier:** *Yes*</span></span>
    - <span data-ttu-id="81de2-171">**Activar calificación de transportistas:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="81de2-171">**Activate carrier rating:** *Yes*</span></span>

1. <span data-ttu-id="81de2-172">En la ficha desplegable **Servicios**, seleccione **Nuevo** para agregar un servicio a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="81de2-172">On the **Services** FastTab, select **New** to add a service to the grid.</span></span>
1. <span data-ttu-id="81de2-173">Establezca los siguientes valores para el nuevo servicio:</span><span class="sxs-lookup"><span data-stu-id="81de2-173">Set the following values for the new service:</span></span>

    - <span data-ttu-id="81de2-174">**Servicio de transportista:** *Servicio de transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-174">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="81de2-175">**Nombre:** *Servicio de transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-175">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="81de2-176">**Método de transporte:** *Tierra*</span><span class="sxs-lookup"><span data-stu-id="81de2-176">**Transportation method:** *Ground*</span></span>

    <span data-ttu-id="81de2-177">Introduzca valores arbitrarios para todos los demás campos, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="81de2-177">Enter arbitrary values for all the other fields, as required.</span></span> <span data-ttu-id="81de2-178">(Cuando guarde el nuevo registro de transportista, se creará un nuevo modo de entrega y el campo **Modo de entrega** se establecerá automáticamente.)</span><span class="sxs-lookup"><span data-stu-id="81de2-178">(When you save the new shipping carrier record, a new mode of delivery will be created, and the **Mode of delivery** field will be set automatically.)</span></span>

1. <span data-ttu-id="81de2-179">En la ficha desplegable **Perfiles de clasificación**, seleccione **Nuevo** para crear un perfil de clasificación a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="81de2-179">On the **Rating profiles** FastTab, select **New** to add a rating profile to the grid.</span></span>
1. <span data-ttu-id="81de2-180">Establezca los siguientes valores para el nuevo perfil:</span><span class="sxs-lookup"><span data-stu-id="81de2-180">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="81de2-181">**Perfil de clasificación:** *Servicio de transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-181">**Rating profile:** *Demo carrier service*</span></span>
    - <span data-ttu-id="81de2-182">**Nombre:** *Servicio de transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-182">**Name:** *Demo carrier service*</span></span>
    - <span data-ttu-id="81de2-183">**Motor de tarifas:** *Motor de tarifas de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-183">**Rate engine:** *Demo rate engine*</span></span>

    <span data-ttu-id="81de2-184">Introduzca valores arbitrarios para todos los demás campos, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="81de2-184">Enter arbitrary values for all the other fields, as required.</span></span>

1. <span data-ttu-id="81de2-185">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="81de2-185">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="81de2-186">Para obtener más información acerca de la configuración de transportista, consulte [Configuración de transportistas de envío](../transportation/tasks/set-up-shipping-carriers.md).</span><span class="sxs-lookup"><span data-stu-id="81de2-186">For more information about how to set up carriers, see [Set up shipping carriers](../transportation/tasks/set-up-shipping-carriers.md).</span></span>

#### <a name="set-up-carrier-service-accounts"></a><span data-ttu-id="81de2-187">Configurar cuentas de servicio de transportista</span><span class="sxs-lookup"><span data-stu-id="81de2-187">Set up carrier service accounts</span></span>

<span data-ttu-id="81de2-188">Siga estos pasos para configurar una cuenta de servicio de transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-188">Follow these steps to set up a carrier service account.</span></span>

1. <span data-ttu-id="81de2-189">Vaya a **Administración de transporte \> Configuración \> Clasificación \> Cuenta de servicio de transportista**.</span><span class="sxs-lookup"><span data-stu-id="81de2-189">Go to **Transportation management \> Setup \> Rating \> Carrier service account**.</span></span>
1. <span data-ttu-id="81de2-190">En el Panel de acciones, seleccione **Nuevo** para agregar una cuenta de servicio de transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-190">On the Action Pane, select **New** to add a carrier service account.</span></span>
1. <span data-ttu-id="81de2-191">Establezca los siguientes valores para la nueva cuenta:</span><span class="sxs-lookup"><span data-stu-id="81de2-191">Set the following values for the new account:</span></span>

    - <span data-ttu-id="81de2-192">**Transportista de envío:** *Transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-192">**Shipping Carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="81de2-193">**Servicio de transportista:** *Servicio de transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-193">**Carrier service:** *Demo carrier service*</span></span>
    - <span data-ttu-id="81de2-194">**Número de cuenta del cliente del transportista:** el número de cuenta del cliente del transportista que se usa para comprobar y autenticar la conexión con el transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-194">**Carrier customer account number:** The carrier customer account number that is used to verify and authenticate the connection to the shipping carrier.</span></span> <span data-ttu-id="81de2-195">Su transportista le proporcionará este valor.</span><span class="sxs-lookup"><span data-stu-id="81de2-195">Your carrier will provide this value.</span></span> <span data-ttu-id="81de2-196">Si está usando el servicio de demostración, puede introducir un valor arbitrario.</span><span class="sxs-lookup"><span data-stu-id="81de2-196">If you're using the demo service, you can enter an arbitrary value.</span></span>
    - <span data-ttu-id="81de2-197">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="81de2-197">**Site:** *6*</span></span>
    - <span data-ttu-id="81de2-198">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="81de2-198">**Warehouse:** *62*</span></span>

    > [!NOTE]
    > <span data-ttu-id="81de2-199">A menudo, el valor del **Número de cuenta del cliente del transportista** es el único valor que se requiere para autenticar la conexión.</span><span class="sxs-lookup"><span data-stu-id="81de2-199">Often, the **Carrier customer account number** value is the only value that is required to authenticate the connection.</span></span> <span data-ttu-id="81de2-200">Sin embargo, si su transportista requiere parámetros de autenticación adicionales, su organización debe personalizar esta página para agregar campos adicionales según corresponda.</span><span class="sxs-lookup"><span data-stu-id="81de2-200">However, if your carrier requires additional authentication parameters, your organization should customize this page to add extra fields as appropriate.</span></span>

#### <a name="set-up-a-container-packing-policy"></a><span data-ttu-id="81de2-201">Configurar una directiva de embalaje de contenedores</span><span class="sxs-lookup"><span data-stu-id="81de2-201">Set up a container packing policy</span></span>

<span data-ttu-id="81de2-202">Siga estos pasos para configurar una directiva de embalaje de contenedores.</span><span class="sxs-lookup"><span data-stu-id="81de2-202">Follow these steps to set up a container packing policy.</span></span>

1. <span data-ttu-id="81de2-203">Si aún no ha configurado una definición de impresora ZPL, utilice la aplicación Agente de ruta de documentos para configurarla.</span><span class="sxs-lookup"><span data-stu-id="81de2-203">If you haven't already set up a ZPL printer definition, use the Document Routing Agent application to set it up.</span></span> <span data-ttu-id="81de2-204">Para más información, consulte [Descripción general de la impresión de documentos](../../fin-ops-core/dev-itpro/analytics/print-documents.md) y temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="81de2-204">For more information, see [Document printing overview](../../fin-ops-core/dev-itpro/analytics/print-documents.md) and related topics.</span></span>
1. <span data-ttu-id="81de2-205">Vaya a **Administración de almacenes \> Configurar \> Contenedores \> Directivas de embalaje en contenedores**.</span><span class="sxs-lookup"><span data-stu-id="81de2-205">Go to **Warehouse Management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="81de2-206">En el Panel de acciones, seleccione **Nuevo** para agregar una directiva de embalaje en contenedores.</span><span class="sxs-lookup"><span data-stu-id="81de2-206">On the Action Pane, select **New** to add a container packing policy.</span></span>
1. <span data-ttu-id="81de2-207">En el encabezado de la nueva directiva, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="81de2-207">On the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="81de2-208">**Directiva de embalaje en contenedores:** *Directiva de embalaje de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-208">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="81de2-209">**Descripción:** una descripción de la directiva</span><span class="sxs-lookup"><span data-stu-id="81de2-209">**Description:** A description of the policy</span></span>

1. <span data-ttu-id="81de2-210">En la ficha desplegable **Visión general**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="81de2-210">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="81de2-211">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="81de2-211">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="81de2-212">**Ubicación predeterminada para envío final:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="81de2-212">**Default location for final shipment:** *Baydoor*</span></span>
    - <span data-ttu-id="81de2-213">**Unidad de peso:** *KG*</span><span class="sxs-lookup"><span data-stu-id="81de2-213">**Weight unit:** *KG*</span></span>
    - <span data-ttu-id="81de2-214">**Directiva de cierre del contenedor:** *Liberación automática*</span><span class="sxs-lookup"><span data-stu-id="81de2-214">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="81de2-215">**Directiva de lanzamiento de contenedores:** *Hacer que esté disponible en la ubicación de envío final*</span><span class="sxs-lookup"><span data-stu-id="81de2-215">**Container release policy:** *Make available at final shipping location*</span></span>

1. <span data-ttu-id="81de2-216">En la ficha rápida **Manifiesto de contenedor**, puede establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="81de2-216">On the **Container manifest** FastTab, set the following values:</span></span>

    - <span data-ttu-id="81de2-217">**Manifiesto automático al cerrar el contenedor:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="81de2-217">**Automatic manifest at container close:** *Yes*</span></span>
    - <span data-ttu-id="81de2-218">**Requisitos de manifiesto para contenedor:** *Administración de transporte*</span><span class="sxs-lookup"><span data-stu-id="81de2-218">**Manifest requirements for container:** *Transportation management*</span></span>
    - <span data-ttu-id="81de2-219">**Imprimir contenido del contenedor:** *No*</span><span class="sxs-lookup"><span data-stu-id="81de2-219">**Print container contents:** *No*</span></span>

1. <span data-ttu-id="81de2-220">En la ficha rápida **Impresión de etiquetas de transportista**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="81de2-220">On the **Carrier label printing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="81de2-221">**Imprimir etiqueta de envío de contenedor:** *Siempre*</span><span class="sxs-lookup"><span data-stu-id="81de2-221">**Print container shipping label:** *Always*</span></span>
    - <span data-ttu-id="81de2-222">**Nombre de la impresora:** El nombre de la impresora ZPL que debe imprimir etiquetas de envío</span><span class="sxs-lookup"><span data-stu-id="81de2-222">**Printer name:** The name of the ZPL printer that should print shipping labels</span></span>

#### <a name="set-up-a-packing-profile"></a><span data-ttu-id="81de2-223">Configurar un perfil de embalaje</span><span class="sxs-lookup"><span data-stu-id="81de2-223">Set up a packing profile</span></span>

<span data-ttu-id="81de2-224">Para configurar un perfil de embalaje, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="81de2-224">Follow these steps to set up a packing profile.</span></span>

1. <span data-ttu-id="81de2-225">Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.</span><span class="sxs-lookup"><span data-stu-id="81de2-225">Go to **Warehouse Management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="81de2-226">En el Panel de acciones, seleccione **Nuevo** para agregar un perfil de embalaje a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="81de2-226">On the Action Pane, select **New** to add a packing profile to the grid.</span></span>
1. <span data-ttu-id="81de2-227">Establezca los siguientes valores para el nuevo perfil:</span><span class="sxs-lookup"><span data-stu-id="81de2-227">Set the following values for the new profile:</span></span>

    - <span data-ttu-id="81de2-228">**Id. de perfil de embalaje:** *Perfil de embalaje de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-228">**Packing profile ID:** *Demo packing profile*</span></span>
    - <span data-ttu-id="81de2-229">**Descripción:** una descripción del perfil</span><span class="sxs-lookup"><span data-stu-id="81de2-229">**Description:** A description of the profile</span></span>
    - <span data-ttu-id="81de2-230">**Directiva de embalaje en contenedores:** *Directiva de embalaje de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-230">**Container packing policy:** *Demo packing policy*</span></span>
    - <span data-ttu-id="81de2-231">**Modo del id. de contenedor:** *Automático*</span><span class="sxs-lookup"><span data-stu-id="81de2-231">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="81de2-232">**Tipo de contenedor:** *Caja pequeña*</span><span class="sxs-lookup"><span data-stu-id="81de2-232">**Container type:** *SmallBox*</span></span>

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a><span data-ttu-id="81de2-233">Configurar un cliente para usar el transportista SPS</span><span class="sxs-lookup"><span data-stu-id="81de2-233">Set up a customer to use the SPS carrier</span></span>

<span data-ttu-id="81de2-234">Siga estos pasos para configurar un cliente para que pueda utilizar el transportista que ha creado.</span><span class="sxs-lookup"><span data-stu-id="81de2-234">Follow these steps to set up a customer so that it can use the carrier that you created.</span></span>

1. <span data-ttu-id="81de2-235">Vaya a **Clientes \> Clientes \> Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="81de2-235">Go to **Accounts receivable \> customers \> All customers**.</span></span>
1. <span data-ttu-id="81de2-236">En la cuadrícula, busque y seleccione el cliente *US-027*.</span><span class="sxs-lookup"><span data-stu-id="81de2-236">In the grid, find and select customer *US-027*.</span></span>
1. <span data-ttu-id="81de2-237">En el panel de acciones, en la pestaña **General**, del grupo **Configuración**, seleccione **Cuentas de cliente de transportista**.</span><span class="sxs-lookup"><span data-stu-id="81de2-237">On the Action Pane, on the **General** tab, in the **Set up** group, select **Carrier customer accounts**.</span></span>
1. <span data-ttu-id="81de2-238">En la página **Cuentas de clientes de transportista**, en el Panel de acciones, seleccione **Nueva** para agregar una cuenta a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="81de2-238">On the **Carrier customer accounts** page, on the Action Pane, select **New** to add an account to the grid.</span></span>
1. <span data-ttu-id="81de2-239">Establezca los siguientes valores para la nueva cuenta:</span><span class="sxs-lookup"><span data-stu-id="81de2-239">Set the following values for the new account:</span></span>

    - <span data-ttu-id="81de2-240">**Transportista de envío:** *Transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-240">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="81de2-241">**Número de cuenta del cliente del transportista:** *12345* (El valor no es importante para este escenario, pero se hará referencia a él en la siguiente sección).</span><span class="sxs-lookup"><span data-stu-id="81de2-241">**Carrier customer account number:** *12345* (The value isn't important for this scenario, but it will be referred to in the next section.)</span></span>

### <a name="go-through-the-example-scenario"></a><span data-ttu-id="81de2-242">Repase el escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="81de2-242">Go through the example scenario</span></span>

<span data-ttu-id="81de2-243">Una vez que haya configurado todos los datos de muestra como se describe en la sección anterior, estará listo para repasar el escenario de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81de2-243">After you've set up all the sample data as described in the previous section, you're ready to go through the example scenario.</span></span>

#### <a name="create-a-sales-order-and-process-the-work"></a><span data-ttu-id="81de2-244">Crear un pedido de venta y procesar el trabajo</span><span class="sxs-lookup"><span data-stu-id="81de2-244">Create a sales order and process the work</span></span>

<span data-ttu-id="81de2-245">Siga los pasos para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="81de2-245">Follow these steps to create a sales order.</span></span>

1. <span data-ttu-id="81de2-246">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="81de2-246">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="81de2-247">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="81de2-247">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="81de2-248">En el cuadro de diálogo **Crear pedido de ventas**, establezca el campo **Cuenta de cliente**, en *US-027*.</span><span class="sxs-lookup"><span data-stu-id="81de2-248">In the **Create sales order** dialog box, set the **Customer account** field to *US-027*.</span></span>
1. <span data-ttu-id="81de2-249">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="81de2-249">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="81de2-250">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="81de2-250">The new sales order is opened.</span></span> <span data-ttu-id="81de2-251">En la ficha desplegable **Encabezado de pedidos de ventas**, establezca el campo **Número de cuenta del cliente del transportista** en el valor que seleccionó para este cliente anteriormente (*12345*).</span><span class="sxs-lookup"><span data-stu-id="81de2-251">On the **Sales order header** FastTab, set the **Carrier customer account number** field to the value that you selected for this customer earlier (*12345*).</span></span>
1. <span data-ttu-id="81de2-252">En la sección **Líneas de pedido de ventas**, agregue una línea de ventas y establezca los siguientes valores para ella:</span><span class="sxs-lookup"><span data-stu-id="81de2-252">In the **Sales order lines** section, add a sales line, and set the following values for it:</span></span>

    - <span data-ttu-id="81de2-253">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="81de2-253">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="81de2-254">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="81de2-254">**Quantity:** *1*</span></span>
    - <span data-ttu-id="81de2-255">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="81de2-255">**Site:** *6*</span></span>
    - <span data-ttu-id="81de2-256">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="81de2-256">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="81de2-257">Cambie a la vista **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="81de2-257">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="81de2-258">En la ficha desplegable **Entrega**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="81de2-258">On the **Delivery** FastTab, set the following values:</span></span>

    - <span data-ttu-id="81de2-259">**Transportista de envío:** *Transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-259">**Shipping carrier:** *Demo Carrier*</span></span>
    - <span data-ttu-id="81de2-260">**Servicio de transportista:** *Servicio de transportista de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-260">**Carrier service:** *Demo carrier service*</span></span>

1. <span data-ttu-id="81de2-261">Vuelva a la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="81de2-261">Switch back to the **Lines** view.</span></span> <span data-ttu-id="81de2-262">Si se le solicita que actualice el modo de entrega de las líneas de venta, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="81de2-262">If you're prompted to update the mode of delivery for the sales lines, select **Yes**.</span></span>
1. <span data-ttu-id="81de2-263">En la sección **Líneas de pedido de ventas**, seleccione la línea de pedido que configuró anteriormente y, a continuación, **Inventario\> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="81de2-263">In the **Sales order lines** section, select the order line that you set up earlier, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="81de2-264">En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="81de2-264">On the **Reservation** page, select **Reserve lot** to reserve the selected line's full quantity in the warehouse.</span></span>
1. <span data-ttu-id="81de2-265">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="81de2-265">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="81de2-266">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="81de2-266">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="81de2-267">El trabajo se crea para mover artículos de la ubicación de picking a la estación de embalaje.</span><span class="sxs-lookup"><span data-stu-id="81de2-267">Work is created to move items from the picking location to the packing station.</span></span>

1. <span data-ttu-id="81de2-268">En la sección **Líneas de pedido de ventas**, seleccione **Almacén \> Detalles de envío**.</span><span class="sxs-lookup"><span data-stu-id="81de2-268">In the **Sales order lines** section, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="81de2-269">En la página **Detalles de envío**, anote el id. de envío.</span><span class="sxs-lookup"><span data-stu-id="81de2-269">On the **Shipment details** page, make a note of the shipment ID.</span></span> <span data-ttu-id="81de2-270">Lo necesitará cuando embale el paquete del envío en la estación de embalaje.</span><span class="sxs-lookup"><span data-stu-id="81de2-270">You will need it when you pack the pack the shipment at the packing station.</span></span>
1. <span data-ttu-id="81de2-271">Cierre la página **Detalles de envío** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="81de2-271">Close the **Shipment details** page to return to the sales order.</span></span>
1. <span data-ttu-id="81de2-272">Anote el número del pedido de venta y luego vaya a **Gestión de almacenes \> Trabajo \> Todo el trabajo**.</span><span class="sxs-lookup"><span data-stu-id="81de2-272">Make a note of the sales order number, and then go to **Warehouse management \> Work \> All work**.</span></span>
1. <span data-ttu-id="81de2-273">Utilice el número del pedido de venta para buscar y seleccionar el trabajo que se creó para el pedido.</span><span class="sxs-lookup"><span data-stu-id="81de2-273">Use the sales order number to find and select the work that was created for the order.</span></span>
1. <span data-ttu-id="81de2-274">En el panel de acciones, en la pestaña **Trabajo**, seleccione **Trabajo completo**.</span><span class="sxs-lookup"><span data-stu-id="81de2-274">On the Action Pane, on the **Work** tab, select **Complete work**.</span></span>
1. <span data-ttu-id="81de2-275">En la página **Finalización de trabajo**, en el campo **Id. de usuario**, seleccione un id. de usuario.</span><span class="sxs-lookup"><span data-stu-id="81de2-275">On the **Work completion** page, in the **User ID** field, select a user ID.</span></span> <span data-ttu-id="81de2-276">Después, en el panel de acciones, seleccione **Validar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="81de2-276">Then, on the Action Pane, select **Validate work**.</span></span>
1. <span data-ttu-id="81de2-277">Si el trabajo pasa la validación, seleccione **Trabajo completado** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="81de2-277">If the work passes validation, select **Complete work** on the Action Pane.</span></span>

    <span data-ttu-id="81de2-278">El trabajo se marca como completado para simular el movimiento de artículos a la estación de embalaje.</span><span class="sxs-lookup"><span data-stu-id="81de2-278">The work is marked as completed to simulate the movement of items to the packing station.</span></span>

#### <a name="pack-the-shipment"></a><span data-ttu-id="81de2-279">Embalar el envío</span><span class="sxs-lookup"><span data-stu-id="81de2-279">Pack the shipment</span></span>

<span data-ttu-id="81de2-280">Para embalar el envío, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="81de2-280">Follow these steps to pack the shipment.</span></span>

1. <span data-ttu-id="81de2-281">Vaya a **Gestión de almacenes \> Configuración \> Trabajador** y asegúrese de que su cuenta de usuario esté asociada a una cuenta de trabajador para la gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="81de2-281">Go to **Warehouse management \> Setup \> Worker**, and make sure that your user account is associated with a worker account for warehouse management.</span></span>
1. <span data-ttu-id="81de2-282">Vaya a **Gestión de almacenes \> Picking y puesta en contenedores \> Paquete**.</span><span class="sxs-lookup"><span data-stu-id="81de2-282">Go to **Warehouse management \> Picking and containerization \> Pack**.</span></span>
1. <span data-ttu-id="81de2-283">En el cuadro de diálogo **Seleccionar estación de embalaje**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="81de2-283">In the **Select packing station** dialog box, set the following values:</span></span>

    - <span data-ttu-id="81de2-284">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="81de2-284">**Site:** *6*</span></span>
    - <span data-ttu-id="81de2-285">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="81de2-285">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="81de2-286">**Ubicación:** *Paquete*</span><span class="sxs-lookup"><span data-stu-id="81de2-286">**Location:** *Pack*</span></span>
    - <span data-ttu-id="81de2-287">**Id. de perfil de embalaje:** *Perfil de embalaje de demostración*</span><span class="sxs-lookup"><span data-stu-id="81de2-287">**Packing profile ID:** *Demo packing profile*</span></span>

1. <span data-ttu-id="81de2-288">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="81de2-288">Select **OK**.</span></span>
1. <span data-ttu-id="81de2-289">Aparecerá la página **Paquete**.</span><span class="sxs-lookup"><span data-stu-id="81de2-289">The **Pack** page appears.</span></span> <span data-ttu-id="81de2-290">En un escenario de producción, un trabajador escaneará una matrícula o un id. de envío.</span><span class="sxs-lookup"><span data-stu-id="81de2-290">In a production scenario, a worker will scan a license plate or shipment ID.</span></span> <span data-ttu-id="81de2-291">Sin embargo, para este escenario, abra la página **Todos los envíos** y busque el número del envío que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="81de2-291">However, for this scenario, open the **All shipments** page, and look up the shipment number for the shipment that you just created.</span></span> <span data-ttu-id="81de2-292">A continuación, introduzca este valor en el campo **Matrícula de entidad de almacén o envío** de la página **Paquete**.</span><span class="sxs-lookup"><span data-stu-id="81de2-292">Then enter this value in the **License plate or shipment** field on the **Pack** page.</span></span> <span data-ttu-id="81de2-293">También puede introducir el id. de envío que anotó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="81de2-293">Alternatively, enter the shipment ID that you made a note of earlier.</span></span>
1. <span data-ttu-id="81de2-294">En el panel de acciones, seleccione **Nuevo contenedor**.</span><span class="sxs-lookup"><span data-stu-id="81de2-294">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="81de2-295">El cuadro de diálogo que aparece muestra detalles sobre el nuevo contenedor.</span><span class="sxs-lookup"><span data-stu-id="81de2-295">The dialog box that appears shows details about the new container.</span></span> <span data-ttu-id="81de2-296">Deje los valores predeterminados y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="81de2-296">Leave the default values, and then select **OK**.</span></span>
1. <span data-ttu-id="81de2-297">En la página **Paquete**, en la ficha desplegable **Embalaje de artículos**, en el campo **Identificador**, seleccione *A0002* para embalar ese artículo.</span><span class="sxs-lookup"><span data-stu-id="81de2-297">On the **Pack** page, on the **Item packing** FastTab, in the **Identifier** field, select *A0002* to pack that item.</span></span> <span data-ttu-id="81de2-298">El artículo se agrega al contenedor.</span><span class="sxs-lookup"><span data-stu-id="81de2-298">The item is added to the container.</span></span>
1. <span data-ttu-id="81de2-299">En el panel de acciones, seleccione **Contenedores para envío**.</span><span class="sxs-lookup"><span data-stu-id="81de2-299">On the Action Pane, select **Containers for shipment**.</span></span>

    <span data-ttu-id="81de2-300">La página **Contenedores para envío** que aparece tiene una fila para el contenedor que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="81de2-300">The **Containers for shipment** page that appears has a row for the container that you just created.</span></span> <span data-ttu-id="81de2-301">Sin embargo, el campo **Id. de manifiesto de contenedor** de esa fila está actualmente en blanco porque aún no ha recibido la etiqueta de envío y el número de seguimiento del transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-301">However, the **Container manifest ID** field in that row is currently blank, because you haven't yet received the shipping label and tracking number from the carrier.</span></span>

1. <span data-ttu-id="81de2-302">En el panel de acciones, seleccione **Cerrar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="81de2-302">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="81de2-303">En el cuadro de diálogo **Cerrar contenedor**, establezca el campo **Peso bruto** en *1 kilogramo* y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="81de2-303">In the **Close container** dialog box, set the **Gross weight** field to *1 kg*, and then select **OK**.</span></span>

    <span data-ttu-id="81de2-304">La etiqueta de envío ahora debería imprimirse en la impresora ZPL que seleccionó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="81de2-304">The shipping label should now be printed on the ZPL printer that you selected earlier.</span></span> <span data-ttu-id="81de2-305">El resultado se parecerá al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="81de2-305">It should resemble the following example.</span></span>

    <span data-ttu-id="81de2-306">![Ejemplo de etiqueta de envío](media/sps-label-example.png "Ejemplo de etiqueta de envío")</span><span class="sxs-lookup"><span data-stu-id="81de2-306">![Example shipping label](media/sps-label-example.png "Example shipping label")</span></span>

1. <span data-ttu-id="81de2-307">Observe que los valores **Id. de manifiesto de contenedor** y **Flete total** se han agregado como se recibieron del transportista.</span><span class="sxs-lookup"><span data-stu-id="81de2-307">Notice that the **Container manifest ID** and **Total freight** values have been added as received from the carrier.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]