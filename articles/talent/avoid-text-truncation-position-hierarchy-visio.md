---
title: "Evitar truncamiento del texto en la jerarquía de puestos y exportar a Visio"
description: "Este tema explica cómo resolver un problema en el que los nombres de personas y de puestos se truncan cuando los clientes ven la jerarquía de puestos en Microsoft Dynamics 365 for Talent. El truncamiento de texto puede hacer difícil tomar una captura de pantalla o imprimir la jerarquía."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: b688a396e3b384aedb06c470b1634150ae7aa038
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="454ba-104">Evitar truncamiento del texto en la jerarquía de puestos y exportar a Visio</span><span class="sxs-lookup"><span data-stu-id="454ba-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="454ba-105">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="454ba-105">**Issue**</span></span>

<span data-ttu-id="454ba-106">Cuando los clientes ven la jerarquía de puestos en Microsoft Dynamics 365 for Talent, los nombres de personas y puestos se truncan.</span><span class="sxs-lookup"><span data-stu-id="454ba-106">When a customer views the position hierarchy in Microsoft Dynamics 365 for Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="454ba-107">Por lo tanto, puede resultar difícil tomar una captura de pantalla, o imprimir y distribuir la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="454ba-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Jerarquía de puestos](media/position-h.png)

<span data-ttu-id="454ba-109">**Causa**</span><span class="sxs-lookup"><span data-stu-id="454ba-109">**Cause**</span></span>

<span data-ttu-id="454ba-110">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="454ba-110">This behavior is by design.</span></span>

<span data-ttu-id="454ba-111">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="454ba-111">**Resolution**</span></span>

<span data-ttu-id="454ba-112">Desafortunadamente, los usuarios no pueden cambiar fácilmente el tamaño de texto.</span><span class="sxs-lookup"><span data-stu-id="454ba-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="454ba-113">Sin embargo, puede exportar la jerarquía de puestos fuera de Talent y después importarla a Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="454ba-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="454ba-114">Aunque el artículo siguiente se escribió para Microsoft Dynamics AX 2012, el proceso también se aplica a Talent: [Exportar una jerarquía de puestos a Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="454ba-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="454ba-115">Siga estos pasos para exportar a Visio.</span><span class="sxs-lookup"><span data-stu-id="454ba-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="454ba-116">En Talent abra la página de lista **Puestos**.</span><span class="sxs-lookup"><span data-stu-id="454ba-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="454ba-117">Para incluir obtener más información en el gráfico de la estructura de la organización, agregue campos a la lista **Puestos** , de modo que estén disponibles cuando utilice el asistente más adelante en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="454ba-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="454ba-118">En el panel de acciones, seleccione el botón **Abrir en Microsoft Office** y, a continuación, en **Exportar a Excel**, seleccione **Puestos**.</span><span class="sxs-lookup"><span data-stu-id="454ba-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="454ba-119">Como alternativa, presione Ctrl+T.</span><span class="sxs-lookup"><span data-stu-id="454ba-119">Alternatively, press Ctrl+T.</span></span>

    ![Exportación de la página de lista de puestos a Microsoft Excel](media/org-admin.png)

3. <span data-ttu-id="454ba-121">Guarde el archivo de Excel que se exporta.</span><span class="sxs-lookup"><span data-stu-id="454ba-121">Save the Excel file that is exported.</span></span>

    ![Exportación al cuadro de diálogo de Excel](media/export-excel.png)

4. <span data-ttu-id="454ba-123">En Visio, seleccione **Visio - Crear nuevo**, y seleccione la categoría de plantilla **Negocio**.</span><span class="sxs-lookup"><span data-stu-id="454ba-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nuevo gráfico](media/new.png)

5. <span data-ttu-id="454ba-125">Seleccione **Asistente para organigramas**, y después seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="454ba-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Cuadro de diálogo del Asistente para organigramas](media/orgchart-wizard.png)

6. <span data-ttu-id="454ba-127">Seleccione **Información que ya está guardada en un archivo o una base de datos**, y después seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Asistente para Organigrama 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="454ba-129">Seleccione **Un archivo de texto, Org Plus (\*.txt), o Excel** y, a continuación seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Asistente para Organigrama 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="454ba-131">Explore para seleccionar el archivo de Excel exportado que contiene la jerarquía de puestos, y después selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Asistente para Organigrama 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="454ba-133">Establezca el campo **Nombre** en **Puesto**, establezca el campo **Informa a** en **Notifica al puesto** y continuación seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Asistente para Organigrama 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="454ba-135">Seleccione los campos que se deben mostrar en cada nodo y, a continuación seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Asistente para Organigrama 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="454ba-137">Agregue la columna **Puesto** a la lista **Campos de los datos de formas** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Asistente para Organigrama 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="454ba-139">Las imágenes no se encuentran disponibles.</span><span class="sxs-lookup"><span data-stu-id="454ba-139">Pictures aren't currently available.</span></span> <span data-ttu-id="454ba-140">Por tanto, en la siguiente página, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="454ba-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="454ba-141">Seleccione **Deseo que el asistente divida automáticamente el organigrama entre las distintas páginas**.</span><span class="sxs-lookup"><span data-stu-id="454ba-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Asistente para Organigrama 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="454ba-143">Seleccione **Fin**.</span><span class="sxs-lookup"><span data-stu-id="454ba-143">Select **Finish**.</span></span>

    <span data-ttu-id="454ba-144">Si existen algunos puestos que no están en la estructura, se le pedirá que los incluya en el diagrama.</span><span class="sxs-lookup"><span data-stu-id="454ba-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="454ba-145">El gráfico que se genera en Visio muestra a cada administrador en una hoja de cálculo propia.</span><span class="sxs-lookup"><span data-stu-id="454ba-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="454ba-146">Según los campos que incluya en el gráfico, cada nodo muestra la información adecuada cuando se genera el archivo de Visio.</span><span class="sxs-lookup"><span data-stu-id="454ba-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagrama de jerarquía](media/hierarchy.png)

<span data-ttu-id="454ba-148">**Opción adicional**</span><span class="sxs-lookup"><span data-stu-id="454ba-148">**Additional option**</span></span>

<span data-ttu-id="454ba-149">En Talent, es posible que también puede usar el espacio de trabajo **Personas** para ver información relacionada con la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="454ba-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>

