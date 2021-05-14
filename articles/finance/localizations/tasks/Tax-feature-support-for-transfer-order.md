---
title: Compatibilidad de la característica de impuestos para pedidos de transferencia
description: Este tema explica la compatibilidad con la nueva función de impuestos para los pedidos de transferencia mediante el servicio de cálculo de impuestos.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920964"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="2cbb0-103">Compatibilidad de la característica de impuestos para pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="2cbb0-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2cbb0-104">Este tema proporciona información sobre el cálculo de impuestos y la integración de la contabilización en los pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="2cbb0-105">Esta funcionalidad le permite configurar el cálculo de impuestos y la contabilización en pedidos de transferencia para transferencias de existencias.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="2cbb0-106">Según las regulaciones del impuesto sobre el valor añadido (IVA) de la Unión Europea (UE), las transferencias de existencias se consideran suministro intracomunitario y adquisiciones intracomunitarias.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="2cbb0-107">Para configurar y utilizar esta funcionalidad, debe completar tres pasos principales:</span><span class="sxs-lookup"><span data-stu-id="2cbb0-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="2cbb0-108">**Configuración de RCS:** En el Servicio de configuración regulatoria, configure la función de impuestos, los códigos de impuestos y la aplicabilidad de los códigos de impuestos para la determinación del código de impuestos en los pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="2cbb0-109">**Configuración de finanzas:** en Microsoft Dynamics 365 Finance, active la característica **Impuesto en pedido de transferencia**, configure los parámetros del servicio de impuestos para el inventario y configure los parámetros de impuestos básicos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="2cbb0-110">**Configuración de inventario:** estableca la configuración de inventario para transacciones de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="2cbb0-111">Configurar RCS para transacciones de pedidos de transferencia e impuestos</span><span class="sxs-lookup"><span data-stu-id="2cbb0-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="2cbb0-112">Siga estos pasos para configurar el impuesto involucrado en un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="2cbb0-113">En el ejemplo que se muestra aquí, el pedido de transferencia es de Países Bajos a Bélgica.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="2cbb0-114">En la página **Características fiscales**, en la pestaña **Versiones**, seleccione la versión preliminar de la función y luego seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Selección de Editar](../media/image1.png)

2. <span data-ttu-id="2cbb0-116">En la página **Configuración de características fiscales**, en la pestaña **Códigos de impuestos**, seleccione **Agregar** para crear nuevos códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="2cbb0-117">Para este ejemplo, se crean tres códigos de impuestos: **NL-Exento**, **BE-RC-21** y **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="2cbb0-118">Cuando un pedido de transferencia se envía desde un almacén en Países Bajos, se aplica el código impositivo exento de IVA de Países Bajos (**NL-Exento**).</span><span class="sxs-lookup"><span data-stu-id="2cbb0-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="2cbb0-119">Cree el código de impuestos **NL-Exento**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="2cbb0-120">Seleccione **Agregar** e introduzca **NL-Exento** en el campo **Código de impuesto**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="2cbb0-121">Seleccione **Por importe neto** en el campo **Componente fiscal**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="2cbb0-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-122">Select **Save**.</span></span>
        4. <span data-ttu-id="2cbb0-123">Seleccione **Agregar** en la tabla **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="2cbb0-124">Cambie **Está exento** a **Sí** en la sección **General**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![Código fiscal NL-Exento](../media/image2.png)

    - <span data-ttu-id="2cbb0-126">Cuando se recibe un pedido de transferencia en un almacén de Bélgica, el mecanismo de inversión del cargo se aplica mediante los códigos de impuestos **BE-RC-21** y **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="2cbb0-127">Cree el código de impuestos **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="2cbb0-128">Seleccione **Agregar** e introduzca **BE-RC-21** en el campo **Código de impuesto**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="2cbb0-129">Seleccione **Por importe neto** en el campo **Componente fiscal**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="2cbb0-130">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-130">Select **Save**.</span></span>
        4. <span data-ttu-id="2cbb0-131">Seleccione **Agregar** en la tabla **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="2cbb0-132">Introduzca **-21** en el campo **Tipo impositivo**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="2cbb0-133">Cambie **Es cargo invertido** a **Sí** en la sección **General**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="2cbb0-134">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-134">Select **Save**.</span></span>

        ![Código de impuestos BE-RC-21 para cargos invertidos](../media/image3.png)
        
        <span data-ttu-id="2cbb0-136">Cree el código de impuestos **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="2cbb0-137">Seleccione **Agregar** e introduzca **BE-RC-21** en el campo **Código de impuesto**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="2cbb0-138">Seleccione **Por importe neto** en el campo **Componente fiscal**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="2cbb0-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-139">Select **Save**.</span></span>
        4. <span data-ttu-id="2cbb0-140">Seleccione **Agregar** en la tabla **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="2cbb0-141">Introduzca **21** en el campo **Tipo impositivo**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="2cbb0-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-142">Select **Save**.</span></span>

        ![Código de impuestos BE-RC+21 para cargos invertidos](../media/image4.png)

3. <span data-ttu-id="2cbb0-144">Defina la aplicabilidad de los códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="2cbb0-145">Seleccione **Administrar columnas** y, a continuación, seleccione las columnas que se deben utilizar para crear la tabla de aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2cbb0-146">Asegúrese de agregar las columnas **Procesos de negocio** y **Direcciones de impuestos** a la tabla.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="2cbb0-147">Ambas columnas son esenciales para la funcionalidad de los impuestos en pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="2cbb0-148">Agregue reglas de aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-148">Add applicability rules.</span></span> <span data-ttu-id="2cbb0-149">No deje en blanco los campos **Códigos de impuestos**, **Grupo de impuestos** y **Grupo de impuestos de artículo**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="2cbb0-150">Agregue una nueva regla para el envío de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="2cbb0-151">Seleccione **Agregar** en la tabla **Reglas de aplicabilidad**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="2cbb0-152">En el campo **Procesos de negocio**, seleccione **Inventario** para que la regla sea aplicable a un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="2cbb0-153">En el campo **Enviar desde país o región**, introduzca **NLD**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="2cbb0-154">En el campo **Enviar a país o región**, introduzca **BEL**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="2cbb0-155">En el campo **Dirección fiscal**, seleccione **Salida** para que la regla sea aplicable al envío del pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="2cbb0-156">En el campo **Códigos de impuestos**, seleccione **NL-Exento**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="2cbb0-157">En el campo **Grupo de impuestos** y en **Grupo de impuestos de artículo**, introduzca el grupo de impuestos relacionado y el grupo de impuestos de artículo que están definidos en su sistema de Finance.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="2cbb0-158">Agregue otra regla para la recepción de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="2cbb0-159">Seleccione **Agregar** en la tabla **Reglas de aplicabilidad**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="2cbb0-160">En el campo **Procesos de negocio**, seleccione **Inventario** para que la regla sea aplicable a un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="2cbb0-161">En el campo **Enviar desde país o región**, introduzca **NLD**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="2cbb0-162">En el campo **Enviar a país o región**, introduzca **BEL**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="2cbb0-163">En el campo **Dirección fiscal**, seleccione **Entrada** para que la regla sea aplicable a la recepción de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="2cbb0-164">En el campo **Códigos de impuestos**, seleccione **BE-RC+21** y **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="2cbb0-165">En el campo **Grupo de impuestos** y en **Grupo de impuestos de artículo**, introduzca el grupo de impuestos relacionado y el grupo de impuestos de artículo que están definidos en su sistema de Finance.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Reglas de aplicabilidad](../media/image5.png)

4. <span data-ttu-id="2cbb0-167">Complete y publique la nueva versión de la característica fiscal.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="2cbb0-168">[![Cambio del estado de la nueva versión](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="2cbb0-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="2cbb0-169">Configurar Finance para transacciones de pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="2cbb0-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="2cbb0-170">Siga estos pasos para habilitar y configurar impuestos para pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="2cbb0-171">En Finance, vaya a **Áreas de trabajo** \> **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="2cbb0-172">En la lista, busque y seleccione la característica **Impuesto en pedido de transferencia** y, a continuación, seleccione **Habilitar ahora** para activarla.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2cbb0-173">La característica **Impuesto en pedido de transferencia** depende completamente del servicio de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="2cbb0-174">Por lo tanto, solo se puede activar después de haber instalado el servicio de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Impuesto en la característica de pedido de transferencia](../media/image7.png)

3. <span data-ttu-id="2cbb0-176">Habilite el servicio de impuestos y seleccione el proceso de negocio **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2cbb0-177">Debe completar este paso para cada entidad jurídica de Finance donde desee que el servicio de impuestos y la funcionalidad para impuestos en pedidos de transferencia estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="2cbb0-178">Vaya a **Impuesto** \> **Configuración** \> **Configuración de impuestos** \> **Configuración del servicio de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="2cbb0-179">En el campo **Procesos de negocio**, seleccione **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Configuración del campo Proceso de negocio](../media/image8.png)

4. <span data-ttu-id="2cbb0-181">Verifique que el mecanismo de cargo inverso esté configurado.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="2cbb0-182">Vaya a **Contabilidad general** \> **Configuración** \> **Parámetros** y luego, en la pestaña **Invertir cargo**, verifique que la opción **Habilitar cargo inverso** esté configurada en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Habilitar la opción de cargo inverso](../media/image9.png)

5. <span data-ttu-id="2cbb0-184">Verifique que los códigos de impuestos relacionados, los grupos de impuestos, los grupos de impuestos de artículos y los números de registro de IVA se hayan configurado en Finance de acuerdo con la guía del servicio de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="2cbb0-185">Configure una cuenta de tránsito provisional.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-185">Set up an interim transit account.</span></span> <span data-ttu-id="2cbb0-186">Este paso es necesario solo cuando el impuesto que se aplica a un pedido de transferencia no es aplicable a un mecanismo de exención de impuestos o de cargo invertido.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="2cbb0-187">Vaya a **Impuesto** \> **Configuración** \> **Impuesto** \> **Grupos de contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="2cbb0-188">En el campo **Tránsito provisional**, seleccione una cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Selección de una cuenta de tránsito provisional](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="2cbb0-190">Configurar el inventario básico para transacciones de pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="2cbb0-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="2cbb0-191">Siga estos pasos para configurar el inventario básico para habilitar las transacciones de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="2cbb0-192">Cree sitios de salida de envío y de llegada de envío para sus almacenes en diferentes países o regiones, y agregue la dirección principal para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="2cbb0-193">Vaya a **Gestión de almacenes** \> **Configurar** \> **Almacén** \> **Sitios**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="2cbb0-194">Seleccione **Nuevo** para crear el sitio que luego asignará a un almacén.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="2cbb0-195">Repita el paso 2 para el resto de sitios que deba crear.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2cbb0-196">Uno de los sitios que cree debe tener por nombre **Tránsito**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="2cbb0-197">En los pasos posteriores de este procedimiento, asignará este sitio al almacén de tránsito, de modo que los asiento de inventario relacionados con los impuestos se puedan registrar en las transacciones de "enviar" y "recibir" para los pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="2cbb0-198">La dirección del sitio de tránsito es irrelevante para el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="2cbb0-199">Por tanto, no se puede dejar en blanco.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-199">Therefore, you can leave it blank.</span></span>

    ![Configuración de sitios](../media/image11.png)

2. <span data-ttu-id="2cbb0-201">Cree almacenes de envío, tránsito y destino.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="2cbb0-202">Cualquier información de dirección que se mantenga en un almacén anulará la dirección del sitio durante el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="2cbb0-203">Vaya a **Gestión de almacenes** \> **Configurar** \> **Almacén** \> **Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="2cbb0-204">Seleccione **Nuevo** para crear un almacén y asignarlo al sitio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="2cbb0-205">Repita el paso 2 para crear un almacén para cada sitio, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Configuración de almacenes](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="2cbb0-207">Para un almacén de envío, se debe seleccionar un almacén de tránsito en el campo **Almacén de tránsito** para transacciones de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Selección de un almacén de tránsito](../media/image13.png)

3. <span data-ttu-id="2cbb0-209">Verifique que la configuración de contabilización de inventario esté configurada para transacciones de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="2cbb0-210">Vaya a **Gestión de inventarios** \> **Configurar** \> **Registro** \> **Registro**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="2cbb0-211">En la pestaña **Inventario**, verifique que una cuenta contable esté configurada para la contabilización de **Problema de inventario** y **Recibo de inventario**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Configuración de incidencias de inventario y contabilización de recibos de inventario](../media/image14.png)

    3. <span data-ttu-id="2cbb0-213">Verifique que una cuenta contable esté configurada para la contabilidad **Pagadera entre unidades**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Configuración de contabilización pagadera entre unidades](../media/image15.png)

    4. <span data-ttu-id="2cbb0-215">Verifique que una cuenta contable esté configurada para contabilización **Recibible entre unidades**.</span><span class="sxs-lookup"><span data-stu-id="2cbb0-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Configuración de contabilización recibible entre unidades](../media/image16.png)
