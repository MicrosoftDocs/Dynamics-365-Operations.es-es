---
title: Crear y actualizar una directiva de devoluciones y reembolsos para un canal
description: Este tema explica cómo configurar una directiva de devoluciones y reembolsos para un canal.
author: ShalabhjainMSFT
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: e23291130d55fdfb5c2e2077b78c221866d72c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792084"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="b4aaa-103">Crear y actualizar una directiva de devoluciones y reembolsos para un canal</span><span class="sxs-lookup"><span data-stu-id="b4aaa-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b4aaa-104">La directiva de devoluciones del canal en Dynamics 365 Commerce permite a los minoristas establecer medidas de cumplimiento sobre las cuales se pueden permitir formas de pago para procesar una devolución en un dispositivo de punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="b4aaa-104">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="b4aaa-105">Este tema describe los pasos para configurar una directiva de devoluciones y reembolsos para un canal.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-105">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="b4aaa-106">El alcance de la directiva se limita actualmente a establecer las formas de pago que se pueden permitir para un canal.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-106">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="b4aaa-107">La lista "permitidos" se basa en los métodos de pago utilizados para realizar la compra.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-107">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="b4aaa-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4aaa-108">For example:</span></span>

- <span data-ttu-id="b4aaa-109">Si una compra se realizó con una tarjeta regalo, la directiva de la tienda es procesar los reembolsos solo a una nueva tarjeta de regalo o dar crédito de la tienda.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-109">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="b4aaa-110">Si una venta se realiza en efectivo, las opciones permitidas para reembolso son efectivo, tarjeta de regalo y cuenta del cliente, pero no tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-110">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="b4aaa-111">Habilitar directiva de devolución</span><span class="sxs-lookup"><span data-stu-id="b4aaa-111">Enable return policy</span></span>

<span data-ttu-id="b4aaa-112">Para habilitar la funcionalidad de directiva de devolución del canal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4aaa-112">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="b4aaa-113">Vaya al espacio de trabajo **Administración de características** en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-113">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="b4aaa-114">Busque la característica **Habilitar directiva de devoluciones del canal** en la lista de nombres de características.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-114">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="b4aaa-115">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-115">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="b4aaa-116">Configurar directiva de devoluciones</span><span class="sxs-lookup"><span data-stu-id="b4aaa-116">Configure return policy</span></span>

<span data-ttu-id="b4aaa-117">Siga estos pasos para configurar una política de devoluciones para una tienda minorista o un canal minorista en línea.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-117">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="b4aaa-118">Vaya a **Retail y Commerce** \> **Configuración de canal** \> **Devoluciones** \> **Directiva de devoluciones del canal**.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-118">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="b4aaa-119">Seleccione **Nueva** para crear una nueva plantilla de directiva de devoluciones.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-119">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="b4aaa-120">Para usar una plantilla existente, seleccione la plantilla en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-120">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="b4aaa-121">Para nuevas plantillas, agregue un nombre y una descripción que le ayudará a identificar la directiva cuando se aplique al canal.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-121">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="b4aaa-122">![Agregar nueva directiva de devoluciones](media/Return-policy-page1.png "Agregar nueva directiva de devoluciones")</span><span class="sxs-lookup"><span data-stu-id="b4aaa-122">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="b4aaa-123">En la sección **Métodos de pago de devoluciones permitidos**, defina las formas de pago de devolución **permitidas** que son específicas para cada método de pago.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-123">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="b4aaa-124">![Agregar métodos de pago](media/Return-policy-page2.PNG "Establecer métodos de pago permitidos por tipo de pago")</span><span class="sxs-lookup"><span data-stu-id="b4aaa-124">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="b4aaa-125">Los métodos de pago se derivan de los métodos de pago establecidos para la organización.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-125">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="b4aaa-126">La adición de un tipo de forma de pago de devolución permitida para cada método de pago mostrado garantizará que las devoluciones se puedan realizar al tipo de forma de pago de devolución permitido.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-126">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="b4aaa-127">Asocie la plantilla de directiva de devoluciones a las tiendas en la que se usará.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-127">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="b4aaa-128">Seleccione **Agregar** en la pestaña **Canales minoristas** y asocie los canales disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-128">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="b4aaa-129">En el cuadro de diálogo **Elegir nodos organizativos**, seleccione las tiendas, regiones y organizaciones a las que debe asociarse la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-129">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="b4aaa-130">Solo se puede asociar una plantilla de directiva de devoluciones a cada tienda.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-130">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="b4aaa-131">Use los botones de flecha para seleccionar tiendas, regiones u organizaciones.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-131">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="b4aaa-132">La fecha de vigencia de la directiva será la fecha en que las directivas se aplican a los canales y se ejecuten los trabajos del canal.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-132">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="b4aaa-133">![Cuadro de diálogo Elegir nodos organizativos](media/Return-policy-page3.PNG "Cuadro de diálogo Elegir nodos organizativos")</span><span class="sxs-lookup"><span data-stu-id="b4aaa-133">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="b4aaa-134">En la página **Programación de distribución**, ejecute el trabajo **1070** para que la directiva de devoluciones del canal esté disponible para el PDV.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-134">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="b4aaa-135">Vista previa de la directiva de devolución del canal en el PDV</span><span class="sxs-lookup"><span data-stu-id="b4aaa-135">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="b4aaa-136">Siga los pasos en cualquiera de los siguientes ejemplos para ver los tipos de formas de pago de devolución permitidos en PDV.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-136">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="b4aaa-137">Inicie sesión en el PDV como cajero o director.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-137">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="b4aaa-138">Debajo de **Turnos y caja registradora**, seleccione **Mostrar diario**.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-138">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="b4aaa-139">Seleccione la transacción que forma parte de la devolución.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-139">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="b4aaa-140">Seleccione los artículos de los que se hará la devolución y elija el método de pago.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-140">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="b4aaa-141">Si la forma de pago seleccionada aparece en la lista permitida de tipos de forma de pago de devolución, el cajero puede completar la transacción.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-141">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="b4aaa-142">Si la forma de pago seleccionada no está permitida, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-142">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="b4aaa-143">Seleccione **Importe vencido** para mostrar una lista de todos los tipos de formas de pago de devolución permitidos.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-143">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="b4aaa-144">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b4aaa-144">-or-</span></span>

1. <span data-ttu-id="b4aaa-145">Inicie sesión en el PDV como cajero o director.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-145">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="b4aaa-146">Seleccione **Transacción de devolución** e introduzca el id. de recibo que usa un análisis de código de barras o introdúzcalo manualmente.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-146">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="b4aaa-147">Seleccione la transacción que forma parte de la devolución.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-147">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="b4aaa-148">Seleccione los artículos de los que se hará la devolución y elija el método de pago.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-148">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="b4aaa-149">Si la forma de pago seleccionada aparece en la lista permitida de tipos de forma de pago de devolución, el cajero puede completar la transacción.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-149">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="b4aaa-150">Si la forma de pago seleccionada no está permitida, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-150">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="b4aaa-151">Seleccione **Importe vencido** para mostrar una lista de todos los tipos de formas de pago de devolución permitidos.</span><span class="sxs-lookup"><span data-stu-id="b4aaa-151">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="b4aaa-152">![Devolución no permitida](media/Return-policy-page6.png "Tipo de devolución no permitido")</span><span class="sxs-lookup"><span data-stu-id="b4aaa-152">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="b4aaa-153">![Lista de métodos de pago](media/Return-policy-page5.PNG "Tipos de devolución permitidos")</span><span class="sxs-lookup"><span data-stu-id="b4aaa-153">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
