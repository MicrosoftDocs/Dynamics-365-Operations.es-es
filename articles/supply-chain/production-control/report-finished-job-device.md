---
title: Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo
description: En este tema se describe el proceso para completar los productos terminados en un pedido de producción al inventario cuando una matrícula de entidad controla la ubicación.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 63073035941cd2ef343c65364536fe76a9b71430
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935131"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="b7754-103">Notificar como terminado a una ubicación controlada mediante matrículas de entidad desde un dispositivo de tarjetas de trabajo</span><span class="sxs-lookup"><span data-stu-id="b7754-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="b7754-104">El proceso denominado Informar como terminado completa los productos terminados en un pedido de producción al inventario.</span><span class="sxs-lookup"><span data-stu-id="b7754-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="b7754-105">Si el producto terminado se habilita para los procesos avanzado de almacenes, el producto se notifica como finalizado a una ubicación denominada la ubicación de salida de la producción.</span><span class="sxs-lookup"><span data-stu-id="b7754-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="b7754-106">Para obtener información sobre la configuración de la ubicación de salida de producción, consulte [Ubicación de salida de producción](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="b7754-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="b7754-107">Si la ubicación de salida de producción está controlada por una matrícula, se debe proporcionar una matrícula cuando se notifique su fin.</span><span class="sxs-lookup"><span data-stu-id="b7754-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="b7754-108">El campo **Matrícula de entidad** estará visible en el **Informe de progreso** en la página **Dispositivo de tarjeta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="b7754-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="b7754-109">El campo solo es visible en el cuadro **Informar progreso** al informar sobre la última operación del pedido de producción y cuando el artículo para el pedido de producción está habilitado para los procesos de gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="b7754-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span> 

<span data-ttu-id="b7754-110">Hay dos opciones para proporcionar la matrícula</span><span class="sxs-lookup"><span data-stu-id="b7754-110">There are two options for providing the license plate</span></span>
- <span data-ttu-id="b7754-111">El usuario selecciona matrícula existente en el campo de matrícula.</span><span class="sxs-lookup"><span data-stu-id="b7754-111">The user is selecting an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="b7754-112">La matrícula se genera automáticamente a partir de una secuencia numérica y se establece de forma predeterminada en el campo de matrícula.</span><span class="sxs-lookup"><span data-stu-id="b7754-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="b7754-113">La opción de generar automáticamente la matrícula se configura seleccionando la opción **Generar matrícula de entidad de almacén** en la página **Configurar tarjeta de trabajo para dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7754-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>
