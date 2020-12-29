---
title: Función ALLITEMSQUERY ER
description: En este tema se proporciona información sobre cómo usar la función ALLITEMSQUERY de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: ed21252fbbe3d4adad106625062e10e3de712bb0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687753"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="a34d8-103">Función ALLITEMSQUERY ER</span><span class="sxs-lookup"><span data-stu-id="a34d8-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a34d8-104">La función `ALLITEMSQUERY` se ejecuta como consulta SQL combinada.</span><span class="sxs-lookup"><span data-stu-id="a34d8-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="a34d8-105">Devuelve un valor aplanado nuevo de *Lista de registros* que consiste en una lista de registros que representa todos los elementos que coinciden con la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="a34d8-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="a34d8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a34d8-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="a34d8-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a34d8-107">Arguments</span></span>

<span data-ttu-id="a34d8-108">`path`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a34d8-108">`path`: *Record list*</span></span>

<span data-ttu-id="a34d8-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a34d8-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="a34d8-110">Debe contener al menos una relación.</span><span class="sxs-lookup"><span data-stu-id="a34d8-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="a34d8-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a34d8-111">Return values</span></span>

<span data-ttu-id="a34d8-112">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a34d8-112">*Record list*</span></span>

<span data-ttu-id="a34d8-113">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="a34d8-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a34d8-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a34d8-114">Usage notes</span></span>

<span data-ttu-id="a34d8-115">La ruta especificada se debe definir como ruta válida de un origen de datos a un elemento de origen de datos del tipo de datos de la *Lista de registro*.</span><span class="sxs-lookup"><span data-stu-id="a34d8-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="a34d8-116">También debe contener al menos una relación.</span><span class="sxs-lookup"><span data-stu-id="a34d8-116">It must also contain at least one relation.</span></span> <span data-ttu-id="a34d8-117">Elementos de datos como la *Cadena* de ruta y la *Fecha* deberían activar un error en el tiempo de diseño del generador de expresiones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="a34d8-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="a34d8-118">Cuando esta función se aplica a las fuentes de datos del tipo de datos *Lista de registros* que se refieren a un objeto de aplicación al que se puede llamar directamente mediante SQL (por ejemplo, una tabla, entidad o consulta), se ejecuta como una consulta SQL unida.</span><span class="sxs-lookup"><span data-stu-id="a34d8-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="a34d8-119">De lo contrario, se ejecuta en la memoria como función [ALLITEMS](er-functions-list-allitems.md).</span><span class="sxs-lookup"><span data-stu-id="a34d8-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="a34d8-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a34d8-120">Example</span></span>

<span data-ttu-id="a34d8-121">Defina los siguientes orígenes de datos en la asignación de su modelo:</span><span class="sxs-lookup"><span data-stu-id="a34d8-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a34d8-122">Una fuente de datos **CustInv** del tipo *Tabla de registros* que hace referencia a la tabla CustInvoiceTable</span><span class="sxs-lookup"><span data-stu-id="a34d8-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="a34d8-123">Una fuente de datos **FilteredInv** del tipo *Campo calculado* que contiene la expresión `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span><span class="sxs-lookup"><span data-stu-id="a34d8-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="a34d8-124">Una **JourLines** del tipo *Campo calculado* que contiene la expresión `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span><span class="sxs-lookup"><span data-stu-id="a34d8-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="a34d8-125">Cuando ejecute la asignación del modelo para llamar al origen de datos **JourLines**, se ejecuta la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="a34d8-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="a34d8-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a34d8-126">Additional resources</span></span>

[<span data-ttu-id="a34d8-127">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="a34d8-127">List functions</span></span>](er-functions-category-list.md)
