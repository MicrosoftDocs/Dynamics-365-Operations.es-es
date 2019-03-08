---
title: Configurar proveedores y cuentas bancarias de los proveedores para las transferencias de crédito ISO20022
description: Este procedimiento muestra cómo configurar el proveedor y la información de cuenta bancaria específica de proveedor necesarios para Transferencia de crédito ISO20022 o para cualquier otra generación del archivo de pago del proveedor.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13b3c37f5d013dd896a456018813f20e5e70350b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "311620"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="64ac3-103">Configurar proveedores y cuentas bancarias de los proveedores para las transferencias de crédito ISO20022</span><span class="sxs-lookup"><span data-stu-id="64ac3-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64ac3-104">Este procedimiento muestra cómo configurar el proveedor y la información de cuenta bancaria específica de proveedor necesarios para Transferencia de crédito ISO20022 o para cualquier otra generación del archivo de pago del proveedor.</span><span class="sxs-lookup"><span data-stu-id="64ac3-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="64ac3-105">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="64ac3-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="64ac3-106">Este es el cuarto procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="64ac3-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="64ac3-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="64ac3-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="64ac3-108">Configuración de detalles bancarios</span><span class="sxs-lookup"><span data-stu-id="64ac3-108">Set up bank details</span></span>
1. <span data-ttu-id="64ac3-109">Vaya a Proveedores > Proveedores > Todos los proveedores.</span><span class="sxs-lookup"><span data-stu-id="64ac3-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="64ac3-110">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="64ac3-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="64ac3-111">Por ejemplo, filtre por el campo Cuenta de proveedor, por el valor "DE-001".</span><span class="sxs-lookup"><span data-stu-id="64ac3-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="64ac3-112">Haga clic en DE-001 para abrir los detalles del proveedor.</span><span class="sxs-lookup"><span data-stu-id="64ac3-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="64ac3-113">En el panel de acciones, haga clic en Proveedor.</span><span class="sxs-lookup"><span data-stu-id="64ac3-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="64ac3-114">Haga clic en Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="64ac3-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="64ac3-115">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="64ac3-115">Click Edit.</span></span>
    * <span data-ttu-id="64ac3-116">Si no hay ninguna cuenta bancaria disponible, necesita crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="64ac3-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="64ac3-117">En el campo Código SWIFT, escriba "COBADEFFXXX".</span><span class="sxs-lookup"><span data-stu-id="64ac3-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="64ac3-118">En el campo IBAN, escriba ''DE36200400000628808808".</span><span class="sxs-lookup"><span data-stu-id="64ac3-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="64ac3-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="64ac3-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="64ac3-120">Configuración de un método de pago para el proveedor</span><span class="sxs-lookup"><span data-stu-id="64ac3-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="64ac3-121">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="64ac3-121">Click Edit.</span></span>
2. <span data-ttu-id="64ac3-122">Expanda o contraiga la sección Pago.</span><span class="sxs-lookup"><span data-stu-id="64ac3-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="64ac3-123">En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="64ac3-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="64ac3-124">En la lista, haga clic en el vínculo de la fila SEPA CT.</span><span class="sxs-lookup"><span data-stu-id="64ac3-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="64ac3-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="64ac3-125">Click Save.</span></span>

