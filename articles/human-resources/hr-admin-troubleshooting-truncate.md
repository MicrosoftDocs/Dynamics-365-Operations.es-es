---
title: Evitar el truncamiento del texto en la jerarquía de puestos y exportar a Visio
description: Este artículo explica cómo resolver una incidencia en la que los nombres de los individuos y las posiciones se truncan cuando los clientes ven la jerarquía de posiciones en Microsoft Dynamics 365 Human Resources. El truncamiento de texto puede hacer difícil tomar una captura de pantalla o imprimir la jerarquía.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a745543f4d2a2e2a94a820f4ff5f35f8067a83d7
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466385"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="9ae25-104">Evitar truncamiento del texto en la jerarquía de puestos y exportar a Visio</span><span class="sxs-lookup"><span data-stu-id="9ae25-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9ae25-105">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="9ae25-105">**Issue**</span></span>

<span data-ttu-id="9ae25-106">Cuando los clientes ven la jerarquía de puestos en Microsoft Dynamics 365 Human Resources, los nombres de personas y puestos se truncan.</span><span class="sxs-lookup"><span data-stu-id="9ae25-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Human Resources, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="9ae25-107">Por lo tanto, puede resultar difícil tomar una captura de pantalla, o imprimir y distribuir la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="9ae25-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Jerarquía de puestos](media/position-h.png)

<span data-ttu-id="9ae25-109">**Causa**</span><span class="sxs-lookup"><span data-stu-id="9ae25-109">**Cause**</span></span>

<span data-ttu-id="9ae25-110">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="9ae25-110">This behavior is by design.</span></span>

<span data-ttu-id="9ae25-111">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="9ae25-111">**Resolution**</span></span>

<span data-ttu-id="9ae25-112">Desafortunadamente, los usuarios no pueden cambiar fácilmente el tamaño de texto.</span><span class="sxs-lookup"><span data-stu-id="9ae25-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="9ae25-113">Sin embargo, puede exportar la jerarquía de puestos fuera de Recursos humanos y después importarla a Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="9ae25-113">However, you can export the position hierarchy out of Human Resources and then import it into Microsoft Visio.</span></span> <span data-ttu-id="9ae25-114">Aunque el artículo siguiente se escribió para Microsoft Dynamics AX 2012, el proceso también se aplica a Recursos humanos: [Exportar una jerarquía de puestos a Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="9ae25-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Human Resources: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="9ae25-115">Siga estos pasos para exportar a Visio.</span><span class="sxs-lookup"><span data-stu-id="9ae25-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="9ae25-116">En Recursos humanos, abra la página de lista **Posiciones**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-116">In Human Resources, open the **Positions** list page.</span></span>

    <span data-ttu-id="9ae25-117">Para incluir obtener más información en el gráfico de la estructura de la organización, agregue campos a la lista **Puestos** , de modo que estén disponibles cuando utilice el asistente más adelante en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9ae25-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="9ae25-118">En el panel de acciones, seleccione el botón **Abrir en Microsoft Office** y, a continuación, en **Exportar a Excel**, seleccione **Puestos**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="9ae25-119">Como alternativa, presione Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="9ae25-119">Alternatively, press Ctrl+T.</span></span>

    ![Exportación de la página de lista de puestos a Excel](media/org-admin.png)

3. <span data-ttu-id="9ae25-121">Guarde el archivo de Excel que se exporta.</span><span class="sxs-lookup"><span data-stu-id="9ae25-121">Save the Excel file that is exported.</span></span>

    ![Exportación al cuadro de diálogo de Excel](media/export-excel.png)

4. <span data-ttu-id="9ae25-123">En Visio, seleccione **Visio - Crear nuevo**, y seleccione la categoría de plantilla **Negocio**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nuevo gráfico](media/new.png)

5. <span data-ttu-id="9ae25-125">Seleccione **Asistente para organigramas**, y después seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Cuadro de diálogo del Asistente para organigramas](media/orgchart-wizard.png)

6. <span data-ttu-id="9ae25-127">Seleccione **Información que ya está guardada en un archivo o una base de datos**, y después seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Asistente para Organigrama 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="9ae25-129">Seleccione **Un archivo de texto, Org Plus (\*.txt), o Excel** y, a continuación seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Asistente para Organigrama 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="9ae25-131">Explore para seleccionar el archivo de Excel exportado que contiene la jerarquía de puestos, y después selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Asistente para Organigrama 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="9ae25-133">Establezca el campo **Nombre** en **Puesto**, establezca el campo **Informa a** en **Notifica al puesto** y continuación seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Asistente para Organigrama 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="9ae25-135">Seleccione los campos que se deben mostrar en cada nodo y, a continuación seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Asistente para Organigrama 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="9ae25-137">Agregue la columna **Puesto** a la lista **Campos de los datos de formas** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Asistente para Organigrama 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="9ae25-139">Las imágenes no se encuentran disponibles.</span><span class="sxs-lookup"><span data-stu-id="9ae25-139">Pictures aren't currently available.</span></span> <span data-ttu-id="9ae25-140">Por tanto, en la siguiente página, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="9ae25-141">Seleccione **Deseo que el asistente divida automáticamente el organigrama entre las distintas páginas**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Asistente para Organigrama 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="9ae25-143">Seleccione **Fin**.</span><span class="sxs-lookup"><span data-stu-id="9ae25-143">Select **Finish**.</span></span>

    <span data-ttu-id="9ae25-144">Si existen algunos puestos que no están en la estructura, se le pedirá que los incluya en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="9ae25-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="9ae25-145">El gráfico que se genera en Visio muestra a cada administrador en una hoja de cálculo propia.</span><span class="sxs-lookup"><span data-stu-id="9ae25-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="9ae25-146">Según los campos que incluya en el gráfico, cada nodo muestra la información adecuada cuando se genera el archivo de Visio.</span><span class="sxs-lookup"><span data-stu-id="9ae25-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagrama de jerarquía](media/hierarchy.png)

<span data-ttu-id="9ae25-148">**Opción adicional**</span><span class="sxs-lookup"><span data-stu-id="9ae25-148">**Additional option**</span></span>

<span data-ttu-id="9ae25-149">En Recursos humanos, es posible que también puede usar el espacio de trabajo **Personas** para ver información relacionada con la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="9ae25-149">In Human Resources, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]