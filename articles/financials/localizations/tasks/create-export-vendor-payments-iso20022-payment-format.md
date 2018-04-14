--- 
title: "Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022"
description: "Este procedimiento muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5787edc4a041e4b571c7ab6f056f4bd0a17cf2d7
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="4221c-103">Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022</span><span class="sxs-lookup"><span data-stu-id="4221c-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4221c-104">Este procedimiento muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="4221c-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="4221c-105">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="4221c-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="4221c-106">Este es el quinto procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4221c-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="4221c-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="4221c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="4221c-108">Creación de líneas de pago</span><span class="sxs-lookup"><span data-stu-id="4221c-108">Create payment lines</span></span>
1. <span data-ttu-id="4221c-109">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="4221c-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="4221c-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4221c-110">Click New.</span></span>
3. <span data-ttu-id="4221c-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4221c-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="4221c-112">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4221c-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="4221c-113">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="4221c-113">Click Lines.</span></span>
6. <span data-ttu-id="4221c-114">Haga clic en Propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="4221c-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="4221c-115">Haga clic en Crear propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="4221c-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="4221c-116">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="4221c-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="4221c-117">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="4221c-117">Click Filter.</span></span>
10. <span data-ttu-id="4221c-118">En la lista, seleccione la fila para la tabla Proveedores y el campo Cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="4221c-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="4221c-119">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4221c-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="4221c-120">Puede aplicar cualquier criterio para seleccionar transacciones de proveedor para pagar, por ejemplo, use DE-001 como cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="4221c-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="4221c-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4221c-121">Click OK.</span></span>
13. <span data-ttu-id="4221c-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4221c-122">Click OK.</span></span>
14. <span data-ttu-id="4221c-123">Haga clic en Crear pagos.</span><span class="sxs-lookup"><span data-stu-id="4221c-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="4221c-124">Generación de un archivo de pago ISO20022</span><span class="sxs-lookup"><span data-stu-id="4221c-124">Generate an ISO20022 payment file</span></span>


