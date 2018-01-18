--- 
title: Almacenar configuraciones para los extractos de Retail
description: Este procedimiento muestra las configuraciones para la Tienda que afectan la manera en que se crean y se registran los extractos comerciales.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 96aff33904c1de4a8b2642890eba7bf854d8e0c1
ms.contentlocale: es-es
ms.lasthandoff: 01/18/2018

---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="782b2-103">Almacenar configuraciones para los extractos de Retail</span><span class="sxs-lookup"><span data-stu-id="782b2-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="782b2-104">Este procedimiento muestra las configuraciones para la Tienda que afectan la manera en que se crean y se registran los extractos comerciales.</span><span class="sxs-lookup"><span data-stu-id="782b2-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="782b2-105">Las dimensiones financieras en tiendas se cubren en otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="782b2-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="782b2-106">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="782b2-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="782b2-107">Vaya a Venta minorista y comercio > Canales > Tiendas > Todas las tiendas minoristas.</span><span class="sxs-lookup"><span data-stu-id="782b2-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="782b2-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="782b2-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="782b2-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="782b2-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="782b2-110">La configuración de la sección Extracto o cierre afecta a la creación, la validación y al registro de extractos para el almacén.</span><span class="sxs-lookup"><span data-stu-id="782b2-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="782b2-111">Abra la sección Extracto o cierre.</span><span class="sxs-lookup"><span data-stu-id="782b2-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="782b2-112">Seleccione el método que desea usar para agrupar las líneas de extracto.</span><span class="sxs-lookup"><span data-stu-id="782b2-112">Select the method you want to use to group the statement lines by.</span></span>  
    * <span data-ttu-id="782b2-113">Seleccione "Sí" si solo se debería crear un extracto al día al crear extractos del trabajo por lotes de la creación de extractos.</span><span class="sxs-lookup"><span data-stu-id="782b2-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="782b2-114">El campo Cálculo de declaración por forma de pago define si las declaraciones por forma de pago se deben agregar juntas o si se debe usar la última.</span><span class="sxs-lookup"><span data-stu-id="782b2-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="782b2-115">Seleccione la cuenta contable en la que registrar diferencias de redondeo.</span><span class="sxs-lookup"><span data-stu-id="782b2-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="782b2-116">En el campo de diferencias de redondeo máxima, puede especificar la diferencia de redondeo máxima permitida.</span><span class="sxs-lookup"><span data-stu-id="782b2-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="782b2-117">En el campo Registro, puede especificar la diferencia de registro total máxima permitida para un extracto.</span><span class="sxs-lookup"><span data-stu-id="782b2-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="782b2-118">En el campo Turno, puede especificar la diferencia total máxima dentro de un turno en un extracto.</span><span class="sxs-lookup"><span data-stu-id="782b2-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="782b2-119">En el campo Transacción, puede especificar la diferencia total máxima en una línea de extracto.</span><span class="sxs-lookup"><span data-stu-id="782b2-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="782b2-120">En el campo Método de cierre, puede definir si las transacciones que se incluirán en un extracto deben parte de un turno cerrado o si puede haber algunas transacciones dentro del intervalo definido de fecha o hora.</span><span class="sxs-lookup"><span data-stu-id="782b2-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="782b2-121">En el campo Final del día laboral, puede especificar una hora si las transacciones que se producen después de medianoche se deben registrar con el día anterior.</span><span class="sxs-lookup"><span data-stu-id="782b2-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="782b2-122">Seleccione "Sí" si las transacciones que se producen después de medianoche se deben registrar como parte del día anterior.</span><span class="sxs-lookup"><span data-stu-id="782b2-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="782b2-123">Seleccione "Sí" para que se creen extractos para cada método de extracto definido.</span><span class="sxs-lookup"><span data-stu-id="782b2-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="782b2-124">Esto puede resultar útil si el rendimiento del registro se debe mejorar para almacenes con volúmenes altos de transacción puesto que creará muchos extractos más pequeños que se pueden procesar en paralelo.</span><span class="sxs-lookup"><span data-stu-id="782b2-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="782b2-125">En el campo Cliente predeterminado, puede seleccionar la cuenta de cliente que se usará para ventas a los clientes que entran.</span><span class="sxs-lookup"><span data-stu-id="782b2-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  


