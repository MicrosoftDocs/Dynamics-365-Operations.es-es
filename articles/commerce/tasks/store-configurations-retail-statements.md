---
title: Almacenar configuraciones para los extractos de Retail
description: Este procedimiento muestra las configuraciones para la tienda que afectan a la manera en que se crean y se registran los extractos de Commerce.
author: jashanno
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: da862af25df241ad42b7e1ade3fdca19f6280278
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804122"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="6d011-103">Almacenar configuraciones para los extractos de Retail</span><span class="sxs-lookup"><span data-stu-id="6d011-103">Store configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d011-104">Este procedimiento muestra las configuraciones para la tienda que afectan a la manera en que se crean y se registran los extractos de Commerce.</span><span class="sxs-lookup"><span data-stu-id="6d011-104">This procedure walks through configurations for the store that affect how Commerce statements get created and posted.</span></span> <span data-ttu-id="6d011-105">Las dimensiones financieras en tiendas se cubren en otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6d011-105">Financial dimensions on stores are covered in another procedure.</span></span> <span data-ttu-id="6d011-106">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="6d011-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="6d011-107">En el **Panel de navegación**, vaya **Módulos > Retail y Commerce > Canales > Tiendas > Todas las tiendas**.</span><span class="sxs-lookup"><span data-stu-id="6d011-107">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
2. <span data-ttu-id="6d011-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6d011-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6d011-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6d011-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="6d011-110">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d011-110">Click **Edit**.</span></span>
5. <span data-ttu-id="6d011-111">La configuración de la ficha desplegable **Extracto/cierre** afecta a la creación, la validación y al registro de extractos para el almacén.</span><span class="sxs-lookup"><span data-stu-id="6d011-111">The settings in the **Statement/closing** FastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="6d011-112">Expanda la ficha desplegable **Extracto/cierre**.</span><span class="sxs-lookup"><span data-stu-id="6d011-112">Expand the **Statement/closing** FastTab.</span></span>  
6. <span data-ttu-id="6d011-113">En el campo **Método de extracto**, seleccione el método que desea usar para agrupar las líneas de extracto.</span><span class="sxs-lookup"><span data-stu-id="6d011-113">In the **Statement method** field, select the method you want to use to group the statement lines by.</span></span>  
7. <span data-ttu-id="6d011-114">Seleccione "Sí" en **Un extracto al día** si solo se debería crear un extracto al día al crear extractos del trabajo por lotes de la creación de extractos.</span><span class="sxs-lookup"><span data-stu-id="6d011-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="6d011-115">El campo **Cálculo de declaración por forma de pago** define si las declaraciones por forma de pago se deben agregar juntas o si se debe usar la última.</span><span class="sxs-lookup"><span data-stu-id="6d011-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="6d011-116">En el campo **Redondeo**, seleccione la cuenta contable en la que registrar diferencias de redondeo.</span><span class="sxs-lookup"><span data-stu-id="6d011-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="6d011-117">En el campo **Diferencia de redondeo máxima**, especifique la diferencia de redondeo máxima permitida.</span><span class="sxs-lookup"><span data-stu-id="6d011-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="6d011-118">En el campo **Registro**, introduzca la diferencia de registro total máxima permitida para un extracto.</span><span class="sxs-lookup"><span data-stu-id="6d011-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="6d011-119">En el campo **Turno**, especifique la diferencia total máxima dentro de un turno en un extracto.</span><span class="sxs-lookup"><span data-stu-id="6d011-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="6d011-120">En el campo **Transacción**, introduzca la diferencia total máxima en una línea de extracto.</span><span class="sxs-lookup"><span data-stu-id="6d011-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="6d011-121">En el campo **Método de cierre**, defina si las transacciones que se incluirán en un extracto deben parte de un turno cerrado o si puede haber algunas transacciones dentro del intervalo definido de fecha o hora.</span><span class="sxs-lookup"><span data-stu-id="6d011-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="6d011-122">En el campo **Final del día laboral**, especifique una hora si las transacciones que se producen después de medianoche se deben registrar con el día anterior.</span><span class="sxs-lookup"><span data-stu-id="6d011-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="6d011-123">Seleccione "Sí" en **Registrar como día laboral** si las transacciones que se producen después de medianoche se deben registrar como parte del día anterior.</span><span class="sxs-lookup"><span data-stu-id="6d011-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="6d011-124">Seleccione "Sí" en **Dividir por método de extracto** para que se creen extractos para cada método de extracto definido.</span><span class="sxs-lookup"><span data-stu-id="6d011-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="6d011-125">Esta acción puede resultar útil si el rendimiento del registro se debe mejorar para almacenes con volúmenes altos de transacción puesto que creará muchos extractos más pequeños que se pueden procesar en paralelo.</span><span class="sxs-lookup"><span data-stu-id="6d011-125">This action can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="6d011-126">En la ficha desplegable **General**, en el campo **Cliente predeterminado**, puede seleccionar la cuenta de cliente que se usará para ventas a los clientes que entran.</span><span class="sxs-lookup"><span data-stu-id="6d011-126">In the **General** FastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]