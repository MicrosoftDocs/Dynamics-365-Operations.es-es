---
title: "Seleccionar el lote más antiguo en un dispositivo móvil"
description: "Este tema describe cómo configurar y aplicar las opciones para seleccionar el lote más antiguo desde un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 8e5ddb8991d98aafc0a18788107ee65f0a950059
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="9e2fe-103">Seleccionar el lote más antiguo en un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="9e2fe-103">Pick oldest batch on a mobile device</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9e2fe-104">Puede acceder a la configuración **Seleccionar lote más antiguo** mediante un menú de dispositivo móvil y le permite forzar o advertir a trabajadores de almacén que seleccionen el lote más antiguo de su ubicación actual.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="9e2fe-105">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="9e2fe-105">Where it applies</span></span>
<span data-ttu-id="9e2fe-106">Seleccionar lote más antiguo se configura en elementos de menú del dispositivo móvil y realiza la selección de artículos del lote siguiente.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="9e2fe-107">Cómo ajustar la configuración de Seleccionar lote más antiguo</span><span class="sxs-lookup"><span data-stu-id="9e2fe-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="9e2fe-108">Para los artículos configurados para usar el trabajo existente, **Seleccionar lote más antiguo** se puede establecer en **Ninguno**, **Advertencia**, o **Forzar** en un menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="9e2fe-109">**Ninguno**: los trabajadores no recibirán ningún mensaje y podrán seleccionar los lotes en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="9e2fe-110">**Advertencia** y **Forzar**: una lista de lotes con la fecha de vencimiento más antigua se mostrará sobre el control de lotes cuando el trabajador seleccione un lote.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="9e2fe-111">Si la ubicación está controlada por matrículas, una lista de matrículas que tengan el lote más antiguo se mostrará sobre el control del número de matrícula.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="9e2fe-112">**Advertencia**: si un trabajador elige una matrícula o lote que no se encuentren en la lista mostrada, el control queda en blanco y se muestra una advertencia de que hay un lote más antiguo para seleccionar.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="9e2fe-113">Para poder continuar el trabajo, el trabajador puede volver a seleccionar la misma matrícula o lote.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="9e2fe-114">**Forzar**: los trabajadores seguirán recibiendo el mensaje de que hay un lote más antiguo que se puede seleccionar.</span><span class="sxs-lookup"><span data-stu-id="9e2fe-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>

