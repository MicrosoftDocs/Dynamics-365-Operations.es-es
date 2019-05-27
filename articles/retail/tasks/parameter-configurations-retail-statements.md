---
title: Configuración de parámetros para los extractos de Retail
description: Este procedimiento muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6dacd2b80ca0d51d81d2bdf5bc2636b47da621ee
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564302"
---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="12a22-103">Configuración de parámetros para los extractos de Retail</span><span class="sxs-lookup"><span data-stu-id="12a22-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="12a22-104">Este procedimiento muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales.</span><span class="sxs-lookup"><span data-stu-id="12a22-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="12a22-105">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="12a22-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="12a22-106">Vaya a Venta minorista y comercio > Configuración de sede minorista > Parámetros > Parámetros comerciales.</span><span class="sxs-lookup"><span data-stu-id="12a22-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="12a22-107">Haga clic en la ficha Registro.</span><span class="sxs-lookup"><span data-stu-id="12a22-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="12a22-108">Seleccione "Sí" si desea registrar los importes de descuento periódicos de manera específica.</span><span class="sxs-lookup"><span data-stu-id="12a22-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="12a22-109">Seleccione “Estándar” para usar cuentas predeterminadas, o seleccione “Periódico” si desea definir qué cuenta se usará para cada descuento periódico.</span><span class="sxs-lookup"><span data-stu-id="12a22-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="12a22-110">Seleccione “Resumen” si se deben agregar las líneas de inventario siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="12a22-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="12a22-111">Seleccione “Sí” si Facturas y pagos se deben liquidar automáticamente como parte del proceso de contabilización de extractos.</span><span class="sxs-lookup"><span data-stu-id="12a22-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="12a22-112">Seleccione “Sí” si se deben agregar transacciones de ingresos seguros.</span><span class="sxs-lookup"><span data-stu-id="12a22-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="12a22-113">Seleccione “Sí” si se deben agregar transacciones de ingreso bancario.</span><span class="sxs-lookup"><span data-stu-id="12a22-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="12a22-114">Seleccione "Sí" para activar la agregación para la contabilización de extractos.</span><span class="sxs-lookup"><span data-stu-id="12a22-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="12a22-115">Seleccione "Sí" para crear y procesar pedidos en paralelo cuando se registran extractos.</span><span class="sxs-lookup"><span data-stu-id="12a22-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="12a22-116">Especifique los pedidos máximos que se procesarán en cada tarea de trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="12a22-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="12a22-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="12a22-117">Click Save.</span></span>

