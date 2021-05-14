---
title: Crear configuraciones basadas en dimensiones
description: Este procedimiento muestra cómo definir una configuración para un producto basado en dimensiones.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 584bb558ee0afeaffaeb003e9f1d1b0bca42d19d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920690"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="08233-103">Crear configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="08233-103">Create dimension-based configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="08233-104">Este procedimiento muestra cómo definir una configuración para un producto basado en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="08233-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="08233-105">Este es el último procedimiento de la serie que explica cómo crear combinaciones para la configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="08233-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="08233-106">La ejecución de este procedimiento depende de los datos creados en los siete registros anteriores.</span><span class="sxs-lookup"><span data-stu-id="08233-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="08233-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="08233-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="08233-108">Buscar el producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="08233-108">Find the dimension-based product master</span></span>

1. <span data-ttu-id="08233-109">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="08233-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="08233-110">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08233-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="08233-111">Seleccione el producto maestro basado en dimensiones que ha creado en el primer registro de esta secuencia de 8 registros.</span><span class="sxs-lookup"><span data-stu-id="08233-111">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="08233-112">Crear configuraciones</span><span class="sxs-lookup"><span data-stu-id="08233-112">Create configurations</span></span>

1. <span data-ttu-id="08233-113">En el panel de acciones **Ingeniería**, seleccione **Mantener configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="08233-113">On the **Engineering** Action Pane, select **Maintain configurations**.</span></span>
1. <span data-ttu-id="08233-114">Seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="08233-114">Select **Configure**.</span></span>
1. <span data-ttu-id="08233-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08233-115">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="08233-116">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08233-116">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="08233-117">Seleccione cualquiera de los artículos del primer grupo de configuración.</span><span class="sxs-lookup"><span data-stu-id="08233-117">Select any of the items in the first configuration group.</span></span>  
1. <span data-ttu-id="08233-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="08233-118">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="08233-119">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08233-119">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="08233-120">Seleccione cualquier artículo del segundo grupo de configuración.</span><span class="sxs-lookup"><span data-stu-id="08233-120">Select any item from the second configuration group.</span></span>  
1. <span data-ttu-id="08233-121">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08233-121">Select **OK**.</span></span>
1. <span data-ttu-id="08233-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08233-122">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="08233-123">En el campo **Configuración**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="08233-123">In the **Configuration** field, type a value.</span></span>
    * <span data-ttu-id="08233-124">Escriba un nombre de configuración que hará que sea sencillo identificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="08233-124">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
1. <span data-ttu-id="08233-125">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="08233-125">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="08233-126">Escriba una descripción de la configuración para explicar lo que contiene.</span><span class="sxs-lookup"><span data-stu-id="08233-126">Enter a description of the configuration to explain what it contains.</span></span>  
1. <span data-ttu-id="08233-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08233-127">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]