---
title: Diseño de enrutamiento de documentos para matrículas de entidad
description: Este tema describe cómo usar métodos de formato para imprimir valores en etiquetas.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 8c96aef5d66ed8f8c44d74eee9b60f0a7d38a46d
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017722"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="c7cb8-103">Diseño de enrutamiento de documentos para matrículas de entidad</span><span class="sxs-lookup"><span data-stu-id="c7cb8-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7cb8-104">El diseño de enrutamiento del documento define el diseño de las etiquetas de las matrículas y los datos que se imprimen en ellas.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="c7cb8-105">Configure los puntos de activación de impresión cuando configure elementos de menú del dispositivo móvil y plantillas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="c7cb8-106">En un escenario típico, los empleados de recepción del almacén imprimen las etiquetas de las matrículas inmediatamente después de registrar el contenido de las paletas que llegan al área de recepción.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="c7cb8-107">Las etiquetas físicas se aplican a los pallets.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="c7cb8-108">Después se pueden usar para la validación como parte del proceso de almacenamiento que sigue y futuras operaciones de picking saliente.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="c7cb8-109">Puede imprimir etiquetas muy complejas, siempre que el dispositivo de impresión pueda interpretar el texto que se le envía.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="c7cb8-110">Por ejemplo, un diseño de Lenguaje de programación de cebra (ZPL) que incluye un código de barras podría parecerse al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

<span data-ttu-id="c7cb8-111">Como parte del proceso de impresión de etiquetas, el texto `$LicensePlateId$` en este ejemplo será reemplazado con un valor de datos.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="c7cb8-112">Para ver los valores que se imprimirán, vaya a **Gestión de almacenes \> Consultas e informes \> Etiquetas de matrícula de entidad**.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="c7cb8-113">Varias herramientas de generación de etiquetas ampliamente disponibles pueden ayudarlo a formatear el texto para el diseño de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="c7cb8-114">Muchas de estas herramientas son compatibles con el formato `$FieldName$`.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="c7cb8-115">Además, Microsoft Dynamics 365 Supply Chain Management utiliza una lógica de formato especial como parte de la asignación de campo para el diseño de enrutamiento de documentos.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="c7cb8-116">Formatos de números personalizados</span><span class="sxs-lookup"><span data-stu-id="c7cb8-116">Custom number formats</span></span>

<span data-ttu-id="c7cb8-117">Puede personalizar el formato de los valores de campo numéricos que se imprimen utilizando códigos que tengan el siguiente formato.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-117">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="c7cb8-118">A continuación aparece una explicación de este formato:</span><span class="sxs-lookup"><span data-stu-id="c7cb8-118">Here is an explanation of this format:</span></span>

- <span data-ttu-id="c7cb8-119">`FieldName` es el nombre del campo de datos (como **Cantidad** ).</span><span class="sxs-lookup"><span data-stu-id="c7cb8-119">`FieldName` is the name of the data field (such as **Qty** ).</span></span>
- <span data-ttu-id="c7cb8-120">`FormatString` define cómo se deben imprimir los datos.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-120">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="c7cb8-121">Los siguientes ejemplos muestran cómo puede personalizar el campo cantidad de trabajo ( **Cantidad** ):</span><span class="sxs-lookup"><span data-stu-id="c7cb8-121">The following examples show how you can customize the work quantity ( **Qty** ) field:</span></span>

- <span data-ttu-id="c7cb8-122">Para mostrar siempre cuatro dígitos (usando ceros como marcadores de posición), use `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-122">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="c7cb8-123">Por ejemplo, si la cantidad es 10, la etiqueta mostrará "0010".</span><span class="sxs-lookup"><span data-stu-id="c7cb8-123">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="c7cb8-124">Para mostrar siempre dos lugares decimales, use `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-124">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="c7cb8-125">Por ejemplo, si la cantidad es 10, la etiqueta mostrará "10,00".</span><span class="sxs-lookup"><span data-stu-id="c7cb8-125">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="c7cb8-126">Para obtener una lista completa de las cadenas de formato de número disponibles, vea [Cadenas de formato numérico personalizado](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="c7cb8-126">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="c7cb8-127">Formatos de cadena personalizados</span><span class="sxs-lookup"><span data-stu-id="c7cb8-127">Custom string formats</span></span>

<span data-ttu-id="c7cb8-128">Puede eliminar los primeros caracteres de una cadena utilizando el siguiente campo y código de formato.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-128">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="c7cb8-129">Aquí, `#` especifica el número de caracteres que se omitirán.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-129">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="c7cb8-130">Por ejemplo, para imprimir un número de matrícula de entidad de almacén de código de contenedor de envío en serie (SSCC) que no incluye los dos primeros caracteres, use `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-130">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="c7cb8-131">En este caso, la matrícula de entidad de almacén 0011111111111222221 se imprimirá como "11111111111222221".</span><span class="sxs-lookup"><span data-stu-id="c7cb8-131">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="c7cb8-132">Formatos de fecha / hora personalizados</span><span class="sxs-lookup"><span data-stu-id="c7cb8-132">Custom date/time formats</span></span>

<span data-ttu-id="c7cb8-133">El siguiente ejemplo muestra cómo puede controlar el formato que se utiliza para imprimir fechas.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-133">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="c7cb8-134">En este ejemplo, la fecha 30 de abril de 2020 se imprimirá como "30-04-2020".</span><span class="sxs-lookup"><span data-stu-id="c7cb8-134">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="c7cb8-135">Para obtener una lista completa de las formatos de fecha / hora disponibles, vea [Cadenas de formato de fecha y personalizadas](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="c7cb8-135">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="c7cb8-136">Imprima líneas individuales a partir de datos multilínea</span><span class="sxs-lookup"><span data-stu-id="c7cb8-136">Print individual lines from multiline data</span></span>

<span data-ttu-id="c7cb8-137">Si un campo de datos contiene varias líneas (es decir, líneas que están separadas por saltos de línea), puede imprimir una línea individual utilizando el siguiente formato.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-137">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="c7cb8-138">Aquí, `#` es el número de línea que desea imprimir.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-138">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="c7cb8-139">(Use 1 para la primera línea).</span><span class="sxs-lookup"><span data-stu-id="c7cb8-139">(Use 1 for the first line.)</span></span>

<span data-ttu-id="c7cb8-140">Por ejemplo, su sistema tiene un campo `AdditionalAddress` que almacena la siguiente dirección multilínea:</span><span class="sxs-lookup"><span data-stu-id="c7cb8-140">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="c7cb8-141">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-141">Contoso Inc.</span></span>  
<span data-ttu-id="c7cb8-142">123 Nombre de la calle</span><span class="sxs-lookup"><span data-stu-id="c7cb8-142">123 Street Name</span></span>  
<span data-ttu-id="c7cb8-143">Alguna ciudad, algún estado</span><span class="sxs-lookup"><span data-stu-id="c7cb8-143">Some City, Some State</span></span>

<span data-ttu-id="c7cb8-144">Puede imprimir esta dirección, una línea a la vez, utilizando los siguientes códigos.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-144">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="c7cb8-145">Código</span><span class="sxs-lookup"><span data-stu-id="c7cb8-145">Code</span></span> | <span data-ttu-id="c7cb8-146">Texto impreso</span><span class="sxs-lookup"><span data-stu-id="c7cb8-146">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="c7cb8-147">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-147">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="c7cb8-148">123 Nombre de la calle</span><span class="sxs-lookup"><span data-stu-id="c7cb8-148">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="c7cb8-149">Alguna ciudad, algún estado</span><span class="sxs-lookup"><span data-stu-id="c7cb8-149">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="c7cb8-150">Imprima y formatee desde un método de visualización</span><span class="sxs-lookup"><span data-stu-id="c7cb8-150">Print and format from a display method</span></span>

<span data-ttu-id="c7cb8-151">Puede imprimir desde un método de visualización utilizando el siguiente formato.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-151">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="c7cb8-152">Puede combinar este formato con otros tipos que se describieron anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-152">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="c7cb8-153">Por ejemplo, tiene un método de visualización que se denomina `DisplayListOfItemsNumbers()`, y desea imprimir el primer número de elemento de este método.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-153">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="c7cb8-154">En este caso, puede usar el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c7cb8-154">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="c7cb8-155">Más información sobre cómo imprimir etiquetas</span><span class="sxs-lookup"><span data-stu-id="c7cb8-155">More information about how to print labels</span></span>

<span data-ttu-id="c7cb8-156">Para obtener más información sobre cómo configurar e imprimir etiquetas, vea [Habilitar la impresión de etiquetas de matrículas](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="c7cb8-156">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>
