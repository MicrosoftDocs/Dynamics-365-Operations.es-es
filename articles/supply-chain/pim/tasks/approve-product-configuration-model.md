---
title: Aprobar un modelo de configuración de producto
description: La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4767d5dc3944d2595a5b2a74a6d5c7c0ea0c849a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809455"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="63370-103">Aprobar un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="63370-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="63370-104">La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.</span><span class="sxs-lookup"><span data-stu-id="63370-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="63370-105">Este procedimiento usa el modelo Altavoz superior de la empresa de demostración de datos USMF.</span><span class="sxs-lookup"><span data-stu-id="63370-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="63370-106">Tenga en cuenta que ya se ha aprobado este modelo, pero el procedimiento le guía por todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="63370-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="63370-107">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="63370-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="63370-108">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="63370-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="63370-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="63370-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="63370-110">Seleccione el modelo Altavoz superior para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="63370-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="63370-111">Haga clic en Versiones.</span><span class="sxs-lookup"><span data-stu-id="63370-111">Click Versions.</span></span>
5. <span data-ttu-id="63370-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="63370-112">Click New.</span></span>
6. <span data-ttu-id="63370-113">En el campo Número de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63370-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="63370-114">La referencia a un producto representa una versión de un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="63370-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="63370-115">Solo los productos maestros con la tecnología de configuración basada en restricciones aparecerán en esta lista.</span><span class="sxs-lookup"><span data-stu-id="63370-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="63370-116">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="63370-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="63370-117">Seleccione si la versión del modelo de producto estará disponible.</span><span class="sxs-lookup"><span data-stu-id="63370-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="63370-118">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="63370-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="63370-119">Seleccione una fecha final para cuándo expirará esta versión del modelo de producto o seleccione Nunca.</span><span class="sxs-lookup"><span data-stu-id="63370-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="63370-120">Haga clic en Aprobar para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="63370-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="63370-121">En el campo Aprobado por, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63370-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="63370-122">Seleccione la persona responsable de aprobar los modelos de productos para usarlos en operaciones.</span><span class="sxs-lookup"><span data-stu-id="63370-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="63370-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="63370-123">Click OK.</span></span>
12. <span data-ttu-id="63370-124">En el campo Método de cálculo de precios, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="63370-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="63370-125">Active la versión del modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="63370-125">Activate the product model version.</span></span> <span data-ttu-id="63370-126">Solo es posible tener un producto activo para un modelo de producto cada vez.</span><span class="sxs-lookup"><span data-stu-id="63370-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="63370-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="63370-127">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]