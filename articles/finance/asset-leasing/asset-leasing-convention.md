---
title: Convenciones de arrendamiento de activos
description: En este tema se describen las convenciones de los activos arrendados.
author: moaamer
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e6450438a6e8c594590df3cc4502895913f50d01
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842403"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="1b2ca-103">Convenciones de arrendamiento de activos</span><span class="sxs-lookup"><span data-stu-id="1b2ca-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="1b2ca-104">En este tema se describen las convenciones de los activos arrendados.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="1b2ca-105">Las convenciones de arrendamiento se utilizan para determinar la fecha de inicio de un libro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="1b2ca-106">Si la convención de arrendamiento se establece en **Ninguna**, la fecha de inicio es la misma que la fecha de inicio del arrendamiento (es decir, el valor del campo **Fecha de inicio del arrendamiento**).</span><span class="sxs-lookup"><span data-stu-id="1b2ca-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="1b2ca-107">Si la convención de arrendamiento se establece en **Mes entero**, la fecha de inicio es el primer día del mes en el que cae la fecha de comienzo del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="1b2ca-108">La fecha de comienzo determina la fecha de inicio del período para los programas de amortización de pasivos y depreciación de activos.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="1b2ca-109">Los gastos por intereses y los gastos de depreciación se contabilizan en la fecha de cierre del período de los anexos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="1b2ca-110">El asiento de diario de reconocimiento y ajuste inicial se contabiliza en la fecha de comienzo.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="1b2ca-111">La característica de convenciones de arrendamiento debe activarse a través de la administración de características.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="1b2ca-112">En el espacio de trabajo **Gestión de funciones**, busque y seleccione la característica denominada **Convenio de arrendamiento para arrendamiento de activos** y luego seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="1b2ca-113">Las convenciones de arrendamiento se asignan a la configuración de un libro de activos de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="1b2ca-114">Para ver o asignar la convención de arrendamiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="1b2ca-115">Vaya a **Arrendamiento de activos \> Configuración \> Libros de arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="1b2ca-116">En el campo **Convención de arrendamiento**, seleccione uno de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="1b2ca-117">Convención de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="1b2ca-117">Leasing convention</span></span> | <span data-ttu-id="1b2ca-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b2ca-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="1b2ca-119">None</span><span class="sxs-lookup"><span data-stu-id="1b2ca-119">None</span></span>               | <span data-ttu-id="1b2ca-120">Los programas de amortización de pasivos y depreciación de activos comienzan en la fecha de inicio del arrendamiento, porque la fecha de comienzo es igual a la fecha de inicio del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="1b2ca-121">La fecha de finalización es un mes después.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-121">The end date is one month later.</span></span> <span data-ttu-id="1b2ca-122">Esta convención de arrendamiento no garantiza que los intereses se contabilicen el último día de cada mes.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="1b2ca-123">Mes completo</span><span class="sxs-lookup"><span data-stu-id="1b2ca-123">Full month</span></span>         | <span data-ttu-id="1b2ca-124">Para los arrendamientos que tienen una fecha de inicio que ocurre en cualquier momento durante el mes, los programas de amortización de pasivos y depreciación de activos comienzan a acumular gastos el primer día de ese mes.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="1b2ca-125">Esta convención de arrendamiento asegura que los intereses se devenguen el último día de cada mes para todo el mes.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="1b2ca-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-126">Select **Save**.</span></span>

<span data-ttu-id="1b2ca-127">Cuando se crea un arrendamiento, la fecha de comienzo de cada libro se introduce automáticamente en función de la fecha de inicio que se introduce para el arrendamiento y la convención de arrendamiento que se especifica para el libro.</span><span class="sxs-lookup"><span data-stu-id="1b2ca-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]