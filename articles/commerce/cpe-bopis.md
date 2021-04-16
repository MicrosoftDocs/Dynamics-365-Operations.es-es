---
title: Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce
description: Este tema explica cómo configurar la compra en línea, la recogida en la tienda (BOPIS) en un ambiente de evaluación de Microsoft Dynamics 365 Commerce después de que se haya aprovisionado.
author: rubendel
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 219504da62fd4637ed01f9acbab32f873cef81b0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795964"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="10579-103">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-103">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="10579-104">Este tema explica cómo configurar la compra en línea, la recogida en la tienda (BOPIS) en un ambiente de evaluación de Microsoft Dynamics 365 Commerce después de que el entorno se haya aprovisionado.</span><span class="sxs-lookup"><span data-stu-id="10579-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce evaluation environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="10579-105">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="10579-105">Prerequisite</span></span>

<span data-ttu-id="10579-106">Complete los procedimientos de este tema solo después de que se haya aprovisionado y configurado su entorno de evaluación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="10579-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned and configured.</span></span> <span data-ttu-id="10579-107">Para obtener información sobre cómo aprovisionar y configurar su entorno, consulte [Aprovisionar un entorno de evaluación de Dynamics 365 Commerce](provisioning-guide.md) y [Configurar un entorno de evaluación de Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span><span class="sxs-lookup"><span data-stu-id="10579-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce evaluation environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce evaluation environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="10579-108">Después de que su entorno de Commerce se haya aprovisionado y configurado de principio a fin, puede usar este tema para habilitar escenarios BOPIS.</span><span class="sxs-lookup"><span data-stu-id="10579-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="10579-109">Configurar el PDV</span><span class="sxs-lookup"><span data-stu-id="10579-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="10579-110">Configurar Modern POS</span><span class="sxs-lookup"><span data-stu-id="10579-110">Configure Modern POS</span></span>

<span data-ttu-id="10579-111">Los escenarios BOPIS que implican un pago con tarjeta de crédito requieren una estación de hardware.</span><span class="sxs-lookup"><span data-stu-id="10579-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="10579-112">La estación de hardware se ha incluido en el programa Modern POS para clientes Windows y Android.</span><span class="sxs-lookup"><span data-stu-id="10579-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="10579-113">Si está utilizando Cloud POS o Modern POS para iOS, el cliente del punto de venta (PDV) debe estar emparejado con una estación de hardware compartida.</span><span class="sxs-lookup"><span data-stu-id="10579-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="10579-114">Este tema explica cómo configurar BOPIS para clientes Windows y Android.</span><span class="sxs-lookup"><span data-stu-id="10579-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="10579-115">Para obtener más información sobre cómo configurar una estación de hardware compartida, consulte [Configurar e instalar la estación de hardware de Retail](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="10579-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="10579-116">Vaya a **Venta minorista y comercio \> Configuración de canal \> Configuración de PDV \> Registros**.</span><span class="sxs-lookup"><span data-stu-id="10579-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="10579-117">Seleccione el registro **SANFRAN-5** y luego seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="10579-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="10579-118">Cambie el valor del campo **Perfil de hardware** de **HW002** a **HW001** y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="10579-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="10579-119">Para sincronizar los cambios, vaya **Venta minorista y comercio \> TI de venta minorista y comercio \> Programación distribución**.</span><span class="sxs-lookup"><span data-stu-id="10579-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="10579-120">Seleccione la programación de distribución **1090** y en el panel de acciones, seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="10579-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="10579-121">Seleccione **Sí** y luego **Aceptar** para iniciar la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="10579-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="10579-122">Instalar Modern POS</span><span class="sxs-lookup"><span data-stu-id="10579-122">Install Modern POS</span></span>

1. <span data-ttu-id="10579-123">Vaya a **Venta minorista y comercio \> Configuración de canal \> Configuración de PDV \> Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="10579-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="10579-124">Seleccione el dispositivo **SANFRANCIS-5**.</span><span class="sxs-lookup"><span data-stu-id="10579-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="10579-125">En el panel de acciones, seleccione **Descargar** y **Archivo de configuración**.</span><span class="sxs-lookup"><span data-stu-id="10579-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="10579-126">Seleccione **Descargar** y luego **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="10579-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="10579-127">Cuando descargue el archivo **ModernPOSSetup.exe**, seleccione **Abrir archivo**.</span><span class="sxs-lookup"><span data-stu-id="10579-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Abrir archivo](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="10579-129">Seleccione **Siguiente** para ejecutar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="10579-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="10579-130">Cuando se complete la instalación, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="10579-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="10579-131">Activar Modern POS</span><span class="sxs-lookup"><span data-stu-id="10579-131">Activate Modern POS</span></span>

1. <span data-ttu-id="10579-132">En el escritorio de Windows, seleccione el botón **Inicio** e introduzca **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="10579-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="10579-133">Seleccione la aplicación **Retail Modern POS** para iniciar la activación.</span><span class="sxs-lookup"><span data-stu-id="10579-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="10579-134">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="10579-134">Select **Next**.</span></span> <span data-ttu-id="10579-135">Los campos **URL del servidor**, **ID del dispositivo** y **Número de registro** deben preestablecerse utilizando la información del archivo de configuración que descargó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="10579-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="10579-136">Seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="10579-136">Select **Activate**.</span></span>
5. <span data-ttu-id="10579-137">Aparece un cuadro de diálogo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="10579-137">An authentication dialog box appears.</span></span> <span data-ttu-id="10579-138">Seleccione la cuenta que usa la dirección de correo electrónico que anteriormente estaba asociada con el trabajador **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="10579-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="10579-139">Si aún no ha asociado a un trabajador con su identidad, la activación no tendrá éxito.</span><span class="sxs-lookup"><span data-stu-id="10579-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="10579-140">En este caso, siga los pasos de la sección "Asociar un trabajador con su identidad" en el tema [Configurar un entorno de evaluación de Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).</span><span class="sxs-lookup"><span data-stu-id="10579-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce evaluation environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="10579-141">Cuando se le solicite que permita que su organización administre el dispositivo, seleccione **Esta aplicación solo**.</span><span class="sxs-lookup"><span data-stu-id="10579-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="10579-142">Cuando se complete la activación, seleccione **Empezar**.</span><span class="sxs-lookup"><span data-stu-id="10579-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="10579-143">Habilitar BOPIS en Modern POS</span><span class="sxs-lookup"><span data-stu-id="10579-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="10579-144">Inicie sesión en Modern POS utilizando **000713** como id. de operador y **123** como contraseña.</span><span class="sxs-lookup"><span data-stu-id="10579-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="10579-145">Mientras se reproduce el vídeo introductorio, seleccione las dos casillas de verificación en la esquina inferior izquierda del cuadro de diálogo y luego cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10579-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="10579-146">Si no se le solicita que cierre el turno, desplácese hacia la derecha en la página **Bienvenidos**, seleccione **Cerrar turno** y luego vuelva a iniciar sesión en el PDV.</span><span class="sxs-lookup"><span data-stu-id="10579-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="10579-147">Después de iniciar sesión, cuando se le solicite, seleccione **Realizar operaciones no relacionadas con la caja registradora**.</span><span class="sxs-lookup"><span data-stu-id="10579-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="10579-148">En la página **Bienvenidos**, desplácese hacia la derecha y seleccione la operación **Seleccionar estación de hardware**.</span><span class="sxs-lookup"><span data-stu-id="10579-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="10579-149">Seleccione **Gestionar**, establezca la opción **Usar estación de hardware** en **Activar** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="10579-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="10579-150">Cierre sesión del PDV y, a continuación, vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="10579-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="10579-151">Después de iniciar sesión, seleccione **Abrir un nuevo turno** y luego seleccione **Cajón**.</span><span class="sxs-lookup"><span data-stu-id="10579-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="10579-152">Completar un escenario BOPIS</span><span class="sxs-lookup"><span data-stu-id="10579-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="10579-153">Crear un pedido de escaparate para recoger en la tienda</span><span class="sxs-lookup"><span data-stu-id="10579-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="10579-154">Vaya a la URL que especificó en el paso [Inicializar comercio electrónico](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) durante la configuración del entorno.</span><span class="sxs-lookup"><span data-stu-id="10579-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="10579-155">Seleccione un artículo y seleccione **Añadir al carrito**.</span><span class="sxs-lookup"><span data-stu-id="10579-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="10579-156">En la página de la bolsa de compras, seleccione **Recoger esto** para la línea de pedido que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="10579-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="10579-157">En el cuadro de diálogo **Seleccionar una tienda**, ingrese **San Francisco** y luego seleccione el botón **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="10579-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="10579-158">En la lista de resultados, busque la tienda de San Francisco y seleccione **Recoger aquí**.</span><span class="sxs-lookup"><span data-stu-id="10579-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="10579-159">En la página de la bolsa de compras, seleccione **Pagar como invitado**.</span><span class="sxs-lookup"><span data-stu-id="10579-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="10579-160">Para continuar con el pago, debe aceptar el aviso de cookies.</span><span class="sxs-lookup"><span data-stu-id="10579-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="10579-161">Este aviso aparece como un banner en la parte superior de la página de pago.</span><span class="sxs-lookup"><span data-stu-id="10579-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="10579-162">Para el método de pago con tarjeta de crédito, ingrese los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="10579-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="10579-163">**Nombre del titular de la tarjeta**: ingrese cualquier nombre.</span><span class="sxs-lookup"><span data-stu-id="10579-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="10579-164">**Número de tarjeta**: introduzca **4111-1111-1111-1111**.</span><span class="sxs-lookup"><span data-stu-id="10579-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="10579-165">**Fecha de vencimiento**: introduzca **10/20**.</span><span class="sxs-lookup"><span data-stu-id="10579-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="10579-166">**Código de seguridad de la tarjeta (CVV)**: introduzca **737**.</span><span class="sxs-lookup"><span data-stu-id="10579-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="10579-167">Bajo ninguna circunstancia intente usar la información de un tarjeta de crédito real en el sitio de prueba.</span><span class="sxs-lookup"><span data-stu-id="10579-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="10579-168">Continúe con el pago ingresando los detalles de la dirección de facturación y luego seleccione **Guardar y continuar**.</span><span class="sxs-lookup"><span data-stu-id="10579-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="10579-169">Cuando el pedido esté listo para ser realizado, seleccione **Finalizar compra**.</span><span class="sxs-lookup"><span data-stu-id="10579-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="10579-170">Sincronizar pedidos en línea con la oficina administrativa</span><span class="sxs-lookup"><span data-stu-id="10579-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="10579-171">Para obtener información sobre cómo sincronizar pedidos en línea, vea [Publicación de ventas y pagos en línea](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="10579-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="10579-172">Recoger un pedido en tienda</span><span class="sxs-lookup"><span data-stu-id="10579-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="10579-173">Inicie sesión en el PDV.</span><span class="sxs-lookup"><span data-stu-id="10579-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="10579-174">En la página **Bienvenidos**, seleccione **Cumplimiento de la orden**.</span><span class="sxs-lookup"><span data-stu-id="10579-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="10579-175">En la lista de artículos para recoger, seleccione la línea del pedido que se realizó en línea.</span><span class="sxs-lookup"><span data-stu-id="10579-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="10579-176">Con la línea de pedido seleccionada, seleccione **Recoger**.</span><span class="sxs-lookup"><span data-stu-id="10579-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="10579-177">La línea de pedido se agrega a la pantalla de transacción y aparece **$ 0.00** como saldo adeudado.</span><span class="sxs-lookup"><span data-stu-id="10579-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="10579-178">Seleccione el saldo adeudado de **$ 0.00** o seleccione cualquier método de pago para concluir la transacción.</span><span class="sxs-lookup"><span data-stu-id="10579-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="10579-179">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="10579-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="10579-180">Los pedidos en línea que se recuperan en el PDV tienen un saldo adeudado distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="10579-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="10579-181">Cuando se recupera un pedido para la recogida en la tienda, si el saldo adeudado no es 0 (cero), asegúrese de que se esté utilizando Modern POS y que la estación de hardware esté activa.</span><span class="sxs-lookup"><span data-stu-id="10579-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="10579-182">Si se utiliza Cloud POS o Modern POS para iOS, asegúrese de que haya activado una estación de hardware compartida.</span><span class="sxs-lookup"><span data-stu-id="10579-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="10579-183">Se requiere alguna forma de estación de hardware activa para recuperar los pagos que se realizaron en línea.</span><span class="sxs-lookup"><span data-stu-id="10579-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="10579-184">Problemas generales con la captura de pagos</span><span class="sxs-lookup"><span data-stu-id="10579-184">General issues with payment capture</span></span>

<span data-ttu-id="10579-185">Para todos los problemas generales, siempre debe consultar los registros de eventos de la estación de hardware de Modern POS o Internet Information Services (IIS) como primer paso.</span><span class="sxs-lookup"><span data-stu-id="10579-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="10579-186">Puede encontrar estos registros en los siguientes nodos en el registro de eventos de Windows:</span><span class="sxs-lookup"><span data-stu-id="10579-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="10579-187">Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="10579-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="10579-188">Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> estación de hardware de Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="10579-189">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="10579-189">Additional resources</span></span>

[<span data-ttu-id="10579-190">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-190">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="10579-191">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-191">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="10579-192">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-192">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="10579-193">Preguntas frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-193">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="10579-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="10579-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="10579-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="10579-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="10579-196">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="10579-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="10579-197">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="10579-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="10579-198">Conector de pago Adyen</span><span class="sxs-lookup"><span data-stu-id="10579-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="10579-199">Guardar los instrumentos de pago en línea con el conector de Adyen</span><span class="sxs-lookup"><span data-stu-id="10579-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="10579-200">Visión general de pagos omnicanal</span><span class="sxs-lookup"><span data-stu-id="10579-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)


[!INCLUDE[footer-include](../includes/footer-banner.md)]