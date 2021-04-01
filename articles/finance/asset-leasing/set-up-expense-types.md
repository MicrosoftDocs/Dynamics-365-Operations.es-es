---
title: Configurar tipos de gastos
description: En este tema se explica cómo configurar tipos de gastos en Arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1538826f140393eec59be9ff4df5242d5ced9d8f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249758"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="749be-103">Configurar tipos de gastos</span><span class="sxs-lookup"><span data-stu-id="749be-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="749be-104">En este tema se explica cómo configurar tipos de gastos en Arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="749be-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="749be-105">Los costes que no están representados mediante la programación de pagos se conocen como *costes de gastos*.</span><span class="sxs-lookup"><span data-stu-id="749be-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="749be-106">Ejemplos de estos costes son los impuestos a la propiedad, costes de mantenimiento de áreas comunes y gastos de seguros.</span><span class="sxs-lookup"><span data-stu-id="749be-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="749be-107">Agregar un tipo de gasto administrativo</span><span class="sxs-lookup"><span data-stu-id="749be-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="749be-108">Vaya a **Arrendamiento de activos \> Configuración \> Tipos de gastos**.</span><span class="sxs-lookup"><span data-stu-id="749be-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="749be-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="749be-109">Select **New**.</span></span>
3. <span data-ttu-id="749be-110">En los campos correspondientes, introduzca el nuevo tipo de gasto y una descripción.</span><span class="sxs-lookup"><span data-stu-id="749be-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="749be-111">Asignar cuentas a costes administrativos</span><span class="sxs-lookup"><span data-stu-id="749be-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="749be-112">A continuación, debe asociar las cuentas con los tipos de gastos.</span><span class="sxs-lookup"><span data-stu-id="749be-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="749be-113">Estas cuentas se adeudarán cuando se registren las entradas de la programación de gastos.</span><span class="sxs-lookup"><span data-stu-id="749be-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="749be-114">La cuenta de contrapartida se especifica en las líneas **Programación de pagos de gastos a cargo del arrendatario en un arrendamiento de capital** de cada arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="749be-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="749be-115">Vaya a **Arrendamiento de activos \> Configuración \> Parámetros de arrendamiento de activos**.</span><span class="sxs-lookup"><span data-stu-id="749be-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="749be-116">En la pestaña **Cuentas**, en la ficha desplegable **Gastos a cargo del arrendatario en un arrendamiento de capital**, en el campo **Tipo de gasto**, seleccione el tipo de gasto.</span><span class="sxs-lookup"><span data-stu-id="749be-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="749be-117">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="749be-117">Select **Add**.</span></span>
4. <span data-ttu-id="749be-118">En el campo **Tipo de libro**, seleccione el tipo de libro para vincular a los costos administrativos.</span><span class="sxs-lookup"><span data-stu-id="749be-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="749be-119">Se pueden vincular varios tipos de libros a la misma cuenta de gastos.</span><span class="sxs-lookup"><span data-stu-id="749be-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="749be-120">En el campo **Código de cuenta**, especifique a qué arrendamientos se debe aplicar el libro:</span><span class="sxs-lookup"><span data-stu-id="749be-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="749be-121">**Todos**: aplicar el libro a todos los arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="749be-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="749be-122">**Grupo**: aplicar el libro a un grupo específico de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="749be-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="749be-123">**Tabla**: aplicar el libro a arrendamientos específicos.</span><span class="sxs-lookup"><span data-stu-id="749be-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="749be-124">Si seleccionó **Tabla** o **Grupo** en el campo **Código de cuenta**, seleccione un número de cuenta o número de grupo en el campo **Número de cuenta/grupo**.</span><span class="sxs-lookup"><span data-stu-id="749be-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="749be-125">En los campos correspondientes, seleccione la cuenta principal del arrendamiento financiero y la cuenta principal del arrendamiento operativo.</span><span class="sxs-lookup"><span data-stu-id="749be-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="749be-126">Cuando haya completado estos pasos, puede agregar gastos a través de las líneas **Calendario de pago de gastos a cargo del arrendatario en un arrendamiento de capital** en la página **Detalles del arrendamiento** de un arrendamiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="749be-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="749be-127">Alternativamente, puede agregar gastos cuando crea un nuevo contrato de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="749be-127">Alternatively, you can add expenses when you create a new lease.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]