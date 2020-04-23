---
title: Crear configuraciones basadas en dimensiones
description: Este procedimiento muestra cómo definir una configuración para un producto basado en dimensiones.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a60a20c1d425f7ef39e9e81143d34075cf3a29
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213340"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="a1928-103">Crear configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="a1928-103">Create dimension-based configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a1928-104">Este procedimiento muestra cómo definir una configuración para un producto basado en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="a1928-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="a1928-105">Este es el último procedimiento de la serie que explica cómo crear combinaciones para la configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="a1928-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="a1928-106">La ejecución de este procedimiento depende de los datos creados en los siete registros anteriores.</span><span class="sxs-lookup"><span data-stu-id="a1928-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="a1928-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a1928-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="a1928-108">Buscar el producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="a1928-108">Find the dimension-based product master</span></span>
1. <span data-ttu-id="a1928-109">Haga clic en Mantenimiento de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="a1928-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="a1928-110">Haga clic en Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="a1928-110">Click Released products.</span></span>
3. <span data-ttu-id="a1928-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a1928-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a1928-112">Seleccione el producto maestro basado en dimensiones que ha creado en el primer registro de esta secuencia de 8 registros.</span><span class="sxs-lookup"><span data-stu-id="a1928-112">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="a1928-113">Crear configuraciones</span><span class="sxs-lookup"><span data-stu-id="a1928-113">Create configurations</span></span>
1. <span data-ttu-id="a1928-114">En el panel de acciones Ingeniería, haga clic en Mantener configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a1928-114">On the Engineering Action Pane, click Maintain configurations.</span></span>
2. <span data-ttu-id="a1928-115">Haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="a1928-115">Click Configure.</span></span>
3. <span data-ttu-id="a1928-116">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a1928-116">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="a1928-117">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a1928-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="a1928-118">Seleccione cualquiera de los artículos del primer grupo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a1928-118">Select any of the items in the first configuration group.</span></span>  
5. <span data-ttu-id="a1928-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a1928-119">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="a1928-120">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a1928-120">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="a1928-121">Seleccione cualquier artículo del segundo grupo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a1928-121">Select any item from the second configuration group.</span></span>  
7. <span data-ttu-id="a1928-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a1928-122">Click OK.</span></span>
8. <span data-ttu-id="a1928-123">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a1928-123">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a1928-124">En el campo Configuración, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a1928-124">In the Configuration field, type a value.</span></span>
    * <span data-ttu-id="a1928-125">Escriba un nombre de configuración que hará que sea sencillo identificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a1928-125">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
10. <span data-ttu-id="a1928-126">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a1928-126">In the Description field, type a value.</span></span>
    * <span data-ttu-id="a1928-127">Escriba una descripción de la configuración para explicar lo que contiene.</span><span class="sxs-lookup"><span data-stu-id="a1928-127">Enter a description of the configuration to explain what it contains.</span></span>  
11. <span data-ttu-id="a1928-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a1928-128">Click OK.</span></span>

