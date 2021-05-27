---
title: No puede importar un artículo utilizando la entidad Productos lanzados V2
description: No puede importar un artículo utilizando la entidad Productos lanzados V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026873"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a><span data-ttu-id="27ff3-103">No puede importar un artículo utilizando la entidad Productos lanzados V2</span><span class="sxs-lookup"><span data-stu-id="27ff3-103">You can't import an item by using the Released products V2 entity</span></span>

<span data-ttu-id="27ff3-104">Número de KB: 4611825</span><span class="sxs-lookup"><span data-stu-id="27ff3-104">KB number: 4611825</span></span>

## <a name="symptoms"></a><span data-ttu-id="27ff3-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="27ff3-105">Symptoms</span></span>

<span data-ttu-id="27ff3-106">Cuando intente importar un elemento utilizando la entidad *Productos lanzados V2*, recibirá un mensaje de error similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27ff3-106">When you try to import an item by using the *Released products V2* entity, you receive an error message that resembles the following example:</span></span>

> <span data-ttu-id="27ff3-107">No se puede crear un registro en Artículos: grupos de dimensiones de seguimiento (EcoResTrackingDimensionGroupItem).</span><span class="sxs-lookup"><span data-stu-id="27ff3-107">Cannot create a record in Items - tracking dimension groups (EcoResTrackingDimensionGroupItem).</span></span> <span data-ttu-id="27ff3-108">Número del artículo: 2040663, lote.</span><span class="sxs-lookup"><span data-stu-id="27ff3-108">Item number: 2040663, Batch.</span></span> <span data-ttu-id="27ff3-109">El registro ya existe.</span><span class="sxs-lookup"><span data-stu-id="27ff3-109">The record already exists.</span></span>

## <a name="resolution"></a><span data-ttu-id="27ff3-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="27ff3-110">Resolution</span></span>

<span data-ttu-id="27ff3-111">Para importar nuevos productos lanzados, debe utilizar la entidad *Creación de productos lanzados V2* en lugar de la entidad *Productos lanzados V2*.</span><span class="sxs-lookup"><span data-stu-id="27ff3-111">To import new released products, you must use the *Released product creation V2* entity instead of the *Released products V2* entity.</span></span>
