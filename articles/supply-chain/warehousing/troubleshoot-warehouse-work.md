---
title: Solucionar problemas de trabajo de almacén
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con trabajo de almacenes en Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: b1814f7b23efda2cabdb7bfc7bea4de6e3d6ec2f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237068"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="8dd8e-103">Solucionar problemas de trabajo de almacén</span><span class="sxs-lookup"><span data-stu-id="8dd8e-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8dd8e-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con trabajo de almacenes en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="8dd8e-105">No puedo mover placas de matrícula que tienen elementos de número de serie cuando se permiten la emisión en blanco y el recibo en blanco en el grupo de dimensiones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8dd8e-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="8dd8e-106">Issue description</span></span>

<span data-ttu-id="8dd8e-107">No puede mover una matrícula usando un elemento de menú **Movimiento** si el número de serie tiene ajustes *Se permite un problema en blanco* y *Recibo en blanco permitido* en el grupo de dimensiones de seguimiento, y si hay varias placas de matrícula en la misma ubicación, algunas de las cuales tienen números de serie y otras no.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8dd8e-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="8dd8e-108">Issue resolution</span></span>

<span data-ttu-id="8dd8e-109">Este problema se solucionará con los cambios implementados en [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="8dd8e-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="8dd8e-110">Esos cambios harán que el campo opcional **Número de serie** cuando se permiten recibo en blanco y emisión en blanco.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="8dd8e-111">Recibo el siguiente mensaje de error en la aplicación del almacén cuando proceso movimientos: "El propietario del inventario %1 no está permitido en este proceso".</span><span class="sxs-lookup"><span data-stu-id="8dd8e-111">I receive the following error message in the warehouse app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8dd8e-112">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="8dd8e-112">Issue description</span></span>

<span data-ttu-id="8dd8e-113">La dimensión de seguimiento **Propietario** falta cuando se utiliza la aplicación del almacén para realizar movimientos.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-113">The **Owner** tracking dimension is missing when the warehouse app is used to make movements.</span></span> <span data-ttu-id="8dd8e-114">Un diario de transferencia de inventario regular del cliente de Supply Chain Management parece funcionar según lo previsto y solo se puede registrar si la dimensión **Propietario** se completa.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8dd8e-115">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="8dd8e-115">Issue resolution</span></span>

<span data-ttu-id="8dd8e-116">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="8dd8e-117">Actualmente, los procesos de gestión de almacenes solo admiten el inventario que es propiedad de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="8dd8e-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]