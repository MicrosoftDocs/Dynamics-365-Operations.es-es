---
title: Agregar análisis a espacios de trabajo mediante Power BI Embedded
description: Este tema muestra cómo insertar un informe de Power BI en la ficha Análisis de un espacio de trabajo.
author: RichdiMSFT
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 8e82c9a5ff4b6d7db1a808e5a94206628cdf0930
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754607"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="573c5-103">Agregar análisis a espacios de trabajo mediante Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="573c5-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="573c5-104">Esta función se admite en Finance and Operations (versión 7.2 y posterior).</span><span class="sxs-lookup"><span data-stu-id="573c5-104">This feature is supported in Finance and Operations (version 7.2 and later).</span></span>

## <a name="introduction"></a><span data-ttu-id="573c5-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="573c5-105">Introduction</span></span>
<span data-ttu-id="573c5-106">Este tema muestra cómo insertar un informe de Microsoft Power BI en la pestaña **Análisis** de un espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="573c5-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="573c5-107">Para el ejemplo que se da aquí, extenderemos el espacio de trabajo **Administración de reserva** en la aplicación de administración de flota para insertar un espacio de trabajo analítico en una pestaña **Análisis** .</span><span class="sxs-lookup"><span data-stu-id="573c5-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="573c5-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="573c5-108">Prerequisites</span></span>
+ <span data-ttu-id="573c5-109">Obtenga acceso a un entorno del desarrollador de software que ejecute la actualización de plataforma 8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="573c5-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="573c5-110">Informe analítico (archivo .pbix) que se ha creado usando Microsoft Microsoft Power BI Desktop, y que tiene un modelo de datos originario de la base de datos del almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="573c5-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

## <a name="overview"></a><span data-ttu-id="573c5-111">Información general</span><span class="sxs-lookup"><span data-stu-id="573c5-111">Overview</span></span>
<span data-ttu-id="573c5-112">Si extiende un espacio de trabajo de la aplicación existente o presenta un nuevo espacio de trabajo propio, puede usar las visualizaciones analíticas incrustadas para entregar visualizaciones profundas e interactivas de los datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="573c5-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="573c5-113">El proceso para agregar una ficha de espacio de trabajo analítico tiene cuatro pasos.</span><span class="sxs-lookup"><span data-stu-id="573c5-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="573c5-114">Agregue un archivo .pbix como recurso de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="573c5-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="573c5-115">Defina una ficha del espacio de trabajo analítico.</span><span class="sxs-lookup"><span data-stu-id="573c5-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="573c5-116">Inserte el recurso .pbix en la ficha del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="573c5-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="573c5-117">Opcional: Agregue extensiones para personalizar la vista.</span><span class="sxs-lookup"><span data-stu-id="573c5-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="573c5-118">Para obtener más información sobre cómo crear informes analíticos, consulte [Introducción a Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="573c5-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="573c5-119">Esta página es muy buena para obtener información que ayude a crear soluciones de informes analíticos interesantes.</span><span class="sxs-lookup"><span data-stu-id="573c5-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

## <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="573c5-120">Agregue un archivo .pbix como recurso</span><span class="sxs-lookup"><span data-stu-id="573c5-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="573c5-121">Antes de empezar, debe crear u obtener el informe de Power BI que insertará en el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="573c5-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="573c5-122">Para obtener más información sobre cómo crear informes analíticos, consulte [Introducción a Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="573c5-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).</span></span>

<span data-ttu-id="573c5-123">Siga estos pasos para agregar un archivo .pbix como artefacto del proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="573c5-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="573c5-124">Cree un nuevo proyecto en el modelo adecuado.</span><span class="sxs-lookup"><span data-stu-id="573c5-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="573c5-125">En Explorador de soluciones, seleccione el proyecto, haga clic con el botón secundario y, a continuación, seleccione **Agregar** \> **Nuevo artículo**.</span><span class="sxs-lookup"><span data-stu-id="573c5-125">In Solution Explorer, select the project, right-click, and then select **Add** \> **New Item**.</span></span>
3. <span data-ttu-id="573c5-126">En el cuadro de diálogo **Agregar nuevo artículo** , en **Artefactos de operaciones**, seleccione la plantilla **Recurso**.</span><span class="sxs-lookup"><span data-stu-id="573c5-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="573c5-127">Escriba un nombre que se usará para hacer referencia al informe en metadatos X++, y después haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="573c5-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Cuadro de diálogo Agregar nuevo artículo](media/analytical-workspace-add.png)

5. <span data-ttu-id="573c5-129">Busque el archivo .pbix que contiene la definición del informe analítico y, a continuación haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="573c5-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Seleccione un cuadro de diálogo del archivo de recursos](media/analytical-workspace-select-resource.png)

<span data-ttu-id="573c5-131">Ahora que ha agregado el archivo .pbix como recurso de Dynamics 365, puede insertar los informes en los espacios de trabajo y agregar vínculos directos mediante elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="573c5-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

## <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="573c5-132">Agregar un control de la ficha a un espacio de trabajo de la aplicación</span><span class="sxs-lookup"><span data-stu-id="573c5-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="573c5-133">En este ejemplo, extenderemos el espacio de trabajo **Administración de reserva** en el modelo de administración de flota agregando la pestaña **Análisis** a la definición del formulario **FMClerkWorkspace** .</span><span class="sxs-lookup"><span data-stu-id="573c5-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>

<span data-ttu-id="573c5-134">La ilustración siguiente muestra qué parece el formulario **FMClerkWorkspace** en el diseñador en Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="573c5-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![Formulario FMClerkWorkspace antes de los cambios](media/analytical-workspace-definition-before.png)

<span data-ttu-id="573c5-136">Siga estos pasos para extender la definición del formulario para el espacio de trabajo **Administración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="573c5-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="573c5-137">Abra el diseñador de formularios para ampliar la definición de diseño.</span><span class="sxs-lookup"><span data-stu-id="573c5-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="573c5-138">En la definición de diseño, seleccione el elemento superior que tiene la etiqueta **Diseño | Patrón: Operacional en espacio de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="573c5-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="573c5-139">Haga clic con el botón secundario y, a continuación seleccione **Nuevo** \> **Ficha** para agregar un nuevo control que se llama **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="573c5-139">Right-click, and then select **New** \> **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="573c5-140">En el diseñador del formulario, seleccione **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="573c5-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="573c5-141">Haga clic con el botón secundario y, a continuación seleccione **Página de nueva pestaña** para agregar una nueva página de pestaña.</span><span class="sxs-lookup"><span data-stu-id="573c5-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="573c5-142">Cambie el nombre de la página de ficha por un nombre con significado, como por ejemplo **Espacio de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="573c5-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="573c5-143">En el diseñador del formulario, seleccione **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="573c5-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="573c5-144">Haga clic con el botón secundario del mouse y seleccione **Página de nueva pestaña**.</span><span class="sxs-lookup"><span data-stu-id="573c5-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="573c5-145">Cambie el nombre de la página de ficha por un nombre con significado, como por ejemplo **Análisis**.</span><span class="sxs-lookup"><span data-stu-id="573c5-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="573c5-146">En el diseñador de formularios, seleccione **Análisis (página de pestaña)**.</span><span class="sxs-lookup"><span data-stu-id="573c5-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="573c5-147">Establezca la propiedad **Subtítulo** a **Análisis** y establezca la propiedad **Declaración automática** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="573c5-147">Set the **Caption** property to **Analytics**, and set the **Auto Declaration** property to **Yes**.</span></span>
12. <span data-ttu-id="573c5-148">Haga clic con el botón secundario en el control y, a continuación seleccione **Nuevo** \> **Grupo** para agregar un nuevo control de grupo del formulario.</span><span class="sxs-lookup"><span data-stu-id="573c5-148">Right-click the control, and then select **New** \> **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="573c5-149">Cambie el nombre del grupo de formulario por un nombre con significado, como por ejemplo **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="573c5-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="573c5-150">En el diseñador de formularios, seleccione **PanoramaBody (ficha)**, y después arrastre el control a la pestaña **Espacio de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="573c5-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="573c5-151">En la definición de diseño, seleccione el elemento superior que tiene la etiqueta **Diseño | Patrón: Operacional en espacio de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="573c5-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="573c5-152">Haga clic con el botón secundario del mouse y seleccione **Quitar patrón**.</span><span class="sxs-lookup"><span data-stu-id="573c5-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="573c5-153">Vuelva a hacer clic con el botón secundario, y después seleccione **Agregar patrón** \> **Espacio de trabajo tabulado**.</span><span class="sxs-lookup"><span data-stu-id="573c5-153">Right-click again, and then select **Add pattern** \> **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="573c5-154">Realice una compilación para comprobar los cambios.</span><span class="sxs-lookup"><span data-stu-id="573c5-154">Perform a build to verify your changes.</span></span>

<span data-ttu-id="573c5-155">La ilustración siguiente muestra el aspecto del diseño después de aplicar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="573c5-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![FMClerkWorkspace después de los cambios](media/analytical-workspace-definition-after.png)

<span data-ttu-id="573c5-157">Ahora que ha agregado los controles de formulario que se usarán para insertar el informe del espacio de trabajo, debe definir el tamaño del control principal de modo que aloje el diseño.</span><span class="sxs-lookup"><span data-stu-id="573c5-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="573c5-158">De forma predeterminada, la página **Panel de los filtros** y la página **Ficha** serán visibles en el informe.</span><span class="sxs-lookup"><span data-stu-id="573c5-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="573c5-159">Sin embargo, puede cambiar la visibilidad de estos controles según corresponda para el consumidor de destino del informe.</span><span class="sxs-lookup"><span data-stu-id="573c5-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>

> [!NOTE]
> <span data-ttu-id="573c5-160">Para los espacios de trabajo incrustados se recomienda usar extensiones para ocultar las páginas **Panel de los filtros** y **Ficha** para tener en cuenta la coherencia.</span><span class="sxs-lookup"><span data-stu-id="573c5-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>

<span data-ttu-id="573c5-161">Ha terminado la tarea de ampliar la definición del formulario de solicitud.</span><span class="sxs-lookup"><span data-stu-id="573c5-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="573c5-162">Para obtener más información sobre cómo usar extensiones para personalizaciones, consulte [Personalización a través de extensiones y superposiciones](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="573c5-162">For more information about how to use extensions to do customizations, see [Customize through extension and overlayering](../extensibility/customization-overlayering-extensions.md).</span></span>

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="573c5-163">Agregue la lógica de negocios X++ para insertar un control del visor</span><span class="sxs-lookup"><span data-stu-id="573c5-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="573c5-164">Siga estos pasos para agregar la lógica de negocios que inicializa el control del visor de informes que está insertado en el espacio de trabajo **Administración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="573c5-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="573c5-165">Abra el diseñador de formularios **FMClerkWorkspace** para ampliar la definición de diseño.</span><span class="sxs-lookup"><span data-stu-id="573c5-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="573c5-166">Presione F7 para obtener acceso al código que subyace a la definición del código.</span><span class="sxs-lookup"><span data-stu-id="573c5-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="573c5-167">Agregue el código X++ siguiente.</span><span class="sxs-lookup"><span data-stu-id="573c5-167">Add the following X++ code.</span></span>

    ```xpp
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. <span data-ttu-id="573c5-168">Realice una compilación para comprobar los cambios.</span><span class="sxs-lookup"><span data-stu-id="573c5-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="573c5-169">Ha terminado la tarea de agregar la lógica de negocios para inicializar el control del visor del informe incrustado.</span><span class="sxs-lookup"><span data-stu-id="573c5-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="573c5-170">La ilustración siguiente muestra el aspecto del espacio de trabajo después de aplicar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="573c5-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![Informe insertado en el espacio de trabajo](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="573c5-172">Puede obtener acceso a la vista operativa existente mediante las fichas del espacio de trabajo de debajo del título de la página.</span><span class="sxs-lookup"><span data-stu-id="573c5-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

## <a name="reference"></a><span data-ttu-id="573c5-173">Referencia</span><span class="sxs-lookup"><span data-stu-id="573c5-173">Reference</span></span>

### <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="573c5-174">Método de PBIReportHelper.initializeReportControl</span><span class="sxs-lookup"><span data-stu-id="573c5-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="573c5-175">Esta sección proporciona información sobre la clase de auxiliar que se utiliza para insertar un informe de Power BI (recurso .pbix) en un control de grupo del formulario.</span><span class="sxs-lookup"><span data-stu-id="573c5-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

#### <a name="syntax"></a><span data-ttu-id="573c5-176">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="573c5-176">Syntax</span></span>
```xpp
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a><span data-ttu-id="573c5-177">Parámetros</span><span class="sxs-lookup"><span data-stu-id="573c5-177">Parameters</span></span>

| <span data-ttu-id="573c5-178">Nombre</span><span class="sxs-lookup"><span data-stu-id="573c5-178">Name</span></span>             | <span data-ttu-id="573c5-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="573c5-179">Description</span></span>                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="573c5-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="573c5-180">resourceName</span></span>     | <span data-ttu-id="573c5-181">El nombre del recurso .pbix.</span><span class="sxs-lookup"><span data-stu-id="573c5-181">The name of the .pbix resource.</span></span>                                                                              |
| <span data-ttu-id="573c5-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="573c5-182">formGroupControl</span></span> | <span data-ttu-id="573c5-183">El control de grupo de formulario al que se aplica el control del informe de Power BI.</span><span class="sxs-lookup"><span data-stu-id="573c5-183">The form group control to apply the Power BI report control to.</span></span>                                              |
| <span data-ttu-id="573c5-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="573c5-184">defaultPageName</span></span>  | <span data-ttu-id="573c5-185">El nombre de la página predeterminada.</span><span class="sxs-lookup"><span data-stu-id="573c5-185">The default page name.</span></span>                                                                                       |
| <span data-ttu-id="573c5-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="573c5-186">showFilterPane</span></span>   | <span data-ttu-id="573c5-187">Un valor booleano que indica si el panel de filtros se debe mostrar (**true**) u ocultar (**false**).</span><span class="sxs-lookup"><span data-stu-id="573c5-187">A Boolean value that indicates whether the filter pane should be shown (**true**) or hidden (**false**).</span></span>     |
| <span data-ttu-id="573c5-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="573c5-188">showNavPane</span></span>      | <span data-ttu-id="573c5-189">Un valor booleano que indica si el panel de navegación se debe mostrar (**true**) u ocultar (**false**).</span><span class="sxs-lookup"><span data-stu-id="573c5-189">A Boolean value that indicates whether the navigation pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="573c5-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="573c5-190">defaultFilters</span></span>   | <span data-ttu-id="573c5-191">Los filtros predeterminados del informe de Power BI.</span><span class="sxs-lookup"><span data-stu-id="573c5-191">The default filters for the Power BI report.</span></span>                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]