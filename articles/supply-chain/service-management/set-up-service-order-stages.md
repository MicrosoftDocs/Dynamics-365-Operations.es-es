---
title: Configurar las etapas de pedido de servicio
description: Configurar las etapas de pedido de servicio.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30f6a6afa6ab91bed41bb19b8312dc7e25bd2478
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551728"
---
# <a name="set-up-service-order-stages"></a><span data-ttu-id="c5d6a-103">Configurar las etapas de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="c5d6a-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="c5d6a-104">Haga clic en **Gestión de servicio** \> **Configuración** \> **Pedidos de servicio** \> **Etapas de servicio**.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-104">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="c5d6a-105">Presione CTRL+N para crear un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-105">Press CTRL+N to create a new record.</span></span>

3.  <span data-ttu-id="c5d6a-106">En los campos **Etapa de servicio** y **Descripción**, especifique un id. de etapa de servicio y una descripción.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="c5d6a-107">Seleccione el parámetro más adecuado para la etapa.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="c5d6a-108">Seleccione la etapa principal para la etapa actual o deje el campo **Principal** en blanco si la etapa es la etapa inicial en la configuración de etapa.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c5d6a-109">No puede modificar el campo <STRONG>Principal</STRONG> después de guardar la etapa.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="c5d6a-110">En lugar de ello, deberá eliminar el registro y crearlo de nuevo con una selección diferente en el campo <STRONG>Principal</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="c5d6a-111">Además, sólo puede crear una etapa con un campo <STRONG>Principal</STRONG> en blanco.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="c5d6a-112">Es decir, sólo se permite una sola etapa inicial.</span><span class="sxs-lookup"><span data-stu-id="c5d6a-112">That is, only one initial stage is permitted.</span></span></P>


  


