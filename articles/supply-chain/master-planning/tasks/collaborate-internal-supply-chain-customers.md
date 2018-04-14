--- 
title: Colaborar con clientes de cadena de suministro interna
description: "Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas."
author: roxanadiaconu
manager: AnnBe
ms.date: 10/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 109c3efae72df878a0d0966e528fe79b6bb97fd9
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="collaborate-with-internal-supply-chain-customers"></a><span data-ttu-id="b818f-103">Colaborar con clientes de cadena de suministro interna</span><span class="sxs-lookup"><span data-stu-id="b818f-103">Collaborate with internal supply chain customers</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b818f-104">Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="b818f-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="b818f-105">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="b818f-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="b818f-106">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="b818f-106">Click Master planning.</span></span>
2. <span data-ttu-id="b818f-107">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b818f-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="b818f-108">Seleccione el plan 10 en el campo Plan.</span><span class="sxs-lookup"><span data-stu-id="b818f-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="b818f-109">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b818f-109">Click Run.</span></span>
4. <span data-ttu-id="b818f-110">En el campo Número de subprocesos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b818f-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="b818f-111">Esto representa el número de subprocesos paralelos que se utilizarán para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="b818f-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="b818f-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b818f-112">Click OK.</span></span>
    * <span data-ttu-id="b818f-113">Esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="b818f-113">This may take a while.</span></span>  
6. <span data-ttu-id="b818f-114">Haga clic en Demanda planificada de empresa vinculada.</span><span class="sxs-lookup"><span data-stu-id="b818f-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="b818f-115">Haga clic en Demanda planificada de empresa vinculada saliente.</span><span class="sxs-lookup"><span data-stu-id="b818f-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="b818f-116">Esta página ofrece una visión general de toda la demanda planificada que cumplirá un proveedor interno de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="b818f-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="b818f-117">Expanda la sección de los detalles de la demanda de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b818f-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="b818f-118">En esta sección, puede ver detalles acerca de cómo se cumplirá con la demanda.</span><span class="sxs-lookup"><span data-stu-id="b818f-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="b818f-119">Es posible que tenga que esperar la planificación maestra que se ejecutará en la empresa de aprovisionamiento antes de que se pueda ver información adicional aquí.</span><span class="sxs-lookup"><span data-stu-id="b818f-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  


