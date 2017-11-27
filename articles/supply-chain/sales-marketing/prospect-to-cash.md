---
title: Prospect to cash
description: "Este tema proporciona una visión general de la solución Prospect to cash entre Dynamics 365 for Sales y Dynamics 365 for Finance and Operations, Enterprise Edition y Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: es-es
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="e1778-103">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="e1778-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e1778-104">La solución Prospect to cash usa una opción de [integración de datos](/common-data-service/entity-reference/dynamics-365-integration) para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y Dynamics 365 for Sales a través de Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="e1778-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="e1778-105">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y datos de facturación de ventas entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="e1778-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="e1778-106">A medida que los datos fluyen entre Finance and Operations y Sales, puede realizar ventas y actividades de marketing en Sales y gestionar el cumplimiento de pedidos con la gestión de inventario en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e1778-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="e1778-107">Esta solución proporciona integración en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="e1778-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="e1778-108">Mantener cuentas en Sales y sincronizarlas con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="e1778-109">Mantener contactos en Sales y sincronizarlos con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="e1778-110">Mantener productos en Finance and Operations y sincronizarlos con Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="e1778-111">Crear presupuestos de ventas en Sales y sincronizarlos con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="e1778-112">Crear pedidos de ventas en Finance and Operations y sincronizarlos con Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="e1778-113">Crear facturas de ventas en Finance and Operations y sincronizarlas con Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

<span data-ttu-id="e1778-114">Esta solución proporciona sincronización directa en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="e1778-114">This solution provides direct synchronization in the following areas:</span></span>

-   [<span data-ttu-id="e1778-115">Mantener cuentas en Sales y sincronizarlas directamente de Sales a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-115">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
-   [<span data-ttu-id="e1778-116">Mantener productos en Finance and Operations y sincronizarlos directamente con Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-116">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
-   [<span data-ttu-id="e1778-117">Mantener contactos en Sales y sincronizarlos directamente con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-117">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
-   [<span data-ttu-id="e1778-118">Sincronizar directamente encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-118">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
-   [<span data-ttu-id="e1778-119">Crear pedidos de ventas en Finance and Operations y sincronizarlos directamente con Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-119">Create sales orders in Finance and Operations and sync them directly to Sales</span></span>](sales-order-template-mapping-direct.md)
-  [<span data-ttu-id="e1778-120">Sincronizar encabezados y líneas de pedido de ventas directamente entre Sales y Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-120">Synchronize sales order headers and lines directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-between-sales-fin.md)
-   [<span data-ttu-id="e1778-121">Sincronizar pedidos de ventas directamente entre Sales y Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1778-121">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
-   [<span data-ttu-id="e1778-122">Crear facturas de ventas en Finance and Operations y sincronizarlos directamente con Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-122">Create sales invoices in Finance and Operations and sync them directly to Sales</span></span>](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="e1778-123">Requisitos del sistema para Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e1778-123">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="e1778-124">Para usar la solución Prospect to cash, debe instalar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1778-124">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="e1778-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Julio de 2017) con la actualización de plataforma 8 (aplicación 7.2.11792.56024 con la plataforma 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="e1778-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="e1778-126">Revisiones de Dynamics 365 for Finance and Operations, Enterprise Edition, (julio de 2017).</span><span class="sxs-lookup"><span data-stu-id="e1778-126">Hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>
        
    -  <span data-ttu-id="e1778-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - Esta revisión habilita soporte para la sincronización de pedidos de ventas con la característica de integración de datos de Sales a Finance and Operations, junto con otras mejoras.</span><span class="sxs-lookup"><span data-stu-id="e1778-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - This hotfix enabels support for sales order synchronization with the Data Integration feature from Sales to Finance and Operations, along with a number of other enhancements.</span></span>

    -  <span data-ttu-id="e1778-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2): esta revisión le permite sincronizar la línea de pedidos de ventas con la característica de integración de datos, de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="e1778-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="e1778-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2): esta revisión le permite sincronizar los pedidos de ventas con la característica de integración de datos, de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="e1778-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>

<span data-ttu-id="e1778-130">**Nota**: solo debe instalar KB4045570 porque la instalación incluye los cambios de las otras KB.</span><span class="sxs-lookup"><span data-stu-id="e1778-130">**Note**: You only need to install KB4045570 because the installation includes the changes from the other KB's.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="e1778-131">Requisitos del sistema para Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-131">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="e1778-132">Para usar la solución Prospect to cash, debe instalar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1778-132">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="e1778-133">Dynamics 365 for Sales, versión 1612 (8.2.1.207) (DB 8.2.1.207) en línea.</span><span class="sxs-lookup"><span data-stu-id="e1778-133">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online.</span></span>
- <span data-ttu-id="e1778-134">Solución Prospect to cash para Dynamics 365 for Sales, versión 1.14.0.0 (v14) o posterior.</span><span class="sxs-lookup"><span data-stu-id="e1778-134">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e1778-135">Instalar la solución Prospect to cash para Sales</span><span class="sxs-lookup"><span data-stu-id="e1778-135">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="e1778-136">Descargue el [archivo .zip que contiene el paquete con la solución Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) en CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="e1778-136">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="e1778-137">Asegúrese de que el archivo .zip esté desbloqueado para que así no vea el mensaje de error "No se encontró ningún paquete de importación" al instalar el paquete de la solución.</span><span class="sxs-lookup"><span data-stu-id="e1778-137">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="e1778-138">Para desbloquear el archivo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1778-138">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="e1778-139">Haga clic con el botón derecho en el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="e1778-139">Right-click the zip file.</span></span>
    -  <span data-ttu-id="e1778-140">Seleccione **Propiedades** y **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="e1778-140">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="e1778-141">Descomprima el archivo y ejecute PackageDeployer.exe.</span><span class="sxs-lookup"><span data-stu-id="e1778-141">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="e1778-142">Instale la solución Prospect to cash en su instancia de Sales.</span><span class="sxs-lookup"><span data-stu-id="e1778-142">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="e1778-143">Seleccione el tipo de implementación **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e1778-143">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="e1778-144">Seleccione **Mostrar opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e1778-144">Select **Show advanced**.</span></span>
    - <span data-ttu-id="e1778-145">Para realizar una instalación rápida, seleccione **Región**.</span><span class="sxs-lookup"><span data-stu-id="e1778-145">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="e1778-146">Si selecciona **No lo se**, el sistema busca todas las regiones y le llevará más tiempo realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="e1778-146">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="e1778-147">Escriba el **nombre de usuario** y la **contraseña** de un usuario administrador que tenga los derechos de usuario necesarios para realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="e1778-147">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

