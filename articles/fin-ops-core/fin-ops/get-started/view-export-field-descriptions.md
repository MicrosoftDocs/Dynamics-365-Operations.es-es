---
title: Ver y exportar descripciones de campos
description: En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 147dc55160de7d3cc01cc077095d2eb71f4d7861
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978187"
---
# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="5158b-103">Ver y exportar descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="5158b-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5158b-104">En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.</span><span class="sxs-lookup"><span data-stu-id="5158b-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="5158b-105">Algunos de los campos más complejos tienen descripciones de campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-105">Some of the more complex fields have field descriptions.</span></span> <span data-ttu-id="5158b-106">Estas descripciones aparecen al colocar el puntero sobre un campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="5158b-107">También puede ver y exportar descripciones en la página **Descripciones de campos**.</span><span class="sxs-lookup"><span data-stu-id="5158b-107">You can also view and export descriptions on the **Field descriptions** page.</span></span>

<span data-ttu-id="5158b-108">No todas las páginas tienen descripciones de campos.</span><span class="sxs-lookup"><span data-stu-id="5158b-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="5158b-109">Queremos proporcionar descripciones solo para los campos más complejos y no donde el uso del campo es evidente.</span><span class="sxs-lookup"><span data-stu-id="5158b-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="5158b-110">Por tanto, algunas páginas no tienen descripciones de campos, otras tienen algunas descripciones y algunas de las páginas más complejas, como muchas de las páginas de parámetros, tienen muchas descripciones.</span><span class="sxs-lookup"><span data-stu-id="5158b-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span>

<span data-ttu-id="5158b-111">Si tiene acceso al entorno de desarrollo, puede agregar nuevas descripciones de campo y personalizar las existentes.</span><span class="sxs-lookup"><span data-stu-id="5158b-111">If you have access to the development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="5158b-112">Por ejemplo, puede agregar información específica de la empresa a una descripción de campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="5158b-113">Para obtener más información, consulte [Personalizar descripciones de campo](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="5158b-113">For more information, see [Customize field descriptions](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="5158b-114">Consulte las descripciones del campo en la interfaz del usuario.</span><span class="sxs-lookup"><span data-stu-id="5158b-114">See field descriptions in the user interface</span></span>

<span data-ttu-id="5158b-115">Puede ver descripciones de los campos manteniendo el ratón sobre un campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="5158b-116">Si no hay ninguna descripción disponible, verá el nombre del campo al mantener el puntero sobre el campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-116">If no description is available, you see the field name when you hover over the field.</span></span>

> [!NOTE]
> <span data-ttu-id="5158b-117">En Dynamics AX 7.0 (febrero de 2016), las descripciones de campos solo se pueden ver en la página **Descripciones de campos**.</span><span class="sxs-lookup"><span data-stu-id="5158b-117">In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.</span></span>

<span data-ttu-id="5158b-118">En la ilustración siguiente se muestra la descripción del campo que aparece al mantener el puntero sobre el campo **Bloquear artículos durante el recuento**.</span><span class="sxs-lookup"><span data-stu-id="5158b-118">The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span>

<span data-ttu-id="5158b-119">[![Ejemplo de una descripción de campo](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="5158b-119">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="5158b-120">Utilice la página Descripciones de campos para ver y exportar la ayuda de campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-120">Use the Field descriptions page to view and export field help</span></span>

<span data-ttu-id="5158b-121">La página **Descripciones de campos** permite ver y exportar descripciones de campos.</span><span class="sxs-lookup"><span data-stu-id="5158b-121">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="5158b-122">Puede ver las descripciones que están disponibles para una página a la vez.</span><span class="sxs-lookup"><span data-stu-id="5158b-122">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="5158b-123">Vea las descripciones de una página</span><span class="sxs-lookup"><span data-stu-id="5158b-123">View the descriptions for a page</span></span>

<span data-ttu-id="5158b-124">Para ver las descripciones de una página, siga este paso.</span><span class="sxs-lookup"><span data-stu-id="5158b-124">To view the descriptions for a page, follow this step.</span></span>

- <span data-ttu-id="5158b-125">En el campo **Seleccionar una página**, escriba el nombre de la página.</span><span class="sxs-lookup"><span data-stu-id="5158b-125">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="5158b-126">De forma alternativa, haga clic en la flecha para abrir una lista de todas las páginas y, a continuación, examine o filtre la lista.</span><span class="sxs-lookup"><span data-stu-id="5158b-126">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="5158b-127">Puede usar el nombre de la página que se muestra en la interfaz de usuario (IU) (por ejemplo, **Clientes**) o el nombre de código (nombre AOT) que está disponible al hacer clic con el botón secundario en una página (por ejemplo, **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="5158b-127">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span>

<span data-ttu-id="5158b-128">Para obtener información sobre las diversas maneras de filtrar la lista de páginas, vea la sección "Buscar una página" más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5158b-128">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span>

<span data-ttu-id="5158b-129">Si establece la opción **Incluir campos sin descripción** en **Sí**, se muestran todos los campos de la página, incluso si no tienen una descripción de campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-129">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="5158b-130">Exportar las descripciones de una página</span><span class="sxs-lookup"><span data-stu-id="5158b-130">Export the descriptions for a page</span></span>

<span data-ttu-id="5158b-131">Para exportar las descripciones de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5158b-131">To export the descriptions for a page, follow these steps.</span></span>

1. <span data-ttu-id="5158b-132">En el campo **Seleccionar una página**, seleccione una página.</span><span class="sxs-lookup"><span data-stu-id="5158b-132">In the **Select a page** field, select a page.</span></span>
2. <span data-ttu-id="5158b-133">Haga clic en el botón **Abrir de Microsoft Office** que se encuentra en la esquina superior derecha y, a continuación, haga clic en **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="5158b-133">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="5158b-134">Buscar una página</span><span class="sxs-lookup"><span data-stu-id="5158b-134">Searching for a page</span></span>

<span data-ttu-id="5158b-135">Hay varias formas de buscar una página en el campo **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="5158b-135">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="5158b-136">En muchos casos deberá hacer clic en la flecha del campo **Seleccionar una página** para abrir la lista desplegable y, a continuación, seleccione entre una lista de páginas.</span><span class="sxs-lookup"><span data-stu-id="5158b-136">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

- <span data-ttu-id="5158b-137">Escriba una parte del nombre y, a continuación, abra la lista desplegable para seleccionar entre una lista de páginas filtrada.</span><span class="sxs-lookup"><span data-stu-id="5158b-137">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
- <span data-ttu-id="5158b-138">Abra la lista desplegable y, a continuación, haga clic en el encabezado **Nombre de página** en la parte superior de la liste o en el encabezado **Nombre AOT de página**.</span><span class="sxs-lookup"><span data-stu-id="5158b-138">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="5158b-139">Aparece un cuadro de diálogo, donde puede utilizar las opciones de filtrado avanzadas, como **El nombre de la página empieza por**.</span><span class="sxs-lookup"><span data-stu-id="5158b-139">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
- <span data-ttu-id="5158b-140">Escriba el nombre completo de la página.</span><span class="sxs-lookup"><span data-stu-id="5158b-140">Type the full name of the page.</span></span> <span data-ttu-id="5158b-141">Al usar esta opción, es mejor abrir la lista desplegable y ver qué más se encuentra en la lista, aunque se muestren las descripciones de campo.</span><span class="sxs-lookup"><span data-stu-id="5158b-141">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>

    - <span data-ttu-id="5158b-142">Si hay una única coincidencia exacta del nombre, se muestran las descripciones de campo de esa página.</span><span class="sxs-lookup"><span data-stu-id="5158b-142">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    - <span data-ttu-id="5158b-143">Si hay más de una coincidencia exacta, no se muestran descripciones.</span><span class="sxs-lookup"><span data-stu-id="5158b-143">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="5158b-144">Debe abrir la lista desplegable y seleccionar la página que desea.</span><span class="sxs-lookup"><span data-stu-id="5158b-144">You must open the drop-down list and select the page that you want.</span></span>
    - <span data-ttu-id="5158b-145">Si el nombre que ha escrito forma parte del nombre de otra página, vea las descripciones de la página.</span><span class="sxs-lookup"><span data-stu-id="5158b-145">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="5158b-146">Sin embargo, si abre la lista desplegable, consulte las páginas adicionales que contienen ese nombre.</span><span class="sxs-lookup"><span data-stu-id="5158b-146">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="5158b-147">Por ejemplo, no se muestran descripciones al escribir **Recuento** en el campo **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="5158b-147">For example, no descriptions are shown when you type **Counting** in the **Select a page** field.</span></span> <span data-ttu-id="5158b-148">Abre la lista desplegable y ve que hay dos páginas con el nombre **Recuento**, así como varias páginas que contienen la palabra "Recuento" en el nombre.</span><span class="sxs-lookup"><span data-stu-id="5158b-148">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="5158b-149">Si selecciona la página que tiene el nombre AOT **InventJournalCount**, se muestran las descripciones de campo de esa página.</span><span class="sxs-lookup"><span data-stu-id="5158b-149">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="5158b-150">Sin embargo, si vuelve a abrir la lista desplegable, verá que, ahora, la lista contiene todas las páginas que tienen "InventJournalCount" como parte de su nombre de AOT.</span><span class="sxs-lookup"><span data-stu-id="5158b-150">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5158b-151">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="5158b-151">Troubleshooting</span></span>

<span data-ttu-id="5158b-152">En esta sección se proporciona información que le ayudará a solucionar los problemas que puedan surgir al utilizar las descripciones de campos.</span><span class="sxs-lookup"><span data-stu-id="5158b-152">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="5158b-153">No puedo encontrar una descripción de campo</span><span class="sxs-lookup"><span data-stu-id="5158b-153">I can't find a field description</span></span>

<span data-ttu-id="5158b-154">Estamos en proceso de agregar descripciones de campos más complejos.</span><span class="sxs-lookup"><span data-stu-id="5158b-154">We're in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="5158b-155">Si necesita ayuda para un campo determinado, háganoslo saber agregando un comentario en este tema.</span><span class="sxs-lookup"><span data-stu-id="5158b-155">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="5158b-156">La descripción de campo no es útil</span><span class="sxs-lookup"><span data-stu-id="5158b-156">The field description isn't helpful</span></span>

<span data-ttu-id="5158b-157">Háganoslo saber agregando un comentario en este tema.</span><span class="sxs-lookup"><span data-stu-id="5158b-157">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="5158b-158">Si es posible, describa la información adicional que requiera.</span><span class="sxs-lookup"><span data-stu-id="5158b-158">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="5158b-159">No encuentro un campo en la página de Descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="5158b-159">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="5158b-160">Para mostrar todos los campos de una página, establezca la opción **Incluir campos sin descripción** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5158b-160">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="5158b-161">Haga clic en el campo **Seleccionar una página** para comprobar que ha seleccionado la página correcta.</span><span class="sxs-lookup"><span data-stu-id="5158b-161">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="5158b-162">Si el nombre que ha escrito forma parte de otro nombre de campo, probablemente haya seleccionado la página con el nombre más largo.</span><span class="sxs-lookup"><span data-stu-id="5158b-162">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="5158b-163">No encuentro una página en la página de Descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="5158b-163">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="5158b-164">Para obtener información sobre las diversas maneras de encontrar páginas, vea la sección "Buscar páginas" anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5158b-164">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="5158b-165">Si ha escrito el nombre exacto de la página, es posible que las descripciones de campo no se muestren si más de una página tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="5158b-165">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="5158b-166">Haga clic en la flecha del campo **Seleccionar una página** para abrir una lista filtrada de las páginas que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="5158b-166">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5158b-167">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5158b-167">Additional resources</span></span>

[<span data-ttu-id="5158b-168">Personalizar descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="5158b-168">Customize field descriptions</span></span>](../../dev-itpro/user-interface/customize-field-help.md)
