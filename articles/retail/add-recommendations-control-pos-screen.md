---
title: Agregue un control de recomendaciones a la pantalla de transacción en dispositivos de PDV
description: Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d646c8ba559ba3e8d2175911e76c57d25eff02ca
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278138"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="0d2b0-103">Agregue un control de recomendaciones a la pantalla de transacción en dispositivos de PDV</span><span class="sxs-lookup"><span data-stu-id="0d2b0-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="0d2b0-104">Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="0d2b0-105">Para obtener más información sobre recomendaciones del producto, lea [recomendaciones del producto en la documentación de PDV.](product.md)</span><span class="sxs-lookup"><span data-stu-id="0d2b0-105">For more information about product recommendations, read the  [product recommendations on POS documentation.](product.md)</span></span>


<span data-ttu-id="0d2b0-106">Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando utilice Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-106">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="0d2b0-107">Para mostrar recomendaciones del producto, debe agregar un control a la pantalla de transacción mediante el diseñador de pantalla.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="0d2b0-108">Abra el Diseñador</span><span class="sxs-lookup"><span data-stu-id="0d2b0-108">Open Layout designer</span></span>

1. <span data-ttu-id="0d2b0-109">Vaya a **Venta minorista** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="0d2b0-110">Utilice el filtro rápido para buscar la pantallla a la que desea agregar el control.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="0d2b0-111">Por ejemplo, filtro el campo **Id. de diseño de pantalla** usando un valor de **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="0d2b0-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="0d2b0-113">Por ejemplo, seleccione **Nombre: F2CP16:9M Id. de diseño de pantalla: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="0d2b0-114">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="0d2b0-115">Siga las instrucciones para iniciar al diseñador.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="0d2b0-116">Cuando se le soliciten las credenciales, introduzca las mismas credenciales que utilizó cuando se inició el Diseñador desde la página **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="0d2b0-117">Cuando inicie sesión, aparece una página similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="0d2b0-118">El diseño variará en función de las personalizaciones que se crearon para su tienda.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="0d2b0-119">[![Diseñador](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="0d2b0-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="0d2b0-120">Elija una opción de visualización</span><span class="sxs-lookup"><span data-stu-id="0d2b0-120">Choose a display option</span></span>

<span data-ttu-id="0d2b0-121">Hay dos opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="0d2b0-121">There are two configurations options available.</span></span> <span data-ttu-id="0d2b0-122">Elija la opción que mejor se ajuste a su tienda y siga las instrucciones restantes para finalizar la configuración del control.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="0d2b0-123">Las dos opciones son:</span><span class="sxs-lookup"><span data-stu-id="0d2b0-123">The two options are:</span></span>

- <span data-ttu-id="0d2b0-124">Las recomendaciones siempre están visibles.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="0d2b0-125">Aparece una pestaña de **Recomendaciones** en la cuadrícula del lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="0d2b0-126">Hacer que las recomendaciones estén siempre visibles</span><span class="sxs-lookup"><span data-stu-id="0d2b0-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="0d2b0-127">Reduzca la altura del área de detalles de las líneas de transacción de manera que tenga la misma altura que el panel de cliente a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="0d2b0-128">[![La altura del espacio de los detalles de las líneas de transacción se ha reducido](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="0d2b0-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="0d2b0-129">En el menú de la izquierda, arrastre y suelte el control de recomendaciones entre el área de detalles de la línea de transacción y la cuadrícula de botones en la parte inferior central de la pantalla de transición.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="0d2b0-130">Cambie el control de modo que se ajuste a ese espacio.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="0d2b0-131">[![Se han agreado al diseño las recomendaciones de control](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="0d2b0-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="0d2b0-132">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="0d2b0-133">En Dynamics 365 for Retail Vaya a **Retail** &gt; **Retail TI** &gt; **Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-133">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="0d2b0-134">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="0d2b0-135">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="0d2b0-136">Agregue una pestaña de Recomendaciones a la cuadrícula de botones en el lado derecho de la pantalla</span><span class="sxs-lookup"><span data-stu-id="0d2b0-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="0d2b0-137">Haga clic con el botón secundario en el espacio vacío por debajo de la última pestaña en la cuadrícula de botones que se encuentra en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="0d2b0-138">Haga clic en **personalizar**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-138">Click **Customize**.</span></span>

    <span data-ttu-id="0d2b0-139">[![Personalización - Pestaña de control del cuadro de diálogo](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="0d2b0-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="0d2b0-140">Haga clic en **Nueva pestaña**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-140">Click **New tab**.</span></span>
4. <span data-ttu-id="0d2b0-141">Encuentre la nueva pestaña que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-141">Find the new tab that you just added.</span></span> <span data-ttu-id="0d2b0-142">Es posible que tenga que desplazarse hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="0d2b0-143">En la lista desplegable **Contenido**, seleccione **Productos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="0d2b0-144">[![Seleccionando productos recomendados en el campo contenidos](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="0d2b0-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="0d2b0-145">En el campo **Etiqueta** , escriba un nombre para la pestaña de recomendaciones. Por ejemplo, escriba "Productos recomendados".</span><span class="sxs-lookup"><span data-stu-id="0d2b0-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="0d2b0-146">En el campo **Imagen**, seleccione la imagen que desea que aparezca en la pestaña.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="0d2b0-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-147">Click **OK**.</span></span> <span data-ttu-id="0d2b0-148">La nueva pestaña aparece en la cuadrícula de botones.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="0d2b0-149">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="0d2b0-150">En Dynamics 365 for Retail Vaya a **Retail** &gt; **Retail TI** &gt; **Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-150">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="0d2b0-151">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="0d2b0-152">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="0d2b0-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d2b0-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0d2b0-153">Additional resources</span></span>

[<span data-ttu-id="0d2b0-154">Recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="0d2b0-154">product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="0d2b0-155">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="0d2b0-155">product recommendations overview</span></span>](../commerce/product-recommendations.md)
