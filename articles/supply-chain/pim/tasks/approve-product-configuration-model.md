---
title: Aprobar un modelo de configuración de producto
description: La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eef6568e012c311c0e5438245c011b876fc4d522
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844979"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="50edc-103">Aprobar un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="50edc-103">Approve a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50edc-104">La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.</span><span class="sxs-lookup"><span data-stu-id="50edc-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="50edc-105">Este procedimiento usa el modelo Altavoz superior de la empresa de demostración de datos USMF.</span><span class="sxs-lookup"><span data-stu-id="50edc-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="50edc-106">Tenga en cuenta que ya se ha aprobado este modelo, pero el procedimiento le guía por todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="50edc-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="50edc-107">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="50edc-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="50edc-108">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="50edc-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="50edc-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="50edc-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="50edc-110">Seleccione el modelo Altavoz superior para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="50edc-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="50edc-111">Haga clic en Versiones.</span><span class="sxs-lookup"><span data-stu-id="50edc-111">Click Versions.</span></span>
5. <span data-ttu-id="50edc-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="50edc-112">Click New.</span></span>
6. <span data-ttu-id="50edc-113">En el campo Número de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50edc-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="50edc-114">La referencia a un producto representa una versión de un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="50edc-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="50edc-115">Solo los productos maestros con la tecnología de configuración basada en restricciones aparecerán en esta lista.</span><span class="sxs-lookup"><span data-stu-id="50edc-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="50edc-116">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="50edc-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="50edc-117">Seleccione si la versión del modelo de producto estará disponible.</span><span class="sxs-lookup"><span data-stu-id="50edc-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="50edc-118">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="50edc-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="50edc-119">Seleccione una fecha final para cuándo expirará esta versión del modelo de producto o seleccione Nunca.</span><span class="sxs-lookup"><span data-stu-id="50edc-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="50edc-120">Haga clic en Aprobar para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="50edc-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="50edc-121">En el campo Aprobado por, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="50edc-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="50edc-122">Seleccione la persona responsable de aprobar los modelos de productos para usarlos en operaciones.</span><span class="sxs-lookup"><span data-stu-id="50edc-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="50edc-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="50edc-123">Click OK.</span></span>
12. <span data-ttu-id="50edc-124">En el campo Método de cálculo de precios, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="50edc-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="50edc-125">Active la versión del modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="50edc-125">Activate the product model version.</span></span> <span data-ttu-id="50edc-126">Solo es posible tener un producto activo para un modelo de producto cada vez.</span><span class="sxs-lookup"><span data-stu-id="50edc-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="50edc-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="50edc-127">Close the page.</span></span>

