---
title: Configuración de la forma de pago para domiciliaciones bancarias ISO20022
description: Este procedimiento muestra cómo configurar la forma de pago de domiciliación bancaria ISO20022 del cliente o cualquier otro tipo de pago mediante informes electrónicos.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 953a3cffc356ab44163944318e7e7d542a113112
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "349685"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="0e2f0-103">Configuración de la forma de pago para domiciliaciones bancarias ISO20022</span><span class="sxs-lookup"><span data-stu-id="0e2f0-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e2f0-104">Este procedimiento muestra cómo configurar la forma de pago de domiciliación bancaria ISO20022 del cliente o cualquier otro tipo de pago mediante informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="0e2f0-105">Antes de completar esta tarea, debe definir las configuraciones de formato de exportación y las cuentas de pago.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="0e2f0-106">Este procedimiento se creó con los datos de demostración de la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="0e2f0-107">Este es el tercero de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="0e2f0-108">Vaya a Clientes > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="0e2f0-109">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0e2f0-110">Por ejemplo, filtre por el campo Forma de pago, por el valor "ELECTRONIC".</span><span class="sxs-lookup"><span data-stu-id="0e2f0-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="0e2f0-111">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-111">Click Edit.</span></span>
4. <span data-ttu-id="0e2f0-112">En el campo Cuenta de pago, especifique los valores "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="0e2f0-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="0e2f0-113">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="0e2f0-114">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="0e2f0-115">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="0e2f0-116">En la lista, seleccione ISO20022 Domiciliación bancaria (DE).</span><span class="sxs-lookup"><span data-stu-id="0e2f0-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="0e2f0-117">Si la lista está vacía, no hay ninguna configuración de formato de exportación de pago de cliente importada y activa.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="0e2f0-118">Seleccione Sí en el campo Requerir orden.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="0e2f0-119">Seleccione el parámetro Requerir orden para los formatos de pago del cliente, que requieren la información de la orden incluida en el mensaje de pago, como la domiciliación bancaria SEPA.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="0e2f0-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0e2f0-120">Click Save.</span></span>

