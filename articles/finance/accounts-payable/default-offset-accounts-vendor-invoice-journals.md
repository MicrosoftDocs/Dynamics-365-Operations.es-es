---
title: Cuentas de contrapartida predeterminadas para diarios de factura de proveedor y diarios de aprobación de facturas
description: Este tema le ayudará a decidir dónde debe asignar cuentas predeterminadas para diarios de facturas.
author: abruer
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6ff4e209f1d1c41d7c05cad735aacc320bdeb83
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189692"
---
# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="ce945-103">Cuentas de contrapartida predeterminadas para diarios de factura de proveedor y diarios de aprobación de facturas</span><span class="sxs-lookup"><span data-stu-id="ce945-103">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce945-104">Las cuentas de contrapartida predeterminadas se usan en las siguientes páginas de diario de facturas de proveedor:</span><span class="sxs-lookup"><span data-stu-id="ce945-104">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="ce945-105">Diario de facturas</span><span class="sxs-lookup"><span data-stu-id="ce945-105">Invoice journal</span></span>
-   <span data-ttu-id="ce945-106">Diario de aprobación de facturas</span><span class="sxs-lookup"><span data-stu-id="ce945-106">Invoice approval journal</span></span>

<span data-ttu-id="ce945-107">Use la siguiente tabla para decidir dónde debe asignar cuentas predeterminadas y cuentas de contrapartida para diarios de facturas.</span><span class="sxs-lookup"><span data-stu-id="ce945-107">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce945-108">Configure las cuentas predeterminadas aquí</span><span class="sxs-lookup"><span data-stu-id="ce945-108">Set up default accounts here</span></span></th>
<th><span data-ttu-id="ce945-109">Dónde se proporcionan cuentas predeterminadas</span><span class="sxs-lookup"><span data-stu-id="ce945-109">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="ce945-110">Cómo afecta esta opción al procesamiento</span><span class="sxs-lookup"><span data-stu-id="ce945-110">How this option affects processing</span></span></th>
<th><span data-ttu-id="ce945-111">Cuándo debe usar esta opción</span><span class="sxs-lookup"><span data-stu-id="ce945-111">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ce945-112"><strong>Grupo de proveedores</strong>: configure cuentas de contrapartida predeterminadas para grupos de proveedores en la página <strong>Configuración de cuenta predeterminada</strong>, la cual puede abrir desde la página <strong>Grupos de proveedores</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-112"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="ce945-113">Cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="ce945-113">Vendor account</span></span></li>
<li><span data-ttu-id="ce945-114">Entradas del diario para las cuentas de proveedores en el grupo de proveedores, si no se especifican cuentas predeterminadas para las cuentas de proveedor</span><span class="sxs-lookup"><span data-stu-id="ce945-114">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="ce945-115">Las cuentas de contrapartida predeterminadas para grupos de proveedores se muestran como cuentas de contrapartida predeterminadas para proveedores en la página <strong>Configuración de cuenta predeterminada</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-115">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="ce945-116">Puede abrir esta página desde la página de lista <strong>Todos los proveedores</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-116">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="ce945-117">Use esta opción si paga normalmente los mismos tipos de elementos de los mismos grupos de proveedores en el transcurso del tiempo.</span><span class="sxs-lookup"><span data-stu-id="ce945-117">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce945-118"><strong>Cuenta de proveedor</strong>: configure cuentas predeterminadas para cuentas de proveedor en la página <strong>Configuración de cuenta predeterminada</strong>, la cual puede abrir desde la página <strong>Proveedores</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-118"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="ce945-119">Entradas del diario para la cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="ce945-119">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="ce945-120">Las cuentas de contrapartida predeterminadas para cuentas de proveedor se muestran como cuentas de contrapartida predeterminadas para entradas de diario para la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="ce945-120">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="ce945-121">Use esta opción si paga normalmente los mismos tipos de elementos de los mismos proveedores en el transcurso del tiempo.</span><span class="sxs-lookup"><span data-stu-id="ce945-121">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ce945-122"><strong>Nombres de diarios</strong>: configure cuentas de contrapartida predeterminadas para los diarios en la página <strong>Nombres de diarios</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-122"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="ce945-123">Seleccione la opción <strong>Cuenta de contrapartida fija</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-123">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="ce945-124">Tenga en cuenta que no puede especificar cuentas de contrapartida predeterminadas en nombres de diario si el tipo de diario de los nombres es <strong>Registro de facturas</strong> o <strong>Aprobación</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-124">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="ce945-125">Encabezado de diario que usa el nombre del diario</span><span class="sxs-lookup"><span data-stu-id="ce945-125">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="ce945-126">Entradas del diario en diarios que usan el nombre del diario</span><span class="sxs-lookup"><span data-stu-id="ce945-126">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="ce945-127">Si la opción <strong>Cuenta de contrapartida fija</strong> de la página <strong>Nombres de diarios</strong> está seleccionada, la cuenta de contrapartida para el nombre de diario anula la cuenta de contrapartida predeterminada para el proveedor o el grupo de proveedores.</span><span class="sxs-lookup"><span data-stu-id="ce945-127">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="ce945-128">Use esta opción para configurar diarios para costes y gastos específicos que se cobran en cuentas específicas, independientemente de quién sea el proveedor o el grupo de proveedores del que forman parte.</span><span class="sxs-lookup"><span data-stu-id="ce945-128">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ce945-129"><strong>Nombres de diarios</strong>: configure cuentas de contrapartida predeterminadas para los diarios en la página <strong>Nombres de diarios</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-129"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="ce945-130">Anule la opción <strong>Cuenta de contrapartida fija</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-130">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="ce945-131">Tenga en cuenta que no puede especificar cuentas de contrapartida predeterminadas en nombres de diario si el tipo de diario de los nombres es <strong>Registro de facturas</strong> o <strong>Aprobación</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-131">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="ce945-132">Cabecera de diario</span><span class="sxs-lookup"><span data-stu-id="ce945-132">Journal header</span></span></li>
<li><span data-ttu-id="ce945-133">Entradas del diario en diarios que usan el nombre del diario</span><span class="sxs-lookup"><span data-stu-id="ce945-133">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="ce945-134">Estas entradas predeterminadas se usan en las páginas de encabezado de diario y la cuenta de contrapartida de la página del encabezado de diario se usa como entrada predeterminada en las páginas de asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="ce945-134">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="ce945-135">Las cuentas predeterminadas de la página <strong>Nombres de diarios </strong>se usan solo si no hay cuentas predeterminadas configuradas para la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="ce945-135">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="ce945-136">Use esta opción para configurar las cuentas predeterminadas para utilizarlas si no se ha asignado una cuenta de contrapartida de proveedor predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce945-136">Use this option to set up default accounts that are used when a default vendor offset account isn&#39;t assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ce945-137"><strong>Cabecera de diario</strong>: configure una cuenta de contrapartida predeterminada para un diario para utilizarla como entrada predeterminada en las páginas de asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="ce945-137"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="ce945-138">Tenga en cuenta que no puede especificar cuentas de contrapartida predeterminadas en el encabezado de diario si el tipo de diario de los nombres es <strong>Registro de facturas</strong> o <strong>Aprobación</strong>.</span><span class="sxs-lookup"><span data-stu-id="ce945-138">Note that you can&#39;t specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="ce945-139">Entradas de diario en el diario</span><span class="sxs-lookup"><span data-stu-id="ce945-139">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="ce945-140">La cuenta de contrapartida predeterminada para un diario se utiliza como entrada predeterminada en las páginas de asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="ce945-140">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="ce945-141">Use esta opción para ayudar a acelerar la entrada de datos si la mayoría de las entradas de un diario tiene la misma cuenta de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="ce945-141">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>





