---
title: Asociar activos fijos con arrendamientos
description: El tema explica cómo asociar un activo fijo existente con un nuevo arrendamiento.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0e2261755d98ee38564b4b864daf8e79551d1239
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814089"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="da343-103">Asociar activos fijos con arrendamientos</span><span class="sxs-lookup"><span data-stu-id="da343-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da343-104">El tema explica cómo asociar un activo fijo existente con un nuevo arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="da343-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="da343-105">Cuando asocia un activo fijo con un arrendamiento, el valor del activo por derecho de uso (ROU) en el reconocimiento inicial será el coste de adquisición del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="da343-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="da343-106">Antes de poder asociar un activo fijo con un arrendamiento, debe crear un registro para el activo fijo en Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="da343-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="da343-107">Entonces, en la página **Resumen de arrendamientos**, debe crear un arrendamiento y vincular el activo a ese arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="da343-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="da343-108">Agregue un arrendamiento siguiendo los pasos de [Agregar o copiar arrendamientos](add-lease.md).</span><span class="sxs-lookup"><span data-stu-id="da343-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="da343-109">En la página **Agregar arrendamiento**, en el campo **Número de activo fijo**, seleccione el activo que aún no se ha adquirido.</span><span class="sxs-lookup"><span data-stu-id="da343-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="da343-110">Seleccione **Libros** y confirme la programación de pagos.</span><span class="sxs-lookup"><span data-stu-id="da343-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="da343-111">Seleccione **Reconocimiento inicial**.</span><span class="sxs-lookup"><span data-stu-id="da343-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="da343-112">Seleccione **Diario de arrendamientos de activos**.</span><span class="sxs-lookup"><span data-stu-id="da343-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="da343-113">El asiento de diario de reconocimiento inicial para el arrendamiento carga el activo fijo por el importe que generalmente se carga en la cuenta de activos por derecho de uso.</span><span class="sxs-lookup"><span data-stu-id="da343-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="da343-114">Ahora puede ver el tipo de transacción y reservar el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="da343-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="da343-115">Seleccione **Detalles de diario**.</span><span class="sxs-lookup"><span data-stu-id="da343-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="da343-116">Seleccione **Líneas** para ver las líneas individuales del movimiento de diario.</span><span class="sxs-lookup"><span data-stu-id="da343-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="da343-117">Seleccione la línea del diario que contiene el activo y luego seleccione la pestaña **Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="da343-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="da343-118">La pestaña **Activos fijos** muestra el tipo de transacción y el libro.</span><span class="sxs-lookup"><span data-stu-id="da343-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="da343-119">Por defecto, el campo **Tipo de transacción** está configurado en **Adquisición**, y el campo **Libro** se establece en el libro actual del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="da343-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="da343-120">Después de registrar el movimiento de diario de reconocimiento inicial, la transacción aparece como una transacción de adquisición para el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="da343-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="da343-121">Para ver la tabla de transacciones, vaya a **Activos fijos \> Activos fijos \> Activos fijos**, seleccione el activo apropiado y luego seleccione **Valoraciones**.</span><span class="sxs-lookup"><span data-stu-id="da343-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="da343-122">Debería aparecer que el movimiento de diario de reconocimiento inicial ha creado una transacción de adquisición para el activo fijo especificado.</span><span class="sxs-lookup"><span data-stu-id="da343-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="da343-123">El activo fijo ahora se puede depreciar utilizando la funcionalidad de depreciación estándar de Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="da343-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="da343-124">Para obtener más información sobre depreciación, consulte [Convenciones y métodos de depreciación](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="da343-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="da343-125">Si asocia un activo fijo con un arrendamiento, los botones **Depreciación de activos** y **Deterioro del arrendamiento** están desactivados en Arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="da343-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="da343-126">Puede ver la depreciación de activos y las transacciones de deterioro de arrendamientos desde Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="da343-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="da343-127">El botón **Transacciones de activos**, que abre un formulario de consulta, también está desactivado.</span><span class="sxs-lookup"><span data-stu-id="da343-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="da343-128">También puede abrir el formulario de consulta **Transacciones de activos** en Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="da343-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]