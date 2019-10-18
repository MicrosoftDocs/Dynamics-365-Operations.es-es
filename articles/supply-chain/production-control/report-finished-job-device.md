---
title: Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo
description: En este tema se describe el proceso para completar los productos terminados en un pedido de producción al inventario cuando una matrícula de entidad controla la ubicación.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 35ad27a6b8a52bfd086fbe4fc57b1681ff88fd5b
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995151"
---
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="0cae9-103">Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo</span><span class="sxs-lookup"><span data-stu-id="0cae9-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="0cae9-104">El proceso denominado Informar como terminado completa los productos terminados en un pedido de producción al inventario.</span><span class="sxs-lookup"><span data-stu-id="0cae9-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="0cae9-105">Si el producto terminado se habilita para los procesos avanzado de almacenes, el producto se notifica como finalizado a una ubicación denominada la ubicación de salida de la producción.</span><span class="sxs-lookup"><span data-stu-id="0cae9-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="0cae9-106">Para obtener información sobre la configuración de la ubicación de salida de producción, consulte [Ubicación de salida de producción](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="0cae9-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="0cae9-107">Debe seleccionar un número de matrícula de entidad de almacén para completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0cae9-107">You must select an existing license plate number to complete this task.</span></span> <span data-ttu-id="0cae9-108">Si la ubicación de salida de la producción está configurada para ser seguida por la matrícula de entidad, entonces debe incluirse una matrícula de entidad de almacén cuando se informe de la ubicación de salida de producción como finalizada.</span><span class="sxs-lookup"><span data-stu-id="0cae9-108">If the production output location is set up to be tracked by license plate, then a license plate number must be included when reporting the production output location as finished.</span></span> <span data-ttu-id="0cae9-109">El campo **Matrícula de entidad** estará visible en el **Informe de progreso** en la página **Dispositivo de tarjeta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0cae9-109">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="0cae9-110">El campo sólo está visible en el **Informe de progreso** al notificar la última operación del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="0cae9-110">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order.</span></span> <span data-ttu-id="0cae9-111">El campo solo se muestra si el artículo para el pedido de producción se habilita para los procesos de la gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="0cae9-111">The field is only shown if the item for the production order is enabled for the warehouse management processes.</span></span> 
