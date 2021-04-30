---
title: Configurar parámetros de arrendamiento (versión preliminar)
description: Este tema describe las opciones de configuración para el arrendamiento de activos, como la información de seguridad y la configuración de contabilidad.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 77caf751f9baf4abef534bac97e226484df7acf7
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881285"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="a6d22-103">Configurar parámetros de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a6d22-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6d22-104">Varias opciones de configuración afectan al comportamiento del arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a6d22-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="a6d22-105">Estas configuraciones incluyen nombres de diarios, parámetros generales y configuraciones de perfil de publicación.</span><span class="sxs-lookup"><span data-stu-id="a6d22-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="a6d22-106">Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="a6d22-107">En la pestaña **Arrendamientos**, seleccione la ficha desplegable **General**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="a6d22-108">El parámetro **Permitir anulación de clasificación manual** determina si la clasificación de arrendamiento se puede anular antes de que se confirme la programación de pagos.</span><span class="sxs-lookup"><span data-stu-id="a6d22-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="a6d22-109">El parámetro **Lote entre entidades** determina si puede publicar en otras entidades jurídicas desde la entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="a6d22-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="a6d22-110">Si este parámetro está activado, puede crear asientos de diario para las entidades jurídicas a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="a6d22-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="a6d22-111">Seleccione la opción **Permitir la eliminación de arrendamientos confirmados** a **Sí** para permitir que se eliminen los arrendamientos que tienen programas de pago confirmados.</span><span class="sxs-lookup"><span data-stu-id="a6d22-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="a6d22-112">Los arrendamientos no se pueden eliminar si tienen asociadas transacciones registradas o no registradas, independientemente de la configuración de esta opción.</span><span class="sxs-lookup"><span data-stu-id="a6d22-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="a6d22-113">No puede restaurar un registro de arrendamiento después de eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="a6d22-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="a6d22-114">Si carga algún registro para un arrendamiento eliminado, ya sea manualmente o mediante entidades de datos, la información cargada se trata como nueva, no como una actualización de un arrendamiento existente.</span><span class="sxs-lookup"><span data-stu-id="a6d22-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="a6d22-115">Si configura esta opción en **Sí** y el tipo de transición del libro es **Opción de recuperación acumulativa A o B**, el sistema establece el campo **Tipo de interés incremental del endeudamiento** al valor del campo **Tipo de interés incremental del endeudamiento en la transición**, en la página **Configuración del libro**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="a6d22-116">Si esta opción se establece en **No**, la tasa del arrendamiento principal se establece en el valor del campo **Tipo de interés incremental del endeudamiento** en la página **Detalles del libro**, independientemente del tipo de transición del libro.</span><span class="sxs-lookup"><span data-stu-id="a6d22-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="a6d22-117">Establezca la opción **Permitir reversiones de depreciación en la versión de libro cerrado** en **Sí** para permitir la reversión de las transacciones de gastos de depreciación.</span><span class="sxs-lookup"><span data-stu-id="a6d22-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="a6d22-118">Las transacciones de gastos se pueden revertir incluso cuando la versión del libro está cerrada.</span><span class="sxs-lookup"><span data-stu-id="a6d22-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6d22-119">Le recomendamos que mantenga esta opción configurada en **No**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="a6d22-120">La configuración de esta opción se utiliza como validación y control para evitar que una versión de libro cerrado se deprecie accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="a6d22-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="a6d22-121">Manteniendo la opción establecida en **No**, ayuda a mantener precisos el valor neto en los libros y los cálculos de depreciación futura.</span><span class="sxs-lookup"><span data-stu-id="a6d22-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
