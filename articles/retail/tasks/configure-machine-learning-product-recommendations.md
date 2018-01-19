--- 
title: "Configurar las recomendaciones del producto accionadas por el aprendizaje automático"
description: "Este procedimiento actualiza los datos en el almacén de entidades que han sido usados por el sistema de aprendizaje automático que acciona las recomendaciones de producto, y, a continuación, habilita las recomendaciones de producto en los clientes de PDV."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 1ee26dfa79bd62ba2d223b9ac4a0171f92ab80ea
ms.contentlocale: es-es
ms.lasthandoff: 01/19/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="5acd0-103">Configurar las recomendaciones del producto accionadas por el aprendizaje automático</span><span class="sxs-lookup"><span data-stu-id="5acd0-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5acd0-104">Este procedimiento actualiza los datos en el almacén de entidades que han sido usados por el sistema de aprendizaje automático que acciona las recomendaciones de producto, y, a continuación, habilita las recomendaciones de producto en los clientes de PDV.</span><span class="sxs-lookup"><span data-stu-id="5acd0-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="5acd0-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="5acd0-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5acd0-106">Vaya a administración del Sistema > Configuración > Almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="5acd0-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="5acd0-107">En la lista, busque y seleccione el registro "RetailSales".</span><span class="sxs-lookup"><span data-stu-id="5acd0-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="5acd0-108">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="5acd0-108">Click Refresh.</span></span>
4. <span data-ttu-id="5acd0-109">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5acd0-109">Click OK.</span></span>
5. <span data-ttu-id="5acd0-110">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5acd0-110">Close the page.</span></span>
6. <span data-ttu-id="5acd0-111">Vaya a Venta minorista y comercio > Configuración de sede central > Parámetros > Parámetros comerciales.</span><span class="sxs-lookup"><span data-stu-id="5acd0-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="5acd0-112">Haga clic en la pestaña del aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="5acd0-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="5acd0-113">Seleccione "Sí" en el campo Habilitar recomendaciones de producto.</span><span class="sxs-lookup"><span data-stu-id="5acd0-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="5acd0-114">Si recibe el mensaje “No se pueden recuperar los modelos de recomendación”, significa que ha actualizado el almacén de entidades muy recientemente y es posible que el sistema no haya terminado de asimilar los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="5acd0-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="5acd0-115">Espere entre 2-3 horas y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="5acd0-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="5acd0-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5acd0-116">Click Save.</span></span>
10. <span data-ttu-id="5acd0-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5acd0-117">Close the page.</span></span>


