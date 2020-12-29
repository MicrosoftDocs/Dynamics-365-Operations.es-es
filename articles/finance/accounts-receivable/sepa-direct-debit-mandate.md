---
title: Configurar orden de domiciliación bancaria SEPA
description: Una domiciliación bancaria SEPA (Zona Única de Pagos en Euros) permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y se la haya entregado al acreedor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aba265e69bde9a9c194147d6ee6a806e9b2bd7c2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447505"
---
# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="3edd3-103">Configurar orden de domiciliación bancaria SEPA</span><span class="sxs-lookup"><span data-stu-id="3edd3-103">Set up SEPA direct debit mandate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3edd3-104">Una domiciliación bancaria SEPA (Zona Única de Pagos en Euros) permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y se la haya entregado al acreedor.</span><span class="sxs-lookup"><span data-stu-id="3edd3-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="3edd3-105">La orden que el cliente firma autoriza el acreedor a cobrar un pago y da instrucciones al banco del cliente para pagar el cobro.</span><span class="sxs-lookup"><span data-stu-id="3edd3-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="3edd3-106">Este tema está organizado para mostrar el proceso de configuración de órdenes de domiciliación bancaria SEPA.</span><span class="sxs-lookup"><span data-stu-id="3edd3-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3edd3-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3edd3-107">Prerequisites</span></span>
<span data-ttu-id="3edd3-108">La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="3edd3-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="3edd3-109">Categoría</span><span class="sxs-lookup"><span data-stu-id="3edd3-109">Category</span></span>       | <span data-ttu-id="3edd3-110">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="3edd3-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3edd3-111">País o región</span><span class="sxs-lookup"><span data-stu-id="3edd3-111">Country/region</span></span> | <span data-ttu-id="3edd3-112">La dirección principal de la entidad jurídica debe estar en los países/regiones siguientes: Alemania, Austria, Bélgica, España, Francia, Italia o los Países Bajos.</span><span class="sxs-lookup"><span data-stu-id="3edd3-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="3edd3-113">Configure una secuencia numérica para las órdenes de domiciliación bancaria. Cada orden de domiciliación bancaria debe tener un número único.</span><span class="sxs-lookup"><span data-stu-id="3edd3-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="3edd3-114">Use la página **Secuencias numéricas** para crear una secuencia numérica para las órdenes de domiciliación.</span><span class="sxs-lookup"><span data-stu-id="3edd3-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="3edd3-115">Usará este identificador para asignar la secuencia numérica en el sistema de órdenes de domiciliación en la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="3edd3-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="3edd3-116">Configurar los parámetros de clientes para las órdenes de domiciliación. Use la página **Parámetros de clientes** para configurar los parámetros para los pedidos de débito directo.</span><span class="sxs-lookup"><span data-stu-id="3edd3-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="3edd3-117">Para configurar los parámetros, en la pestaña **Domiciliación bancaria**, cambie los parámetros predeterminados como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3edd3-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="3edd3-118">A continuación, en la pestaña **Secuencias numéricas**, actualice el campo **Id. de orden de domiciliación bancaria** con la secuencia numérica configurada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3edd3-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="3edd3-119">Configurar un método de pago para las órdenes de domiciliación. Debe configurar un método de pago para las órdenes de domiciliación.</span><span class="sxs-lookup"><span data-stu-id="3edd3-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="3edd3-120">Este método de pago se usa para realizar consultas de facturas para las que desee generar pagos por domiciliación.</span><span class="sxs-lookup"><span data-stu-id="3edd3-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="3edd3-121">Use la página **Formas de pago** para configurar el método de pago.</span><span class="sxs-lookup"><span data-stu-id="3edd3-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="3edd3-122">Para configurar un método de pago para las órdenes de domiciliación bancaria, debe seguir estos pasos adicionales para un método de pago:</span><span class="sxs-lookup"><span data-stu-id="3edd3-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="3edd3-123">En el campo **Tipo de pago**, seleccione **Pago electrónico**.</span><span class="sxs-lookup"><span data-stu-id="3edd3-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="3edd3-124">Opcional: si espera que cada uno de los clientes tenga varias órdenes, en el campo **Período**, seleccione **Factura**.</span><span class="sxs-lookup"><span data-stu-id="3edd3-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="3edd3-125">Se crea un pago independiente para cada factura y cada pago usa la orden que se especifica para la factura.</span><span class="sxs-lookup"><span data-stu-id="3edd3-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="3edd3-126">Seleccione la opción **Requerir orden** para crear pagos con órdenes de domiciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="3edd3-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="3edd3-127">La opción **Requerir orden** solo está disponible si selecciona **Pago electrónico** en el campo **Tipo de pago**.</span><span class="sxs-lookup"><span data-stu-id="3edd3-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="3edd3-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3edd3-128">Additional resources</span></span>

[<span data-ttu-id="3edd3-129">Visión general de las domiciliaciones SEPA</span><span class="sxs-lookup"><span data-stu-id="3edd3-129">SEPA direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="3edd3-130">Crear una orden de domiciliación bancaria para un cliente</span><span class="sxs-lookup"><span data-stu-id="3edd3-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 

