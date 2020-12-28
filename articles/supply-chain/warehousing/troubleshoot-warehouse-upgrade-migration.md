---
title: Solucionar problemas de actualización y migración a la gestión avanzada de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al actualizar y migrar a la gestión de almacenes avanzada.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d50c6d75ec7cc98109cf81c38ff42b4d2b105b0c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645826"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="6d5c4-103">Solucionar problemas de actualización y migración a la gestión avanzada de almacenes</span><span class="sxs-lookup"><span data-stu-id="6d5c4-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d5c4-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al actualizar y migrar a la gestión de almacenes avanzada.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="6d5c4-105">Recibo el siguiente mensaje de error: "java.security.cert.certPathValidatorException: no se encuentra el ancla de confianza para la ruta de certificación".</span><span class="sxs-lookup"><span data-stu-id="6d5c4-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="6d5c4-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="6d5c4-106">Issue description</span></span>

<span data-ttu-id="6d5c4-107">Recibe este mensaje de error en la aplicación del almacén, porque los certificados autofirmados no son confiables en Android 8+ en entornos locales.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-107">You receive this error message in the warehouse app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6d5c4-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="6d5c4-108">Issue resolution</span></span>

<span data-ttu-id="6d5c4-109">Utilice una autoridad de certificación (CA) externa (pública).</span><span class="sxs-lookup"><span data-stu-id="6d5c4-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="6d5c4-110">Hay una solución para este problema disponible en la versión 1.9.0.0 de la aplicación de almacén.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="6d5c4-111">Para obtener más información sobre este problema y cómo solucionarlo, consulte [Solucionar problemas de conexión de la aplicación de almacén](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="6d5c4-111">For more information about this issue and how to fix it, see [Troubleshoot warehouse app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="6d5c4-112">¿Cuál es el proceso aprobado para pasar del almacenamiento básico al almacenamiento avanzado?</span><span class="sxs-lookup"><span data-stu-id="6d5c4-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="6d5c4-113">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="6d5c4-113">Issue description</span></span>

<span data-ttu-id="6d5c4-114">Actualmente se encuentra bajo la gestión de existencias / inventario y utiliza la funcionalidad básica de existencias, y desea pasar a un almacenamiento avanzado para aprovechar los dispositivos móviles, las olas y el trabajo.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="6d5c4-115">Sin embargo, está experimentando problemas cuando intenta hacer este movimiento.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="6d5c4-116">Por ejemplo, no puede cambiar sus productos para que utilicen dimensiones de almacenamiento (sitio, almacén y ubicación), porque los productos tienen transacciones contra ellos.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="6d5c4-117">Por lo tanto, debe aprender el proceso aprobado para pasar del almacenamiento básico al almacenamiento avanzado.</span><span class="sxs-lookup"><span data-stu-id="6d5c4-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6d5c4-118">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="6d5c4-118">Issue resolution</span></span>

<span data-ttu-id="6d5c4-119">Para obtener más información sobre el proceso para pasar del almacenamiento básico al almacenamiento avanzado, consulte las siguientes publicaciones de blog y documentación:</span><span class="sxs-lookup"><span data-stu-id="6d5c4-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="6d5c4-120">Habilitar el proceso de gestión de almacén para artículos y almacenes existentes</span><span class="sxs-lookup"><span data-stu-id="6d5c4-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="6d5c4-121">Migración de Microsoft Dynamics AX WMS a la nueva funcionalidad de transporte y almacenamiento R3</span><span class="sxs-lookup"><span data-stu-id="6d5c4-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="6d5c4-122">Migración de elementos WMSI/WMS2</span><span class="sxs-lookup"><span data-stu-id="6d5c4-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="6d5c4-123">Actualizar la gestión de almacenes de Microsoft Dynamics AX 2012 a Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6d5c4-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)
