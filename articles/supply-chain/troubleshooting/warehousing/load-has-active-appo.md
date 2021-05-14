---
title: No puede confirmar un envío debido a un problema con el calendario
description: No puede confirmar un envío debido a un problema con el calendario
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938548"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="25fed-103">No puede confirmar un envío debido a un problema con el calendario</span><span class="sxs-lookup"><span data-stu-id="25fed-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="25fed-104">Código de error: TRX2716</span><span class="sxs-lookup"><span data-stu-id="25fed-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="25fed-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="25fed-105">Symptoms</span></span>

<span data-ttu-id="25fed-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="25fed-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="25fed-107">El tipo de calendario %1 requiere que se registre la entrada y salida de la cita %2.</span><span class="sxs-lookup"><span data-stu-id="25fed-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="25fed-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="25fed-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="25fed-109">Causa</span><span class="sxs-lookup"><span data-stu-id="25fed-109">Cause</span></span>

<span data-ttu-id="25fed-110">Existen citas activas para la carga.</span><span class="sxs-lookup"><span data-stu-id="25fed-110">Active appointments for the load exist.</span></span> <span data-ttu-id="25fed-111">Por ejemplo, hay una regla que requiere que el conductor registre.</span><span class="sxs-lookup"><span data-stu-id="25fed-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="25fed-112">Por lo tanto, la carga se encuentra actualmente en un estado en el que falla la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="25fed-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="25fed-113">Resolución</span><span class="sxs-lookup"><span data-stu-id="25fed-113">Resolution</span></span>

<span data-ttu-id="25fed-114">Debe investigar y solucionar cualquier problema con las citas activas que están vinculadas a la carga.</span><span class="sxs-lookup"><span data-stu-id="25fed-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="25fed-115">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="25fed-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="25fed-116">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="25fed-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="25fed-117">En el panel Acciones, en la pestaña **Transporte**, en el grupo **Citas**, seleccione **Programación de citas**.</span><span class="sxs-lookup"><span data-stu-id="25fed-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="25fed-118">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="25fed-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="25fed-119">Asegúrese de que el registro de entrada/salida del conductor esté completo para la cita.</span><span class="sxs-lookup"><span data-stu-id="25fed-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="25fed-120">Complete o cancele la cita.</span><span class="sxs-lookup"><span data-stu-id="25fed-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="25fed-121">Desactive la opción **Se requiere registro del conductor** para la regla de cita relacionada.</span><span class="sxs-lookup"><span data-stu-id="25fed-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
