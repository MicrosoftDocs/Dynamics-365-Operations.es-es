---
title: "Agregue un control de recomendaciones a la página de transacción en un dispositivo de PDV"
description: "Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 0d366997fbb6f23474047fa8c465a594491c46ad
ms.contentlocale: es-es
ms.lasthandoff: 01/19/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="83395-103">Agregue un control de recomendaciones a la página de transacción en un dispositivo de PDV</span><span class="sxs-lookup"><span data-stu-id="83395-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="83395-104">Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="83395-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="83395-105">Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando utilice Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="83395-105">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="83395-106">Las *Recomendaciones* son artículos que pueden interesar a su cliente en función de su historial de compra, los artículos de su lista de deseos y los artículos que compraron otros clientes en línea y en tiendas de físicas.</span><span class="sxs-lookup"><span data-stu-id="83395-106">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="83395-107">Para mostrar recomendaciones del producto, debe agregar un control a la pantalla de transacción mediante el diseñador de pantalla.</span><span class="sxs-lookup"><span data-stu-id="83395-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="83395-108">Abra el Diseñador</span><span class="sxs-lookup"><span data-stu-id="83395-108">Open Layout designer</span></span>
1.  <span data-ttu-id="83395-109">Vaya a **Venta minorista** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="83395-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="83395-110">Utilice el filtro rápido para buscar la pantallla a la que desea agregar el control.</span><span class="sxs-lookup"><span data-stu-id="83395-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="83395-111">Por ejemplo, filtro el campo **Id. de diseño de pantalla** usando un valor de ‘F2CP16:9M’.</span><span class="sxs-lookup"><span data-stu-id="83395-111">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="83395-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="83395-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="83395-113">Por ejemplo, seleccione ‘Nombre: F2CP16:9M Id. de diseño de pantalla: F2CP16:9M’.</span><span class="sxs-lookup"><span data-stu-id="83395-113">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="83395-114">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="83395-114">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="83395-115">Siga las instrucciones para iniciar al diseñador.</span><span class="sxs-lookup"><span data-stu-id="83395-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="83395-116">Cuando se le soliciten las credenciales, introduzca las mismas credenciales que utilizó cuando se inició el Diseñador desde la página **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="83395-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="83395-117">Cuando inicie sesión, aparece una página similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="83395-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="83395-118">El diseño variará en función de las personalizaciones que se crearon para su tienda.</span><span class="sxs-lookup"><span data-stu-id="83395-118">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="83395-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Elija una opción de visualización</span><span class="sxs-lookup"><span data-stu-id="83395-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="83395-120">Hay dos opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="83395-120">There are two configurations options available.</span></span> <span data-ttu-id="83395-121">Elija la opción que mejor se ajuste a su tienda y siga las instrucciones restantes para finalizar la configuración del control.</span><span class="sxs-lookup"><span data-stu-id="83395-121">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="83395-122">Las dos opciones son:</span><span class="sxs-lookup"><span data-stu-id="83395-122">The two options are:</span></span>
-   <span data-ttu-id="83395-123">Las recomendaciones siempre están visibles.</span><span class="sxs-lookup"><span data-stu-id="83395-123">Recommendations are always visible.</span></span>
-   <span data-ttu-id="83395-124">Aparece una pestaña de **Recomendaciones** en la cuadrícula del lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="83395-124">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="83395-125">Para hacer que las recomendaciones siempre estén visibles</span><span class="sxs-lookup"><span data-stu-id="83395-125">To make recommendations always visible</span></span>

1.  <span data-ttu-id="83395-126">Reduzca la altura del área de detalles de las líneas de transacción de manera que tenga la misma altura que el panel de cliente a la izquierda.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="83395-126">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="83395-127">En el menú de la izquierda, arrastre y suelte el control de recomendaciones entre el área de detalles de la línea de transacción y la cuadrícula de botones en la parte inferior central de la pantalla de transición.</span><span class="sxs-lookup"><span data-stu-id="83395-127">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="83395-128">Cambie el tamaño del control de modo que se ajuste a ese espacio.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="83395-128">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="83395-129">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="83395-129">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="83395-130">En Dynamics 365 for Retail, vaya a **Venta minorista** &gt; **TI de venta minorista** &gt; **Programaciones de distribución**.</span><span class="sxs-lookup"><span data-stu-id="83395-130">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="83395-131">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="83395-131">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="83395-132">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="83395-132">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="83395-133">Para agregar una pestaña de Recomendaciones a la cuadrícula de botones en el lado derecho de la pantalla</span><span class="sxs-lookup"><span data-stu-id="83395-133">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="83395-134">Haga clic con el botón secundario en el espacio vacío por debajo de la última pestaña en la cuadrícula de botones que se encuentra en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="83395-134">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="83395-135">Haga clic en **Personalizar**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="83395-135">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="83395-136">Haga clic en **Nueva pestaña**.</span><span class="sxs-lookup"><span data-stu-id="83395-136">Click **New tab**.</span></span>
4.  <span data-ttu-id="83395-137">Encuentre la nueva pestaña que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="83395-137">Find the new tab that you just added.</span></span> <span data-ttu-id="83395-138">Es posible que tenga que desplazarse hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="83395-138">You may need to scroll down.</span></span>
5.  <span data-ttu-id="83395-139">En la lista desplegable **Contenido**, seleccione **Productos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="83395-139">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="83395-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="83395-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="83395-141">En el campo **Etiqueta** , escriba un nombre para la pestaña de recomendaciones. Por ejemplo, escriba "Productos recomendados".</span><span class="sxs-lookup"><span data-stu-id="83395-141">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="83395-142">En el campo **Imagen**, seleccione la imagen que desea que aparezca en la pestaña.</span><span class="sxs-lookup"><span data-stu-id="83395-142">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="83395-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="83395-143">Click **OK**.</span></span> <span data-ttu-id="83395-144">La nueva pestaña aparece en la cuadrícula de botones.</span><span class="sxs-lookup"><span data-stu-id="83395-144">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="83395-145">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="83395-145">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="83395-146">En Dynamics 365 for Retail, vaya a **Venta minorista** &gt; **TI de venta minorista** &gt; **Programaciones de distribución**.</span><span class="sxs-lookup"><span data-stu-id="83395-146">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="83395-147">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="83395-147">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="83395-148">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="83395-148">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="83395-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83395-149">See also</span></span>
--------

[<span data-ttu-id="83395-150">Visión general de recomendaciones de productos personalizados</span><span class="sxs-lookup"><span data-stu-id="83395-150">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




