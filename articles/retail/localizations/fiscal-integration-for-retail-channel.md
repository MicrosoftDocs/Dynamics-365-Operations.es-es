---
title: "Integración fiscal para el canal comercial"
description: "Este tema proporciona una introducción a la integración fiscal para Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: es-es
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a><span data-ttu-id="2b55a-103">Integración fiscal para el canal comercial</span><span class="sxs-lookup"><span data-stu-id="2b55a-103">Fiscal integration for Retail channel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b55a-104">Este tema es una visión general de la funcionalidad de integración fiscal que está disponible en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="2b55a-104">This topic is an overview of the fiscal integration functionality that is available in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="2b55a-105">La funcionalidad de la integración fiscal es un marco diseñado para dar soporte a las leyes fiscales locales que están dirigidas a evitar el fraude en el sector minorista.</span><span class="sxs-lookup"><span data-stu-id="2b55a-105">The fiscal integration functionality is a framework designed to support local fiscal laws that are aimed to prevent fraud in the Retail industry.</span></span> <span data-ttu-id="2b55a-106">Situaciones de ejemplo habituales que se pueden cubrir mediante inclusión de la integración fiscal:</span><span class="sxs-lookup"><span data-stu-id="2b55a-106">Typical scenarios that could be covered by using fiscal integration include:</span></span>

- <span data-ttu-id="2b55a-107">Imprimir un recibo fiscal y dárselo al cliente.</span><span class="sxs-lookup"><span data-stu-id="2b55a-107">Printing a fiscal receipt and giving it to the customer.</span></span>
- <span data-ttu-id="2b55a-108">Asegurar el envío de la información relacionada con las ventas y devoluciones realizados en POS a un servicio externo proporcionado por la autoridad.</span><span class="sxs-lookup"><span data-stu-id="2b55a-108">Securing the submission of the information related to sales and returns performed on POS to an external service provided by the authority.</span></span>
- <span data-ttu-id="2b55a-109">Usasr la protección de datos con una firma digital autorizada por la autoridad.</span><span class="sxs-lookup"><span data-stu-id="2b55a-109">Using data protection with a digital signature authorized by the authority.</span></span>

<span data-ttu-id="2b55a-110">En este tema se proporcionan instrucciones para configurar la integración fiscal para que los usuarios pueden realizar las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="2b55a-110">This topic provides guidelines for setting up fiscal integration so users can perform the following tasks.</span></span> 

- <span data-ttu-id="2b55a-111">Configurar los conectores fiscales, que son dispositivos o servicios fiscales usados para fines fiscales de registro como el guardado, las firmas digitales y el envío seguro de datos fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-111">Configure fiscal connectors, which are fiscal devices or services used for fiscal registration purposes like saving, digital signatures, and secured submission of fiscal data.</span></span>
- <span data-ttu-id="2b55a-112">Configurar el proveedor de documentos, que define un método de salida y un algoritmo de generación de documentos fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-112">Configure the document provider, which defines an output method and an algorithm of fiscal document generation.</span></span>
- <span data-ttu-id="2b55a-113">Configurar el proceso de registro fiscal, que define una secuencia de pasos y un grupo de conectores utilizados en cada paso.</span><span class="sxs-lookup"><span data-stu-id="2b55a-113">Configure the fiscal registration process, which is defines a sequence of steps and a group of connectors used on each step.</span></span>
- <span data-ttu-id="2b55a-114">Asignar procesos de registro fiscales a perfiles de funcionalidad de PDV.</span><span class="sxs-lookup"><span data-stu-id="2b55a-114">Assign fiscal registration processes to POS functionality profiles.</span></span>
- <span data-ttu-id="2b55a-115">Asignar perfiles técnicos de conector a perfiles de hardware (para los conectores fiscales locales) o a perfiles de funcionalidad PDV (para otros tipos de conectores fiscales).</span><span class="sxs-lookup"><span data-stu-id="2b55a-115">Assign connector technical profiles, either to hardware profiles (for the local fiscal connectors) or to POS functionality profiles (for other fiscal connector types).</span></span>

## <a name="fiscal-integration-execution-flow"></a><span data-ttu-id="2b55a-116">Flujo de ejecución de integración fiscal</span><span class="sxs-lookup"><span data-stu-id="2b55a-116">Fiscal integration execution flow</span></span>
<span data-ttu-id="2b55a-117">La situación de ejemplo siguiente muestra el flujo de ejecución de la integración fiscal común.</span><span class="sxs-lookup"><span data-stu-id="2b55a-117">The following scenario shows the common fiscal integration execution flow.</span></span>

1. <span data-ttu-id="2b55a-118">Inicialización del proceso de registro fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-118">Initialization of the fiscal registration process.</span></span>
  
   <span data-ttu-id="2b55a-119">Después de realizar algunos acciones en las que se requiere el registro fiscal, como por ejemplo después de finalizar una transacción al por menor, el proceso de registro fiscal se asocia al perfil de funcionalidad actual de PDV.</span><span class="sxs-lookup"><span data-stu-id="2b55a-119">After performing some actions where fiscal registration is required, such as after a retail transaction has been concluded, the fiscal registration process is associated with the current POS functionality profile.</span></span>

1. <span data-ttu-id="2b55a-120">Buscar un conector fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-120">Search for a fiscal connector.</span></span>
   
   <span data-ttu-id="2b55a-121">Para cada paso de registro fiscal incluido en el proceso de registro fiscal, el sistema correlaciona la lista de conectores fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-121">For each fiscal registration step included in the fiscal registration process, the system matches the list of fiscal connectors.</span></span> <span data-ttu-id="2b55a-122">Estos conectores tienen un perfil funcional incluido en el grupo de conectores especificados, con una lista de conectores que tienen un perfil técnico asociado al perfil de hardware actual (para un tipo de conector que es **Local** solo) o al perfil de funcionalidad actual de PDV (para otros tipos de conectores).</span><span class="sxs-lookup"><span data-stu-id="2b55a-122">These connectors have a functional profile included in the specified connector group, with a list of connectors that have a technical profile associated with the current hardware profile (for a connector type that equals **Local** only) or with the current POS functionality profile (for other connector types).</span></span>
   
1. <span data-ttu-id="2b55a-123">Realice la integración fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-123">Perform the fiscal integration.</span></span>

   <span data-ttu-id="2b55a-124">El sistema ejecuta todas las acciones necesarias definidas por un ensamblado vinculado con el conector encontrado.</span><span class="sxs-lookup"><span data-stu-id="2b55a-124">The system executes all necessary actions defined by an assembly linked with the found connector.</span></span> <span data-ttu-id="2b55a-125">Esto se realiza de acuerdo con los valores del perfil funcional y del perfil técnico que se encontraron en el paso anterior para este conector.</span><span class="sxs-lookup"><span data-stu-id="2b55a-125">This is done in accordance with the settings of the functional profile and technical profile that were found on the previous step for this connector.</span></span>

## <a name="setup-needed-before-using-fiscal-integration"></a><span data-ttu-id="2b55a-126">Configuración necesaria antes de utilizar la integración fiscal</span><span class="sxs-lookup"><span data-stu-id="2b55a-126">Setup needed before using fiscal integration</span></span>
<span data-ttu-id="2b55a-127">Antes de usar la funcionalidad de la integración fiscal, debe definir los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b55a-127">Before using the fiscal integration functionality, you should define the following settings:</span></span>

- <span data-ttu-id="2b55a-128">Defina la secuencia numérica en la página **Parámetros de ventas** para el número de perfil funcional fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-128">Define the number sequence on the **Retail parameters** page for the fiscal functional profile number.</span></span>
  
- <span data-ttu-id="2b55a-129">Defina las secuencias numéricas en la página **Parámetros compartidos comerciales** para las referencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b55a-129">Define the number sequences on the **Retail shared parameters** page for the following references:</span></span>
  
  - <span data-ttu-id="2b55a-130">Número de perfil técnico fiscal</span><span class="sxs-lookup"><span data-stu-id="2b55a-130">Fiscal technical profile number</span></span>
  - <span data-ttu-id="2b55a-131">Número de grupo del conector fiscal</span><span class="sxs-lookup"><span data-stu-id="2b55a-131">Fiscal connector group number</span></span>
  - <span data-ttu-id="2b55a-132">Número de proceso de registro</span><span class="sxs-lookup"><span data-stu-id="2b55a-132">Registration process number</span></span>

- <span data-ttu-id="2b55a-133">Cree un **Conector fiscal** en **Venta minorista > Configuración de canal > integración fiscal > conectores fiscales** para cada dispositivo o servicio que tenga previsto usar para fines de integración fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-133">Create a **Fiscal connector** in **Retail > Channel setup > Fiscal integration > Fiscal connectors** for each device or service that you plan to use for fiscal integration purposes.</span></span>

-  <span data-ttu-id="2b55a-134">Cree **Proveedor de documento fiscal** en **Venta minorista > Configuración de canal > integración fiscal > proveedores de documentos fiscales** para todos los conectores fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-134">Create a **Fiscal document provider** in **Retail > Channel setup > Fiscal integration > Fiscal document providers** for all fiscal connectors.</span></span> <span data-ttu-id="2b55a-135">La asignación de datos se considera una parte del proveedor de documentos fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-135">Data mapping is considered a part of the fiscal document provider.</span></span> <span data-ttu-id="2b55a-136">Para configurar diferentes asignaciones de datos para el mismo conector (como normas de esetado específicas), debe crear varios proveedores de documentos fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-136">To set up different data mappings for the same connector (like state-specific regulations), you should create different fiscal document providers.</span></span>

- <span data-ttu-id="2b55a-137">Cree un **Perfil funcional de conector** en **Venta minorista > configurar canal> integración fiscal > perfiles funcionales de conector** para cada proveedor de documentos fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-137">Create a **Connector functional profile** in **Retail > Channel setup > Fiscal integration > Connector functional profiles** for each fiscal document provider.</span></span>
  - <span data-ttu-id="2b55a-138">Seleccione un nombre de conector.</span><span class="sxs-lookup"><span data-stu-id="2b55a-138">Select a connector name.</span></span>
  - <span data-ttu-id="2b55a-139">Seleccione un proveedor de documentos.</span><span class="sxs-lookup"><span data-stu-id="2b55a-139">Select a document provider.</span></span>
  - <span data-ttu-id="2b55a-140">Especifique los valores de índices de IVA en la pestaña **configuración del servicio**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-140">Specify VAT rates settings on the **Service setup** tab.</span></span>
  - <span data-ttu-id="2b55a-141">Especifique la asignación de códigos de IVA y la asignación de tipo de pago en la pestaña **Asignación de datos**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-141">Specify VAT codes mapping and tender type mapping on the **Data mapping** tab.</span></span>

  #### <a name="examples"></a><span data-ttu-id="2b55a-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b55a-142">Examples</span></span> 

  |  | <span data-ttu-id="2b55a-143">Formato</span><span class="sxs-lookup"><span data-stu-id="2b55a-143">Format</span></span> | <span data-ttu-id="2b55a-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b55a-144">Example</span></span> | 
  |--------|--------|--------|
  | <span data-ttu-id="2b55a-145">Configuración de índices de IVA</span><span class="sxs-lookup"><span data-stu-id="2b55a-145">VAT rates settings</span></span> | <span data-ttu-id="2b55a-146">valor: VATrate</span><span class="sxs-lookup"><span data-stu-id="2b55a-146">value : VATrate</span></span> | <span data-ttu-id="2b55a-147">1 : 2000, 2 : 1800</span><span class="sxs-lookup"><span data-stu-id="2b55a-147">1 : 2000, 2 : 1800</span></span> |
  | <span data-ttu-id="2b55a-148">Asignación de códigos de IVA</span><span class="sxs-lookup"><span data-stu-id="2b55a-148">VAT codes mapping</span></span> | <span data-ttu-id="2b55a-149">VATcode : valor</span><span class="sxs-lookup"><span data-stu-id="2b55a-149">VATcode : value</span></span> | <span data-ttu-id="2b55a-150">vat20 : 1, vat18 : 2</span><span class="sxs-lookup"><span data-stu-id="2b55a-150">vat20 : 1, vat18 : 2</span></span> |
  | <span data-ttu-id="2b55a-151">Asignación de tipos de forma de pago</span><span class="sxs-lookup"><span data-stu-id="2b55a-151">Tender types mapping</span></span> | <span data-ttu-id="2b55a-152">TenderTyp: valor</span><span class="sxs-lookup"><span data-stu-id="2b55a-152">TenderTyp : value</span></span> | <span data-ttu-id="2b55a-153">Cash : 1, Card : 2</span><span class="sxs-lookup"><span data-stu-id="2b55a-153">Cash : 1, Card : 2</span></span> |

- <span data-ttu-id="2b55a-154">Cree **Grupos del conector fiscal** en **Venta minorista > Configuración de canal > integración fiscal > grupo del conector fiscal**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-154">Create **Fiscal connector groups** in **Retail > Channel setup > Fiscal integration > Fiscal connector group**.</span></span> <span data-ttu-id="2b55a-155">Un grupo de conectores es un subconjunto de perfiles funcionales vinculados con conectores fiscales que realizan idénticas funciones y se usan en la misma etapa del proceso de registro fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-155">A connector group is a subset of functional profiles linked with fiscal connectors that perform identical functions and are used at the same stage within a fiscal registration process.</span></span>

   - <span data-ttu-id="2b55a-156">Agregue perfiles funcionales el grupo de conectores.</span><span class="sxs-lookup"><span data-stu-id="2b55a-156">Add functional profiles to the connector group.</span></span> <span data-ttu-id="2b55a-157">Haga clic en **Agregar** en la página **Perfiles funcionales** y seleccione un número del perfil.</span><span class="sxs-lookup"><span data-stu-id="2b55a-157">Click **Add** on the **Functional profiles** page and select a profile number.</span></span>
   - <span data-ttu-id="2b55a-158">Si desea suspender el uso del perfil funcional, establezca **Deshabilitar** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-158">If you want to suspend usage of the functional profile, set **Disable** to **Yes**.</span></span> 
   
     <span data-ttu-id="2b55a-159">Este cambio afecta al grupo de conectores actuales únicamente.</span><span class="sxs-lookup"><span data-stu-id="2b55a-159">This change affects the current connector group only.</span></span> <span data-ttu-id="2b55a-160">Puede continuar con el mismo perfil funcional en otros grupos de conectores.</span><span class="sxs-lookup"><span data-stu-id="2b55a-160">You can continue using the same functional profile in other connector groups.</span></span>

     >[!NOTE]
     > <span data-ttu-id="2b55a-161">Dentro de un grupo de conectores, cada conector fiscal solo puede tener un perfil funcional.</span><span class="sxs-lookup"><span data-stu-id="2b55a-161">Within a connector group, each fiscal connector can only have one functional profile.</span></span>

- <span data-ttu-id="2b55a-162">Cree un **Perfil técnico de conector** en **Venta minorista > configurar canal> integración fiscal > perfiles técnicos de conector** para cada conector fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-162">Create a **Connector technical profile** in **Retail > Channel setup > Fiscal integration > Connector technical profiles** for each fiscal connector.</span></span>
  - <span data-ttu-id="2b55a-163">Seleccione un nombre de conector.</span><span class="sxs-lookup"><span data-stu-id="2b55a-163">Select a connector name.</span></span>
  - <span data-ttu-id="2b55a-164">Seleccione un tipo de conector:</span><span class="sxs-lookup"><span data-stu-id="2b55a-164">Select a connector type:</span></span> 
      - <span data-ttu-id="2b55a-165">**Local** - Establezca este tipo para los dispositivos o las solicitudes instaladas en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="2b55a-165">**Local** - Set this type for physical devices or applications installed on a local machine.</span></span>
      - <span data-ttu-id="2b55a-166">**Interno** - Estableza este tipo para los dispositivos fiscales y servicios conectados a Retail Server.</span><span class="sxs-lookup"><span data-stu-id="2b55a-166">**Internal** - Set this type for fiscal devices and services connected to Retail Server.</span></span>
      - <span data-ttu-id="2b55a-167">**Externo** - Para los servicios fiscales externos como un portal Web proporcionado por una autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-167">**External** - For external fiscal services like a web-portal provided by a tax authority.</span></span>
    
  - <span data-ttu-id="2b55a-168">Especifique la configuración en la pestaña **Conexión**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-168">Specify settings on the **Connection** tab.</span></span>

      
 >[!NOTE]
 > <span data-ttu-id="2b55a-169">Una versión actualizada de una configuración que se cargó anteriormente se cargará para los perfiles funcionales y técnicos.</span><span class="sxs-lookup"><span data-stu-id="2b55a-169">An updated version of a configuration that was loaded earlier will be loaded for both functional and technical profiles.</span></span> <span data-ttu-id="2b55a-170">Si ya se está usando un conector o un proveedor de documentos adecuado, se le notificará.</span><span class="sxs-lookup"><span data-stu-id="2b55a-170">If an appropriate connector or document provider is already in use, you will be notified.</span></span> <span data-ttu-id="2b55a-171">De forma predeterminada, todos los cambios realizados manualmente en perfiles funcionales y técnicos se guardarán.</span><span class="sxs-lookup"><span data-stu-id="2b55a-171">By default, all changes that have been made manually in functional and technical profiles will be stored.</span></span> <span data-ttu-id="2b55a-172">Para anular estos perfiles con el conjunto de parámetros predeterminado de una configuración, haga clic en **Actualizar** en la página **Perfiles funcionales del conector** y la página **Perfiles técnicos del conector**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-172">In order to override these profiles with the default set of parameters from a configuration, click **Update** on the **Connector functional profiles** page and **Connector technical profiles** page.</span></span>
 
- <span data-ttu-id="2b55a-173">Cree un **Proceso de registro fiscal** en **venta minorista > configurar canal > integración fiscal > procesos de registro fiscales** para cada proceso único de integración fiscal.</span><span class="sxs-lookup"><span data-stu-id="2b55a-173">Create a **Fiscal registration process** in **Retail > Channel setup > Fiscal integration > Fiscal registration processes** for each unique process of the fiscal integration.</span></span> <span data-ttu-id="2b55a-174">Un proceso de registro se define por la secuencia de los pasos de registro y el grupo de conectores utilizados en cada paso.</span><span class="sxs-lookup"><span data-stu-id="2b55a-174">A registration process is defined by the sequence of the registration steps and the connector group used on each step.</span></span> 
  
  - <span data-ttu-id="2b55a-175">Agregar pasos de registro al proceso:</span><span class="sxs-lookup"><span data-stu-id="2b55a-175">Add registration steps to the process:</span></span>
      - <span data-ttu-id="2b55a-176">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-176">Click **Add**.</span></span>
      - <span data-ttu-id="2b55a-177">Seleccione un tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="2b55a-177">Select a connector type.</span></span>
      
      >[!NOTE]
      > <span data-ttu-id="2b55a-178">Este campo define dónde el sistema buscará el conector en un perfil técnico, en los perfiles de hardware para el tipo de conector **local** o en los perfiles de funcionalidad de PDV para otros tipos de conectores fiscales.</span><span class="sxs-lookup"><span data-stu-id="2b55a-178">This field defines where the system will search in a technical profile for the connector, either in hardware profiles for connector type **Local**, or in POS functionality profiles for other fiscal connector types.</span></span>
      
   - <span data-ttu-id="2b55a-179">Seleccione un grupo de conectores.</span><span class="sxs-lookup"><span data-stu-id="2b55a-179">Select a connector group.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="2b55a-180">Haga clic en **Validar** para comprobar la integridad de la estructura del proceso de registro.</span><span class="sxs-lookup"><span data-stu-id="2b55a-180">Click **Validate** to check the integrity of the registration process structure.</span></span> <span data-ttu-id="2b55a-181">Se recomienda que se hagan las validaciones en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b55a-181">It’s recommended that validations be made in the following cases:</span></span>
       >- <span data-ttu-id="2b55a-182">Para un proceso de registro nuevo después de que toda la configuración se complete, incluidos los perfiles de funcionalidad PDV y los perfiles de hardware.</span><span class="sxs-lookup"><span data-stu-id="2b55a-182">For a new registration process after all the settings are completed, including binding to POS functionality profiles and hardware profiles.</span></span>
       >- <span data-ttu-id="2b55a-183">Después de crear actualizaciones en un proceso de registro existente.</span><span class="sxs-lookup"><span data-stu-id="2b55a-183">After making updates to an existing registration process.</span></span>

-  <span data-ttu-id="2b55a-184">Vincule los procesos de registro fiscales a los perfiles de funcionalidad del PDV en **Venta minorista > configurar canal > Configuración de PDV > perfiles de PDV > perfiles de funcionalidad**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-184">Bind fiscal registration processes to POS functionality profiles in **Retail > Channel setup > POS setup > POS profiles > Functionality profiles**.</span></span>
   - <span data-ttu-id="2b55a-185">Haga clic en **Editar** y seleccione **Número de proceso** en la pestaña **Proceso de registro fiscal**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-185">Click **Edit** and select a **Process number** on the **Fiscal registration process** tab.</span></span>
- <span data-ttu-id="2b55a-186">Vincule los perfiles técnicos de conectores a los perfiles de hardware en **venta minorista > configurar canal > Configuración de PDV > perfiles PDV > perfiles de hardware**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-186">Bind the connector technical profiles to the hardware profiles in **Retail > Channel setup > POS setup > POS profiles > Hardware profiles**.</span></span>
   - <span data-ttu-id="2b55a-187">Haga clic en **Editar** y, a continuación, haga clic en **Nuevo** en la pestaña **Perfil técnico fiscal**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-187">Click **Edit**, then click **New** on the **Fiscal technical profile** tab.</span></span>
   - <span data-ttu-id="2b55a-188">Seleccione un perfil del técnico de conector en el campo **Número de perfil**.</span><span class="sxs-lookup"><span data-stu-id="2b55a-188">Select a connector technical profile in the **Profile number** field.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="2b55a-189">Puede agregar varios perfiles técnicos a un perfil de hardware.</span><span class="sxs-lookup"><span data-stu-id="2b55a-189">You can add several technical profiles to a hardware profile.</span></span> <span data-ttu-id="2b55a-190">Sin embargo, esto no se admite si un perfil de hardware tiene más de una intersección con cualquier grupo de conectores.</span><span class="sxs-lookup"><span data-stu-id="2b55a-190">However, this is not supported if a hardware profile has more than one intersection with any connector group.</span></span> <span data-ttu-id="2b55a-191">Para evitar valores incorrectos, se recomienda que valide el proceso de registro después de actualizar todos los perfiles de hardware.</span><span class="sxs-lookup"><span data-stu-id="2b55a-191">To avoid incorrect settings, it’s recommended that you validate the registration process after updating all the hardware profiles.</span></span>

