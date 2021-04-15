---
title: Agregar recomendaciones a la pantalla de transacción
description: Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 38099909f169391c17760ac381af07f0848fc384
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797488"
---
# <a name="add-recommendations-to-the-transaction-screen"></a><span data-ttu-id="59b6f-103">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="59b6f-103">Add recommendations to the transaction screen</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="59b6f-104">Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="59b6f-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="59b6f-105">Para obtener más información sobre recomendaciones del producto, lea [recomendaciones del producto en la documentación de PDV](product.md).</span><span class="sxs-lookup"><span data-stu-id="59b6f-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="59b6f-106">Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando utilice Commerce.</span><span class="sxs-lookup"><span data-stu-id="59b6f-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="59b6f-107">Para mostrar recomendaciones del producto, debe agregar un control a la pantalla de transacción mediante el diseñador de pantalla.</span><span class="sxs-lookup"><span data-stu-id="59b6f-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="59b6f-108">Abra el Diseñador</span><span class="sxs-lookup"><span data-stu-id="59b6f-108">Open Layout designer</span></span>

1. <span data-ttu-id="59b6f-109">Vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="59b6f-110">Utilice el filtro rápido para buscar la pantallla a la que desea agregar el control.</span><span class="sxs-lookup"><span data-stu-id="59b6f-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="59b6f-111">Por ejemplo, filtro el campo **Id. de diseño de pantalla** usando un valor de **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="59b6f-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="59b6f-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="59b6f-113">Por ejemplo, seleccione **Nombre: F2CP16:9M Id. de diseño de pantalla: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="59b6f-114">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="59b6f-115">Siga las instrucciones para iniciar al diseñador.</span><span class="sxs-lookup"><span data-stu-id="59b6f-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="59b6f-116">Cuando se le soliciten las credenciales, introduzca las mismas credenciales que utilizó cuando se inició el Diseñador desde la página **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="59b6f-117">Cuando inicie sesión, aparece una página similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="59b6f-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="59b6f-118">El diseño variará en función de las personalizaciones que se crearon para su tienda.</span><span class="sxs-lookup"><span data-stu-id="59b6f-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="59b6f-119">[![Diseñador](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="59b6f-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="59b6f-120">Elija una opción de visualización</span><span class="sxs-lookup"><span data-stu-id="59b6f-120">Choose a display option</span></span>

<span data-ttu-id="59b6f-121">Hay dos opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="59b6f-121">There are two configurations options available.</span></span> <span data-ttu-id="59b6f-122">Elija la opción que mejor se ajuste a su tienda y siga las instrucciones restantes para finalizar la configuración del control.</span><span class="sxs-lookup"><span data-stu-id="59b6f-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="59b6f-123">Las dos opciones son:</span><span class="sxs-lookup"><span data-stu-id="59b6f-123">The two options are:</span></span>

- <span data-ttu-id="59b6f-124">Las recomendaciones siempre están visibles.</span><span class="sxs-lookup"><span data-stu-id="59b6f-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="59b6f-125">Aparece una pestaña de **Recomendaciones** en la cuadrícula del lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="59b6f-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="59b6f-126">Hacer que las recomendaciones estén siempre visibles</span><span class="sxs-lookup"><span data-stu-id="59b6f-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="59b6f-127">Reduzca la altura del área de detalles de las líneas de transacción de manera que tenga la misma altura que el panel de cliente a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="59b6f-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="59b6f-128">[![La altura del espacio de los detalles de las líneas de transacción se ha reducido](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="59b6f-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="59b6f-129">En el menú de la izquierda, arrastre y suelte el control de recomendaciones entre el área de detalles de la línea de transacción y la cuadrícula de botones en la parte inferior central de la pantalla de transición.</span><span class="sxs-lookup"><span data-stu-id="59b6f-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="59b6f-130">Cambie el control de modo que se ajuste a ese espacio.</span><span class="sxs-lookup"><span data-stu-id="59b6f-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="59b6f-131">[![Se han agreado al diseño las recomendaciones de control](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="59b6f-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="59b6f-132">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="59b6f-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="59b6f-133">En Commerce, vaya a **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programaciones de distribución**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="59b6f-134">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="59b6f-135">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="59b6f-136">Agregue una pestaña de Recomendaciones a la cuadrícula de botones en el lado derecho de la pantalla</span><span class="sxs-lookup"><span data-stu-id="59b6f-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="59b6f-137">Haga clic con el botón secundario en el espacio vacío por debajo de la última pestaña en la cuadrícula de botones que se encuentra en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="59b6f-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="59b6f-138">Haga clic en **personalizar**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-138">Click **Customize**.</span></span>

    <span data-ttu-id="59b6f-139">[![Personalización - Pestaña de control del cuadro de diálogo](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="59b6f-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="59b6f-140">Haga clic en **Nueva pestaña**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-140">Click **New tab**.</span></span>
4. <span data-ttu-id="59b6f-141">Encuentre la nueva pestaña que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="59b6f-141">Find the new tab that you just added.</span></span> <span data-ttu-id="59b6f-142">Es posible que tenga que desplazarse hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="59b6f-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="59b6f-143">En la lista desplegable **Contenido**, seleccione **Productos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="59b6f-144">[![Seleccionando productos recomendados en el campo contenidos](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="59b6f-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="59b6f-145">En el campo **Etiqueta** , escriba un nombre para la pestaña de recomendaciones. Por ejemplo, escriba "Productos recomendados".</span><span class="sxs-lookup"><span data-stu-id="59b6f-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="59b6f-146">En el campo **Imagen**, seleccione la imagen que desea que aparezca en la pestaña.</span><span class="sxs-lookup"><span data-stu-id="59b6f-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="59b6f-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-147">Click **OK**.</span></span> <span data-ttu-id="59b6f-148">La nueva pestaña aparece en la cuadrícula de botones.</span><span class="sxs-lookup"><span data-stu-id="59b6f-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="59b6f-149">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="59b6f-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="59b6f-150">En Commerce, vaya a **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programaciones de distribución**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="59b6f-151">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="59b6f-152">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="59b6f-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59b6f-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="59b6f-153">Additional resources</span></span>

[<span data-ttu-id="59b6f-154">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="59b6f-154">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="59b6f-155">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="59b6f-155">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="59b6f-156">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="59b6f-156">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="59b6f-157">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="59b6f-157">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="59b6f-158">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="59b6f-158">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="59b6f-159">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="59b6f-159">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="59b6f-160">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="59b6f-160">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="59b6f-161">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="59b6f-161">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="59b6f-162">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="59b6f-162">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="59b6f-163">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="59b6f-163">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="59b6f-164">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="59b6f-164">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]