---
title: Solucionar problemas de trabajo de almacén
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con trabajo de almacenes en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 08cc074fe851b952ebfc942ae3d1cb05240d3b91
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837450"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="3bc59-103">Solucionar problemas de trabajo de almacén</span><span class="sxs-lookup"><span data-stu-id="3bc59-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3bc59-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con trabajo de almacenes en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3bc59-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="3bc59-105">No puedo mover placas de matrícula que tienen elementos de número de serie cuando se permiten la emisión en blanco y el recibo en blanco en el grupo de dimensiones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3bc59-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3bc59-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="3bc59-106">Issue description</span></span>

<span data-ttu-id="3bc59-107">No puede mover una matrícula usando un elemento de menú **Movimiento** si el número de serie tiene ajustes *Se permite un problema en blanco* y *Recibo en blanco permitido* en el grupo de dimensiones de seguimiento, y si hay varias placas de matrícula en la misma ubicación, algunas de las cuales tienen números de serie y otras no.</span><span class="sxs-lookup"><span data-stu-id="3bc59-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3bc59-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="3bc59-108">Issue resolution</span></span>

<span data-ttu-id="3bc59-109">Este problema se solucionará con los cambios implementados en [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="3bc59-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="3bc59-110">Esos cambios harán que el campo opcional **Número de serie** cuando se permiten recibo en blanco y emisión en blanco.</span><span class="sxs-lookup"><span data-stu-id="3bc59-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-management-mobile-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="3bc59-111">Recibo el siguiente mensaje de error en la aplicación móvil Warehouse Management cuando proceso movimientos: "El propietario del inventario %1 no está permitido en este proceso".</span><span class="sxs-lookup"><span data-stu-id="3bc59-111">I receive the following error message in the Warehouse Management mobile app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3bc59-112">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="3bc59-112">Issue description</span></span>

<span data-ttu-id="3bc59-113">La dimensión de seguimiento **Propietario** falta cuando se utiliza la aplicación móvil Warehouse Management para realizar movimientos.</span><span class="sxs-lookup"><span data-stu-id="3bc59-113">The **Owner** tracking dimension is missing when the Warehouse Management mobile app is used to make movements.</span></span> <span data-ttu-id="3bc59-114">Un diario de transferencia de inventario regular del cliente de Supply Chain Management parece funcionar según lo previsto y solo se puede registrar si la dimensión **Propietario** se completa.</span><span class="sxs-lookup"><span data-stu-id="3bc59-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3bc59-115">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="3bc59-115">Issue resolution</span></span>

<span data-ttu-id="3bc59-116">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="3bc59-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="3bc59-117">Actualmente, los procesos de gestión de almacenes solo admiten el inventario que es propiedad de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="3bc59-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]