---
title: Función EMPTYRECORD de ER
description: En este tema se proporciona información sobre cómo usar la función EMPTYRECORD de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 2d3c34cbff8551b84121201b9489250c07c7799e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563255"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="5ca5b-103">Función EMPTYRECORD de ER</span><span class="sxs-lookup"><span data-stu-id="5ca5b-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ca5b-104">La función `EMPTYRECORD` devuelve un valor nulo de tipo *Contenedor (registro)* que tiene la misma estructura que la lista de registros o el registro especificados.</span><span class="sxs-lookup"><span data-stu-id="5ca5b-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ca5b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ca5b-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="5ca5b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5ca5b-106">Arguments</span></span>

<span data-ttu-id="5ca5b-107">`list`: *Lista de registros* o *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="5ca5b-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="5ca5b-108">La ruta válida de un origen de datos de tipo *Lista de registros* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="5ca5b-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="5ca5b-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5ca5b-109">Return values</span></span>

<span data-ttu-id="5ca5b-110">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="5ca5b-110">*Container (record)*</span></span>

<span data-ttu-id="5ca5b-111">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="5ca5b-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5ca5b-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5ca5b-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="5ca5b-113">Un registro nulo es un registro donde todos los campos tienen un valor vacío.</span><span class="sxs-lookup"><span data-stu-id="5ca5b-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="5ca5b-114">Un valor vacío es **0** (cero) para números, una cadena vacía para las cadenas, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5ca5b-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="5ca5b-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ca5b-115">Example</span></span>

<span data-ttu-id="5ca5b-116">`EMPTYRECORD (SPLIT ("abc", 1))` devuelve un nuevo registro vacío que tiene la misma estructura que la lista que devuelve la función `SPLIT` utilizada.</span><span class="sxs-lookup"><span data-stu-id="5ca5b-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="5ca5b-117">Para obtener más información, consulte [SPLIT](er-functions-list-split.md)</span><span class="sxs-lookup"><span data-stu-id="5ca5b-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ca5b-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5ca5b-118">Additional resources</span></span>

[<span data-ttu-id="5ca5b-119">Funciones de registro</span><span class="sxs-lookup"><span data-stu-id="5ca5b-119">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]