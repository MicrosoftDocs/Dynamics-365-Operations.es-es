---
title: Comprobador de coherencia de transacción comercial
description: Este tema describe la funcionalidad del comprobador de coherencia de transacción comercial en Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8b373ce3cfd1183a082e2b1ebaf8c907b16e581e
ms.sourcegitcommit: ca4562fafa33b3512f0a5e246b15545fcf53e834
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "380002"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="f573e-103">Comprobador de coherencia de transacción comercial</span><span class="sxs-lookup"><span data-stu-id="f573e-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="f573e-104">Este tema describe la funcionalidad del comprobador de coherencia de transacción comercial presentada en la versión 8.1.3. de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f573e-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="f573e-105">El comprobador de coherencia identifica y aísla transacciones incoherentes antes de que sean recogidos por el proceso de registro de extractos.</span><span class="sxs-lookup"><span data-stu-id="f573e-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="f573e-106">Cuando un extracto se registra en Retail, el registro puede fallar debido a datos incoherentes en las tablas de transacción comercial.</span><span class="sxs-lookup"><span data-stu-id="f573e-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="f573e-107">El problema de los datos puede ser causado por problemas imprevistos en la aplicación de punto de venta (PDV) o si las transacciones se importaron incorrectamente de los sistemas PDV de terceros.</span><span class="sxs-lookup"><span data-stu-id="f573e-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="f573e-108">Entre los ejemplos de cómo estas incoherencias pueden aparecer se incluyen:</span><span class="sxs-lookup"><span data-stu-id="f573e-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="f573e-109">El total de la transacción en la tabla de encabezado no coincide con el total de la transacción en las líneas.</span><span class="sxs-lookup"><span data-stu-id="f573e-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="f573e-110">El recuento de líneas en la tabla de encabezado no coincide con el número de líneas en la tabla de transacción.</span><span class="sxs-lookup"><span data-stu-id="f573e-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="f573e-111">Los impuestos de la tabla de encabezado no coinciden con el importe de impuestos en las líneas.</span><span class="sxs-lookup"><span data-stu-id="f573e-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="f573e-112">Cuando las transacciones incoherentes son recogidas por el proceso de registro de extractos, se crean facturas de ventas y diarios de pagos incoherentes y, como resultado, el proceso completo de registro de extractos da error.</span><span class="sxs-lookup"><span data-stu-id="f573e-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="f573e-113">Recuperar los extractos de ese estado implica correcciones de datos complejos en varias tablas de transacción.</span><span class="sxs-lookup"><span data-stu-id="f573e-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="f573e-114">El comprobador de coherencia de transacción comercial evita estos problemas.</span><span class="sxs-lookup"><span data-stu-id="f573e-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="f573e-115">El siguiente gráfico ilustra el proceso de registro con el comprobador de coherencia de transacción.</span><span class="sxs-lookup"><span data-stu-id="f573e-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="f573e-116">![Proceso de registro de extractos con comprobador de coherencia de transacción comercial](./media/validchecker.png "Proceso de registro de extractos con comprobador de coherencia de transacción comercial")</span><span class="sxs-lookup"><span data-stu-id="f573e-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transaction consistency checker")</span></span>

<span data-ttu-id="f573e-117">El proceso por lotes **Validar transacciones de la tienda** comprueba la coherencia de las tablas de transacción comercial para los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="f573e-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="f573e-118">Cuenta de cliente: valida que la cuenta de cliente en las tablas de transacción comercial existe en el maestro de clientes de la sede.</span><span class="sxs-lookup"><span data-stu-id="f573e-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="f573e-119">Recuento de líneas: valida que el número de líneas, como se recoge en la tabla de encabezado de transacción, coincide con el número de líneas en las tablas de transacción de ventas.</span><span class="sxs-lookup"><span data-stu-id="f573e-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="f573e-120">Configurar el comprobador de coherencia</span><span class="sxs-lookup"><span data-stu-id="f573e-120">Set up the consistency checker</span></span>
<span data-ttu-id="f573e-121">Configurar el proceso por lotes "Validan transacciones de la tienda", en **Venta minorista \> TI de venta minorista \> Registro de PDV**, para ejecuciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="f573e-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="f573e-122">El trabajo por lotes se puede programar según la jerarquía organizativa de la tienda, similar a cómo se configuran los procesos "Calcular extracto en lote" y "Registrar extracto en lote".</span><span class="sxs-lookup"><span data-stu-id="f573e-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="f573e-123">Es recomendable que configure este proceso por lotes para ejecutar varias veces en un día y programarlo de modo que se ejecute al final de cada ejecución de trabajo P.</span><span class="sxs-lookup"><span data-stu-id="f573e-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="f573e-124">Resultados del proceso de validación</span><span class="sxs-lookup"><span data-stu-id="f573e-124">Results of validation process</span></span>
<span data-ttu-id="f573e-125">Los resultados de la comprobación de validación por el proceso por lotes se etiquetan en la transacción comercial adecuada.</span><span class="sxs-lookup"><span data-stu-id="f573e-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="f573e-126">El campo **Estado de validación** en el registro de transacción comercial se establece en **Correcto** o **Error** y la fecha de la última ejecución de validación aparece en el campo **Hora de la última validación**.</span><span class="sxs-lookup"><span data-stu-id="f573e-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="f573e-127">Para ver un texto de error más descriptivo relativo a un error de validación, seleccione el registro de transacción de tienda relevante y haga clic en el botón **Errores de validación**.</span><span class="sxs-lookup"><span data-stu-id="f573e-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="f573e-128">Las transacciones que producen un error en la comprobación de validación y las transacciones que aún no se han validado no se incluirán en los extractos.</span><span class="sxs-lookup"><span data-stu-id="f573e-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="f573e-129">Durante el proceso "Calcule extracto", se notificará a los usuarios si hay transacciones que se habrían podido incluir en el extracto pero no se incluyeron.</span><span class="sxs-lookup"><span data-stu-id="f573e-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="f573e-130">Si se encuentra un error de validación, la única forma de corregir el error es contactar el Soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f573e-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="f573e-131">En una versión futura, se agregará una capacidad para que los usuarios puedan corregir los registros que produjeron error a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f573e-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="f573e-132">Las capacidades de registro y auditoría también estarán disponibles para realizar un seguimiento del historial de las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="f573e-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="f573e-133">En una versión futura se agregarán reglas de validación adicionales para admitir más escenarios.</span><span class="sxs-lookup"><span data-stu-id="f573e-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
