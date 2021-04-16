---
title: Función GUIDVALUE de ER
description: Este tema proporciona información general sobre cómo usar la función GUIDVALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec8222708b999a17794a396b5bf807dab037799d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746396"
---
# <a name="guidvalue-er-function"></a><span data-ttu-id="93453-103">Función GUIDVALUE de ER</span><span class="sxs-lookup"><span data-stu-id="93453-103">GUIDVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="93453-104">La función `GUIDVALUE` convierte la entrada especificada de tipo *Cadena* en un elemento de datos de tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="93453-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="93453-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93453-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="93453-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="93453-106">Arguments</span></span>

<span data-ttu-id="93453-107">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="93453-107">`input`: *String*</span></span>

<span data-ttu-id="93453-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="93453-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="93453-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="93453-109">Return values</span></span>

<span data-ttu-id="93453-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="93453-110">*GUID*</span></span>

<span data-ttu-id="93453-111">El valor del identificador único global (GUID) resultante.</span><span class="sxs-lookup"><span data-stu-id="93453-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="93453-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="93453-112">Usage notes</span></span>

<span data-ttu-id="93453-113">Para hacer una conversión en sentido contrario (es decir, convertir la entrada especificada con tipo de datos *GUID* en un elemento de datos de tipo *Cadena*), puede utilizar la función [TEXT()](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="93453-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="93453-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93453-114">Example</span></span>

<span data-ttu-id="93453-115">Defina los siguientes orígenes de datos en la asignación de su modelo:</span><span class="sxs-lookup"><span data-stu-id="93453-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="93453-116">Un origen de datos **myID** de tipo *Campo calculado* que contiene la expresión `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="93453-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="93453-117">Un origen de datos **Users** de tipo *Registros de tabla* que hace referencia a la tabla UserInfo</span><span class="sxs-lookup"><span data-stu-id="93453-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="93453-118">Después puede usar una expresión como `FILTER (Users, Users.objectId = myID)` para filtrar la tabla UserInfo por el campo **objectId** con tipo de datos *GUID*.</span><span class="sxs-lookup"><span data-stu-id="93453-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93453-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="93453-119">Additional resources</span></span>

[<span data-ttu-id="93453-120">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="93453-120">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]