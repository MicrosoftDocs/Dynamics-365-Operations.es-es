---
title: Reglas de configuración
description: Este artículo ofrece información general relativa a las reglas de configuración. Las reglas de configuración definen relaciones entre artículos de una lista de materiales (L. MAT) para los productos que usan la tecnología de configuración basada en dimensiones.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b8b3de89235c6dac52f059af9665ea70f80d83a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007806"
---
# <a name="configuration-rules"></a><span data-ttu-id="3467d-104">Reglas de configuración</span><span class="sxs-lookup"><span data-stu-id="3467d-104">Configuration rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3467d-105">Este artículo ofrece información general relativa a las reglas de configuración.</span><span class="sxs-lookup"><span data-stu-id="3467d-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="3467d-106">Las reglas de configuración definen relaciones entre artículos de una lista de materiales (L. MAT) para los productos que usan la tecnología de configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3467d-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="3467d-107">Las reglas de configuración están disponibles si define modelos de configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3467d-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="3467d-108">Las reglas de configuración se usan para hacer cumplir o prohibir combinaciones específicas de artículos en una lista de materiales (L. MAT.).</span><span class="sxs-lookup"><span data-stu-id="3467d-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="3467d-109">Después de crear una L. MAT. y asignar los artículos relevantes a los grupos de configuración respectivos, pueden definirse una o más reglas de configuración.</span><span class="sxs-lookup"><span data-stu-id="3467d-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="3467d-110">Si dos artículos deben ir juntos, se usará el operador **Seleccionar** para garantizar la inclusión.</span><span class="sxs-lookup"><span data-stu-id="3467d-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="3467d-111">Si dos artículos se excluyen mutuamente, se usa el operador **Anular selección** para garantizar la exclusión.</span><span class="sxs-lookup"><span data-stu-id="3467d-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="3467d-112">**Nota**: esta información solo se aplica a los productos maestros que utilizan la tecnología de configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3467d-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="3467d-113">Las configuraciones existentes no se ven afectadas por los cambios posteriores en las reglas de configuración.</span><span class="sxs-lookup"><span data-stu-id="3467d-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="3467d-114">No obstante, es importante establecer las reglas antes de definir una nueva configuración y comprobarlas si cree que las reglas se han cambiado.</span><span class="sxs-lookup"><span data-stu-id="3467d-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="3467d-115">**Nota**: para el método **Seleccionar**, el grupo de configuración derivado, el número de artículo y la configuración se seleccionan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3467d-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="3467d-116">Para el método **Anular selección**, el grupo de configuración derivado, el número de artículo y la configuración no se pueden seleccionar.</span><span class="sxs-lookup"><span data-stu-id="3467d-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="additional-resources"></a><span data-ttu-id="3467d-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3467d-117">Additional resources</span></span>
--------

[<span data-ttu-id="3467d-118">Visión general de la configuración de producto basada en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3467d-118">Dimension-based product configuration overview</span></span>](dimension-based-product-configuration.md)



