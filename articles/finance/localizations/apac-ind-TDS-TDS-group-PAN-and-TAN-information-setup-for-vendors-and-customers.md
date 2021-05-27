---
title: Configurar información de grupo de TDS, PAN y TAN para proveedores y clientes
description: Este tema explica cómo configurar información sobre el grupo de impuestos deducidos en el origen (TDS), el número de cuenta permanente (PAN) y el número de cuenta de impuestos (TAN) para proveedores y clientes.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023569"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="1d053-103">Configuración de la información de grupo de TDS, PAN y TAN para proveedores y clientes</span><span class="sxs-lookup"><span data-stu-id="1d053-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d053-104">Este tema explica cómo configurar información sobre el grupo de impuestos deducidos en el origen (TDS), el número de cuenta permanente (PAN) y el número de cuenta de impuestos (TAN) para proveedores y clientes.</span><span class="sxs-lookup"><span data-stu-id="1d053-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="1d053-105">Vaya a **Proveedores \> Proveedores \> Todos los proveedores** o **Clientes \> Clientes \> Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="1d053-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="1d053-106">[![Página de todos los proveedores](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="1d053-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="1d053-107">En el panel de acciones, seleccione **Nuevo** para crear un proveedor o cliente e introduzca los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="1d053-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="1d053-108">Alternativamente, seleccione un proveedor o cliente existente.</span><span class="sxs-lookup"><span data-stu-id="1d053-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="1d053-109">En la ficha desplegable **Factura y entrega**, en la sección **Retención de impuestos**, establezca la opción **Calcular retención de impuestos** a **Sí** para calcular la retención de impuestos, TDS o impuestos cobrados en el origen (TCS) para el proveedor o cliente.</span><span class="sxs-lookup"><span data-stu-id="1d053-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="1d053-110">El TDS para una factura de compra se calcula en función del grupo de TDS predeterminado que se define para el proveedor o cliente.</span><span class="sxs-lookup"><span data-stu-id="1d053-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="1d053-111">En el campo **Grupo de TDS**, seleccione el grupo de TDS predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1d053-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d053-112">Cuando selecciona un grupo de TDS en el campo **Grupo de TDS**, los campos **Grupo de retención de impuestos** y **Grupo de TCS** dejan de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="1d053-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="1d053-113">En la ficha desplegable **Información de impuestos**, en la sección **Información de PAN**, en el campo **Estado**, seleccione el estado del número de cuenta permanente para el proveedor o cliente.</span><span class="sxs-lookup"><span data-stu-id="1d053-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="1d053-114">**No disponible**: el proveedor o cliente no tiene PAN.</span><span class="sxs-lookup"><span data-stu-id="1d053-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="1d053-115">**Recibido**: el proveedor o cliente tiene un PAN.</span><span class="sxs-lookup"><span data-stu-id="1d053-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="1d053-116">**Solicitado**: el proveedor o cliente ha solicitado un PAN.</span><span class="sxs-lookup"><span data-stu-id="1d053-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="1d053-117">**No válido**: el proveedor o cliente tiene un PAN, pero no es válido.</span><span class="sxs-lookup"><span data-stu-id="1d053-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="1d053-118">Si ha seleccionado **Recibido** en el campo **Estado** para indicar que el proveedor o cliente tiene un PAN, introduzca el PAN en el campo **Número**.</span><span class="sxs-lookup"><span data-stu-id="1d053-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="1d053-119">El PAN debe constar de cinco caracteres alfabéticos, luego cuatro caracteres numéricos y luego un carácter alfabético.</span><span class="sxs-lookup"><span data-stu-id="1d053-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="1d053-120">Este es un ejemplo: **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="1d053-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="1d053-121">Si ha seleccionado **Solicitado** en el campo **Estado** para indicar que el proveedor o cliente ha solicitado un PAN, introduzca el número de referencia en el campo **Número de referencia**.</span><span class="sxs-lookup"><span data-stu-id="1d053-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="1d053-122">En el campo **Naturaleza del evaluado**, seleccione la categoría de naturaleza del evaluado a la que pertenece el proveedor o cliente:</span><span class="sxs-lookup"><span data-stu-id="1d053-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="1d053-123">Empresa</span><span class="sxs-lookup"><span data-stu-id="1d053-123">Company</span></span>
    - <span data-ttu-id="1d053-124">HUF</span><span class="sxs-lookup"><span data-stu-id="1d053-124">HUF</span></span>
    - <span data-ttu-id="1d053-125">En firme</span><span class="sxs-lookup"><span data-stu-id="1d053-125">Firm</span></span>
    - <span data-ttu-id="1d053-126">Individual</span><span class="sxs-lookup"><span data-stu-id="1d053-126">Individual</span></span>
    - <span data-ttu-id="1d053-127">AOP</span><span class="sxs-lookup"><span data-stu-id="1d053-127">AOP</span></span>
    - <span data-ttu-id="1d053-128">BOI</span><span class="sxs-lookup"><span data-stu-id="1d053-128">BOI</span></span>
    - <span data-ttu-id="1d053-129">Autoridad local</span><span class="sxs-lookup"><span data-stu-id="1d053-129">Local authority</span></span>
    - <span data-ttu-id="1d053-130">Otros</span><span class="sxs-lookup"><span data-stu-id="1d053-130">Others</span></span>

    <span data-ttu-id="1d053-131">[![Ficha desplegable de información de impuestos](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="1d053-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="1d053-132">En el Panel de acciones, en la pestaña **Proveedor**, en el grupo **Registro**, seleccione **Id. de registro** para abrir la página **Administrar direcciones**.</span><span class="sxs-lookup"><span data-stu-id="1d053-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="1d053-133">En la página **Administrar direcciones**, en la ficha desplegable **Información de impuestos**, seleccione **Agregar** o **Editar** para abrir la página **Administrar información de impuestos**, donde puede mantener la entrada de registro de impuestos.</span><span class="sxs-lookup"><span data-stu-id="1d053-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="1d053-134">En la página **Administrar información de impuestos**, en la ficha desplegable **Retención de impuestos**, en el campo **Número de cuenta de impuestos (TAN)**, introduzca el TAN.</span><span class="sxs-lookup"><span data-stu-id="1d053-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="1d053-135">El TAN debe constar de cuatro caracteres alfabéticos, luego cinco caracteres numéricos y luego un carácter alfabético.</span><span class="sxs-lookup"><span data-stu-id="1d053-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="1d053-136">Este es un ejemplo: **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="1d053-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="1d053-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1d053-137">Close the page.</span></span>
