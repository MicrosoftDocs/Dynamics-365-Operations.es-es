---
title: Comprar y vender bajas
description: En Dynamics 365 Human Resources, puede enviar solicitudes para comprar y vender licencias según las políticas de compra y venta de licencias establecidas por su empresa.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d32abacc1539cb930ad6f1ebcfe6fa9af4befcf
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271503"
---
# <a name="buy-and-sell-leave"></a><span data-ttu-id="7bda8-103">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="7bda8-103">Buy and sell leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7bda8-104">En Dynamics 365 Human Resources, puede enviar solicitudes para comprar y vender licencias según las políticas de compra y venta de licencias establecidas por su empresa.</span><span class="sxs-lookup"><span data-stu-id="7bda8-104">In Dynamics 365 Human Resources, you can submit requests to buy and sell leave based on the buy and sell leave policies set up by your company.</span></span>  

## <a name="request-to-buy-leave"></a><span data-ttu-id="7bda8-105">Solicitud para comprar baja</span><span class="sxs-lookup"><span data-stu-id="7bda8-105">Request to buy leave</span></span>

1. <span data-ttu-id="7bda8-106">En el espacio de trabajo **Autoservicio de empleados**, seleccione **Solicitar compra de baja** en el icono **Saldos de permisos**.</span><span class="sxs-lookup"><span data-stu-id="7bda8-106">In the **Employee self service** workspace, select **Buy leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="7bda8-107">Agregue un **Tipo de baja** e introduzca un **Importe** por la cantidad de baja que le gustaría comprar.</span><span class="sxs-lookup"><span data-stu-id="7bda8-107">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to buy.</span></span> 

3. <span data-ttu-id="7bda8-108">Seleccione **Enviar** cuando esté listo para enviar su solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bda8-108">Select **Submit** when you're ready to submit your request.</span></span> 

<span data-ttu-id="7bda8-109">Sus saldos se actualizarán automáticamente o pasarán por un proceso de aprobación antes de actualizarse.</span><span class="sxs-lookup"><span data-stu-id="7bda8-109">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="7bda8-110">Esto depende de cómo se haya configurado la política de compra.</span><span class="sxs-lookup"><span data-stu-id="7bda8-110">This depends on how the buy policy has been configured.</span></span>

## <a name="request-to-sell-leave"></a><span data-ttu-id="7bda8-111">Solicitud para vender baja</span><span class="sxs-lookup"><span data-stu-id="7bda8-111">Request to sell leave</span></span>

1. <span data-ttu-id="7bda8-112">En el espacio de trabajo **Autoservicio de empleados**, seleccione **Solicitar venta de baja** en el icono **Saldos de permisos**.</span><span class="sxs-lookup"><span data-stu-id="7bda8-112">In the **Employee self service** workspace, select **Sell leave request** in the **Time Off Balances** tile.</span></span> 

2. <span data-ttu-id="7bda8-113">Agregue un **Tipo de baja** e introduzca un **Importe** por la cantidad de baja que le gustaría vender.</span><span class="sxs-lookup"><span data-stu-id="7bda8-113">Add a **Leave type** and enter an **Amount** for the amount of leave you'd like to sell.</span></span> 

3. <span data-ttu-id="7bda8-114">Seleccione **Enviar** cuando esté listo para enviar su solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bda8-114">Select **Submit** when you're ready to submit your request.</span></span>

<span data-ttu-id="7bda8-115">Sus saldos se actualizarán automáticamente o pasarán por un proceso de aprobación antes de actualizarse.</span><span class="sxs-lookup"><span data-stu-id="7bda8-115">Your balances will either automatically update or go through an approval process before updating.</span></span> <span data-ttu-id="7bda8-116">Esto depende de cómo se haya configurado la política de compra.</span><span class="sxs-lookup"><span data-stu-id="7bda8-116">This depends on how the buy policy has been configured.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="7bda8-117">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="7bda8-117">Troubleshooting</span></span> 

<span data-ttu-id="7bda8-118">Si falla un flujo de trabajo de solicitud de licencia de compra o venta, los usuarios con el privilegio **EssLeaveBuySellRequestApprover** puede revisar el registro de mensajes para todas las solicitudes de compra y venta de licencias.</span><span class="sxs-lookup"><span data-stu-id="7bda8-118">If a buy or sell leave request workflow fails, users with the **EssLeaveBuySellRequestApprover** privilege can review the message log for all leave buy and sell requests.</span></span> <span data-ttu-id="7bda8-119">Para hacer esto, vaya a **Licencias y ausencias > Enlace > Compra y venta de solicitudes de licencia> Registro de mensajes** (arriba a la izquierda).</span><span class="sxs-lookup"><span data-stu-id="7bda8-119">To do this, go to **Leave and absence > Link > Buy and sell leave requests > Message log** (on the upper left).</span></span> <span data-ttu-id="7bda8-120">**Registro de mensajes** muestra a los usuarios cómo se procesaron las transacciones y el historial de flujo de trabajo asociado.</span><span class="sxs-lookup"><span data-stu-id="7bda8-120">The **Message log** shows users how the transactions were processed and the associated workflow history.</span></span>


## <a name="see-also"></a><span data-ttu-id="7bda8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7bda8-121">See also</span></span>

[<span data-ttu-id="7bda8-122">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="7bda8-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="7bda8-123">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="7bda8-123">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
