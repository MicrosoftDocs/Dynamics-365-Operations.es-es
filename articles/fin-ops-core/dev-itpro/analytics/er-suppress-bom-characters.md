---
title: Diseñe configuraciones de ER para suprimir caracteres BOM en archivos generados
description: Este tema explica cómo configurar un formato de informes electrónicos (ER) para generar informes que suprimen los caracteres de marca BOM.
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19fbbdea4bfdf30b1313a47e65056b536ed73dbe
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060828"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>Diseñe configuraciones de ER para suprimir caracteres BOM en archivos generados

[!include [banner](../includes/banner.md)]

Puede diseñar una [solución](er-quick-start1-new-solution.md) de [Informes electrónicos (ER)](general-electronic-reporting.md) para generar documentos salientes. Para generar los documentos como archivos de texto o XML, la solución debe incluir una [configuración](general-electronic-reporting.md#Configuration) ER que contiene un componente en [formato](general-electronic-reporting.md#FormatComponentOutbound) ER. Para especificar la [codificación de caracteres](https://docs.microsoft.com/windows/win32/intl/character-sets) que representa el conjunto de caracteres en archivos generados, el formato ER debe contener el elemento de formato **Común\\Archivo**. Para configurar el componente de formato ER, abra la versión [borrador](general-electronic-reporting.md#component-versioning) de la configuración ER creada en el diseñador de formato ER y añada el elemento **Común\\Archivo**. En el campo **Codificación**, especifique la codificación de los archivos salientes que se generan en tiempo de ejecución mediante este componente.

> [!NOTE]
> Si el formato contiene un nombre de codificación incorrecto, se genera un error al guardar los cambios en la configuración del formato.

![Agregar un elemento raíz en la página del diseñador de formato](./media/er-suppress-bom-characters-image1.gif)

Si especifica **UTF-8**, **UTF-16** o **UTF-32** como la codificación, la opción **Suprimir caracteres BOM** estará disponible. Establezca esta opción en **Sí** para suprimir [caracteres de marca BOM](https://docs.microsoft.com/globalization/encoding/byte-order-mark) en archivos salientes que se generan en tiempo de ejecución cuando se ejecuta el formato ER editable.

> [!NOTE]
> Si se deja el campo **Codificación** en blanco, se usará la codificación predeterminada **UTF-8**.

![Configuración de la opción Suprimir caracteres BOM de la página de diseñador de formato](./media/er-suppress-bom-characters-image2.gif)

Para revisar la funcionalidad en tiempo de ejecución, complete el procedimiento apropiado. Por ejemplo, complete los pasos del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md). Una vez que haya completado los pasos de la sección [Modificar el formato para que el cálculo se base en la salida generada](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) de ese tema, siga estos pasos adicionales.

1. Especifique la codificación UTF:

    1. Seleccione el elemento **Informe** del tipo **Común\\Archivo**.
    2. En el campo **Codificación**, especifique la codificación **UTF-8**.

2. Genere un archivo XML que incluya un carácter BOM:

    1. Cambie la opción **Suprimir caracteres BOM** a **No** para incluir caracteres BOM en archivos XML generados.
    2. Complete los pasos de la sección [Aplazar la ejecución del elemento XML de resumen para que se utilice el total calculado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md) y guarde el archivo generado como **SampleXmlReport.xml**.

3. Genere un archivo XML que no incluya un carácter BOM:

    1. Cambie la opción **Suprimir caracteres BOM** a **Sí** para eliminar caracteres BOM en archivos XML generados.
    2. Complete los pasos de la sección [Aplazar la ejecución del elemento XML de resumen para que se utilice el total calculado](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md) y guarde el archivo generado como **SampleXmlReport (1).xml**.

4. En una herramienta de comparación de archivos, compare los archivos generados.

    La primera diferencia que notará está en el encabezado del archivo. El archivo SampleXmlReport.xml contiene un carácter BOM, mientras que el archivo SampleXmlReport (1).xml, no.

    ![Comparación de archivos generados mediante una herramienta de comparación de archivos](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Consulte también

- [Aplazar la ejecución de elementos de XML en formatos de informes electrónicos](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]