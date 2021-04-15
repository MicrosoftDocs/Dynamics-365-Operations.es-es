---
title: Diseñe configuraciones de ER para suprimir caracteres BOM en archivos generados
description: Este tema explica cómo configurar un formato de informes electrónicos (ER) para generar informes que suprimen los caracteres de marca BOM.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fabc308b1b0682c6fdce3e81e7335417846bebd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743542"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="df60c-103">Diseñe configuraciones de ER para suprimir caracteres BOM en archivos generados</span><span class="sxs-lookup"><span data-stu-id="df60c-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df60c-104">Puede diseñar una [solución](er-quick-start1-new-solution.md) de [Informes electrónicos (ER)](general-electronic-reporting.md) para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="df60c-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="df60c-105">Para generar los documentos como archivos de texto o XML, la solución debe incluir una [configuración](general-electronic-reporting.md#Configuration) ER que contiene un componente en [formato](general-electronic-reporting.md#FormatComponentOutbound) ER.</span><span class="sxs-lookup"><span data-stu-id="df60c-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="df60c-106">Para especificar la [codificación de caracteres](https://docs.microsoft.com/windows/win32/intl/character-sets) que representa el conjunto de caracteres en archivos generados, el formato ER debe contener el elemento de formato **Común\\Archivo**.</span><span class="sxs-lookup"><span data-stu-id="df60c-106">To specify the [character encoding](https://docs.microsoft.com/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="df60c-107">Para configurar el componente de formato ER, abra la versión [borrador](general-electronic-reporting.md#component-versioning) de la configuración ER creada en el diseñador de formato ER y añada el elemento **Común\\Archivo**.</span><span class="sxs-lookup"><span data-stu-id="df60c-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="df60c-108">En el campo **Codificación**, especifique la codificación de los archivos salientes que se generan en tiempo de ejecución mediante este componente.</span><span class="sxs-lookup"><span data-stu-id="df60c-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="df60c-109">Si el formato contiene un nombre de codificación incorrecto, se genera un error al guardar los cambios en la configuración del formato.</span><span class="sxs-lookup"><span data-stu-id="df60c-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Agregar un elemento raíz en la página del diseñador de formato](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="df60c-111">Si especifica **UTF-8**, **UTF-16** o **UTF-32** como la codificación, la opción **Suprimir caracteres BOM** estará disponible.</span><span class="sxs-lookup"><span data-stu-id="df60c-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="df60c-112">Establezca esta opción en **Sí** para suprimir [caracteres de marca BOM](https://docs.microsoft.com/globalization/encoding/byte-order-mark) en archivos salientes que se generan en tiempo de ejecución cuando se ejecuta el formato ER editable.</span><span class="sxs-lookup"><span data-stu-id="df60c-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](https://docs.microsoft.com/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="df60c-113">Si se deja el campo **Codificación** en blanco, se usará la codificación predeterminada **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="df60c-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![Configuración de la opción Suprimir caracteres BOM de la página de diseñador de formato](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="df60c-115">Para revisar la funcionalidad en tiempo de ejecución, complete el procedimiento apropiado.</span><span class="sxs-lookup"><span data-stu-id="df60c-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="df60c-116">Por ejemplo, complete los pasos del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="df60c-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="df60c-117">Una vez que haya completado los pasos de la sección [Modificar el formato para que el cálculo se base en la salida generada](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) de ese tema, siga estos pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="df60c-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="df60c-118">Especifique la codificación UTF:</span><span class="sxs-lookup"><span data-stu-id="df60c-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="df60c-119">Seleccione el elemento **Informe** del tipo **Común\\Archivo**.</span><span class="sxs-lookup"><span data-stu-id="df60c-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="df60c-120">En el campo **Codificación**, especifique la codificación **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="df60c-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="df60c-121">Genere un archivo XML que incluya un carácter BOM:</span><span class="sxs-lookup"><span data-stu-id="df60c-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="df60c-122">Cambie la opción **Suprimir caracteres BOM** a **No** para incluir caracteres BOM en archivos XML generados.</span><span class="sxs-lookup"><span data-stu-id="df60c-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="df60c-123">Complete los pasos de la sección [Aplazar la ejecución del elemento XML de resumen para que se utilice el total calculado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md) y guarde el archivo generado como **SampleXmlReport.xml**.</span><span class="sxs-lookup"><span data-stu-id="df60c-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="df60c-124">Genere un archivo XML que no incluya un carácter BOM:</span><span class="sxs-lookup"><span data-stu-id="df60c-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="df60c-125">Cambie la opción **Suprimir caracteres BOM** a **Sí** para eliminar caracteres BOM en archivos XML generados.</span><span class="sxs-lookup"><span data-stu-id="df60c-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="df60c-126">Complete los pasos de la sección [Aplazar la ejecución del elemento XML de resumen para que se utilice el total calculado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md) y guarde el archivo generado como **SampleXmlReport (1).xml**.</span><span class="sxs-lookup"><span data-stu-id="df60c-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="df60c-127">En una herramienta de comparación de archivos, compare los archivos generados.</span><span class="sxs-lookup"><span data-stu-id="df60c-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="df60c-128">La primera diferencia que notará está en el encabezado del archivo.</span><span class="sxs-lookup"><span data-stu-id="df60c-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="df60c-129">El archivo SampleXmlReport.xml contiene un carácter BOM, mientras que el archivo SampleXmlReport (1).xml, no.</span><span class="sxs-lookup"><span data-stu-id="df60c-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Comparación de archivos generados mediante una herramienta de comparación de archivos](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="df60c-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df60c-131">See also</span></span>

- [<span data-ttu-id="df60c-132">Aplazar la ejecución de elementos de XML en formatos de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="df60c-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]