---
title: Crear facturas de pago
description: Este tema explica cómo crear facturas de arrendamiento mensual. Puede crear facturas para arrendamientos individuales o puede utilizar un proceso por lotes para crearlas para arrendamientos múltiples.
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
ms.openlocfilehash: 303fb0e70530fdc29cb129736b01c0e0e8d02075
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969587"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="0ebbd-104">Crear facturas de pago</span><span class="sxs-lookup"><span data-stu-id="0ebbd-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ebbd-105">Puede crear facturas mensuales para arrendamientos individuales o puede utilizar un proceso por lotes para crearlas para arrendamientos múltiples.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="0ebbd-106">El siguiente procedimiento muestra cómo crear un asiento de pago de arrendamiento individual cuando el parámetro **Pagar al proveedor** de la página **Configuración del libro de arrendamiento** está activado.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="0ebbd-107">En la página **Resumen de arrendamiento**, seleccione un arrendamiento y luego seleccione **Libros \> Programación de pagos**.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="0ebbd-108">Seleccione el pago que se debe realizar y luego seleccione **Crear diario**.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="0ebbd-109">Recibe un mensaje que indica que se ha creado un diario con el pago seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="0ebbd-110">Seleccione **Diarios de facturas** y luego seleccione la factura que debe pagarse.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="0ebbd-111">En la pestaña **Líneas**, revise la entrada del diario antes de registrarla en contabilidad.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ebbd-112">De forma predeterminada, las líneas de factura de proveedor que se crean utilizan el perfil de contabilización de proveedor de la página **Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="0ebbd-113">Seleccione el diario correcto y luego seleccione la factura que debe pagarse.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="0ebbd-114">Para este ejemplo, el parámetro **Pagar al proveedor** del libro de arrendamiento está activado.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="0ebbd-115">Por lo tanto, la factura estará en el diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="0ebbd-116">La sección **Visión de conjunto** muestra un resumen de la entrada de diario y la sección **Líneas** muestra detalles de las líneas de diario reales.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ebbd-117">Si el parámetro **Pagar al proveedor** está desactivado, las entradas del diario de pagos se enumerarán en la página **Arrendamiento de activos** del libro de arrendamiento, y el sistema creará una entrada de arrendamiento de activos en lugar de una factura.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="0ebbd-118">La entrada de pago de arrendamiento se publicará en el nombre del diario que se especifica en el campo **Diario de arrendamiento mensual**.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="0ebbd-119">Una vez que se registra la transacción, puede ver la información de la transacción y el valor en libros del pasivo por arrendamiento seleccionando **Transacciones de pasivo** en el libro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="0ebbd-120">En la programación de pagos, estará seleccionada la casilla **Diario publicado** y la línea mostrará el número de diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="0ebbd-121">Después de crear un diario de pagos y una entrada para ese diario, debe revertir la entrada antes de que pueda volver a crearse.</span><span class="sxs-lookup"><span data-stu-id="0ebbd-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>
