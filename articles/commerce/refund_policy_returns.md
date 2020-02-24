---
title: Crear y actualizar una directiva de devoluciones y reembolsos para un canal
description: Este tema explica cómo configurar una directiva de devoluciones y reembolsos para un canal.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 66bb9bbd338561315f2f69ae4aff86a67513b190
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024009"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="340d9-103">Crear y actualizar una directiva de devoluciones y reembolsos para un canal</span><span class="sxs-lookup"><span data-stu-id="340d9-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]


## <a name="overview"></a><span data-ttu-id="340d9-104">Visión general</span><span class="sxs-lookup"><span data-stu-id="340d9-104">Overview</span></span>

<span data-ttu-id="340d9-105">La directiva de devoluciones del canal en Dynamics 365 Commerce permite a los minoristas establecer medidas de cumplimiento sobre las cuales se pueden permitir formas de pago para procesar una devolución en un dispositivo de punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="340d9-105">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="340d9-106">Este tema describe los pasos para configurar una directiva de devoluciones y reembolsos para un canal.</span><span class="sxs-lookup"><span data-stu-id="340d9-106">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="340d9-107">El alcance de la directiva se limita actualmente a establecer las formas de pago que se pueden permitir para un canal.</span><span class="sxs-lookup"><span data-stu-id="340d9-107">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="340d9-108">La lista "permitidos" se basa en los métodos de pago utilizados para realizar la compra.</span><span class="sxs-lookup"><span data-stu-id="340d9-108">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="340d9-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="340d9-109">For example:</span></span>

- <span data-ttu-id="340d9-110">Si una compra se realizó con una tarjeta regalo, la directiva de la tienda es procesar los reembolsos solo a una nueva tarjeta de regalo o dar crédito de la tienda.</span><span class="sxs-lookup"><span data-stu-id="340d9-110">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="340d9-111">Si una venta se realiza en efectivo, las opciones permitidas para reembolso son efectivo, tarjeta de regalo y cuenta del cliente, pero no tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="340d9-111">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="340d9-112">Habilitar directiva de devolución</span><span class="sxs-lookup"><span data-stu-id="340d9-112">Enable return policy</span></span>

<span data-ttu-id="340d9-113">Para habilitar la funcionalidad de directiva de devolución del canal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="340d9-113">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="340d9-114">Vaya al espacio de trabajo **Administración de características** en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="340d9-114">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="340d9-115">Busque la característica **Habilitar directiva de devoluciones del canal** en la lista de nombres de características.</span><span class="sxs-lookup"><span data-stu-id="340d9-115">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="340d9-116">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="340d9-116">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="340d9-117">Configurar directiva de devoluciones</span><span class="sxs-lookup"><span data-stu-id="340d9-117">Configure return policy</span></span>

<span data-ttu-id="340d9-118">Siga estos pasos para configurar una política de devoluciones para una tienda minorista o un canal minorista en línea.</span><span class="sxs-lookup"><span data-stu-id="340d9-118">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="340d9-119">Vaya a **Retail y Commerce** \> **Configuración de canal** \> **Devoluciones** \> **Directiva de devoluciones del canal**.</span><span class="sxs-lookup"><span data-stu-id="340d9-119">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="340d9-120">Seleccione **Nueva** para crear una nueva plantilla de directiva de devoluciones.</span><span class="sxs-lookup"><span data-stu-id="340d9-120">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="340d9-121">Para usar una plantilla existente, seleccione la plantilla en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="340d9-121">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="340d9-122">Para nuevas plantillas, agregue un nombre y una descripción que le ayudará a identificar la directiva cuando se aplique al canal.</span><span class="sxs-lookup"><span data-stu-id="340d9-122">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="340d9-123">![Agregar nueva directiva de devoluciones](media/Return-policy-page1.png "Agregar nueva directiva de devoluciones")</span><span class="sxs-lookup"><span data-stu-id="340d9-123">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="340d9-124">En la sección **Métodos de pago de devoluciones permitidos**, defina las formas de pago de devolución **permitidas** que son específicas para cada método de pago.</span><span class="sxs-lookup"><span data-stu-id="340d9-124">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="340d9-125">![Agregar métodos de pago](media/Return-policy-page2.PNG "Establecer métodos de pago permitidos por tipo de pago")</span><span class="sxs-lookup"><span data-stu-id="340d9-125">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="340d9-126">Los métodos de pago se derivan de los métodos de pago establecidos para la organización.</span><span class="sxs-lookup"><span data-stu-id="340d9-126">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="340d9-127">La adición de un tipo de forma de pago de devolución permitida para cada método de pago mostrado garantizará que las devoluciones se puedan realizar al tipo de forma de pago de devolución permitido.</span><span class="sxs-lookup"><span data-stu-id="340d9-127">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="340d9-128">Asocie la plantilla de directiva de devoluciones a las tiendas en la que se usará.</span><span class="sxs-lookup"><span data-stu-id="340d9-128">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="340d9-129">Seleccione **Agregar** en la pestaña **Canales minoristas** y asocie los canales disponibles.</span><span class="sxs-lookup"><span data-stu-id="340d9-129">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="340d9-130">En el cuadro de diálogo **Elegir nodos organizativos**, seleccione las tiendas, regiones y organizaciones a las que debe asociarse la plantilla.</span><span class="sxs-lookup"><span data-stu-id="340d9-130">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="340d9-131">Solo se puede asociar una plantilla de directiva de devoluciones a cada tienda.</span><span class="sxs-lookup"><span data-stu-id="340d9-131">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="340d9-132">Use los botones de flecha para seleccionar tiendas, regiones u organizaciones.</span><span class="sxs-lookup"><span data-stu-id="340d9-132">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="340d9-133">La fecha de vigencia de la directiva será la fecha en que las directivas se aplican a los canales y se ejecuten los trabajos del canal.</span><span class="sxs-lookup"><span data-stu-id="340d9-133">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="340d9-134">![Cuadro de diálogo Elegir nodos organizativos](media/Return-policy-page3.PNG "Cuadro de diálogo Elegir nodos organizativos")</span><span class="sxs-lookup"><span data-stu-id="340d9-134">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="340d9-135">En la página **Programación de distribución**, ejecute el trabajo **1070** para que la directiva de devoluciones del canal esté disponible para el PDV.</span><span class="sxs-lookup"><span data-stu-id="340d9-135">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="340d9-136">Vista previa de la directiva de devolución del canal en el PDV</span><span class="sxs-lookup"><span data-stu-id="340d9-136">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="340d9-137">Siga los pasos en cualquiera de los siguientes ejemplos para ver los tipos de formas de pago de devolución permitidos en PDV.</span><span class="sxs-lookup"><span data-stu-id="340d9-137">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="340d9-138">Inicie sesión en el PDV como cajero o director.</span><span class="sxs-lookup"><span data-stu-id="340d9-138">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="340d9-139">Debajo de **Turnos y caja registradora**, seleccione **Mostrar diario**.</span><span class="sxs-lookup"><span data-stu-id="340d9-139">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="340d9-140">Seleccione la transacción que forma parte de la devolución.</span><span class="sxs-lookup"><span data-stu-id="340d9-140">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="340d9-141">Seleccione los artículos de los que se hará la devolución y elija el método de pago.</span><span class="sxs-lookup"><span data-stu-id="340d9-141">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="340d9-142">Si la forma de pago seleccionada aparece en la lista permitida de tipos de forma de pago de devolución, el cajero puede completar la transacción.</span><span class="sxs-lookup"><span data-stu-id="340d9-142">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="340d9-143">Si la forma de pago seleccionada no está permitida, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="340d9-143">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="340d9-144">Seleccione **Importe vencido** para mostrar una lista de todos los tipos de formas de pago de devolución permitidos.</span><span class="sxs-lookup"><span data-stu-id="340d9-144">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="340d9-145">– O bien –</span><span class="sxs-lookup"><span data-stu-id="340d9-145">-or-</span></span>

1. <span data-ttu-id="340d9-146">Inicie sesión en el PDV como cajero o director.</span><span class="sxs-lookup"><span data-stu-id="340d9-146">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="340d9-147">Seleccione **Transacción de devolución** e introduzca el id. de recibo que usa un análisis de código de barras o introdúzcalo manualmente.</span><span class="sxs-lookup"><span data-stu-id="340d9-147">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="340d9-148">Seleccione la transacción que forma parte de la devolución.</span><span class="sxs-lookup"><span data-stu-id="340d9-148">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="340d9-149">Seleccione los artículos de los que se hará la devolución y elija el método de pago.</span><span class="sxs-lookup"><span data-stu-id="340d9-149">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="340d9-150">Si la forma de pago seleccionada aparece en la lista permitida de tipos de forma de pago de devolución, el cajero puede completar la transacción.</span><span class="sxs-lookup"><span data-stu-id="340d9-150">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="340d9-151">Si la forma de pago seleccionada no está permitida, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="340d9-151">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="340d9-152">Seleccione **Importe vencido** para mostrar una lista de todos los tipos de formas de pago de devolución permitidos.</span><span class="sxs-lookup"><span data-stu-id="340d9-152">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="340d9-153">![Devolución no permitida](media/Return-policy-page6.png "Tipo de devolución no permitido")</span><span class="sxs-lookup"><span data-stu-id="340d9-153">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="340d9-154">![Lista de métodos de pago](media/Return-policy-page5.PNG "Tipos de devolución permitidos")</span><span class="sxs-lookup"><span data-stu-id="340d9-154">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>
