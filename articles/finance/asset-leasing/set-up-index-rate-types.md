---
title: Configurar tipos indexados
description: En este tema se explica cómo configurar tipos indexados. Se requieren tipos indexados si su organización asocia los importes de pago de arrendamientos con un conjunto de tipos indexados.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b6d201329996f23d94c0fc76a9635d3bb99c931e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249686"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="5de97-104">Configurar tipos indexados</span><span class="sxs-lookup"><span data-stu-id="5de97-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5de97-105">Si los pagos de arrendamientos dependen de un índice, los tipos indexados se pueden agregar y mantener en el sistema.</span><span class="sxs-lookup"><span data-stu-id="5de97-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="5de97-106">Para revalorizar los pagos de arrendamientos de la página **Tipo de tipo indexado**, el proceso de revalorización del tipo indexado utiliza el tipo indexado más reciente desde la fecha de la revalorización.</span><span class="sxs-lookup"><span data-stu-id="5de97-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="5de97-107">Para agregar tipos de tipo indexado y tipos indexados, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5de97-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="5de97-108">Vaya a **Arrendamiento de activos \> Configuración \> Tipo de tipo indexado**.</span><span class="sxs-lookup"><span data-stu-id="5de97-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="5de97-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5de97-109">Select **New**.</span></span>
3. <span data-ttu-id="5de97-110">En los campos correspondientes, introduzca el tipo de tipo y el nombre del tipo indexado.</span><span class="sxs-lookup"><span data-stu-id="5de97-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="5de97-111">Para agregar un nuevo valor de tipo indexado, seleccione el tipo de tipo indexado y luego seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5de97-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="5de97-112">Seleccione la fecha de inicio efectiva del tipo y seleccione el valor del tipo.</span><span class="sxs-lookup"><span data-stu-id="5de97-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="5de97-113">Debe seleccionar **Diferencia de valor de tipo indexado** o **Valor de tipo indexado** como método de tipo indexado.</span><span class="sxs-lookup"><span data-stu-id="5de97-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="5de97-114">Seleccione el método **Diferencia de valor de tipo indexado** para calcular un nuevo pago por arrendamiento, basado en la diferencia entre el tipo indexado en la fecha de inicio y el tipo indexado más reciente.</span><span class="sxs-lookup"><span data-stu-id="5de97-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="5de97-115">El tipo indexado se define en el campo **Tipo indexado (%)**.</span><span class="sxs-lookup"><span data-stu-id="5de97-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="5de97-116">Seleccione el método **Valor de tipo indexado** para calcular el pago del arrendamiento utilizando el porcentaje que se especifica en el campo **Tipo indexado (%)**.</span><span class="sxs-lookup"><span data-stu-id="5de97-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]