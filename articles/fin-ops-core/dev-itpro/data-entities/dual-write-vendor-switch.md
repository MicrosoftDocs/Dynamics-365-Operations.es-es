---
title: Cambiar entre los diseños de proveedor
description: ''
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 4e97ff0b0e6195b5e3703e15a0bb0de7644ef8d1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772373"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="d4057-102">Cambiar entre los diseños de proveedor</span><span class="sxs-lookup"><span data-stu-id="d4057-102">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="d4057-103">Flujo de datos del proveedor</span><span class="sxs-lookup"><span data-stu-id="d4057-103">Vendor data flow</span></span> 

<span data-ttu-id="d4057-104">Si usa otras aplicaciones de Dynamics 365 para el control de proveedores y desea aislar la información de proveedor de los clientes, use este diseño de proveedor básico.</span><span class="sxs-lookup"><span data-stu-id="d4057-104">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Flujo básico del proveedor](media/dual-write-switch-1.png)
 
<span data-ttu-id="d4057-106">Si usa otras aplicaciones Dynamics 365 para el control de proveedores y desea seguir usando la entidad **Cuenta** para almacenar la información de proveedor, use este diseño de proveedor ampliado.</span><span class="sxs-lookup"><span data-stu-id="d4057-106">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="d4057-107">En este diseño, la información de proveedor extendida, como el estado en espera del proveedor y el perfil de proveedor, se almacena en la entidad **proveedores** en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d4057-107">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Flujo ampliado del proveedor](media/dual-write-switch-2.png)
 
<span data-ttu-id="d4057-109">Siga los pasos siguientes para usar el diseño de proveedor extendido:</span><span class="sxs-lookup"><span data-stu-id="d4057-109">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="d4057-110">El paquete de solución **SupplyChainCommon** contiene las plantillas el proceso de flujo de trabajo tal y como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4057-110">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d4057-111">![Plantillas de proceso de flujo de trabajo](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="d4057-111">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="d4057-112">Cree nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="d4057-112">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="d4057-113">Cree un nuevo proceso de flujo de trabajo para la entidad **Proveedor** mediante la plantilla del proceso de flujo de trabajo **Crear proveedores en la entidad cuenta** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4057-113">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="d4057-114">Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="d4057-114">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d4057-115">![Crear proveedores en la entidad cuenta](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="d4057-115">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="d4057-116">Cree un nuevo proceso de flujo de trabajo para la entidad **Proveedor** mediante la plantilla del proceso de flujo de trabajo **Actualizar entidad Cuentas** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4057-116">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="d4057-117">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="d4057-117">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d4057-118">![Actualizar la entidad Cuentas](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="d4057-118">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="d4057-119">Cree nuevos procesos de flujo de trabajo a partir de las plantillas creadas en la entidad **Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="d4057-119">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d4057-120">![Crear proveedores en la entidad proveedores](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="d4057-120">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="d4057-121">![Actualizar la entidad de proveedores](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="d4057-121">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="d4057-122">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o de fondo en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d4057-122">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d4057-123">![Convertir a un flujo de trabajo de fondo](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="d4057-123">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="d4057-124">Active los flujos de trabajo que ha creado en las entidades **Cuenta** y **Proveedor** para comenzar a utilizar la entidad **Cuenta** de Customer Engagement para almacenar información del proveedor.</span><span class="sxs-lookup"><span data-stu-id="d4057-124">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the Customer Engagement **Account** entity for storing vendor information.</span></span> 
 
