---
title: Función QRCODE de ER
description: Este tema proporciona información general sobre cómo usar la función QRCODE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b62ed829202028ca0cbf95a0dbc3460d047ca5a5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682976"
---
# <a name="qrcode-er-function"></a><span data-ttu-id="42dba-103">Función QRCODE de ER</span><span class="sxs-lookup"><span data-stu-id="42dba-103">QRCODE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42dba-104">La función `QRCODE` devuelve un valor de tipo *Contenedor* que presenta la imagen del código de respuesta rápida (código QR) para la cadena especificada en formato binario.</span><span class="sxs-lookup"><span data-stu-id="42dba-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="42dba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42dba-105">Syntax</span></span>

```vb
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="42dba-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="42dba-106">Arguments</span></span>

<span data-ttu-id="42dba-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="42dba-107">`text`: *String*</span></span>

<span data-ttu-id="42dba-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="42dba-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="42dba-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="42dba-109">Return values</span></span>

<span data-ttu-id="42dba-110">*Contenedor*</span><span class="sxs-lookup"><span data-stu-id="42dba-110">*Container*</span></span>

<span data-ttu-id="42dba-111">La secuencia binaria resultante.</span><span class="sxs-lookup"><span data-stu-id="42dba-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="42dba-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42dba-112">Example</span></span>

<span data-ttu-id="42dba-113">Puede configurar un formato de informe electrónico (ER) para generar un documento de salida con formato de Microsoft Office (libros de Excel o documentos de Word) mediante una plantilla predefinida.</span><span class="sxs-lookup"><span data-stu-id="42dba-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="42dba-114">Esta plantilla puede contener un objeto de tipo **Imagen** (libro de Excel) o un **Control de contenido de imagen** (Documento de Word) como marcador de posición para una imagen de código QR.</span><span class="sxs-lookup"><span data-stu-id="42dba-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="42dba-115">Debe agregar al formato de ER configurado un elemento de **Celda** que se utilizará para rellenar este marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="42dba-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="42dba-116">Para especificar qué información se almacenará en un código QR, debe definir un enlace para este elemento **Celda**.</span><span class="sxs-lookup"><span data-stu-id="42dba-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="42dba-117">Por ejemplo, puede configurar un enlace que contenga la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="42dba-117">For example, you can configure such binding as containing the following expression:</span></span>

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="42dba-118">Al ejecutar el formato de ER configurado, el valor de texto del campo **LabelText** del origen de datos **model.ListOfShelfLabels** se usará para generar una imagen de código QR.</span><span class="sxs-lookup"><span data-stu-id="42dba-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="42dba-119">Esta imagen reemplazará un marcador de posición de imagen de código QR en la plantilla de documento que se utiliza para generar un documento de salida.</span><span class="sxs-lookup"><span data-stu-id="42dba-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="42dba-120">Cuando se escanea esta imagen del documento generado, devuelve el texto que se tomó del campo **LabelText** del origen de datos **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="42dba-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="42dba-121">Para obtener más información, consulte [Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="42dba-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42dba-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="42dba-122">Additional resources</span></span>

[<span data-ttu-id="42dba-123">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="42dba-123">Text functions</span></span>](er-functions-category-text.md)
