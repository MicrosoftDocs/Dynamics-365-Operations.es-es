---
title: Implementar campos personalizados para la aplicación móvil de Microsoft Dynamics 365 Project Timesheet en iOS y Android
description: Este tema proporciona los patrones comunes para usar extensiones para implementar campos personalizados.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 4343c875da05641c57b7784bf52f1c814dd26d20
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "1618005"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="10137-103">Implementar campos personalizados para la aplicación móvil de Microsoft Dynamics 365 Project Timesheet en iOS y Android</span><span class="sxs-lookup"><span data-stu-id="10137-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10137-104">Este tema proporciona los patrones comunes para usar extensiones para implementar campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="10137-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="10137-105">Se cubren los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="10137-105">The following topics are covered:</span></span>

- <span data-ttu-id="10137-106">Los distintos tipos de datos que el marco de campos personalizados admite</span><span class="sxs-lookup"><span data-stu-id="10137-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="10137-107">Cómo mostrar campos de sólo lectura o editables en entradas de hoja de horas y guardar valores proporcionados por el usuario en la base de datos</span><span class="sxs-lookup"><span data-stu-id="10137-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="10137-108">Cómo mostrar campos de sólo lectura en el encabezado de la hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="10137-109">Cómo integrar la otra lógica de negocios personalizada para especificar los valores predeterminados en los campos y emitir la validación adicional</span><span class="sxs-lookup"><span data-stu-id="10137-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="10137-110">Audiencia</span><span class="sxs-lookup"><span data-stu-id="10137-110">Audience</span></span>

<span data-ttu-id="10137-111">Este tema se ha creado para los desarrolladores que están integrando sus campos personalizados en la aplicación móvil Microsoft Dynamics 365 Project Timesheet que está disponible para Apple iOS y Google Android.</span><span class="sxs-lookup"><span data-stu-id="10137-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="10137-112">Se asume que el lector está familiarizado con el desarrollo en X++ y la funcionalidad de la hoja de horas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="10137-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="10137-113">Contrato de datos – Clase de X++ TSTimesheetCustomField</span><span class="sxs-lookup"><span data-stu-id="10137-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="10137-114">La clase **TSTimesheetCustomField** es la clase de contrato de datos de X++ que representa información sobre un campo personalizado para la funcionalidad de la hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="10137-115">Las listas de los objetos de campos personalizados se aplican en el contrato de datos de TSTimesheetDetails y el contrato de datos de TSTimesheetEntry para mostrar campos personalizados en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="10137-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="10137-116">**TSTimesheetDetails** - El contrato de encabezado de hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="10137-117">**TSTimesheetEntry** - El contrato de la transacción de la hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="10137-118">Grupos de estos objetos con la misma información de proyecto y valor **timesheetLineRecId** constituyen una línea.</span><span class="sxs-lookup"><span data-stu-id="10137-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="10137-119">fieldBaseType (tipos)</span><span class="sxs-lookup"><span data-stu-id="10137-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="10137-120">La propiedad **FieldBaseType** en el objeto **TsTimesheetCustom** determina el tipo de campo que aparece en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="10137-121">Los valores **Tipos** siguientes se admiten.</span><span class="sxs-lookup"><span data-stu-id="10137-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="10137-122">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="10137-122">Types value</span></span> | <span data-ttu-id="10137-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="10137-123">Type</span></span>              | <span data-ttu-id="10137-124">Notas</span><span class="sxs-lookup"><span data-stu-id="10137-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="10137-125">0</span><span class="sxs-lookup"><span data-stu-id="10137-125">0</span></span>           | <span data-ttu-id="10137-126">Cadena (y Enum)</span><span class="sxs-lookup"><span data-stu-id="10137-126">String (and Enum)</span></span> | <span data-ttu-id="10137-127">El campo aparece como campo de texto.</span><span class="sxs-lookup"><span data-stu-id="10137-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="10137-128">1</span><span class="sxs-lookup"><span data-stu-id="10137-128">1</span></span>           | <span data-ttu-id="10137-129">Entero</span><span class="sxs-lookup"><span data-stu-id="10137-129">Integer</span></span>           | <span data-ttu-id="10137-130">El valor se muestra como número sin decimales.</span><span class="sxs-lookup"><span data-stu-id="10137-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="10137-131">2</span><span class="sxs-lookup"><span data-stu-id="10137-131">2</span></span>           | <span data-ttu-id="10137-132">Real</span><span class="sxs-lookup"><span data-stu-id="10137-132">Real</span></span>              | <span data-ttu-id="10137-133">El valor se muestra como número que tiene decimales.</span><span class="sxs-lookup"><span data-stu-id="10137-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="10137-134">Para mostrar el valor real como divisa en la aplicación, use la propiedad **fieldExtenededType**.</span><span class="sxs-lookup"><span data-stu-id="10137-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="10137-135">Puede utilizar la propiedad **numberOfDecimals** para establecer el número de decimales que se muestran.</span><span class="sxs-lookup"><span data-stu-id="10137-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="10137-136">3</span><span class="sxs-lookup"><span data-stu-id="10137-136">3</span></span>           | <span data-ttu-id="10137-137">Fecha</span><span class="sxs-lookup"><span data-stu-id="10137-137">Date</span></span>              | <span data-ttu-id="10137-138">Los formatos de fecha son determinados por la configuración **Fecha, horas y formato de número** del usuario que se especifica en **Idioma y preferencia del país/región** en **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="10137-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="10137-139">4</span><span class="sxs-lookup"><span data-stu-id="10137-139">4</span></span>           | <span data-ttu-id="10137-140">Booleano</span><span class="sxs-lookup"><span data-stu-id="10137-140">Boolean</span></span>           | |
| <span data-ttu-id="10137-141">15</span><span class="sxs-lookup"><span data-stu-id="10137-141">15</span></span>          | <span data-ttu-id="10137-142">GUID</span><span class="sxs-lookup"><span data-stu-id="10137-142">GUID</span></span>              | |
| <span data-ttu-id="10137-143">16</span><span class="sxs-lookup"><span data-stu-id="10137-143">16</span></span>          | <span data-ttu-id="10137-144">Int64</span><span class="sxs-lookup"><span data-stu-id="10137-144">Int64</span></span>             | |

- <span data-ttu-id="10137-145">Si la propiedad **stringOptions** no se proporciona en el objeto **TSTimesheetCustomField**, un campo de texto libre se proporciona al usuario.</span><span class="sxs-lookup"><span data-stu-id="10137-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="10137-146">La propiedad **stringLength** se puede usar para establecer la longitud máxima de la cadena que los usuarios pueden especificar.</span><span class="sxs-lookup"><span data-stu-id="10137-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="10137-147">Si la propiedad **stringOptions** se proporciona en el objeto **TSTimesheetCustomField**, estos elementos de la lista son los únicos valores que los usuarios pueden seleccionar mediante los botones de opción (botones de opción).</span><span class="sxs-lookup"><span data-stu-id="10137-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="10137-148">En este caso, el campo de la cadena puede actuar como valor de la enumeración con el fin de entrada de usuario.</span><span class="sxs-lookup"><span data-stu-id="10137-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="10137-149">Para guardar la configuración a la base de datos como enumeración, asigne manualmente el valor de la cadena de nuevo al valor de la enumeración antes de guardar a la base de datos mediante cadena de mando (consulte “Usar la cadena de mando de la clase de TSTimesheetEntryService para guardar una entrada de hoja de horas de la aplicación de nuevo la sección es la base de datos” más adelante en este tema para un ejemplo).</span><span class="sxs-lookup"><span data-stu-id="10137-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="10137-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="10137-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="10137-151">Puede usar esta propiedad para dar formato a valores reales como divisas.</span><span class="sxs-lookup"><span data-stu-id="10137-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="10137-152">Este enfoque es aplicable si el valor **fieldBaseType** es **Real**.</span><span class="sxs-lookup"><span data-stu-id="10137-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="10137-153">**TSCustomFieldExtendedType: Ninguno** - No se aplica ningún formato.</span><span class="sxs-lookup"><span data-stu-id="10137-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="10137-154">**TSCustomFieldExtendedType::Divisa** - Da formato el valor como divisa.</span><span class="sxs-lookup"><span data-stu-id="10137-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="10137-155">Cuando el formato de la divisa está activo, el campo **stringValue** puede ser correcto utilizado el código de divisa que se debe mostrar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="10137-156">El valor es un valor de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="10137-156">The value is a read-only value.</span></span>

    <span data-ttu-id="10137-157">El campo **realValue** contiene el importe de dinero que se debe guardar en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10137-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="10137-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="10137-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="10137-159">Puede usar esta propiedad para especificar dónde el campo personalizado debe aparecer en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="10137-160">**TSCustomFieldSection::Encabezado** - El campo aparecerá en la sección **Ver más detalles** en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="10137-161">Estos campos son siempre de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="10137-161">These fields are always read-only.</span></span>
- <span data-ttu-id="10137-162">**TSCustomFieldSection::Línea** - El campo aparecerá después de todos los campos línea del componente estándar en entradas de la hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="10137-163">Estos campos pueden ser editables o de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="10137-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="10137-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="10137-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="10137-165">Esta propiedad identifica el campo cuando los valores que la aplicación proporciona se guardan de nuevo a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10137-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="10137-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="10137-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="10137-167">Esta propiedad identifica el campo cuando los valores que la aplicación proporciona se guardan de nuevo a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10137-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="10137-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="10137-168">isEditable (NoYes)</span></span>

<span data-ttu-id="10137-169">Establezca esta propiedad en **Sí** para especificar que el campo en la sección de la entrada de hoja de horas debe ser editables los usuarios.</span><span class="sxs-lookup"><span data-stu-id="10137-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="10137-170">Establezca la propiedad en **No** para crear el campo de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="10137-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="10137-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="10137-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="10137-172">Establezca esta propiedad en **Sí** para especificar que el campo en la sección de la entrada de hoja de horas debe ser obligatorio.</span><span class="sxs-lookup"><span data-stu-id="10137-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="10137-173">label (str)</span><span class="sxs-lookup"><span data-stu-id="10137-173">label (str)</span></span>

<span data-ttu-id="10137-174">Esta propiedad especifica la etiqueta que se muestra junto al campo en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="10137-175">stringOptions (lista de cadenas)</span><span class="sxs-lookup"><span data-stu-id="10137-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="10137-176">Esta propiedad solo es aplicable si **fieldBaseType** se establece en **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="10137-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="10137-177">Si se establece **stringOptions**, los valores de cadena disponibles para la selección mediante los botones de opción (botones de opción) son especificados por las cadenas en la lista.</span><span class="sxs-lookup"><span data-stu-id="10137-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="10137-178">Si no se proporciona ninguna cadena, se permite introducir texto libre en el campo cadena (consulte “Usar la cadena de mando de la clase de TSTimesheetEntryService para guardar una entrada de hoja de horas de la aplicación de nuevo la sección es la base de datos” más adelante en este tema para un ejemplo).</span><span class="sxs-lookup"><span data-stu-id="10137-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="10137-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="10137-179">stringLength (int)</span></span>

<span data-ttu-id="10137-180">Esta propiedad especifica la longitud máxima para un campo cadena.</span><span class="sxs-lookup"><span data-stu-id="10137-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="10137-181">Solo es aplicable si **fieldBaseType** se establece en **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="10137-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="10137-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="10137-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="10137-183">Esta propiedad especifica el número de decimales que se muestran para un campo real.</span><span class="sxs-lookup"><span data-stu-id="10137-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="10137-184">Solo es aplicable si **fieldBaseType** se establece en **Real**.</span><span class="sxs-lookup"><span data-stu-id="10137-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="10137-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="10137-185">orderSequence (int)</span></span>

<span data-ttu-id="10137-186">Esta propiedad controla el orden en que los campos personalizados se muestran en la aplicación cuando se especifica más de un campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="10137-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="10137-187">Los campos que tienen números menores se muestran primero.</span><span class="sxs-lookup"><span data-stu-id="10137-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="10137-188">booleanValue (booleano)</span><span class="sxs-lookup"><span data-stu-id="10137-188">booleanValue (boolean)</span></span>

<span data-ttu-id="10137-189">Para los campos de tipo **Booleano**, esta propiedad pasa el valor booleano del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="10137-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="10137-190">guidValue (guid)</span></span>

<span data-ttu-id="10137-191">Para los campos de tipo **GUID**, esta propiedad pasa el valor identificador único global (GUID) del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="10137-192">int64Value (int64)</span><span class="sxs-lookup"><span data-stu-id="10137-192">int64Value (int64)</span></span>

<span data-ttu-id="10137-193">Para los campos de tipo **Int64**, esta propiedad pasa el valor int64 del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="10137-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="10137-194">intValue (int)</span></span>

<span data-ttu-id="10137-195">Para los campos de tipo **Int**, esta propiedad pasa el valor int del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="10137-196">realValue (real)</span><span class="sxs-lookup"><span data-stu-id="10137-196">realValue (real)</span></span>

<span data-ttu-id="10137-197">Para los campos de tipo **Real**, esta propiedad pasa el valor real del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="10137-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="10137-198">stringValue (str)</span></span>

<span data-ttu-id="10137-199">Para los campos de tipo **Cadena**, esta propiedad pasa el valor cadena del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="10137-200">También se usa para los campos del tipo **Real** que se aplican el formato como divisa.</span><span class="sxs-lookup"><span data-stu-id="10137-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="10137-201">Para estos campos, la propiedad se usa para pasar el código de divisa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="10137-202">dateValue (fecha)</span><span class="sxs-lookup"><span data-stu-id="10137-202">dateValue (date)</span></span>

<span data-ttu-id="10137-203">Para los campos de tipo **Fecha**, esta propiedad pasa el valor fecha del campo entre el servidor y la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="10137-204">Muestra y guardar un campo personalizado en la sección de la entrada de hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="10137-205">Abajo aparece una captura de pantalla de la aplicación móvil de una creación de la entrada de hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="10137-206">Muestra los campos del componente estándar y un campo personalizado en la sección “Entrada de tiempo” llamado "Cadena de prueba" con un valor de enumeración "Segunda opción" ya establecido.</span><span class="sxs-lookup"><span data-stu-id="10137-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Campo personalizado de la cadena de prueba en la aplicación](media/timesheet-entry.jpg)



<span data-ttu-id="10137-208">Abajo aparece una captura de pantalla de la aplicación móvil del usuario que selecciona una de las opciones de la enumeración disponibles para el campo personalizado "Cadena de prueba".</span><span class="sxs-lookup"><span data-stu-id="10137-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="10137-209">Las dos opciones son “Primera opción “y “Segunda opción” y aparecen como botones de opción.</span><span class="sxs-lookup"><span data-stu-id="10137-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="10137-210">La segunda opción está seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="10137-210">The second option is currently selected.</span></span>

![Botones de opción (botones de opción) para el campo personalizado de la cadena de la prueba](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="10137-212">Extiende la tabla de TSTimesheetLine de modo que tiene un campo personalizado</span><span class="sxs-lookup"><span data-stu-id="10137-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="10137-213">En situaciones habituales, es probable que los datos de un campo personalizado en la sección de la entrada de hoja de horas son se guarden en la tabla de TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="10137-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="10137-214">Sin embargo, otras tablas se pueden usar si los datos se pueden recuperar según un registro de TSTimesheetTrans que se proporcione, o si no tiene contexto de registro determinado (por ejemplo, si el campo está establecido como de sólo lectura en los parámetros de proyecto).</span><span class="sxs-lookup"><span data-stu-id="10137-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="10137-215">Tenga en cuenta que los campos personalizados no tienen que tener ningún registros de la base de datos de respaldo.</span><span class="sxs-lookup"><span data-stu-id="10137-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="10137-216">Pueden ser generados dinámicamente en función de la lógica de X++.</span><span class="sxs-lookup"><span data-stu-id="10137-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="10137-217">Este enfoque puede ser útil en escenarios de sólo lectura (consulte “Usar la cadena de mando de la clase de TSTimesheetDetails, el método de buildCustomFieldListForHeader para completar la sección de los detalles de la hoja de horas” para un ejemplo de los valores de forma dinámica generados de campos personalizados.)</span><span class="sxs-lookup"><span data-stu-id="10137-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="10137-218">Abajo aparece una captura de pantalla Visual Studio del árbol de objetos de aplicación (AOT).</span><span class="sxs-lookup"><span data-stu-id="10137-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="10137-219">Muestra una extensión de la tabla de TSTimesheetLine con el campo de TestLineString agregado como campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="10137-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Cadena de la línea](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="10137-221">Cadena de mando del método de buildCustomFieldList de la clase de TSTimesheetSettings para mostrar un campo en la sección de la entrada de hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="10137-222">Este código controla los valores de visualización del campo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="10137-223">Por ejemplo, controla el tipo de campo, la etiqueta, si el campo es obligatorio y en qué sección el campo aparece.</span><span class="sxs-lookup"><span data-stu-id="10137-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="10137-224">El siguiente ejemplo muestra entradas de un campo de la cadena en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="10137-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="10137-225">Este campo tiene dos opciones, **Primera opción** y **Segunda opción**, que están disponibles mediante los botones de opción (botones de opción).</span><span class="sxs-lookup"><span data-stu-id="10137-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="10137-226">El campo de la aplicación está asociado al campo **TestLineString** que se agrega a la tabla de TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="10137-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="10137-227">Tega en cuenta el uso del método **TSTimesheetCustomField::(newFromMetatdata)** para simplificar la inicialización de las propiedades del campo personalizado: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** y **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="10137-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="10137-228">También puede definir los parámetros manualmente, como prefiera.</span><span class="sxs-lookup"><span data-stu-id="10137-228">You can also set these parameters manually, as you prefer.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="10137-229">Cadena de mando del método de buildCustomFieldListForEntry de la clase de TSTimesheetEntry para introducir valores en la entrada de hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="10137-230">El método **buildCustomFieldListForEntry** se utiliza para especificar los valores en las líneas de hoja de horas guardadas en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="10137-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="10137-231">Toma un registro de TSTimesheetTrans como parámetro.</span><span class="sxs-lookup"><span data-stu-id="10137-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="10137-232">Los campos de ese registro se pueden usar para completar el valor del campo personalizado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="10137-233">Usar la cadena de mando de la clase de TSTimesheetEntryService para guardar una entrada de hoja de horas de la aplicación de nuevo a la base de datos</span><span class="sxs-lookup"><span data-stu-id="10137-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="10137-234">Para guardar un campo personalizado de nuevo a la base de datos en uso habitual, debe extender varios métodos:</span><span class="sxs-lookup"><span data-stu-id="10137-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="10137-235">El método **el timesheetLineNeedsUpdating** se usa para determinar si el usuario de la aplicación ha cambiado registro de la línea y se debe guardar en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10137-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="10137-236">Si el rendimiento no es una preocupación, este método puede ser simplificado de modo que devuelva siempre **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="10137-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="10137-237">Los métodos **populateTimesheetLineFromEntryDuringCreate** y **populateTimesheetLineFromEntryDuringUpdate** se pueden ampliar de modo que especifiquen valores en el registro de base de datos de TSTimesheetLine de registro de contrato de datos de TSTimesheetEntry que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="10137-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="10137-238">En el ejemplo siguiente, note cómo la asignación entre el campo de base de datos y el campo de entrada se hace manualmente mediante código X++.</span><span class="sxs-lookup"><span data-stu-id="10137-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="10137-239">El método **populateTimesheetWeekFromEntry** también se puede extender si el campo personalizado asignado al objeto **TSTimesheetEntry** debe escribir de nuevo a la tabla de base de datos de TSTimesheetLineweek.</span><span class="sxs-lookup"><span data-stu-id="10137-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="10137-240">El siguiente ejemplo guarda el **firstOption** o el valor **secondOption** que el usuario selecciona a la base de datos como valor de cadena sin formato.</span><span class="sxs-lookup"><span data-stu-id="10137-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="10137-241">Si el campo de base de datos es un campo del tipo **Enum**, estos valores pueden asignarse manualmente a un valor de enumeración y luego guardar un campo de la enumeración en la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="10137-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="10137-242">Muestra un campo personalizado en la sección del encabezado de hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="10137-243">Abajo aparece una captura de pantalla de la aplicación de un usuario viendo una hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="10137-244">El botón de “Más información” se ha seleccionado en la esquina superior derecha para mostrar la opción “Ver más detalles".</span><span class="sxs-lookup"><span data-stu-id="10137-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![Comando Ver más detalles](media/show-more.png)



<span data-ttu-id="10137-246">Abajo aparece una captura de pantalla de la aplicación mostrando la sección "Más" de una hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="10137-247">Un campo personalizado denominado “Tasa de utilización de esta hoja de horas (campo personalizado calculado)” se ha agregado a la sección de encabezado de hoja de horas.</span><span class="sxs-lookup"><span data-stu-id="10137-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="10137-248">Un valor de sólo lectura de “0,667 " se establece en el campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="10137-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Sección Más](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="10137-250">Extiende la tabla de TSTimesheetTable de modo que tiene un campo personalizado</span><span class="sxs-lookup"><span data-stu-id="10137-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="10137-251">En situaciones habituales, es probable que los datos de un campo personalizado en la sección del encabezado de hoja de horas se extraigan de la tabla TSTimesheetHeader.</span><span class="sxs-lookup"><span data-stu-id="10137-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="10137-252">Sin embargo, otras tablas se pueden usar si los datos se pueden recuperar según un registro de TSTimesheetTable que se proporcione, o si no tiene contexto de registro determinado (por ejemplo, si el campo está establecido como de sólo lectura en los parámetros de proyecto).</span><span class="sxs-lookup"><span data-stu-id="10137-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="10137-253">Tenga en cuenta que los campos personalizados no tienen que tener ningún registros de la base de datos de respaldo.</span><span class="sxs-lookup"><span data-stu-id="10137-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="10137-254">Pueden ser generados dinámicamente en función de la lógica de X++.</span><span class="sxs-lookup"><span data-stu-id="10137-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="10137-255">El siguiente ejemplo muestra este planteamiento.</span><span class="sxs-lookup"><span data-stu-id="10137-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="10137-256">Los campos de la sección de encabezado son siempre de sólo lectura en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="10137-257">Usar la cadena de mando del método de buildCustomFieldList de la clase de TSTimesheetSettings para mostrar un campo en la sección del encabezado.</span><span class="sxs-lookup"><span data-stu-id="10137-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="10137-258">Este código controla los valores de visualización del campo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="10137-259">Por ejemplo, controla el tipo de campo, la etiqueta, si el campo es obligatorio y en qué sección el campo aparece.</span><span class="sxs-lookup"><span data-stu-id="10137-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="10137-260">El ejemplo siguiente muestra un valor calculado en la sección de encabezado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-260">The following example shows a computed value in the header section in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="10137-261">Cadena de mando del método de buildCustomFieldListForHeader de la clase de TSTimesheetDetails para rellenar los detalles de la hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="10137-262">El método **buildCustomFieldListForHeader** se utiliza para rellenar los valores del encabezado en la hoja de horas en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="10137-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="10137-263">Toma un registro de TSTimesheetTable como parámetro.</span><span class="sxs-lookup"><span data-stu-id="10137-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="10137-264">Los campos de ese registro se pueden usar para completar el valor del campo personalizado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="10137-265">El siguiente ejemplo no lee ningún valor de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10137-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="10137-266">En su lugar, usa lógica X++ para generar un valor calculado que se muestre en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10137-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="10137-267">Otras oportunidades de la flexibilidad de configuración o la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="10137-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="10137-268">Agregar una validación adicional para la aplicación</span><span class="sxs-lookup"><span data-stu-id="10137-268">Adding additional validation for the app</span></span>

<span data-ttu-id="10137-269">La lógica existente para la funcionalidad de la hoja de horas en el nivel de la base de datos aún funcionará como esperado.</span><span class="sxs-lookup"><span data-stu-id="10137-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="10137-270">Para suspender la finalización de guardar o enviar operaciones y mostrar un mensaje de error específico, puede agregar **error de captura (“mensaje para el usuario”)** al código mediante una extensión de la cadena de mando.</span><span class="sxs-lookup"><span data-stu-id="10137-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="10137-271">Aquí tiene tres ejemplos de métodos de extensión útiles:</span><span class="sxs-lookup"><span data-stu-id="10137-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="10137-272">Si **validateWrite** en la tabla de TSTimesheetLine devuelve **falso** durante una operación de guardado para una línea de hoja de horas, un mensaje de error se muestra en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="10137-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="10137-273">Si **validateSubmit** en la tabla de TSTimesheetTable devuelve **falso** durante el envío de una hoja de horas en la aplicación, un mensaje de error se muestra al usuario.</span><span class="sxs-lookup"><span data-stu-id="10137-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="10137-274">La lógica que complete campos (por ejemplo, **Propiedad de línea**) durante el método **inserción** en la tabla de TSTimesheetLine se ejecutará de todas formas.</span><span class="sxs-lookup"><span data-stu-id="10137-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="10137-275">Ocultar y marcar componente estándar como los campos de sólo lectura a través de la configuración</span><span class="sxs-lookup"><span data-stu-id="10137-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="10137-276">De los parámetros de proyecto, puede crear campos del componente estándar de sólo lectura o ocultarán en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="10137-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="10137-277">Establezca las opciones de la sección **Hojas de horas móviles** en la pestaña **Hoja de horas** de la página **Gestión de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="10137-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Parámetros del proyecto](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="10137-279">Cambiando las actividades disponibles para la selección a través de extensiones</span><span class="sxs-lookup"><span data-stu-id="10137-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="10137-280">Las actividades disponibles para la selección de un proyecto se completan a través de los métodos **(getActivitiesForProject)** y **(getActivityQuery)** en la clase **TsTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="10137-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="10137-281">Puede usar la cadena de mando para cambiar este comportamiento para coincidir con su escenario empresarial para las actividades que están disponibles para la selección para un proyecto específico.</span><span class="sxs-lookup"><span data-stu-id="10137-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="10137-282">Especificación de una categoría de proyecto predeterminada en entradas de la hoja de horas</span><span class="sxs-lookup"><span data-stu-id="10137-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="10137-283">Escribir una categoría de proyecto predeterminada en entradas de la hoja de horas tiene lugar a tres niveles.</span><span class="sxs-lookup"><span data-stu-id="10137-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="10137-284">Puede usar la cadena de mando para ampliar el comportamiento en cualquiera de estos niveles para lograr el comportamiento deseado.</span><span class="sxs-lookup"><span data-stu-id="10137-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="10137-285">Se usa la siguiente jerarquía:</span><span class="sxs-lookup"><span data-stu-id="10137-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="10137-286">La aplicación intenta poner la categoría predeterminada del recurso del proyecto.</span><span class="sxs-lookup"><span data-stu-id="10137-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="10137-287">Esta categoría predeterminada se establece en los métodos **getCurrentUserResource** y **getDelegatedResourcesForCurrentUser** en la clase **TSTimesheetSettingsService**.</span><span class="sxs-lookup"><span data-stu-id="10137-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="10137-288">Si la categoría predeterminada no se proporciona en el nivel del recurso del proyecto, la aplicación intentará extraerlo de la actividad de proyecto.</span><span class="sxs-lookup"><span data-stu-id="10137-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="10137-289">Esta categoría predeterminada se configura en el método **getActivitiesForProject** en la clase **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="10137-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="10137-290">Si la categoría predeterminada no se proporciona en el nivel de actividad del proyecto, la categoría predeterminada se tomará de los parámetros del proyecto.</span><span class="sxs-lookup"><span data-stu-id="10137-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="10137-291">Esta categoría predeterminada se configura en el método **getProjectDetailsbyRule** en la clase **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="10137-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>
