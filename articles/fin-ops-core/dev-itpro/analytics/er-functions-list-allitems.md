---
title: Función ALLITEMS ER
description: En este tema se proporciona información sobre cómo usar la función ALLITEMS de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 79c43b6ecdb307433b0c2091840c21a5ada3a689
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917451"
---
# <span data-ttu-id="459d0-103"><a name="ALLITEMS">Función ALLITEMS ER</a></span><span class="sxs-lookup"><span data-stu-id="459d0-103"><a name="ALLITEMS">ALLITEMS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="459d0-104">La función `ALLITEMS` se ejecuta como una selección en memoria y devuelve un nuevo valor aplanado *Lista de registros* como una lista de registros que representa todos los elementos que coinciden con la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="459d0-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="459d0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="459d0-105">Syntax</span></span>

```
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="459d0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="459d0-106">Arguments</span></span>

<span data-ttu-id="459d0-107">`path`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="459d0-107">`path`: *Record list*</span></span>

<span data-ttu-id="459d0-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="459d0-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="459d0-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="459d0-109">Return values</span></span>

<span data-ttu-id="459d0-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="459d0-110">*Record list*</span></span>

<span data-ttu-id="459d0-111">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="459d0-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="459d0-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="459d0-112">Usage notes</span></span>

<span data-ttu-id="459d0-113">La ruta se debe definir como ruta válida de un origen de datos a un elemento de origen de datos del tipo de datos de la *Lista de registro*.</span><span class="sxs-lookup"><span data-stu-id="459d0-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="459d0-114">Elementos de datos como la cadena de ruta y la fecha deberían activar un error en el tiempo de diseño del generador de expresiones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="459d0-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="459d0-115">No recomendamos que utilice esta función para orígenes de datos transaccionales que puedan contener un gran volumen de datos.</span><span class="sxs-lookup"><span data-stu-id="459d0-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="459d0-116">En cambio, considere usar la función [ALLTEMSQUERY ](er-functions-list-allitemsquery.md).</span><span class="sxs-lookup"><span data-stu-id="459d0-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="459d0-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="459d0-117">Example 1</span></span>

<span data-ttu-id="459d0-118">Si introduce `SPLIT("abcdef" , 2)` como fuente de datos **DS**, la expresión `COUNT( ALLITEMS (DS))` devuelve **3**.</span><span class="sxs-lookup"><span data-stu-id="459d0-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="459d0-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="459d0-119">Example 2</span></span>

<span data-ttu-id="459d0-120">Si introduce **Vendedor** como la fuente de datos del tipo de datos *Lista de registros* que se refiere a la tabla de la aplicación VendTable, la expresión `ALLITEMS (Vend.'<Relations'.ContactPerson)` devuelve una lista aplanada de registros que tiene la estructura de tabla **Persona de contacto** y contiene todas las personas de contacto a las que se puede acceder utilizando la relación **ContactPerson.ContactForParty == VendTable.Party**, y eso está disponible para todos los proveedores de la tabla de proveedores referenciada.</span><span class="sxs-lookup"><span data-stu-id="459d0-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="459d0-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="459d0-121">Additional resources</span></span>

[<span data-ttu-id="459d0-122">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="459d0-122">List functions</span></span>](er-functions-category-list.md)