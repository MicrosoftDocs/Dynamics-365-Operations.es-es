--- 
title: "Configurar las opciones de método de pago que afectan a los extractos comerciales"
description: "Este procedimiento muestra las configuraciones para los métodos de pago comerciales, que afectan a la manera en que se crean y se registran los extractos comerciales."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ba21db9ee97dc4d851c77a906927ef513940b743
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="configure-payment-method-settings-that-affect-retail-statements"></a><span data-ttu-id="565c3-103">Configurar las opciones de método de pago que afectan a los extractos comerciales</span><span class="sxs-lookup"><span data-stu-id="565c3-103">Configure payment method settings that affect retail statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="565c3-104">Este procedimiento muestra las configuraciones para los métodos de pago comerciales, que afectan a la manera en que se crean y se registran los extractos comerciales.</span><span class="sxs-lookup"><span data-stu-id="565c3-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="565c3-105">Esta grabación usa la empresa de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="565c3-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="565c3-106">Vaya a Venta minorista y comercio > Canales > Tiendas > Todas las tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="565c3-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="565c3-107">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="565c3-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="565c3-108">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="565c3-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="565c3-109">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="565c3-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="565c3-110">Haga clic en Métodos de pago.</span><span class="sxs-lookup"><span data-stu-id="565c3-110">Click Payment methods.</span></span>
6. <span data-ttu-id="565c3-111">Expanda o contraiga la sección Registro.</span><span class="sxs-lookup"><span data-stu-id="565c3-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="565c3-112">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="565c3-112">Click Edit.</span></span>
    * <span data-ttu-id="565c3-113">Seleccione si los importes recibidos para este método de pago se deben registrar en una cuenta contable o en una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="565c3-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="565c3-114">Seleccione la cuenta en la que se deben registrar los importes recibidos para este método de pago.</span><span class="sxs-lookup"><span data-stu-id="565c3-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="565c3-115">Seleccione una cuenta para registrar posibles diferencias entre el importe total de la transacción recibido y el importe contado para este método de pago.</span><span class="sxs-lookup"><span data-stu-id="565c3-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="565c3-116">En este campo puede especificar un importe para controlar cuándo se debe registrar el importe de la diferencia en otra cuenta de diferencia.</span><span class="sxs-lookup"><span data-stu-id="565c3-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="565c3-117">Puede usar esto para realizar un seguimiento de grandes diferencias.</span><span class="sxs-lookup"><span data-stu-id="565c3-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="565c3-118">Seleccione una cuenta para registrar posibles diferencias entre el importe total de la transacción recibido y el importe contado, cuando supera el valor definido en el campo de "Importe máximo de diferencia".</span><span class="sxs-lookup"><span data-stu-id="565c3-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="565c3-119">Seleccione "Sí" para registrar importes de ingresos bancarios en una cuenta independiente.</span><span class="sxs-lookup"><span data-stu-id="565c3-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="565c3-120">En este campo puede seleccionar si se deben registrar importes de ingresos bancarios en una cuenta contable o en una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="565c3-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="565c3-121">Seleccione la cuenta en la que registrar importes de ingresos bancarios.</span><span class="sxs-lookup"><span data-stu-id="565c3-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="565c3-122">Seleccione el tipo de transacción bancaria que se usará al registrar importes de ingresos bancarios en la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="565c3-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="565c3-123">Seleccione "Sí" para registrar importes seguros en una cuenta independiente.</span><span class="sxs-lookup"><span data-stu-id="565c3-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="565c3-124">Seleccione si se deben registrar importes seguros en la cuenta contable o en la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="565c3-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="565c3-125">Seleccione la cuenta en la que registrar importes seguros.</span><span class="sxs-lookup"><span data-stu-id="565c3-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="565c3-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="565c3-126">Click Save.</span></span>


