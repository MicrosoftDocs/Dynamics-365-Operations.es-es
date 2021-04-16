---
title: Ver y exportar descripciones de campos
description: En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.
author: rschloma
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0e4bba6524f225d614ffdab370f2a1993cb3a29
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754689"
---
# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="f3a17-103">Ver y exportar descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="f3a17-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3a17-104">En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.</span><span class="sxs-lookup"><span data-stu-id="f3a17-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="f3a17-105">Algunos de los campos más complejos tienen descripciones de campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-105">Some of the more complex fields have field descriptions.</span></span> <span data-ttu-id="f3a17-106">Estas descripciones aparecen al colocar el puntero sobre un campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="f3a17-107">También puede ver y exportar descripciones en la página **Descripciones de campos**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-107">You can also view and export descriptions on the **Field descriptions** page.</span></span>

<span data-ttu-id="f3a17-108">No todas las páginas tienen descripciones de campos.</span><span class="sxs-lookup"><span data-stu-id="f3a17-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="f3a17-109">Queremos proporcionar descripciones solo para los campos más complejos y no donde el uso del campo es evidente.</span><span class="sxs-lookup"><span data-stu-id="f3a17-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="f3a17-110">Por tanto, algunas páginas no tienen descripciones de campos, otras tienen algunas descripciones y algunas de las páginas más complejas, como muchas de las páginas de parámetros, tienen muchas descripciones.</span><span class="sxs-lookup"><span data-stu-id="f3a17-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span>

<span data-ttu-id="f3a17-111">Si tiene acceso al entorno de desarrollo, puede agregar nuevas descripciones de campo y personalizar las existentes.</span><span class="sxs-lookup"><span data-stu-id="f3a17-111">If you have access to the development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="f3a17-112">Por ejemplo, puede agregar información específica de la empresa a una descripción de campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="f3a17-113">Para obtener más información, consulte [Personalizar descripciones de campo](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="f3a17-113">For more information, see [Customize field descriptions](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="f3a17-114">Consulte las descripciones del campo en la interfaz del usuario.</span><span class="sxs-lookup"><span data-stu-id="f3a17-114">See field descriptions in the user interface</span></span>

<span data-ttu-id="f3a17-115">Puede ver descripciones de los campos manteniendo el ratón sobre un campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="f3a17-116">Si no hay ninguna descripción disponible, verá el nombre del campo al mantener el puntero sobre el campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-116">If no description is available, you see the field name when you hover over the field.</span></span>

> [!NOTE]
> <span data-ttu-id="f3a17-117">En Dynamics AX 7.0 (febrero de 2016), las descripciones de campos solo se pueden ver en la página **Descripciones de campos**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-117">In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.</span></span>

<span data-ttu-id="f3a17-118">En la ilustración siguiente se muestra la descripción del campo que aparece al mantener el puntero sobre el campo **Bloquear artículos durante el recuento**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-118">The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span>

<span data-ttu-id="f3a17-119">[![Ejemplo de una descripción de campo](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="f3a17-119">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="f3a17-120">Utilice la página Descripciones de campos para ver y exportar la ayuda de campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-120">Use the Field descriptions page to view and export field help</span></span>

<span data-ttu-id="f3a17-121">La página **Descripciones de campos** permite ver y exportar descripciones de campos.</span><span class="sxs-lookup"><span data-stu-id="f3a17-121">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="f3a17-122">Puede ver las descripciones que están disponibles para una página a la vez.</span><span class="sxs-lookup"><span data-stu-id="f3a17-122">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="f3a17-123">Vea las descripciones de una página</span><span class="sxs-lookup"><span data-stu-id="f3a17-123">View the descriptions for a page</span></span>

<span data-ttu-id="f3a17-124">Para ver las descripciones de una página, siga este paso.</span><span class="sxs-lookup"><span data-stu-id="f3a17-124">To view the descriptions for a page, follow this step.</span></span>

- <span data-ttu-id="f3a17-125">En el campo **Seleccionar una página**, escriba el nombre de la página.</span><span class="sxs-lookup"><span data-stu-id="f3a17-125">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="f3a17-126">De forma alternativa, haga clic en la flecha para abrir una lista de todas las páginas y, a continuación, examine o filtre la lista.</span><span class="sxs-lookup"><span data-stu-id="f3a17-126">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="f3a17-127">Puede usar el nombre de la página que se muestra en la interfaz de usuario (IU) (por ejemplo, **Clientes**) o el nombre de código (nombre AOT) que está disponible al hacer clic con el botón secundario en una página (por ejemplo, **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="f3a17-127">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span>

<span data-ttu-id="f3a17-128">Para obtener información sobre las diversas maneras de filtrar la lista de páginas, vea la sección "Buscar una página" más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-128">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span>

<span data-ttu-id="f3a17-129">Si establece la opción **Incluir campos sin descripción** en **Sí**, se muestran todos los campos de la página, incluso si no tienen una descripción de campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-129">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="f3a17-130">Exportar las descripciones de una página</span><span class="sxs-lookup"><span data-stu-id="f3a17-130">Export the descriptions for a page</span></span>

<span data-ttu-id="f3a17-131">Para exportar las descripciones de una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f3a17-131">To export the descriptions for a page, follow these steps.</span></span>

1. <span data-ttu-id="f3a17-132">En el campo **Seleccionar una página**, seleccione una página.</span><span class="sxs-lookup"><span data-stu-id="f3a17-132">In the **Select a page** field, select a page.</span></span>
2. <span data-ttu-id="f3a17-133">Haga clic en el botón **Abrir de Microsoft Office** que se encuentra en la esquina superior derecha y, a continuación, haga clic en **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-133">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="f3a17-134">Buscar una página</span><span class="sxs-lookup"><span data-stu-id="f3a17-134">Searching for a page</span></span>

<span data-ttu-id="f3a17-135">Hay varias formas de buscar una página en el campo **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-135">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="f3a17-136">En muchos casos deberá hacer clic en la flecha del campo **Seleccionar una página** para abrir la lista desplegable y, a continuación, seleccione entre una lista de páginas.</span><span class="sxs-lookup"><span data-stu-id="f3a17-136">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

- <span data-ttu-id="f3a17-137">Escriba una parte del nombre y, a continuación, abra la lista desplegable para seleccionar entre una lista de páginas filtrada.</span><span class="sxs-lookup"><span data-stu-id="f3a17-137">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
- <span data-ttu-id="f3a17-138">Abra la lista desplegable y, a continuación, haga clic en el encabezado **Nombre de página** en la parte superior de la liste o en el encabezado **Nombre AOT de página**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-138">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="f3a17-139">Aparece un cuadro de diálogo, donde puede utilizar las opciones de filtrado avanzadas, como **El nombre de la página empieza por**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-139">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
- <span data-ttu-id="f3a17-140">Escriba el nombre completo de la página.</span><span class="sxs-lookup"><span data-stu-id="f3a17-140">Type the full name of the page.</span></span> <span data-ttu-id="f3a17-141">Al usar esta opción, es mejor abrir la lista desplegable y ver qué más se encuentra en la lista, aunque se muestren las descripciones de campo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-141">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>

    - <span data-ttu-id="f3a17-142">Si hay una única coincidencia exacta del nombre, se muestran las descripciones de campo de esa página.</span><span class="sxs-lookup"><span data-stu-id="f3a17-142">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    - <span data-ttu-id="f3a17-143">Si hay más de una coincidencia exacta, no se muestran descripciones.</span><span class="sxs-lookup"><span data-stu-id="f3a17-143">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="f3a17-144">Debe abrir la lista desplegable y seleccionar la página que desea.</span><span class="sxs-lookup"><span data-stu-id="f3a17-144">You must open the drop-down list and select the page that you want.</span></span>
    - <span data-ttu-id="f3a17-145">Si el nombre que ha escrito forma parte del nombre de otra página, vea las descripciones de la página.</span><span class="sxs-lookup"><span data-stu-id="f3a17-145">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="f3a17-146">Sin embargo, si abre la lista desplegable, consulte las páginas adicionales que contienen ese nombre.</span><span class="sxs-lookup"><span data-stu-id="f3a17-146">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="f3a17-147">Por ejemplo, no se muestran descripciones al escribir **Recuento** en el campo **Seleccionar una página**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-147">For example, no descriptions are shown when you type **Counting** in the **Select a page** field.</span></span> <span data-ttu-id="f3a17-148">Abre la lista desplegable y ve que hay dos páginas con el nombre **Recuento**, así como varias páginas que contienen la palabra "Recuento" en el nombre.</span><span class="sxs-lookup"><span data-stu-id="f3a17-148">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="f3a17-149">Si selecciona la página que tiene el nombre AOT **InventJournalCount**, se muestran las descripciones de campo de esa página.</span><span class="sxs-lookup"><span data-stu-id="f3a17-149">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="f3a17-150">Sin embargo, si vuelve a abrir la lista desplegable, verá que, ahora, la lista contiene todas las páginas que tienen "InventJournalCount" como parte de su nombre de AOT.</span><span class="sxs-lookup"><span data-stu-id="f3a17-150">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f3a17-151">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f3a17-151">Troubleshooting</span></span>

<span data-ttu-id="f3a17-152">En esta sección se proporciona información que le ayudará a solucionar los problemas que puedan surgir al utilizar las descripciones de campos.</span><span class="sxs-lookup"><span data-stu-id="f3a17-152">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="f3a17-153">No puedo encontrar una descripción de campo</span><span class="sxs-lookup"><span data-stu-id="f3a17-153">I can't find a field description</span></span>

<span data-ttu-id="f3a17-154">Estamos en proceso de agregar descripciones de campos más complejos.</span><span class="sxs-lookup"><span data-stu-id="f3a17-154">We're in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="f3a17-155">Si necesita ayuda para un campo determinado, háganoslo saber agregando un comentario en este tema.</span><span class="sxs-lookup"><span data-stu-id="f3a17-155">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="f3a17-156">La descripción de campo no es útil</span><span class="sxs-lookup"><span data-stu-id="f3a17-156">The field description isn't helpful</span></span>

<span data-ttu-id="f3a17-157">Háganoslo saber agregando un comentario en este tema.</span><span class="sxs-lookup"><span data-stu-id="f3a17-157">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="f3a17-158">Si es posible, describa la información adicional que requiera.</span><span class="sxs-lookup"><span data-stu-id="f3a17-158">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="f3a17-159">No encuentro un campo en la página de Descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="f3a17-159">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="f3a17-160">Para mostrar todos los campos de una página, establezca la opción **Incluir campos sin descripción** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f3a17-160">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="f3a17-161">Haga clic en el campo **Seleccionar una página** para comprobar que ha seleccionado la página correcta.</span><span class="sxs-lookup"><span data-stu-id="f3a17-161">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="f3a17-162">Si el nombre que ha escrito forma parte de otro nombre de campo, probablemente haya seleccionado la página con el nombre más largo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-162">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="f3a17-163">No encuentro una página en la página de Descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="f3a17-163">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="f3a17-164">Para obtener información sobre las diversas maneras de encontrar páginas, vea la sección "Buscar páginas" anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="f3a17-164">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="f3a17-165">Si ha escrito el nombre exacto de la página, es posible que las descripciones de campo no se muestren si más de una página tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="f3a17-165">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="f3a17-166">Haga clic en la flecha del campo **Seleccionar una página** para abrir una lista filtrada de las páginas que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f3a17-166">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3a17-167">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f3a17-167">Additional resources</span></span>

[<span data-ttu-id="f3a17-168">Personalizar descripciones de campos</span><span class="sxs-lookup"><span data-stu-id="f3a17-168">Customize field descriptions</span></span>](../../dev-itpro/user-interface/customize-field-help.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]