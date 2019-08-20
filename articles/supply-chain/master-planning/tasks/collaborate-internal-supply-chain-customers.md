---
title: Colaborar con clientes de cadena de suministro interna
description: Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 930a986b6dfe40d4d40de1f9ee8b1e4b88371166
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835991"
---
# <a name="collaborate-with-internal-supply-chain-customers"></a><span data-ttu-id="0816b-103">Colaborar con clientes de cadena de suministro interna</span><span class="sxs-lookup"><span data-stu-id="0816b-103">Collaborate with internal supply chain customers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0816b-104">Este procedimiento muestra cómo ver todos los pedidos planificados que cumplirá un proveedor de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="0816b-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="0816b-105">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="0816b-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="0816b-106">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="0816b-106">Click Master planning.</span></span>
2. <span data-ttu-id="0816b-107">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0816b-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="0816b-108">Seleccione el plan 10 en el campo Plan.</span><span class="sxs-lookup"><span data-stu-id="0816b-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="0816b-109">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0816b-109">Click Run.</span></span>
4. <span data-ttu-id="0816b-110">En el campo Número de subprocesos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="0816b-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="0816b-111">Esto representa el número de subprocesos paralelos que se utilizarán para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="0816b-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="0816b-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0816b-112">Click OK.</span></span>
    * <span data-ttu-id="0816b-113">Esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="0816b-113">This may take a while.</span></span>  
6. <span data-ttu-id="0816b-114">Haga clic en Demanda planificada de empresa vinculada.</span><span class="sxs-lookup"><span data-stu-id="0816b-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="0816b-115">Haga clic en Demanda planificada de empresa vinculada saliente.</span><span class="sxs-lookup"><span data-stu-id="0816b-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="0816b-116">Esta página ofrece una visión general de toda la demanda planificada que cumplirá un proveedor interno de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="0816b-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="0816b-117">Expanda la sección de los detalles de la demanda de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="0816b-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="0816b-118">En esta sección, puede ver detalles acerca de cómo se cumplirá con la demanda.</span><span class="sxs-lookup"><span data-stu-id="0816b-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="0816b-119">Es posible que tenga que esperar la planificación maestra que se ejecutará en la empresa de aprovisionamiento antes de que se pueda ver información adicional aquí.</span><span class="sxs-lookup"><span data-stu-id="0816b-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

