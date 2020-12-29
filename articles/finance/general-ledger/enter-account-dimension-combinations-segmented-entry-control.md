---
title: Especificar combinaciones de cuentas y dimensiones (control de entrada segmentada)
description: Este artículo describe cómo especificar combinaciones de cuenta y dimensión o cuentas contables. La experiencia de entrada suele denominarse control de entrada segmentado.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 872ee7812d98e6102798c3a10773176541c02c90
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447493"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="9276c-104">Especificar combinaciones de cuentas y dimensiones (control de entrada segmentada)</span><span class="sxs-lookup"><span data-stu-id="9276c-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9276c-105">Este artículo describe cómo especificar combinaciones de cuenta y dimensión o cuentas contables.</span><span class="sxs-lookup"><span data-stu-id="9276c-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="9276c-106">La experiencia de entrada suele denominarse control de entrada segmentado.</span><span class="sxs-lookup"><span data-stu-id="9276c-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="9276c-107">Los usuarios especifican combinaciones de cuenta y dimensiones en diversas páginas, como páginas para diarios generales, gestión presupuestaria, y definiciones de contabilización.</span><span class="sxs-lookup"><span data-stu-id="9276c-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="9276c-108">Las combinaciones de cuentas y dimensiones válidas dependen de las estructuras contables que se asignan al libro mayor y las reglas avanzadas que se asignan a las estructuras contables.</span><span class="sxs-lookup"><span data-stu-id="9276c-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="9276c-109">Cuando los usuarios especifican una combinación, pueden escribir manualmente los valores o aprovecharse de una experiencia de búsqueda enriquecida.</span><span class="sxs-lookup"><span data-stu-id="9276c-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="9276c-110">En el campo, puede empezar a escribir y se buscarán el valor y la descripción.</span><span class="sxs-lookup"><span data-stu-id="9276c-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="9276c-111">Por ejemplo, si escribe 180 se busca algún valor que comience con esa combinación de números.</span><span class="sxs-lookup"><span data-stu-id="9276c-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="9276c-112">O bien puede escribir Efectivo y se buscará cualquier valor que tenga una descripción que empiece por Efectivo.</span><span class="sxs-lookup"><span data-stu-id="9276c-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="9276c-113">También puede usar un comodín para buscar, como \*Efectivo o \*180, si el valor o la descripción contienen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9276c-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="9276c-114">En la tabla siguiente se describen los métodos abreviados de teclado que se pueden usar cuando se cierre la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9276c-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9276c-115">Método abreviado de teclado</span><span class="sxs-lookup"><span data-stu-id="9276c-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="9276c-116">Acción</span><span class="sxs-lookup"><span data-stu-id="9276c-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9276c-117">Alt+Flecha abajo</span><span class="sxs-lookup"><span data-stu-id="9276c-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="9276c-118">Abra la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9276c-118">Open the lookup.</span></span> <span data-ttu-id="9276c-119">Si pulsa Alt+Flecha abajo una segunda vez, el foco se traslada a los segmentos del elemento flotante.</span><span class="sxs-lookup"><span data-stu-id="9276c-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="9276c-120">Entrar y Mayús+Entrar</span><span class="sxs-lookup"><span data-stu-id="9276c-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="9276c-121">Delimitador de plan contable</span><span class="sxs-lookup"><span data-stu-id="9276c-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="9276c-122">Flecha derecha y flecha izquierda</span><span class="sxs-lookup"><span data-stu-id="9276c-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="9276c-123">Ir al segmento siguiente o anterior.</span><span class="sxs-lookup"><span data-stu-id="9276c-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9276c-124">Tabulación</span><span class="sxs-lookup"><span data-stu-id="9276c-124">Tab</span></span></td>
<td><span data-ttu-id="9276c-125">Desplazar al siguiente campo de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9276c-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9276c-126">En la tabla siguiente se describen los métodos abreviados de teclado que se pueden usar cuando se abre la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9276c-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9276c-127">Método abreviado de teclado</span><span class="sxs-lookup"><span data-stu-id="9276c-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="9276c-128">Acción</span><span class="sxs-lookup"><span data-stu-id="9276c-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9276c-129">Esc</span><span class="sxs-lookup"><span data-stu-id="9276c-129">Esc</span></span></td>
<td><span data-ttu-id="9276c-130">Cerrar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9276c-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="9276c-131">Flecha arriba y flecha abajo</span><span class="sxs-lookup"><span data-stu-id="9276c-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="9276c-132">Re Pág y Av Pág</span><span class="sxs-lookup"><span data-stu-id="9276c-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="9276c-133">Inicio y Fin</span><span class="sxs-lookup"><span data-stu-id="9276c-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="9276c-134">Ir al valor anterior o siguiente de las listas, al grupo anterior o al siguiente de valores, o al primer o último elemento de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9276c-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="9276c-135">Delimitador de plan contable</span><span class="sxs-lookup"><span data-stu-id="9276c-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="9276c-136">Flecha derecha y flecha izquierda</span><span class="sxs-lookup"><span data-stu-id="9276c-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="9276c-137">Ir al segmento siguiente o anterior.</span><span class="sxs-lookup"><span data-stu-id="9276c-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9276c-138">Ficha</span><span class="sxs-lookup"><span data-stu-id="9276c-138">Tab</span></span></td>
<td><span data-ttu-id="9276c-139">Desplazar al siguiente campo de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9276c-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9276c-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="9276c-140">Alt+W</span></span></td>
<td><span data-ttu-id="9276c-141">Cambiar entre<strong>Mostrar todo</strong> y <strong>Mostrar válido</strong>.</span><span class="sxs-lookup"><span data-stu-id="9276c-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>





