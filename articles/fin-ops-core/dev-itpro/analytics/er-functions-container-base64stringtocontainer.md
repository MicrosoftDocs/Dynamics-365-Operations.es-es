---
title: Función ER Base64StringToContainer
description: En este tema se proporciona información sobre cómo usar la función Base64StringToContainer de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e92ae41a3e0f03cb14d4791ab768f096f2a0523
ms.sourcegitcommit: e8a46e127d70986539c138b27a641bff6f6874d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "4739110"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="b92e8-103">Función ER Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="b92e8-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b92e8-104">La [función](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *[Contenedor](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="b92e8-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="b92e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b92e8-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="b92e8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b92e8-106">Arguments</span></span>

<span data-ttu-id="b92e8-107">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="b92e8-107">`input`: *String*</span></span>

<span data-ttu-id="b92e8-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="b92e8-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b92e8-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b92e8-109">Return values</span></span>

<span data-ttu-id="b92e8-110">*Contenedor*</span><span class="sxs-lookup"><span data-stu-id="b92e8-110">*Container*</span></span>

<span data-ttu-id="b92e8-111">El valor binario resultante en formato de objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="b92e8-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b92e8-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="b92e8-112">Usage notes</span></span>

<span data-ttu-id="b92e8-113">La excepción "El parámetro no es válido" aparece si la cadena de entrada no proporciona un grupo Base64 correcto de esquemas de codificación de binario a texto.</span><span class="sxs-lookup"><span data-stu-id="b92e8-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="b92e8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b92e8-114">Example</span></span>

<span data-ttu-id="b92e8-115">Defina los siguientes orígenes de datos en la asignación de su modelo:</span><span class="sxs-lookup"><span data-stu-id="b92e8-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="b92e8-116">El origen de datos raíz **DocuTypeGroupEnum** del tipo *Dynamics 365 for Operations/Enumeración* que se refiere a la enumeración de aplicación **DocuTypeGroup**</span><span class="sxs-lookup"><span data-stu-id="b92e8-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="b92e8-117">El origen de datos raíz **Cliente** del tipo *Dynamics 365 for Operations/Registros de tabla* que se refiere a la tabla de aplicación **CustTable**</span><span class="sxs-lookup"><span data-stu-id="b92e8-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="b92e8-118">El origen de datos **\#Medios** del tipo *Campo calculado* que se configura de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b92e8-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="b92e8-119">Se agrega como origen de datos secundaria del origen de datos **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="b92e8-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="b92e8-120">Contiene la expresión `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="b92e8-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="b92e8-121">El origen de datos **\#MediaAsBase64String** del tipo *Campo calculado* que se configura de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b92e8-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="b92e8-122">Se agrega como origen de datos secundaria del origen de datos **Cliente.'\#Medios**.</span><span class="sxs-lookup"><span data-stu-id="b92e8-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="b92e8-123">Contiene la expresión `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="b92e8-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="b92e8-124">El origen de datos **\#BlobFomBase64** del tipo *Campo calculado* que se configura de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b92e8-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="b92e8-125">Se agrega como origen de datos secundaria del origen de datos **Cliente.'\#Medios**.</span><span class="sxs-lookup"><span data-stu-id="b92e8-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="b92e8-126">Contiene la expresión `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="b92e8-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="b92e8-127">En este ejemplo, el origen de datos **\#MediaAsBase64String** codifica el contenido binario del adjunto multimedia actual como texto que representa un grupo Base64 de esquemas de codificación de binario a texto.</span><span class="sxs-lookup"><span data-stu-id="b92e8-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="b92e8-128">El origen de datos **\#BlobFomBase64** decodifica la cadena Base64 y devuelve un valor binario en formato BLOB.</span><span class="sxs-lookup"><span data-stu-id="b92e8-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Orígenes de datos de ejemplo en la página del diseñador de asignación de modelo ER](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="b92e8-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b92e8-130">Additional resources</span></span>

[<span data-ttu-id="b92e8-131">Funciones de contenedor</span><span class="sxs-lookup"><span data-stu-id="b92e8-131">Container functions</span></span>](er-functions-category-container.md)
