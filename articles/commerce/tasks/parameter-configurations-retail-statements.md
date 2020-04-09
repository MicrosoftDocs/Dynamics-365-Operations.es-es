---
title: Configurar parámetros que afectan a extractos comerciales
description: Este tema muestra las configuraciones para los parámetros de Commerce que afectan la manera en que se crean y se registran los extractos.
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
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140854"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="18841-103">Configurar parámetros que afectan a extractos comerciales</span><span class="sxs-lookup"><span data-stu-id="18841-103">Configure parameters that affect retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18841-104">Este tema muestra las configuraciones para los parámetros de Commerce que afectan la manera en que se crean y se registran los extractos.</span><span class="sxs-lookup"><span data-stu-id="18841-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="18841-105">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="18841-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="18841-106">En el panel de navegación, vaya a **Módulos > Retail y Commerce > Configuración de sede central > Parámetros > Parámetros de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="18841-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="18841-107">Seleccione la pestaña **Registro**.</span><span class="sxs-lookup"><span data-stu-id="18841-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="18841-108">Seleccione **Sí** si desea registrar los importes de descuento periódicos de manera específica.</span><span class="sxs-lookup"><span data-stu-id="18841-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="18841-109">Seleccione **Estándar** para usar cuentas predeterminadas, o seleccione **Periódico** si desea definir qué cuenta se usará para cada descuento periódico.</span><span class="sxs-lookup"><span data-stu-id="18841-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="18841-110">Seleccione **Resumen** si se deben agregar las líneas de inventario siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="18841-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="18841-111">Seleccione **Sí** si Facturas y pagos se deben liquidar automáticamente como parte del proceso de contabilización de extractos.</span><span class="sxs-lookup"><span data-stu-id="18841-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="18841-112">Seleccione **Sí** si se deben agregar transacciones de ingresos seguros.</span><span class="sxs-lookup"><span data-stu-id="18841-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="18841-113">Seleccione **Sí** si se deben agregar transacciones de ingreso bancario.</span><span class="sxs-lookup"><span data-stu-id="18841-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="18841-114">Seleccione **Sí** para activar la agregación para la contabilización de extractos.</span><span class="sxs-lookup"><span data-stu-id="18841-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="18841-115">Seleccione **Sí** para crear y procesar pedidos en paralelo cuando se registran extractos.</span><span class="sxs-lookup"><span data-stu-id="18841-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="18841-116">Especifique los pedidos máximos que se procesarán en cada tarea de trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="18841-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="18841-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="18841-117">Select **Save**.</span></span>

