---
title: Recuento de etiquetas de inventario
description: En este tema se proporciona información sobre el recuento de etiquetas, que se usa para comparar el contenido real de un almacén con el inventario disponible.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78402840ad86a0f43d30b3c80307b4646fffbaeb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216138"
---
# <a name="inventory-tag-counting"></a><span data-ttu-id="480b5-103">Recuento de etiquetas de inventario</span><span class="sxs-lookup"><span data-stu-id="480b5-103">Inventory tag counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="480b5-104">En este tema se proporciona información sobre el recuento de etiquetas, que se usa para comparar el contenido real de un almacén con el inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="480b5-104">This topic provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="480b5-105">Al crear líneas en la página **Recuento de etiquetas**, coloca un número de etiqueta en cada artículo de inventario, como un número del 1 al 500.</span><span class="sxs-lookup"><span data-stu-id="480b5-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="480b5-106">Durante el recuento, escribe el código de artículo y la cantidad en una etiqueta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="480b5-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="480b5-107">Esta etiqueta se puede usar como la base para la entrada del diario de recuento de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="480b5-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="480b5-108">Tras registra el diario de recuento de etiquetas, se crea un diario de recuento nuevo en la página **Recuento**.</span><span class="sxs-lookup"><span data-stu-id="480b5-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="480b5-109">El nuevo diario se basa en las líneas de diario de recuento de etiquetas que ha creado.</span><span class="sxs-lookup"><span data-stu-id="480b5-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="480b5-110">Para contar las etiquetas de artículos por una dimensión de inventario específica, seleccione la dimensión en la página **Mostrar dimensiones** que aparece al crear el diario de recuento de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="480b5-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="480b5-111">Por ejemplo, para contar artículos de un almacén especifico, active la casilla **Almacén**.</span><span class="sxs-lookup"><span data-stu-id="480b5-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="480b5-112">Si el control deslizante **Bloquear artículos durante el recuento** de la página **Parámetros de gestión de inventario y almacenes** está seleccionado, los artículos no se pueden actualizar físicamente durante el recuento.</span><span class="sxs-lookup"><span data-stu-id="480b5-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="480b5-113">Sin embargo, los artículos de los diarios de recuento de etiquetas no se bloquean durante el recuento.</span><span class="sxs-lookup"><span data-stu-id="480b5-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="480b5-114">Las transacciones de inventario no se crean hasta que las líneas de recuento de etiquetas se registran y se transfieren a un diario de recuento.</span><span class="sxs-lookup"><span data-stu-id="480b5-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="480b5-115">Si las etiquetas se colocan aleatoriamente y desea identificar las etiquetas que faltan, haga clic en el encabezado de columna **Etiqueta** para ordenar las líneas por etiqueta.</span><span class="sxs-lookup"><span data-stu-id="480b5-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="480b5-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="480b5-116">Additional resources</span></span>

[<span data-ttu-id="480b5-117">Recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="480b5-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]