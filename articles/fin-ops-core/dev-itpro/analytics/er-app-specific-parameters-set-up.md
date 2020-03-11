---
title: Configurar los parámetros de un formato de ER por entidad jurídica
description: En este tema se explica cómo puede configurar los parámetros de un formato de informes electrónicos (ER) por entidad jurídica.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: ca837026f18034cddb34d7a2d5a62002ed69106a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042766"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="450cf-103">Configurar los parámetros de un formato de ER por entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="450cf-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="450cf-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="450cf-104">Prerequisites</span></span>

<span data-ttu-id="450cf-105">Para completar estos pasos, primero debe completar los pasos del tema [Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="450cf-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="450cf-106">Para completar los ejemplos de este tema, debe tener acceso a Microsoft Dynamics 365 Finance (Finance) para uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="450cf-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="450cf-107">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="450cf-107">Electronic reporting developer</span></span>
- <span data-ttu-id="450cf-108">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="450cf-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="450cf-109">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="450cf-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="450cf-110">Importar configuraciones de ER</span><span class="sxs-lookup"><span data-stu-id="450cf-110">Import ER configurations</span></span>

1.  <span data-ttu-id="450cf-111">Inicie sesión en su entorno.</span><span class="sxs-lookup"><span data-stu-id="450cf-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="450cf-112">En el panel predeterminado, seleccione **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="450cf-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="450cf-113">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="450cf-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="450cf-114">Importe, en la instancia actual de Finance, las configuraciones que exportó de los Regulatory Configuration Services (RCS) mientras completaba los pasos del tema [Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="450cf-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="450cf-115">Siga estos pasos para cada configuración de informe electrónico (ER) en el siguiente orden: modelo de datos, asignación de modelo y formatos.</span><span class="sxs-lookup"><span data-stu-id="450cf-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="450cf-116">Seleccione **Cambio \> Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="450cf-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="450cf-117">Seleccione **Examinar** para seleccionar el archivo para la configuración necesaria de ER en formato XML.</span><span class="sxs-lookup"><span data-stu-id="450cf-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="450cf-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-118">Select **OK**.</span></span>
    
    <span data-ttu-id="450cf-119">La siguiente ilustración muestra las configuraciones que debe tener cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="450cf-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![Página de configuraciones de ER](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="450cf-121">Configurar parámetros para la empresa DEMF</span><span class="sxs-lookup"><span data-stu-id="450cf-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="450cf-122">Puede usar el marco de ER para configurar los parámetros específicos de la aplicación para un formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="450cf-123">Seleccionar la entidad jurídica **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="450cf-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="450cf-124">En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.</span><span class="sxs-lookup"><span data-stu-id="450cf-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="450cf-125">En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros específicos de la aplicación**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![Página de parámetros específicos de la aplicación de ER](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="450cf-127">En la página **Parámetros específicos de la aplicación**, puede configurar las reglas para el origen de datos **Selector** del formato **Formato para aprender a buscar datos de LE**.</span><span class="sxs-lookup"><span data-stu-id="450cf-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="450cf-128">Si el formato básico de ER contiene varios orígenes de datos del tipo **Búsqueda**, debe seleccionar el origen de datos deseado en la ficha desplegable **Búsquedas** antes de empezar a configurar el conjunto de reglas para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="450cf-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="450cf-129">Para cada origen de datos, puede configurar reglas independientes para cada versión del formato de ER seleccionado.</span><span class="sxs-lookup"><span data-stu-id="450cf-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="450cf-130">El conjunto completo de reglas para todos los orígenes de datos de la búsqueda que están disponibles en la versión seleccionada del formato básico de ER constituye los parámetros específicos de la aplicación para el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="450cf-131">Seleccione la versión **1.1.1** del formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="450cf-132">En la ficha desplegable **Condiciones**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="450cf-133">En el campo **Código** del nuevo registro, seleccione la flecha desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="450cf-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="450cf-134">La búsqueda presenta la lista de códigos de impuestos para la selección.</span><span class="sxs-lookup"><span data-stu-id="450cf-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="450cf-135">El origen de datos **Model.Data.Tax** que se ha configurado en el formato básico de ER ha devuelto esta lista.</span><span class="sxs-lookup"><span data-stu-id="450cf-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="450cf-136">Puesto que este origen de datos contiene el campo **Nombre**, el nombre de cada código de impuestos aparece en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="450cf-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![Página de parámetros específicos de la aplicación de ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="450cf-138">Seleccione el código de impuestos **VAT19**.</span><span class="sxs-lookup"><span data-stu-id="450cf-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="450cf-139">En el campo **Resultado de la búsqueda** del nuevo registro, seleccione la flecha desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="450cf-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="450cf-140">La búsqueda presenta la lista de valores para la enumeración del formato TaxationLevel para la selección.</span><span class="sxs-lookup"><span data-stu-id="450cf-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="450cf-141">Tenga en cuenta que, si selecciona el alemán como el idioma preferido del usuario que inicia sesión, las etiquetas de los valores de la búsqueda estarán en alemán, siempre que se haya traducido en el formato básico de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="450cf-142">Además, si se ha traducido la etiqueta de un origen de datos de la búsqueda, esa etiqueta aparecerá en el idioma preferido del usuario en la pestaña **Búsquedas**.</span><span class="sxs-lookup"><span data-stu-id="450cf-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![Página de parámetros específicos de la aplicación de ER](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="450cf-144">Seleccione el valor **Impuesto normal**.</span><span class="sxs-lookup"><span data-stu-id="450cf-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="450cf-145">Al agregar este registro, define la siguiente regla: Siempre que se solicite el origen de datos de la búsqueda **Selector** y el código de impuesto **VAT19** se pase como argumento, **Impuesto normal** se devolverá como el nivel impositivo solicitado.</span><span class="sxs-lookup"><span data-stu-id="450cf-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="450cf-146">Seleccione **Agregar** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="450cf-147">En el campo **Código**, seleccione el código de impuestos **InVAT19**.</span><span class="sxs-lookup"><span data-stu-id="450cf-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="450cf-148">En el campo **Resultado de la búsqueda**, seleccione el valor **Impuesto normal**.</span><span class="sxs-lookup"><span data-stu-id="450cf-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="450cf-149">Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="450cf-150">En el campo **Código**, seleccione el código de impuestos **VAT7**.</span><span class="sxs-lookup"><span data-stu-id="450cf-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="450cf-151">En el campo **Resultado de la búsqueda**, seleccione el valor **Impuesto reducido**.</span><span class="sxs-lookup"><span data-stu-id="450cf-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="450cf-152">Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="450cf-153">En el campo **Código**, seleccione el código de impuestos **InVAT**.</span><span class="sxs-lookup"><span data-stu-id="450cf-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="450cf-154">En el campo **Resultado de la búsqueda**, seleccione el valor **Impuesto reducido**.</span><span class="sxs-lookup"><span data-stu-id="450cf-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="450cf-155">Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="450cf-156">En el campo **Código**, seleccione el código de impuestos **THIRD**.</span><span class="sxs-lookup"><span data-stu-id="450cf-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="450cf-157">En el campo **Resultado de la búsqueda**, seleccione el valor **Ningún impuesto**.</span><span class="sxs-lookup"><span data-stu-id="450cf-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="450cf-158">Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="450cf-159">En el campo **Código**, seleccione el código de impuestos **InVAT0**.</span><span class="sxs-lookup"><span data-stu-id="450cf-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="450cf-160">En el campo **Resultado de la búsqueda**, seleccione el valor **Ningún impuesto**.</span><span class="sxs-lookup"><span data-stu-id="450cf-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="450cf-161">Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="450cf-162">En el campo **Código**, seleccione la opción **\*No en blanco\***.</span><span class="sxs-lookup"><span data-stu-id="450cf-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="450cf-163">En el campo **Resultado de la búsqueda**, seleccione el valor **Otro**.</span><span class="sxs-lookup"><span data-stu-id="450cf-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="450cf-164">Al agregar este último registro, define la siguiente regla: Siempre que el código se impuestos que se pasa como argumento no cumpla ninguna de las reglas anteriores, el origen de datos de la búsqueda devolverá **Otro** como el nivel impositivo solicitado.</span><span class="sxs-lookup"><span data-stu-id="450cf-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![Página de parámetros específicos de la aplicación de ER](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="450cf-166">En el campo **Estado**, seleccione **Completado**.</span><span class="sxs-lookup"><span data-stu-id="450cf-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="450cf-167">Cuando ejecute una versión de formato de ER que tenga un estado **Completado** o **Compartido**, este conjunto de reglas debe estar en el estado **Completado**.</span><span class="sxs-lookup"><span data-stu-id="450cf-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="450cf-168">De lo contrario, la ejecución del formato básico de ER se interrumpirá cuando el formato trate de cargar datos de este conjunto de reglas mientras se está ejecutando el origen de datos de la búsqueda **Selector**.</span><span class="sxs-lookup"><span data-stu-id="450cf-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="450cf-169">Cuando ejecute una versión de formato de ER que tenga un estado **Borrador**, el formato básico de ER puede acceder a este conjunto de reglas, independientemente de su estado.</span><span class="sxs-lookup"><span data-stu-id="450cf-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="450cf-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-170">Select **Save**.</span></span>
18. <span data-ttu-id="450cf-171">Cierre la página **Parámetros específicos de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="450cf-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="450cf-172">Ejecutar el formato de ER en la empresa DEMF</span><span class="sxs-lookup"><span data-stu-id="450cf-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="450cf-173">En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.</span><span class="sxs-lookup"><span data-stu-id="450cf-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="450cf-174">En el panel de acciones, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="450cf-175">En el cuadro de diálogo que aparece, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="450cf-176">Descargue el extracto que se ha generado y almacénelo localmente.</span><span class="sxs-lookup"><span data-stu-id="450cf-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="450cf-177">En la declaración, tenga en cuenta que el resumen del código de impuestos **InVAT7** se ha establecido en el nivel **Reducido** y los resúmenes de los códigos de impuestos **VAT19** e **InVA19** se han colocado en el nivel **Normal**.</span><span class="sxs-lookup"><span data-stu-id="450cf-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="450cf-178">Este comportamiento se determina según la configuración del conjunto de reglas que dependen de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="450cf-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="450cf-179">Vaya a **Impuestos \> Impuestos indirectos \> Impuestos \> Códigos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="450cf-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="450cf-180">Seleccione el código de impuestos **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="450cf-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="450cf-181">En el panel de acciones, en la pestaña **Código de impuestos**, en el grupo **Consultas**, seleccione **Impuestos registrados** para ver información acerca del valor de los impuestos y el tipo impositivo aplicado por código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="450cf-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Página de impuestos registrados](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="450cf-183">Cierre la página Impuestos registrados.</span><span class="sxs-lookup"><span data-stu-id="450cf-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="450cf-184">Configurar parámetros para la empresa USMF</span><span class="sxs-lookup"><span data-stu-id="450cf-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="450cf-185">Seleccionar la entidad jurídica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="450cf-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="450cf-186">Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="450cf-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="450cf-187">En el árbol de configuraciones, expanda el elemento **Modelo para aprender llamadas con parámetros**, expanda el elemento **Formato para aprender llamadas con parámetros** y seleccione el formato **Formato para aprender a buscar datos de LE**.</span><span class="sxs-lookup"><span data-stu-id="450cf-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="450cf-188">En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros específicos de la aplicación**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="450cf-189">Seleccione la versión **1.1.1** del formato de ER seleccionado.</span><span class="sxs-lookup"><span data-stu-id="450cf-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="450cf-190">En la ficha desplegable **Condiciones**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="450cf-191">En el campo **Código** del nuevo registro, seleccione la flecha desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="450cf-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="450cf-192">La búsqueda presenta ahora la lista de códigos de impuestos para los impuestos de empresa **USMF** para su selección.</span><span class="sxs-lookup"><span data-stu-id="450cf-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![Página de parámetros específicos de la aplicación de ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="450cf-194">Seleccione el código de impuestos **EXEMPT**.</span><span class="sxs-lookup"><span data-stu-id="450cf-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="450cf-195">En el campo **Resultado de la búsqueda** del nuevo registro, seleccione el valor **Ningún impuesto**.</span><span class="sxs-lookup"><span data-stu-id="450cf-195">In the **Lookup resul**t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="450cf-196">Seleccione de nuevo **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-196">Select **Add** again.</span></span>
11. <span data-ttu-id="450cf-197">En el campo **Código** del nuevo registro, seleccione la opción **\*No en blanco\***.</span><span class="sxs-lookup"><span data-stu-id="450cf-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="450cf-198">En el campo **Resultado de la búsqueda** del nuevo registro, seleccione el valor **Impuesto normal**.</span><span class="sxs-lookup"><span data-stu-id="450cf-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="450cf-199">En el campo **Estado**, seleccione **Completado**.</span><span class="sxs-lookup"><span data-stu-id="450cf-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="450cf-200">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-200">Select **Save**.</span></span>

    ![Página de parámetros específicos de la aplicación de ER](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="450cf-202">Cierre la página **Parámetros específicos de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="450cf-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="450cf-203">Ejecutar el formato de ER en la empresa USMF</span><span class="sxs-lookup"><span data-stu-id="450cf-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="450cf-204">En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.</span><span class="sxs-lookup"><span data-stu-id="450cf-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="450cf-205">En el panel de acciones, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="450cf-206">En el cuadro de diálogo que aparece, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="450cf-207">Descargue el extracto que se ha generado y almacénelo localmente.</span><span class="sxs-lookup"><span data-stu-id="450cf-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="450cf-208">En la declaración generada, tenga en cuenta que ahora ha reutilizado el mismo formato de ER para una entidad jurídica diferente, pero sin realizar ningún ajuste en el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="450cf-209">Reutilizar parámetros que dependen de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="450cf-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="450cf-210">Exportar parámetros</span><span class="sxs-lookup"><span data-stu-id="450cf-210">Export parameters</span></span>

1.  <span data-ttu-id="450cf-211">Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="450cf-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="450cf-212">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="450cf-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="450cf-213">En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.</span><span class="sxs-lookup"><span data-stu-id="450cf-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="450cf-214">En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros específicos de la aplicación**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="450cf-215">Seleccione la versión **1.1.1** del formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="450cf-216">En el panel de acciones, seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="450cf-217">Descargue el archivo que se ha generado y almacénelo localmente.</span><span class="sxs-lookup"><span data-stu-id="450cf-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="450cf-218">El conjunto configurado de parámetros específicos de la aplicación se ha exportado ahora como un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="450cf-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="450cf-219">Importar parámetros</span><span class="sxs-lookup"><span data-stu-id="450cf-219">Import parameters</span></span>

1.  <span data-ttu-id="450cf-220">Seleccione la versión **1.1.2** del formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="450cf-221">En el panel de acciones, seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="450cf-222">Seleccione **Sí** para confirmar que desea anular los parámetros específicos de la aplicación existentes para esta versión del formato.</span><span class="sxs-lookup"><span data-stu-id="450cf-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="450cf-223">Seleccione **Examinar** para encontrar el archivo que contiene los parámetros específicos de la aplicación exportados para la versión **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="450cf-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="450cf-224">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="450cf-224">Select **OK**.</span></span>

    <span data-ttu-id="450cf-225">La versión **1.1.2** del formato de ER ahora tiene los mismos parámetros específicos de la aplicación que configuró originalmente para la versión **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="450cf-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="450cf-226">Tenga en cuenta que los parámetros específicos de la aplicación de un formato de ER dependen de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="450cf-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="450cf-227">Para reutilizar los parámetros específicos de la aplicación que se configuraron para una entidad jurídica en una entidad jurídica diferente, debe exportarlos mientras inicia sesión en la primera entidad jurídica y después importarlos después de iniciar sesión en la otra entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="450cf-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="450cf-228">También puede usar este enfoque para transferir un formato de ER relacionado con parámetros específicos de la aplicación que se configuró originalmente en una instancia de Finance a otra instancia de Finance.</span><span class="sxs-lookup"><span data-stu-id="450cf-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="450cf-229">Tenga en cuenta que si configura parámetros específicos de la aplicación para una versión de un formato de ER y importa una versión superior del mismo formato en la instancia actual de Finance, los parámetros específicos de la aplicación existentes no se aplicarán para la versión importada.</span><span class="sxs-lookup"><span data-stu-id="450cf-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="450cf-230">Tenga también en cuenta que, cuando selecciona un archivo para importarlo, la estructura de los parámetros específicos de la aplicación en ese archivo se compara con la estructura del origen de datos correspondiente del tipo **Búsqueda** en el formato de ER seleccionado para su importación.</span><span class="sxs-lookup"><span data-stu-id="450cf-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="450cf-231">La importación se realiza cuando la estructura de cada parámetro específico de la aplicación coincide con la estructura del origen de datos correspondiente en el formato de ER seleccionado para su importación.</span><span class="sxs-lookup"><span data-stu-id="450cf-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="450cf-232">Si las estructuras no coinciden, recibe un mensaje de advertencia que indica que la importación no se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="450cf-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="450cf-233">Si fuerza que se haga la importación, los parámetros específicos de la aplicación existentes para el formato de ER seleccionado se borrarán, y deberá configurarlos desde el principio.</span><span class="sxs-lookup"><span data-stu-id="450cf-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="450cf-234">Relación entre los parámetros específicos de la aplicación y un formato de ER</span><span class="sxs-lookup"><span data-stu-id="450cf-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="450cf-235">La relación entre un formato de ER y sus parámetros específicos de la aplicación la establece el código de identificación único independiente de la instancia del formato de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="450cf-236">Por lo tanto, cuando elimina un formato de ER de Finance, los parámetros específicos de la aplicación que se configuran para el formato de ER se mantienen en la instancia actual de Finance.</span><span class="sxs-lookup"><span data-stu-id="450cf-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="450cf-237">Se puede acceder a estos siempre que el formato básico de ER se reimporte en esta instancia de Finance.</span><span class="sxs-lookup"><span data-stu-id="450cf-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="450cf-238">Acceder a parámetros específicos de la aplicación mediante el marco de ER</span><span class="sxs-lookup"><span data-stu-id="450cf-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="450cf-239">En el ejemplo anterior, ha accedido a parámetros específicos de la aplicación de un formato de ER mediante el marco de ER.</span><span class="sxs-lookup"><span data-stu-id="450cf-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="450cf-240">Este enfoque no le permite restringir el acceso a los parámetros específicos de la aplicación de un formato de ER específico.</span><span class="sxs-lookup"><span data-stu-id="450cf-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="450cf-241">Si debe aplicar como restricciones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="450cf-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="450cf-242">Volver a usar un elemento de menú **ERSolutionAppSpecificParametersDesigner** existente o implemente su propio elemento de menú **ERSolutionAppSpecificParametersDesigner**.</span><span class="sxs-lookup"><span data-stu-id="450cf-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Página Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="450cf-244">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="450cf-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="450cf-245">Cree un nuevo botón de elementos de menú y vincúlelo al registro correspondiente de la tabla **ERSolutionTable** estableciendo su propiedad **Origen de datos** en **ERSolutionTable**.</span><span class="sxs-lookup"><span data-stu-id="450cf-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Página Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="450cf-247">Cree un simple botón y anule el método **En el que se ha hecho clic** como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="450cf-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="450cf-248">Mediante este enfoque, puede especificar un id. de solución único (definido mediante el valor **GUID**) para permitir el acceso a los parámetros específicos de la aplicación de solo un formato de ER específico y a las copias descendientes que se han derivado de este.</span><span class="sxs-lookup"><span data-stu-id="450cf-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="450cf-249">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="450cf-249">Additional resources</span></span>

[<span data-ttu-id="450cf-250">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="450cf-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="450cf-251">Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="450cf-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)
