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
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d3c6d8157803e0a8d33520a0cd64fb725e8c9a3
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848656"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="474ff-103">Configuración de la forma de pago para domiciliaciones bancarias ISO20022</span><span class="sxs-lookup"><span data-stu-id="474ff-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="474ff-104">Este procedimiento muestra cómo configurar la forma de pago de domiciliación bancaria ISO20022 del cliente o cualquier otro tipo de pago mediante informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="474ff-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="474ff-105">Antes de completar esta tarea, debe definir las configuraciones de formato de exportación y las cuentas de pago.</span><span class="sxs-lookup"><span data-stu-id="474ff-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="474ff-106">Este procedimiento se creó con los datos de demostración de la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="474ff-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="474ff-107">Este es el tercero de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="474ff-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="474ff-108">Vaya a Clientes > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="474ff-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="474ff-109">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="474ff-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="474ff-110">Por ejemplo, filtre por el campo Forma de pago, por el valor "ELECTRONIC".</span><span class="sxs-lookup"><span data-stu-id="474ff-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="474ff-111">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="474ff-111">Click Edit.</span></span>
4. <span data-ttu-id="474ff-112">En el campo Cuenta de pago, especifique los valores "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="474ff-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="474ff-113">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="474ff-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="474ff-114">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="474ff-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="474ff-115">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="474ff-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="474ff-116">En la lista, seleccione ISO20022 Domiciliación bancaria (DE).</span><span class="sxs-lookup"><span data-stu-id="474ff-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="474ff-117">Si la lista está vacía, no hay ninguna configuración de formato de exportación de pago de cliente importada y activa.</span><span class="sxs-lookup"><span data-stu-id="474ff-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="474ff-118">Seleccione Sí en el campo Requerir orden.</span><span class="sxs-lookup"><span data-stu-id="474ff-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="474ff-119">Seleccione el parámetro Requerir orden para los formatos de pago del cliente, que requieren la información de la orden incluida en el mensaje de pago, como la domiciliación bancaria SEPA.</span><span class="sxs-lookup"><span data-stu-id="474ff-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="474ff-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="474ff-120">Click Save.</span></span>

