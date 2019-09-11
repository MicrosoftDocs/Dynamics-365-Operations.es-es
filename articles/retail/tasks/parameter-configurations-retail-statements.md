---
title: Configurar parámetros de Retail que afectan a extractos comerciales
description: Este tema muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867280"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a><span data-ttu-id="5bb6b-103">Configurar parámetros de Retail que afectan a extractos comerciales</span><span class="sxs-lookup"><span data-stu-id="5bb6b-103">Configure Retail parameters that affect retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5bb6b-104">Este tema muestra las configuraciones para los Parámetros comerciales que afectan la manera en que se crean y se registran los extractos comerciales.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-104">This topic demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="5bb6b-105">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="5bb6b-106">En el panel de navegación, vaya a **Módulos > Venta minorista y comercio > Configuración de sede central > Parámetros > Parámetros comerciales**.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-106">In the navigation pane, go to **Modules > Retail and commerce > Headquarters setup  > Parameters > Retail parameters**.</span></span>
2. <span data-ttu-id="5bb6b-107">Seleccione la pestaña **Registro**.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="5bb6b-108">Seleccione **Sí** si desea registrar los importes de descuento periódicos de manera específica.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="5bb6b-109">Seleccione **Estándar** para usar cuentas predeterminadas, o seleccione **Periódico** si desea definir qué cuenta se usará para cada descuento periódico.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="5bb6b-110">Seleccione **Resumen** si se deben agregar las líneas de inventario siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="5bb6b-111">Seleccione **Sí** si Facturas y pagos se deben liquidar automáticamente como parte del proceso de contabilización de extractos.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="5bb6b-112">Seleccione **Sí** si se deben agregar transacciones de ingresos seguros.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="5bb6b-113">Seleccione **Sí** si se deben agregar transacciones de ingreso bancario.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="5bb6b-114">Seleccione **Sí** para activar la agregación para la contabilización de extractos.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="5bb6b-115">Seleccione **Sí** para crear y procesar pedidos en paralelo cuando se registran extractos.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="5bb6b-116">Especifique los pedidos máximos que se procesarán en cada tarea de trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="5bb6b-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5bb6b-117">Select **Save**.</span></span>

