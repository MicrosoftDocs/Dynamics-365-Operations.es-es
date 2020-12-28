---
title: Ver demanda planificada de empresa vinculada saliente
description: Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 259ce229c18466b7d29fd231dc3f0be8a6906c6b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436628"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="bc04c-103">Ver demanda planificada de empresa vinculada saliente</span><span class="sxs-lookup"><span data-stu-id="bc04c-103">View outbound planned intercompany demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc04c-104">Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="bc04c-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="bc04c-105">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="bc04c-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="bc04c-106">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="bc04c-106">Click Master planning.</span></span>
2. <span data-ttu-id="bc04c-107">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc04c-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="bc04c-108">Seleccione el plan 10 en el campo Plan.</span><span class="sxs-lookup"><span data-stu-id="bc04c-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="bc04c-109">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="bc04c-109">Click Run.</span></span>
4. <span data-ttu-id="bc04c-110">En el campo Número de subprocesos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="bc04c-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="bc04c-111">Esto representa el número de subprocesos paralelos que se utilizarán para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="bc04c-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="bc04c-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc04c-112">Click OK.</span></span>
    * <span data-ttu-id="bc04c-113">Esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="bc04c-113">This may take a while.</span></span>  
6. <span data-ttu-id="bc04c-114">Haga clic en Demanda planificada de empresa vinculada.</span><span class="sxs-lookup"><span data-stu-id="bc04c-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="bc04c-115">Haga clic en Demanda planificada de empresa vinculada saliente.</span><span class="sxs-lookup"><span data-stu-id="bc04c-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="bc04c-116">Esta página ofrece una visión general de toda la demanda planificada que cumplirá un proveedor interno de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="bc04c-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="bc04c-117">Expanda la sección de los detalles de la demanda de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="bc04c-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="bc04c-118">En esta sección, puede ver detalles acerca de cómo se cumplirá con la demanda.</span><span class="sxs-lookup"><span data-stu-id="bc04c-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="bc04c-119">Es posible que tenga que esperar la planificación maestra que se ejecutará en la empresa de aprovisionamiento antes de que se pueda ver información adicional aquí.</span><span class="sxs-lookup"><span data-stu-id="bc04c-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

