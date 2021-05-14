---
title: Gestionar las unidades de medida
description: Este rema describe cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921350"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="922e7-103">Gestionar las unidades de medida</span><span class="sxs-lookup"><span data-stu-id="922e7-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="922e7-104">Este rema describe cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="922e7-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="922e7-105">Abrir la página de unidades</span><span class="sxs-lookup"><span data-stu-id="922e7-105">Open the Units page</span></span>

<span data-ttu-id="922e7-106">Para crear y trabajar con las unidades de medida que están disponibles en su sistema, vaya a **Administración de la organización \> Configuración \> Unidades \> Unidades**.</span><span class="sxs-lookup"><span data-stu-id="922e7-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="922e7-107">Las secciones restantes de este tema describen lo que puede hacer en la página **Unidades**.</span><span class="sxs-lookup"><span data-stu-id="922e7-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="922e7-108">Crear unidades y conversiones estándar</span><span class="sxs-lookup"><span data-stu-id="922e7-108">Create standard units and conversions</span></span>

<span data-ttu-id="922e7-109">Si su sistema aún no incluye las unidades de medida más utilizadas para el sistema métrico y/o el sistema particular de EE. UU. (USCS), el asistente de configuración de unidades puede ayudarle a comenzar rápidamente con las definiciones y conversiones de unidades básicas.</span><span class="sxs-lookup"><span data-stu-id="922e7-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="922e7-110">Para completar el asistente, seleccione **Asistente de creación de unidades** en el panel de acciones y luego siga las instrucciones en pantalla.</span><span class="sxs-lookup"><span data-stu-id="922e7-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="922e7-111">Crear o editar una unidad de medida</span><span class="sxs-lookup"><span data-stu-id="922e7-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="922e7-112">Para crear o editar una unidad de medida, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="922e7-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="922e7-113">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="922e7-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="922e7-114">Para editar una unidad existente, selecciónela en el panel de lista.</span><span class="sxs-lookup"><span data-stu-id="922e7-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="922e7-115">Para crear una nueva unidad, seleccione **Nueva** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="922e7-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="922e7-116">En el encabezado del registro, establezca los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="922e7-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="922e7-117">**Unidad**: introduzca el id. o el símbolo que se utilizará para hacer referencia a la unidad en el idioma del sistema.</span><span class="sxs-lookup"><span data-stu-id="922e7-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="922e7-118">Este id. o símbolo suele ser una abreviatura común de la unidad, como *ea* por cada uno o *cm* por centímetro.</span><span class="sxs-lookup"><span data-stu-id="922e7-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="922e7-119">**Descripción**: especifique un nombre descriptivo para la unidad de medida en el idioma del sistema.</span><span class="sxs-lookup"><span data-stu-id="922e7-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="922e7-120">Este nombre suele ser el nombre completo de la unidad, como *Cada uno* o *Centímetro*.</span><span class="sxs-lookup"><span data-stu-id="922e7-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="922e7-121">En la ficha rápida **General**, establezca los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="922e7-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="922e7-122">**Clase de unidad**: seleccione la propiedad que mide la unidad (como longitud, área, masa o cantidad).</span><span class="sxs-lookup"><span data-stu-id="922e7-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="922e7-123">**Sistema de unidades**: seleccione el sistema de medida al que pertenece la unidad (*Unidades metricas* o *Unidades particulares de Estados Unidos*).</span><span class="sxs-lookup"><span data-stu-id="922e7-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="922e7-124">**Unidad base**: establezca esta opción en *Sí* para utilizar la unidad actual como unidad base para su clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="922e7-125">En este caso, solo tiene que especificar el factor de conversión entre la unidad base y cada unidad adicional en la clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="922e7-126">A continuación, el sistema puede convertir entre todas las unidades de esa clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="922e7-127">Por lo tanto, es más fácil configurar conversiones.</span><span class="sxs-lookup"><span data-stu-id="922e7-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="922e7-128">Por ejemplo, si galón es la unidad base para la clase de unidad *Volumen*, solo tiene que configurar los factores de conversión de un cuarto a un galón y de una pinta a un galón.</span><span class="sxs-lookup"><span data-stu-id="922e7-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="922e7-129">Luego, el sistema también puede convertir de un cuarto a una pinta.</span><span class="sxs-lookup"><span data-stu-id="922e7-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="922e7-130">Solo puede tener una unidad base por clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="922e7-131">**Unidad del sistema**: establezca esta opción en *Sí* para utilizar la unidad actual como unidad supuesta para todas las medidas no especificadas de su clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="922e7-132">Por ejemplo, si un campo que se usa para introducir una cantidad no permite especificar una unidad (o si el usuario no selecciona una unidad), el sistema usa la unidad que está configurada como la unidad del sistema para la clase de unidad *Cantidad*.</span><span class="sxs-lookup"><span data-stu-id="922e7-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="922e7-133">Solo puede tener una unidad de sistema por clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="922e7-134">**Precisión decimal**: especifique el número de lugares decimales a los que se deben redondear los valores que se especifican para la unidad actual o que se convierten a ella.</span><span class="sxs-lookup"><span data-stu-id="922e7-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="922e7-135">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="922e7-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="922e7-136">Definición de conversiones de unidades</span><span class="sxs-lookup"><span data-stu-id="922e7-136">Define unit translations</span></span>

<span data-ttu-id="922e7-137">Para definir traducciones para el id. o símbolo y la descripción de una unidad de medida, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="922e7-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="922e7-138">Cree o seleccione la unidad para la que creará traducciones.</span><span class="sxs-lookup"><span data-stu-id="922e7-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="922e7-139">En el panel de acciones, seleccione **Textos de unidades**.</span><span class="sxs-lookup"><span data-stu-id="922e7-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="922e7-140">Aparece la página **Textos de unidades**.</span><span class="sxs-lookup"><span data-stu-id="922e7-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="922e7-141">Utilice esta página para definir traducciones para el id. o símbolo de la unidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="922e7-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="922e7-142">A continuación, esas traducciones se pueden utilizar en documentos externos en idiomas específicos del cliente o del proveedor.</span><span class="sxs-lookup"><span data-stu-id="922e7-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="922e7-143">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="922e7-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="922e7-144">En ell campo **Idioma**, seleccione el idioma al que traducir el id. de unidad o símbolo.</span><span class="sxs-lookup"><span data-stu-id="922e7-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="922e7-145">En el campo **Texto**, introduzca la traducción del id. de la unidad o símbolo en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="922e7-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="922e7-146">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="922e7-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="922e7-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="922e7-147">Close the page.</span></span>
1. <span data-ttu-id="922e7-148">En el **Panel de acciones**, seleccione **Descripciones de unidades convertidas**.</span><span class="sxs-lookup"><span data-stu-id="922e7-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="922e7-149">Aparece la página **Descripciones de unidades traducidas**.</span><span class="sxs-lookup"><span data-stu-id="922e7-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="922e7-150">Utilice esta página para definir descripciones específicas del idioma para la unidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="922e7-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="922e7-151">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="922e7-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="922e7-152">En el campo **Idioma**, seleccione el idioma al que traducir la descripción de la unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="922e7-153">En el campo **Descripción**, introduzca la traducción de la descripción de la unidad en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="922e7-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="922e7-154">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="922e7-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="922e7-155">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="922e7-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="922e7-156">Definición de reglas de conversión de unidades</span><span class="sxs-lookup"><span data-stu-id="922e7-156">Define unit conversion rules</span></span>

<span data-ttu-id="922e7-157">Para definir reglas de conversiones entre unidades de medida, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="922e7-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="922e7-158">Cree o seleccione la unidad para la que definir reglas de conversión.</span><span class="sxs-lookup"><span data-stu-id="922e7-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="922e7-159">En el panel de acciones, seleccione **Conversiones de unidades**.</span><span class="sxs-lookup"><span data-stu-id="922e7-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="922e7-160">Se abrirá la página **Conversiones de unidades**.</span><span class="sxs-lookup"><span data-stu-id="922e7-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="922e7-161">Puede usar esta página para definir reglas para convertir la unidad seleccionada a y desde otras unidades de la clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="922e7-162">Seleccione una de las siguientes pestañas, en función del tipo de conversión que desee configurar:</span><span class="sxs-lookup"><span data-stu-id="922e7-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="922e7-163">**Conversiones estándar**: permite configurar reglas de conversión estándar para todos los productos.</span><span class="sxs-lookup"><span data-stu-id="922e7-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="922e7-164">**Conversiones intraclase**: permite configurar reglas de conversión específicas de producto para unidades de la misma clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="922e7-165">**Conversiones entre clases**: permite configurar reglas de conversión específicas de producto para unidades de todas las clases de unidades.</span><span class="sxs-lookup"><span data-stu-id="922e7-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="922e7-166">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="922e7-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="922e7-167">Para crear una nueva conversión, seleccione **Nueva** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="922e7-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="922e7-168">Para editar una conversión existente, seleccione la conversión en la cuadrícula y luego seleccione **Editar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="922e7-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="922e7-169">En el cuadro de diálogo emergente, establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="922e7-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="922e7-170">**Producto**: seleccione el producto específico al que se aplica la conversión.</span><span class="sxs-lookup"><span data-stu-id="922e7-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="922e7-171">Este campo está disponible solo para conversiones intraclase y entre clases.</span><span class="sxs-lookup"><span data-stu-id="922e7-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="922e7-172">**Diseño de fórmula**: deje este campo configurado en *Sencillo* para especificar una conversión simple que tiene un solo factor.</span><span class="sxs-lookup"><span data-stu-id="922e7-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="922e7-173">Configúrelo en *Avanzado* para configurar una ecuación más compleja.</span><span class="sxs-lookup"><span data-stu-id="922e7-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="922e7-174">El formato de las ecuaciones avanzadas varía según la clase de unidad.</span><span class="sxs-lookup"><span data-stu-id="922e7-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="922e7-175">**De la unidad**: este campo muestra la unidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="922e7-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="922e7-176">Por lo general, no debe cambiarse el valor.</span><span class="sxs-lookup"><span data-stu-id="922e7-176">Usually, you should not change the value.</span></span> <span data-ttu-id="922e7-177">(Si cambia el valor, debe abrir la página **Conversiones de unidades** de la unidad seleccionada para ver su nueva conversión después de guardarla).</span><span class="sxs-lookup"><span data-stu-id="922e7-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="922e7-178">**A la unidad**: seleccione la unidad a la que desea convertir.</span><span class="sxs-lookup"><span data-stu-id="922e7-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="922e7-179">**Redondeo**: seleccione cómo se deben redondear las fracciones, según el valor **Precisión decimal** de la unidad seleccionada (*Al más cercano*, *Superior* o *Inferior*).</span><span class="sxs-lookup"><span data-stu-id="922e7-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="922e7-180">**Fórmula de conversión**: utilice los campos restantes en la parte superior del cuadro de diálogo desplegable para especificar la fórmula de conversión entre las dos unidades.</span><span class="sxs-lookup"><span data-stu-id="922e7-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="922e7-181">Los campos disponibles varían, según la clase de unidad y el diseño de fórmula que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="922e7-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="922e7-182">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="922e7-182">Select **OK**.</span></span>
1. <span data-ttu-id="922e7-183">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="922e7-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="922e7-184">También puede configurar conversiones de unidades por variante de producto.</span><span class="sxs-lookup"><span data-stu-id="922e7-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="922e7-185">Para más información, consulte [Conversión de unidad de medida por variante del producto](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="922e7-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
