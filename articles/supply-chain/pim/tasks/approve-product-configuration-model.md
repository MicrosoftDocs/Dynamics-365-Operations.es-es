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
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920516"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="b5ca4-103">Aprobar un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="b5ca4-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5ca4-104">La ejecución de este procedimiento requiere que haya al menos un modelo de configuración de producto disponible.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="b5ca4-105">Este procedimiento usa el modelo Altavoz superior de la empresa de demostración de datos USMF.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="b5ca4-106">Tenga en cuenta que ya se ha aprobado este modelo, pero el procedimiento le guía por todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="b5ca4-107">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="b5ca4-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b5ca4-109">Seleccione el modelo Altavoz superior para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-109">Select the High end speaker model for this procedure.</span></span>  
1. <span data-ttu-id="b5ca4-110">Seleccione **Versiones**.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-110">Select **Versions**.</span></span>
1. <span data-ttu-id="b5ca4-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-111">Select **New**.</span></span>
1. <span data-ttu-id="b5ca4-112">En el campo **Número de producto**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-112">In the **Product number** field, enter or select a value.</span></span>
    * <span data-ttu-id="b5ca4-113">La referencia a un producto representa una versión de un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-113">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="b5ca4-114">Solo los productos maestros con la tecnología de configuración basada en restricciones aparecerán en esta lista.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-114">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
1. <span data-ttu-id="b5ca4-115">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-115">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="b5ca4-116">Seleccione si la versión del modelo de producto estará disponible.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-116">Select when the product model version will be available.</span></span>  
1. <span data-ttu-id="b5ca4-117">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-117">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="b5ca4-118">Seleccione una fecha final para cuándo expirará esta versión del modelo de producto o seleccione Nunca.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-118">Select an end date when this product model version will expire, or select Never.</span></span>  
1. <span data-ttu-id="b5ca4-119">Seleccione **Aprobar** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-119">Select **Approve** to open the drop dialog.</span></span>
1. <span data-ttu-id="b5ca4-120">En el campo **Aprobado por**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-120">In the **Approved by** field, enter or select a value.</span></span>
    * <span data-ttu-id="b5ca4-121">Seleccione la persona responsable de aprobar los modelos de productos para usarlos en operaciones.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-121">Select the person who is responsible for approving product models for use in operations.</span></span>  
1. <span data-ttu-id="b5ca4-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-122">Select **OK**.</span></span>
1. <span data-ttu-id="b5ca4-123">En el campo **Método de cálculo de precios**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-123">In the **Pricing method** field, select an option.</span></span>
    * <span data-ttu-id="b5ca4-124">Active la versión del modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-124">Activate the product model version.</span></span> <span data-ttu-id="b5ca4-125">Solo es posible tener un producto activo para un modelo de producto cada vez.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-125">It is only possible to have one product active for one product model at a time.</span></span>  
1. <span data-ttu-id="b5ca4-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b5ca4-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]