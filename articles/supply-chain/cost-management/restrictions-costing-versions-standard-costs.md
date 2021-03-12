---
title: Restricciones en versiones de gestión de costes para costes estándar
description: Este tema describe las restricciones que se aplican una versión de gestión de costes para costes estándar.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5339c3c4a62b94a06cbffc200ed1e9b227d6b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963797"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="28f5b-103">Restricciones en versiones de gestión de costes para costes estándar</span><span class="sxs-lookup"><span data-stu-id="28f5b-103">Restrictions on costing versions for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28f5b-104">Este tema describe las restricciones que se aplican una versión de gestión de costes para costes estándar.</span><span class="sxs-lookup"><span data-stu-id="28f5b-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="28f5b-105">Las siguientes restricciones ayudan garantizar el cumplimiento de los principios de gestión de costes estándar:</span><span class="sxs-lookup"><span data-stu-id="28f5b-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="28f5b-106">Los gastos deben incluirse en el coste de un artículo.</span><span class="sxs-lookup"><span data-stu-id="28f5b-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="28f5b-107">Los gastos de un artículo fabricado representan los costes constantes amortizados de la lista de materiales (L. MAT.) y la información de ruta,</span><span class="sxs-lookup"><span data-stu-id="28f5b-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="28f5b-108">Por tanto, los gastos deben incluirse en el coste unitario.</span><span class="sxs-lookup"><span data-stu-id="28f5b-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="28f5b-109">Los gastos de los artículos fabricados se incluirán también en el coste unitario.</span><span class="sxs-lookup"><span data-stu-id="28f5b-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="28f5b-110">El cálculo de costes estándar de los artículos fabricados debe basarse en los registros de costes de la versión de gestión de costes estándar.</span><span class="sxs-lookup"><span data-stu-id="28f5b-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="28f5b-111">Solo se pueden utilizar otros orígenes de datos de costes con una versión de gestión de costes para costes planificados, como acuerdos comerciales de precios de compra de artículos adquiridos.</span><span class="sxs-lookup"><span data-stu-id="28f5b-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="28f5b-112">Los otros orígenes de datos de costes están definidos por el grupo de cálculo de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="28f5b-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="28f5b-113">Los cálculos de L. MAT. deben ejecutarse en un modo de expansión de un único nivel.</span><span class="sxs-lookup"><span data-stu-id="28f5b-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="28f5b-114">Los datos de costes estándar de un artículo pueden copiarse en otra versión de gestión de costes que incluya costes estándar o costes planificados.</span><span class="sxs-lookup"><span data-stu-id="28f5b-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="28f5b-115">Sin embargo, los datos de costes planificados de un artículo no pueden copiarse en una versión de costes que incluya costes estándar, debido a que las restricciones que se describen anteriormente en este tema no se aplican a los costes planificados.</span><span class="sxs-lookup"><span data-stu-id="28f5b-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

<a name="related-topics"></a><span data-ttu-id="28f5b-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="28f5b-116">Related topics</span></span>
--------

[<span data-ttu-id="28f5b-117">Visión general de las versiones de gestión de costes</span><span class="sxs-lookup"><span data-stu-id="28f5b-117">Costing versions overview</span></span>](costing-versions.md)

[<span data-ttu-id="28f5b-118">Actualizar costes estándar en un entorno de no fabricación</span><span class="sxs-lookup"><span data-stu-id="28f5b-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="28f5b-119">Preparar el mantenimiento de los costes estándar de artículos fabricados</span><span class="sxs-lookup"><span data-stu-id="28f5b-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)

