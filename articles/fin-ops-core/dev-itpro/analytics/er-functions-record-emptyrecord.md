---
title: Función EMPTYRECORD de ER
description: En este tema se proporciona información sobre cómo usar la función EMPTYRECORD de informes electrónicos (ER).
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
ms.openlocfilehash: e614c06b4cfad628bbd8a966719ed994ce05b792
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746540"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="d95fc-103">Función EMPTYRECORD de ER</span><span class="sxs-lookup"><span data-stu-id="d95fc-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d95fc-104">La función `EMPTYRECORD` devuelve un valor nulo de tipo *Contenedor (registro)* que tiene la misma estructura que la lista de registros o el registro especificados.</span><span class="sxs-lookup"><span data-stu-id="d95fc-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="d95fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d95fc-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="d95fc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d95fc-106">Arguments</span></span>

<span data-ttu-id="d95fc-107">`list`: *Lista de registros* o *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="d95fc-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="d95fc-108">La ruta válida de un origen de datos de tipo *Lista de registros* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="d95fc-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d95fc-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d95fc-109">Return values</span></span>

<span data-ttu-id="d95fc-110">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="d95fc-110">*Container (record)*</span></span>

<span data-ttu-id="d95fc-111">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="d95fc-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d95fc-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="d95fc-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="d95fc-113">Un registro nulo es un registro donde todos los campos tienen un valor vacío.</span><span class="sxs-lookup"><span data-stu-id="d95fc-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="d95fc-114">Un valor vacío es **0** (cero) para números, una cadena vacía para las cadenas, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d95fc-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="d95fc-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d95fc-115">Example</span></span>

<span data-ttu-id="d95fc-116">`EMPTYRECORD (SPLIT ("abc", 1))` devuelve un nuevo registro vacío que tiene la misma estructura que la lista que devuelve la función `SPLIT` utilizada.</span><span class="sxs-lookup"><span data-stu-id="d95fc-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="d95fc-117">Para obtener más información, consulte [SPLIT](er-functions-list-split.md)</span><span class="sxs-lookup"><span data-stu-id="d95fc-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d95fc-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d95fc-118">Additional resources</span></span>

[<span data-ttu-id="d95fc-119">Funciones de registro</span><span class="sxs-lookup"><span data-stu-id="d95fc-119">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]