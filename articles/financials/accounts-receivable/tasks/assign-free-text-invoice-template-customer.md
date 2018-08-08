--- 
title: Asignar una plantilla de factura de servicios a un cliente
description: "Esta tarea muestra cómo asignar una plantilla de factura de texto libre a un cliente."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e29122fa775385ca4d407ddbe190626d743da69b
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="ff3de-103">Asignar una plantilla de factura de servicios a un cliente</span><span class="sxs-lookup"><span data-stu-id="ff3de-103">Assign a free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff3de-104">Esta tarea muestra cómo asignar una plantilla de factura de texto libre a un cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="ff3de-105">Esta tarea utiliza la empresa de demostración USMF y se va a utilizar para el usuario responsable de gestionar y de procesar facturas de cuentas por cobrar.</span><span class="sxs-lookup"><span data-stu-id="ff3de-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="ff3de-106">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="ff3de-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="ff3de-107">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ff3de-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ff3de-108">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="ff3de-108">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="ff3de-109">Haga clic en Facturas periódicas.</span><span class="sxs-lookup"><span data-stu-id="ff3de-109">Click Recurring invoices.</span></span>
    * <span data-ttu-id="ff3de-110">Use esta página para asignar plantillas de factura de texto libre a clientes y especificar la frecuencia con la que se enviarán facturas al cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="ff3de-111">Haga clic en Nuevo para asignar una plantilla nueva al cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-111">Click New to assign a new template to the customer.</span></span>
6. <span data-ttu-id="ff3de-112">Seleccione la plantilla de factura de texto libre que desee asignar al cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-112">Select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="ff3de-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ff3de-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ff3de-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff3de-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ff3de-115">Escriba la fecha en que se generará la primera factura.</span><span class="sxs-lookup"><span data-stu-id="ff3de-115">Enter the date when the first invoice will be generated.</span></span>
    * <span data-ttu-id="ff3de-116">Especifique una fecha final periódica.</span><span class="sxs-lookup"><span data-stu-id="ff3de-116">Enter a recurring end date.</span></span>  
    * <span data-ttu-id="ff3de-117">Seleccione alguna de las siguientes opciones: No hay fecha final: las facturas se generarán de manera indefinida hasta que se elimine la plantilla de la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>  <span data-ttu-id="ff3de-118">Fecha de finalización de la facturación: seleccione esta opción y escriba la última fecha en la que se puede generar la factura.</span><span class="sxs-lookup"><span data-stu-id="ff3de-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
    * <span data-ttu-id="ff3de-119">El importe acumulativo máximo tras el cual dejarán de generarse facturas.</span><span class="sxs-lookup"><span data-stu-id="ff3de-119">Maximum cumulative amount after which invoice generation will stop.</span></span>  
    * <span data-ttu-id="ff3de-120">Especifique el importe acumulado máximo que se puede alcanzar mediante la plantilla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff3de-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="ff3de-121">Por ejemplo, si especifica 1.000,00 y genera facturas mensuales por 100,00 cada una, la generación de facturas se detendrá al generarse la décima factura.</span><span class="sxs-lookup"><span data-stu-id="ff3de-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
    * <span data-ttu-id="ff3de-122">Genere facturas periódicas mediante los valores predeterminados de la plantilla de factura de texto libre o la cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-122">Generate recurring invoices by using the default values from either free text invoice template or the customer account.</span></span>  
    * <span data-ttu-id="ff3de-123">Seleccione si se debe usar la plantilla de factura de servicios o la cuenta de cliente para determinar los valores predeterminados del idioma, el perfil de contabilización, el grupo de impuestos, el grupo de impuestos de artículos, el código de lista, el país o región de la entrega, la divisa, las condiciones de pago, la forma de pago, la especificación del pago, la programación del pago, el descuento por pronto pago, las dimensiones financieras y el resguardo de la transferencia del giro bancario cuando se crean las facturas.</span><span class="sxs-lookup"><span data-stu-id="ff3de-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
10. <span data-ttu-id="ff3de-124">Seleccione el patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="ff3de-124">Select the recurrence pattern.</span></span>
    * <span data-ttu-id="ff3de-125">Diariamente: seleccione esta opción y especifique el número de días en el campo Por.</span><span class="sxs-lookup"><span data-stu-id="ff3de-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="ff3de-126">Por ejemplo, si escribe 15, se generará una factura cada 15 días para este cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>  <span data-ttu-id="ff3de-127">Semanal: seleccione esta opción y especifique el número de semanas en el campo Por.</span><span class="sxs-lookup"><span data-stu-id="ff3de-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="ff3de-128">Por ejemplo, si escribe 2, se generará una factura cada dos semanas para este cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>  <span data-ttu-id="ff3de-129">Mensual: seleccione esta opción y especifique el número de meses en el campo Por.</span><span class="sxs-lookup"><span data-stu-id="ff3de-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="ff3de-130">Por ejemplo, si escribe 6, se generará una factura cada seis meses para este cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>  <span data-ttu-id="ff3de-131">Anual: seleccione esta opción y especifique el número de años en el campo Por.</span><span class="sxs-lookup"><span data-stu-id="ff3de-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="ff3de-132">Por ejemplo, si escribe 2, se generará una factura cada dos años para este cliente.</span><span class="sxs-lookup"><span data-stu-id="ff3de-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
11. <span data-ttu-id="ff3de-133">En el campo Por, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ff3de-133">In the Per field, enter a number.</span></span>


