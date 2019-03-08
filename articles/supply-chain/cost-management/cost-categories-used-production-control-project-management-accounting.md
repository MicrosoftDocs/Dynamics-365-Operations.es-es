---
title: Categorías de coste usadas en el control de producción y en la contabilidad de la administración de proyectos
description: Algunos tipos de trabajo de producción se pueden aplicar a estimaciones del tiempo del proyecto y a los informes. Este artículo proporciona información acerca de las categorías de coste que debe definir para estos tipos de trabajos de producción con fines de producción y del proyecto.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 78253
ms.assetid: cfdd58a0-8afa-4a6f-a208-a76e2c162429
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cab4629740e92f9075b7afc7a5d228b2e01c4664
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "326041"
---
# <a name="cost-categories-used-in-production-control-and-project-management-accounting"></a><span data-ttu-id="60953-104">Categorías de coste usadas en el control de producción y en la contabilidad de la administración de proyectos</span><span class="sxs-lookup"><span data-stu-id="60953-104">Cost categories used in Production control and Project management accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60953-105">Algunos tipos de trabajo de producción se pueden aplicar a estimaciones del tiempo del proyecto y a los informes.</span><span class="sxs-lookup"><span data-stu-id="60953-105">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="60953-106">Este artículo proporciona información acerca de las categorías de coste que debe definir para estos tipos de trabajos de producción con fines de producción y del proyecto.</span><span class="sxs-lookup"><span data-stu-id="60953-106">This article provides information about the cost categories that you must define for these types of production work for production and project purposes.</span></span>

<span data-ttu-id="60953-107">Algunos tipos de trabajo de producción se pueden aplicar a estimaciones del tiempo del proyecto y a los informes.</span><span class="sxs-lookup"><span data-stu-id="60953-107">Some types of production work can apply to project time estimates and reporting.</span></span> <span data-ttu-id="60953-108">En este caso, se requiere una categoría de coste para fines de proyecto y producción.</span><span class="sxs-lookup"><span data-stu-id="60953-108">In this case, a cost category is required for production and project purposes.</span></span> <span data-ttu-id="60953-109">Cuando una categoría de coste se utiliza en la producción y en proyectos, se debe definir información adicional relativa al proyecto.</span><span class="sxs-lookup"><span data-stu-id="60953-109">When a cost category is used in production and projects, additional project-related information must be defined.</span></span> <span data-ttu-id="60953-110">Por ejemplo, los costes por hora asociados a proyectos pueden ser diferentes a los costes por hora asociados a la producción.</span><span class="sxs-lookup"><span data-stu-id="60953-110">For example, the hourly costs that are associated with projects can differ from the hourly costs that are associated with production.</span></span> <span data-ttu-id="60953-111">Puede usar la página **Categorías de coste** para definir una categoría de coste que se use en control de producción y contabilidad de gestión de proyectos.</span><span class="sxs-lookup"><span data-stu-id="60953-111">You can use the **Cost categories** page to define a cost category that is used in Production control and Project management accounting.</span></span> 

<span data-ttu-id="60953-112">**Nota:** La contabilidad de costes tiene una página **Categorías de proyecto**, pero esta página no tiene ninguna relación con la funcionalidad que se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="60953-112">**Note:** Cost accounting has a **Project categories** page, but this page has no relationship to the functionality that is described in this topic.</span></span> <span data-ttu-id="60953-113">Al usar una categoría de coste en los proyectos, la página **Categorías de coste** tiene fichas adicionales que muestran información adicional relacionada con el proyecto.</span><span class="sxs-lookup"><span data-stu-id="60953-113">When you use a cost category in projects, the **Cost categories** page has additional tabs that show additional project-related information.</span></span> <span data-ttu-id="60953-114">Esta información incluye el grupo de categorías, una propiedad de línea y las cuentas contables que están asignadas a la categoría de coste.</span><span class="sxs-lookup"><span data-stu-id="60953-114">This information includes the category group, a line property, and ledger accounts that are assigned to the cost category.</span></span>

-   <span data-ttu-id="60953-115">La categoría de coste debe asignarse a un grupo de categorías que admite un tipo de transacción de **Horas**.</span><span class="sxs-lookup"><span data-stu-id="60953-115">The cost category must be assigned to a category group that supports a transaction type of **Hours**.</span></span>
-   <span data-ttu-id="60953-116">La propiedad de línea indica la información predeterminada sobre cómo se puede cargar el tiempo registrado a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="60953-116">The line property indicates default information about how reported time can be charged to a project.</span></span>
-   <span data-ttu-id="60953-117">Normalmente, las cuentas contables relacionadas con costes y ventas se definen para el grupo de categorías asignado a la categoría de coste.</span><span class="sxs-lookup"><span data-stu-id="60953-117">Typically, the ledger accounts that are related to costs and sales are defined for the category group that is assigned to the cost category.</span></span> <span data-ttu-id="60953-118">Sin embargo, se pueden definir cuentas específicas para una categoría de coste individual.</span><span class="sxs-lookup"><span data-stu-id="60953-118">However, specific accounts can be defined for an individual cost category.</span></span>

<span data-ttu-id="60953-119">Los botones adicionales de la página **Categorías de coste** le permiten acceso a la información relativa al proyecto, acerca de una categoría de costes seleccionada.</span><span class="sxs-lookup"><span data-stu-id="60953-119">Additional buttons on the **Cost categories** page let you access project-related information about a selected cost category.</span></span> <span data-ttu-id="60953-120">Por ejemplo, puede ver transacciones relacionadas con el proyecto, definir empleados o proyectos, definir costes por hora y precios de venta, y ver informes.</span><span class="sxs-lookup"><span data-stu-id="60953-120">For example, you can view project-related transactions, define employees or projects, define hourly costs and sales prices, and view reports.</span></span>



