---
title: Cambiar entre diseños de proveedor
description: Este tema describe como cambiar entre la integración de datos de proveedor entre aplicaciones de Finance and Operations y Common Data Service.
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
ms.openlocfilehash: 587a9b98f28b11e303aff4b59e9726f220d956eb
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019993"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="a87aa-103">Cambiar entre diseños de proveedor</span><span class="sxs-lookup"><span data-stu-id="a87aa-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="a87aa-104">Flujo de datos del proveedor</span><span class="sxs-lookup"><span data-stu-id="a87aa-104">Vendor data flow</span></span> 

<span data-ttu-id="a87aa-105">Si usa otras aplicaciones de Dynamics 365 para el control de proveedores y desea aislar la información de proveedor de los clientes, use este diseño de proveedor básico.</span><span class="sxs-lookup"><span data-stu-id="a87aa-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Flujo básico del proveedor](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="a87aa-107">Si usa otras aplicaciones Dynamics 365 para el control de proveedores y desea seguir usando la entidad **Cuenta** para almacenar la información de proveedor, use este diseño de proveedor ampliado.</span><span class="sxs-lookup"><span data-stu-id="a87aa-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="a87aa-108">En este diseño, la información de proveedor extendida, como el estado en espera del proveedor y el perfil de proveedor, se almacena en la entidad **proveedores** en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a87aa-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Flujo ampliado del proveedor](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="a87aa-110">Siga los pasos siguientes para usar el diseño de proveedor extendido:</span><span class="sxs-lookup"><span data-stu-id="a87aa-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="a87aa-111">El paquete de solución **SupplyChainCommon** contiene las plantillas el proceso de flujo de trabajo tal y como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="a87aa-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a87aa-112">![Plantillas de proceso de flujo de trabajo](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="a87aa-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="a87aa-113">Cree nuevos procesos de flujo de trabajo mediante las plantillas de proceso de flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="a87aa-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="a87aa-114">Cree un nuevo proceso de flujo de trabajo para la entidad **Proveedor** mediante la plantilla del proceso de flujo de trabajo **Crear proveedores en la entidad cuenta** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a87aa-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="a87aa-115">Este flujo de trabajo gestiona el escenario de creación de proveedor para la entidad **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="a87aa-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="a87aa-116">![Crear proveedores en la entidad cuenta](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="a87aa-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="a87aa-117">Cree un nuevo proceso de flujo de trabajo para la entidad **Proveedor** mediante la plantilla del proceso de flujo de trabajo **Actualizar entidad Cuentas** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a87aa-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="a87aa-118">Este flujo de trabajo gestiona el escenario de actualización de proveedor para la entidad **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="a87aa-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="a87aa-119">![Actualizar la entidad Cuentas](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="a87aa-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="a87aa-120">Cree nuevos procesos de flujo de trabajo a partir de las plantillas creadas en la entidad **Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="a87aa-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="a87aa-121">![Crear proveedores en la entidad proveedores](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="a87aa-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="a87aa-122">![Actualizar la entidad de proveedores](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="a87aa-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="a87aa-123">Puede configurar los flujos de trabajo como flujos de trabajo en tiempo real o de fondo en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a87aa-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="a87aa-124">![Convertir a un flujo de trabajo de fondo](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="a87aa-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="a87aa-125">Active los flujos de trabajo que ha creado en las entidades **Cuenta** y **Proveedor** para comenzar a utilizar la entidad **Cuenta** para almacenar información del proveedor.</span><span class="sxs-lookup"><span data-stu-id="a87aa-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
