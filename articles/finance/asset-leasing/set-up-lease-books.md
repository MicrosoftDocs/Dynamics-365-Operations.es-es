---
title: Configurar libros de arrendamiento
description: Este tema describe la información que se mantiene en los libros de arrendamiento. Los libros de arrendamiento contienen las directivas contables que determinan cómo se contabiliza un arrendamiento en el sistema.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447803"
---
# <a name="set-up-lease-books"></a><span data-ttu-id="7a78c-104">Configurar libros de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="7a78c-104">Set up lease books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a78c-105">Los libros de arrendamiento contienen las directivas contables que determinan cómo se contabiliza un arrendamiento en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7a78c-105">Lease books contain the accounting policies that determine how a lease is accounted for in the system.</span></span> <span data-ttu-id="7a78c-106">Además de la contabilidad basada en efectivo, Arrendamiento de activos admite los siguientes estándares:</span><span class="sxs-lookup"><span data-stu-id="7a78c-106">In addition to cash basis accounting, Asset leasing supports the following standards:</span></span>

- <span data-ttu-id="7a78c-107">Principios Contables Generalmente Aceptados en los Estados Unidos (US GAAP)</span><span class="sxs-lookup"><span data-stu-id="7a78c-107">Generally Accepted Accounting Principles in the United States (US GAAP)</span></span>
- <span data-ttu-id="7a78c-108">Tema 842 de Codificación de Normas de Contabilidad (ASC 842)</span><span class="sxs-lookup"><span data-stu-id="7a78c-108">Accounting Standards Codification Topic 842 (ASC 842)</span></span>
- <span data-ttu-id="7a78c-109">ASC 840</span><span class="sxs-lookup"><span data-stu-id="7a78c-109">ASC 840</span></span>
- <span data-ttu-id="7a78c-110">Norma Internacional de Información Financiera 16 (IFRS 16)</span><span class="sxs-lookup"><span data-stu-id="7a78c-110">International Financial Reporting Standard 16 (IFRS 16)</span></span>
- <span data-ttu-id="7a78c-111">Norma Internacional de Contabilidad 17 (IAS 17)</span><span class="sxs-lookup"><span data-stu-id="7a78c-111">International Accounting Standard 17 (IAS 17)</span></span>

<span data-ttu-id="7a78c-112">Para crear un nuevo libro de arrendamiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7a78c-112">To create a lease book, follow these steps.</span></span>

1. <span data-ttu-id="7a78c-113">Vaya a **Arrendamiento de activos \> Configuración \> Libros de arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="7a78c-113">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="7a78c-114">Seleccione **Nuevo** para agregar un libro.</span><span class="sxs-lookup"><span data-stu-id="7a78c-114">Select **New** to add a book.</span></span>
3. <span data-ttu-id="7a78c-115">Establezca los campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7a78c-115">Set the following fields.</span></span>

    | <span data-ttu-id="7a78c-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="7a78c-116">Name</span></span>                                     | <span data-ttu-id="7a78c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a78c-117">Description</span></span> |
    |------------------------------------------|-------------|
    | <span data-ttu-id="7a78c-118">Capa de registro</span><span class="sxs-lookup"><span data-stu-id="7a78c-118">Posting layer</span></span>                            | <span data-ttu-id="7a78c-119">Seleccione una capa de registro a utilizar.</span><span class="sxs-lookup"><span data-stu-id="7a78c-119">Select the posting layer to use.</span></span> <span data-ttu-id="7a78c-120">Cada libro adjunto a un arrendamiento se configura para una capa de publicación específica.</span><span class="sxs-lookup"><span data-stu-id="7a78c-120">Each book that is attached to a lease is set up for a specific posting layer.</span></span> <span data-ttu-id="7a78c-121">Cada capa de registro tiene diferentes propósitos de registro.</span><span class="sxs-lookup"><span data-stu-id="7a78c-121">Each posting layer has different posting purposes.</span></span> |
    | <span data-ttu-id="7a78c-122">Tipo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="7a78c-122">Lease type</span></span>                               | <span data-ttu-id="7a78c-123">Seleccione si el arrendamiento debe clasificarse automáticamente o si debe estar predefinido como arrendamiento financiero u operativo.</span><span class="sxs-lookup"><span data-stu-id="7a78c-123">Select whether the lease should be classified automatically, or whether it should be predefined as a finance or operating lease.</span></span> |
    | <span data-ttu-id="7a78c-124">Marco de contabilidad</span><span class="sxs-lookup"><span data-stu-id="7a78c-124">Accounting framework</span></span>                     | <span data-ttu-id="7a78c-125">Seleccione el marco asociado con el libro.</span><span class="sxs-lookup"><span data-stu-id="7a78c-125">Select the framework that is associated with the book.</span></span> |
    | <span data-ttu-id="7a78c-126">Configuración del plazo del arrendamiento/vida útil</span><span class="sxs-lookup"><span data-stu-id="7a78c-126">Lease term/Useful life Set Up</span></span>          | <span data-ttu-id="7a78c-127">El sistema clasificará el arrendamiento como financiero si el tipo de arrendamiento se establece en **Automático** y si el plazo del arrendamiento durante la vida útil del activo es mayor o igual al porcentaje introducido en este campo.</span><span class="sxs-lookup"><span data-stu-id="7a78c-127">The system will classify the lease as a finance lease if the lease type is set to **Automatic**, and if the lease term over useful life of the asset is greater than or equal to the percentage entered in this field.</span></span>  |
    | <span data-ttu-id="7a78c-128">Configuración del valor actual/valor razonable del activo</span><span class="sxs-lookup"><span data-stu-id="7a78c-128">Present value / Asset fair value setup</span></span>   | <span data-ttu-id="7a78c-129">Introduzca un número entero para definir el umbral que determinará el tipo de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="7a78c-129">Enter a whole number to define the threshold that will determine the lease type.</span></span> <span data-ttu-id="7a78c-130">Si el valor presente de los futuros pagos mínimos de arrendamiento es mayor que el valor definido por el usuario de la configuración del libro, y si la clasificación del arrendamiento del libro se establece en automática, el sistema clasificará el arrendamiento como arrendamiento financiero.</span><span class="sxs-lookup"><span data-stu-id="7a78c-130">If the present value of future minimum lease payments is more than the user-defined value from the book setup, and if the book's lease classification is set to automatic, the system will classify the lease as a finance lease.</span></span> |
    | <span data-ttu-id="7a78c-131">Umbral a corto plazo</span><span class="sxs-lookup"><span data-stu-id="7a78c-131">Short-term threshold</span></span>                     | <span data-ttu-id="7a78c-132">Introduzca el número de meses que se utilizará como umbral para los arrendamientos a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="7a78c-132">Enter the number of months to use as a threshold for short-term leases.</span></span> <span data-ttu-id="7a78c-133">Si el plazo del arrendamiento es menor o igual al número de meses que introduce aquí, el sistema clasificará el arrendamiento como arrendamiento a corto plazo y se aplicará el tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="7a78c-133">If the lease term is less than or equal to the number of months that you enter here, the system will classify the lease as a short-term lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="7a78c-134">Umbral de valor bajo</span><span class="sxs-lookup"><span data-stu-id="7a78c-134">Low value threshold</span></span>                      | <span data-ttu-id="7a78c-135">Introduzca una cantidad para usarla como umbral de arrendamientos de bajo valor.</span><span class="sxs-lookup"><span data-stu-id="7a78c-135">Enter an amount to use as a threshold for low-value leases.</span></span> <span data-ttu-id="7a78c-136">Si el valor razonable del activo es menor o igual al valor que introduce aquí, el sistema clasificará el arrendamiento como arrendamiento de bajo valor y se aplicará el tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="7a78c-136">If the fair value of the asset is less than or equal or the value that you enter here, the system will classify the lease as a low-value lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="7a78c-137">Pagar a proveedor</span><span class="sxs-lookup"><span data-stu-id="7a78c-137">Pay to vendor</span></span>                            | <span data-ttu-id="7a78c-138">Establezca esta opción en **Sí** para permitir que los pagos del arrendamiento se registren, como una factura, en la cuenta del proveedor que se especifica en cada arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="7a78c-138">Set this option to **Yes** to allow lease payments to be posted, as an invoice, to the vendor account that is specified on each lease.</span></span> <span data-ttu-id="7a78c-139">Cuando se registra un pago de arrendamiento, se abona en la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="7a78c-139">When a lease payment is posted, the vendor account will be credited.</span></span> <span data-ttu-id="7a78c-140">Si esta opción se establece en **No**, será la cuenta que se especifica para el tipo de registro **Pago de arrendamiento** en la página **Parámetros de registro de arrendamiento** la que se acreditará en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7a78c-140">If this option is set to **No**, the account that is specified for the **Lease payment** posting type on the **Lease posting parameters** page will be credited instead.</span></span> |
