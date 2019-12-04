---
title: Configuración de grupos de registro para impuestos
description: Los impuestos se calculan y registran en las cuentas principales que se especifican en los grupos de registro.
author: twheeloc
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cab2f427ed4f90021ed74da07527bc4b9378d97
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186035"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a><span data-ttu-id="f16bf-103">Configuración de grupos de registro para impuestos</span><span class="sxs-lookup"><span data-stu-id="f16bf-103">Set up Ledger posting groups for sales tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f16bf-104">Los impuestos se calculan y registran en las cuentas principales que se especifican en los grupos de registro.</span><span class="sxs-lookup"><span data-stu-id="f16bf-104">Sales tax is calculated and posted to main accounts that are specified in the Ledger posting groups.</span></span> <span data-ttu-id="f16bf-105">Los grupos de registro se asocian a cada código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f16bf-105">Ledger posting groups are attached to each sales tax code.</span></span> <span data-ttu-id="f16bf-106">Puede establecer grupos de registro individuales para cada código de impuestos, usar un grupo de registro para todos los códigos de impuestos o bien asignar varios grupos de registro a los códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f16bf-106">You can set up individual ledger posting groups for each sales tax code, use one ledger posting group for all sales tax codes or assign multiple ledger posting groups to the sales tax codes.</span></span> <span data-ttu-id="f16bf-107">Esta grabación usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="f16bf-107">This recording uses the DEMF demo company.</span></span> 

1. <span data-ttu-id="f16bf-108">Vaya a **Panel de navegación > Módulos > Impuestos > Configuración > Impuestos > Grupos de registro**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-108">Go to **Navigation pane > Modules > Tax > Setup > Sales tax > Ledger posting groups**.</span></span>
2. <span data-ttu-id="f16bf-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-109">Click **New**.</span></span>
3. <span data-ttu-id="f16bf-110">En el campo **Grupo de registro**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f16bf-110">In the **Ledger posting group** field, type a value.</span></span>
4. <span data-ttu-id="f16bf-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f16bf-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f16bf-112">En el campo **Impuestos repercutidos**, seleccione la cuenta principal para impuestos repercutidos que se pagan a la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="f16bf-112">In the **Sales tax payable** field, select the main account for outgoing sales taxes that are payable to the tax authority.</span></span> <span data-ttu-id="f16bf-113">Los impuestos se cobran en nombre de la autoridad fiscal cuando se venden bienes y servicios gravables.</span><span class="sxs-lookup"><span data-stu-id="f16bf-113">Sales taxes are collected on behalf of the tax authority when you sell taxable goods and services.</span></span>  
6. <span data-ttu-id="f16bf-114">En el campo de **Impuestos soportados**, seleccione la cuenta principal para impuestos soportados que se reciben de la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="f16bf-114">In the **Sales tax receivable** field, select the main account for incoming taxes that are received from the tax authority.</span></span> <span data-ttu-id="f16bf-115">Los proveedores cobran los impuestos en nombre de la autoridad fiscal cuando les compra bienes y servicios gravables.</span><span class="sxs-lookup"><span data-stu-id="f16bf-115">Vendors collect taxes on behalf of the tax authority when you buy taxable goods and services.</span></span> <span data-ttu-id="f16bf-116">Este campo no está disponible si está activada la opción Aplicar reglas de tributación de impuestos en la página **Parámetros de contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-116">This field is not available if the Apply sales tax taxation rules option is selected in the **General ledger parameters** page.</span></span> <span data-ttu-id="f16bf-117">En su lugar, los impuestos que se pagan a los proveedores se adeudan en la misma cuenta que la compra.</span><span class="sxs-lookup"><span data-stu-id="f16bf-117">Instead, sales taxes that are paid to vendors are debited to the same account as the purchase.</span></span>   
7. <span data-ttu-id="f16bf-118">En el campo **Gasto de IVA de importación**, seleccione la cuenta principal para registrar los impuestos deducibles no reclamados o notificados a la autoridad fiscal por los distribuidores como parte del cargo invertido de GST/HST.</span><span class="sxs-lookup"><span data-stu-id="f16bf-118">In the **Use tax expense** field, select  the main account for posting deductible Use taxes that are not claimed or reported to the tax authority by vendors as part of EU reverse charge GST/HST.</span></span> <span data-ttu-id="f16bf-119">La opción **IVA de importación** tiene que seleccionarse para el **Código de impuestos** en el **Grupo de impuestos** que se usa en la transacción.</span><span class="sxs-lookup"><span data-stu-id="f16bf-119">The **Use tax** option needs to be selected for the **Sales tax code** in the **Sales tax group** that is used in the transaction.</span></span> <span data-ttu-id="f16bf-120">Este campo no está disponible si está activada la opción **Aplicar reglas de tributación de impuestos** en la página **Parámetros de contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-120">This field is not be available if the **Apply sales tax taxation rules** option is selected in the **General ledger parameters** page.</span></span>   
8. <span data-ttu-id="f16bf-121">En el campo **IVA de importación repercutido**, seleccione la cuenta principal para registrar el IVA de importación soportado que se paga a la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="f16bf-121">In the **Use tax payable** field, select the main account for posting incoming Use taxes that are payable to tax authorities.</span></span> <span data-ttu-id="f16bf-122">La opción **IVA de importación** tiene que seleccionarse en el **Código de impuestos** del **Grupo de impuestos** para registrar el **IVA de importación**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-122">The **Use tax** option needs to be selected in the **Sales tax code** in the **Sales tax group** to post **Use tax**.</span></span> <span data-ttu-id="f16bf-123">Si está activada la opción **Aplicar reglas de tributación de impuestos** en los **Parámetros de contabilidad general**, la diferencia se registra en la cuenta de gastos de la transacción.</span><span class="sxs-lookup"><span data-stu-id="f16bf-123">If **Apply sales tax taxation rules** option is selected in **General ledger parameters** page, the offset is posted to the transaction’s expense account.</span></span>   
9. <span data-ttu-id="f16bf-124">En el campo de la **Cuenta de liquidación**, seleccione la cuenta principal en la que se registrará el saldo neto de las cuentas contables especificadas en los campos **IVA de importación repercutido** e **Impuestos soportados**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-124">In the **Settlement account** field, select the main account that the net balance of the ledger accounts specified in the **Use tax payable** and **Sales tax receivable** fields will be posted.</span></span> <span data-ttu-id="f16bf-125">El saldo se creará al ejecutar el trabajo Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="f16bf-125">The balance will be created when the sales tax settle and post job is ran.</span></span>  <span data-ttu-id="f16bf-126">Si la autoridad fiscal para el período de liquidación está asociada con una cuenta de proveedor, el saldo se registra en la cuenta de proveedor en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f16bf-126">If the tax authority for the settlement period is associated with a vendor account, the balance is posted to the vendor account instead.</span></span>
10. <span data-ttu-id="f16bf-127">En el campo **Descuento por pronto pago del proveedor**, seleccione la cuenta principal para registrar el descuento por pronto pago para los códigos de impuestos asociados a este grupo de registro.</span><span class="sxs-lookup"><span data-stu-id="f16bf-127">In the **Vendor cash discount** field, select the main account to post cash discount for Sales tax codes associated with this Ledger posting group.</span></span> <span data-ttu-id="f16bf-128">Esto es opcional y, si no se especifica ninguna cuenta, se usará la cuenta principal de **Códigos de descuento por pronto pago**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-128">This is optional and if no account is entered,  the main account on **Cash discount codes** will be used.</span></span> <span data-ttu-id="f16bf-129">Puede resultar útil usar cuentas diferentes por cada **Grupo de registro** si se usa la opción Deducir los impuestos del descuento por pronto pago en los Grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f16bf-129">It can be useful to use different accounts per **Ledger posting group** if using the reverse sales tax on cash discount option on Sales tax groups.</span></span>  
11. <span data-ttu-id="f16bf-130">En el campo **Descuento por pronto pago del cliente**, seleccione la cuenta principal para registrar el descuento por pronto pago para los **Códigos de impuestos** asociados a este **Grupo de registro**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-130">In the **Customer case discount** field, select the main account to post cash discount for **Sales tax codes** associated with this **Ledger posting group**.</span></span> <span data-ttu-id="f16bf-131">Esto es opcional y, si no se especifica ninguna cuenta, se usará la cuenta principal de **Códigos de descuento por pronto pago**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-131">This is optional and if no account is entered, the main account on the **Cash discount codes** will be used.</span></span> <span data-ttu-id="f16bf-132">Puede resultar útil usar cuentas diferentes por cada **Grupo de registro** si se usa la opción Deducir los impuestos del descuento por pronto pago en los **Grupos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-132">It can be useful to use different accounts per **Ledger posting group** if using the reverse sales tax on cash discount option on **Sales tax groups**.</span></span>  
12. <span data-ttu-id="f16bf-133">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f16bf-133">Click **Save**.</span></span>
