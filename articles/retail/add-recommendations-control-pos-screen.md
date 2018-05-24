---
title: "Agregue un control de recomendaciones a la página de transacción en un dispositivo de PDV"
description: "Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: eac70614770189d1e45f347b282c94e645e95b00
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="f8577-103">Agregue un control de recomendaciones a la página de transacción en un dispositivo de PDV</span><span class="sxs-lookup"><span data-stu-id="f8577-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="f8577-104">Estamos retirando la versión actual del servicio de recomendación de productos ya que rediseñamos esta función con un algoritmo mejor y capacidades más nuevas orientadas a la venta minorista.</span><span class="sxs-lookup"><span data-stu-id="f8577-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="f8577-105">Para obtener más información, consulte [Funciones retiradas u obsoletas](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="f8577-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span> 

<span data-ttu-id="f8577-106">Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f8577-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="f8577-107">Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando utilice Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="f8577-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="f8577-108">Las *Recomendaciones* son artículos que pueden interesar a su cliente en función de su historial de compra, los artículos de su lista de deseos y los artículos que compraron otros clientes en línea y en tiendas de físicas.</span><span class="sxs-lookup"><span data-stu-id="f8577-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="f8577-109">Para mostrar recomendaciones del producto, debe agregar un control a la pantalla de transacción mediante el diseñador de pantalla.</span><span class="sxs-lookup"><span data-stu-id="f8577-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="f8577-110">Abra el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f8577-110">Open Layout designer</span></span>
1.  <span data-ttu-id="f8577-111">Vaya a **Venta minorista** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="f8577-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="f8577-112">Utilice el filtro rápido para buscar la pantallla a la que desea agregar el control.</span><span class="sxs-lookup"><span data-stu-id="f8577-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="f8577-113">Por ejemplo, filtro el campo **Id. de diseño de pantalla** usando un valor de ‘F2CP16:9M’.</span><span class="sxs-lookup"><span data-stu-id="f8577-113">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="f8577-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f8577-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="f8577-115">Por ejemplo, seleccione ‘Nombre: F2CP16:9M Id. de diseño de pantalla: F2CP16:9M’.</span><span class="sxs-lookup"><span data-stu-id="f8577-115">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="f8577-116">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="f8577-116">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="f8577-117">Siga las instrucciones para iniciar al diseñador.</span><span class="sxs-lookup"><span data-stu-id="f8577-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="f8577-118">Cuando se le soliciten las credenciales, introduzca las mismas credenciales que utilizó cuando se inició el Diseñador desde la página **Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="f8577-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="f8577-119">Cuando inicie sesión, aparece una página similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8577-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="f8577-120">El diseño variará en función de las personalizaciones que se crearon para su tienda.</span><span class="sxs-lookup"><span data-stu-id="f8577-120">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="f8577-121">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Elija una opción de visualización</span><span class="sxs-lookup"><span data-stu-id="f8577-121">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="f8577-122">Hay dos opciones de configuración disponibles:</span><span class="sxs-lookup"><span data-stu-id="f8577-122">There are two configurations options available.</span></span> <span data-ttu-id="f8577-123">Elija la opción que mejor se ajuste a su tienda y siga las instrucciones restantes para finalizar la configuración del control.</span><span class="sxs-lookup"><span data-stu-id="f8577-123">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="f8577-124">Las dos opciones son:</span><span class="sxs-lookup"><span data-stu-id="f8577-124">The two options are:</span></span>
-   <span data-ttu-id="f8577-125">Las recomendaciones siempre están visibles.</span><span class="sxs-lookup"><span data-stu-id="f8577-125">Recommendations are always visible.</span></span>
-   <span data-ttu-id="f8577-126">Aparece una pestaña de **Recomendaciones** en la cuadrícula del lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f8577-126">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="f8577-127">Para hacer que las recomendaciones siempre estén visibles</span><span class="sxs-lookup"><span data-stu-id="f8577-127">To make recommendations always visible</span></span>

1.  <span data-ttu-id="f8577-128">Reduzca la altura del área de detalles de las líneas de transacción de manera que tenga la misma altura que el panel de cliente a la izquierda.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="f8577-128">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="f8577-129">En el menú de la izquierda, arrastre y suelte el control de recomendaciones entre el área de detalles de la línea de transacción y la cuadrícula de botones en la parte inferior central de la pantalla de transición.</span><span class="sxs-lookup"><span data-stu-id="f8577-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="f8577-130">Cambie el tamaño del control de modo que se ajuste a ese espacio.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="f8577-130">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="f8577-131">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="f8577-131">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="f8577-132">En Dynamics 365 for Retail, vaya a **Venta minorista** &gt; **TI de venta minorista** &gt; **Programaciones de distribución**.</span><span class="sxs-lookup"><span data-stu-id="f8577-132">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="f8577-133">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="f8577-133">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="f8577-134">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f8577-134">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="f8577-135">Para agregar una pestaña de Recomendaciones a la cuadrícula de botones en el lado derecho de la pantalla</span><span class="sxs-lookup"><span data-stu-id="f8577-135">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="f8577-136">Haga clic con el botón secundario en el espacio vacío por debajo de la última pestaña en la cuadrícula de botones que se encuentra en el lado derecho de la página.</span><span class="sxs-lookup"><span data-stu-id="f8577-136">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="f8577-137">Haga clic en **Personalizar**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="f8577-137">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="f8577-138">Haga clic en **Nueva pestaña**.</span><span class="sxs-lookup"><span data-stu-id="f8577-138">Click **New tab**.</span></span>
4.  <span data-ttu-id="f8577-139">Encuentre la nueva pestaña que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="f8577-139">Find the new tab that you just added.</span></span> <span data-ttu-id="f8577-140">Es posible que tenga que desplazarse hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="f8577-140">You may need to scroll down.</span></span>
5.  <span data-ttu-id="f8577-141">En la lista desplegable **Contenido**, seleccione **Productos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="f8577-141">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="f8577-142">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="f8577-142">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="f8577-143">En el campo **Etiqueta** , escriba un nombre para la pestaña de recomendaciones. Por ejemplo, escriba "Productos recomendados".</span><span class="sxs-lookup"><span data-stu-id="f8577-143">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="f8577-144">En el campo **Imagen**, seleccione la imagen que desea que aparezca en la pestaña.</span><span class="sxs-lookup"><span data-stu-id="f8577-144">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="f8577-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8577-145">Click **OK**.</span></span> <span data-ttu-id="f8577-146">La nueva pestaña aparece en la cuadrícula de botones.</span><span class="sxs-lookup"><span data-stu-id="f8577-146">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="f8577-147">Haga clic en la **X** para guardar y salir del Diseñador.</span><span class="sxs-lookup"><span data-stu-id="f8577-147">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="f8577-148">En Dynamics 365 for Retail, vaya a **Venta minorista** &gt; **TI de venta minorista** &gt; **Programaciones de distribución**.</span><span class="sxs-lookup"><span data-stu-id="f8577-148">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="f8577-149">En la lista, seleccione **1090, Cajas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="f8577-149">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="f8577-150">Haga clic en **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f8577-150">Click **Run now**.</span></span>


<a name="additional-resources"></a><span data-ttu-id="f8577-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f8577-151">Additional resources</span></span>
--------

[<span data-ttu-id="f8577-152">Visión general de recomendaciones de productos personalizados</span><span class="sxs-lookup"><span data-stu-id="f8577-152">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




