--- 
title: "Configuración forma de pago para transferencias de crédito ISO20022"
description: "Este procedimiento muestra cómo configurar la forma de pago de la transferencia de crédito ISO20022 del proveedor o cualquier otro tipo de pago mediante informes electrónicos para generar un archivo."
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
ms.openlocfilehash: 6c45324b1523e29aa5c6274b289fa823bf66ea12
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a><span data-ttu-id="1f9e6-103">Configuración forma de pago para transferencias de crédito ISO20022</span><span class="sxs-lookup"><span data-stu-id="1f9e6-103">Set up method of payment for ISO20022 credit transfer</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f9e6-104">Este procedimiento muestra cómo configurar la forma de pago de la transferencia de crédito ISO20022 del proveedor o cualquier otro tipo de pago mediante informes electrónicos para generar un archivo.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-104">This procedure shows how to set up the vendor method of payment for ISO20022 credit transfer or any other payment type using electronic reporting to generate a file.</span></span> 

<span data-ttu-id="1f9e6-105">Antes de completar esta tarea, debe exportar las configuraciones de formato y configurar las cuentas de pago.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-105">Before you complete this task, you must export format configurations and set up payment accounts.</span></span>

<span data-ttu-id="1f9e6-106">Esta tarea se creó con la empresa de datos de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-106">This task was created using the DEMF demo data company.</span></span>

<span data-ttu-id="1f9e6-107">Este es el tercer procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-107">This is the third procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="1f9e6-108">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="1f9e6-109">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-109">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="1f9e6-110">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="1f9e6-111">Por ejemplo, filtre por el campo Forma de pago, por el valor "SEPA CT".</span><span class="sxs-lookup"><span data-stu-id="1f9e6-111">For example, filter on the Method of payment field with a value of 'SEPA CT'.</span></span>
3. <span data-ttu-id="1f9e6-112">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-112">Click Edit.</span></span>
4. <span data-ttu-id="1f9e6-113">En el campo Período, seleccione Total.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-113">In the Period field, select 'Total'.</span></span>
5. <span data-ttu-id="1f9e6-114">En el campo Tipo de pago, seleccione Pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-114">In the Payment type field, select 'Electronic payment'.</span></span>
6. <span data-ttu-id="1f9e6-115">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-115">Expand the File formats section.</span></span>
7. <span data-ttu-id="1f9e6-116">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-116">Select Yes in the Generic electronic reporting field.</span></span>
8. <span data-ttu-id="1f9e6-117">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-117">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="1f9e6-118">En la lista, seleccione el valor de transferencia de crédito ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="1f9e6-118">In the list, select the value ISO20022 Credit transfer (DE).</span></span> <span data-ttu-id="1f9e6-119">Si la lista está vacía, no hay ninguna configuración de formato de exportación de pago de proveedor importada y activa.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-119">If the list is empty, the vendor payment export format configuration is not imported and active.</span></span>  
9. <span data-ttu-id="1f9e6-120">En el campo Tipo de cuenta, seleccione Banco.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-120">In the Account type field, select 'Bank'.</span></span>
10. <span data-ttu-id="1f9e6-121">En el campo Cuenta de pago, especifique los valores "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="1f9e6-121">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
11. <span data-ttu-id="1f9e6-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1f9e6-122">Click Save.</span></span>


