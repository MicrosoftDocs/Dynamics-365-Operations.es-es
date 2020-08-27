---
title: Conciliación financiera en tiendas minoristas
description: Este tema describe la conciliación financiera en las tiendas minoristas de PDV para Microsoft Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
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
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5d0520f35391f76b52fd8a333033b0d7ba4f7fe1
ms.sourcegitcommit: 1e6a7b50596eaf9d965e0155f3f2c50f7f50747e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "3498022"
---
# <a name="financial-reconciliation-in-retail-stores"></a><span data-ttu-id="f3f83-103">Conciliación financiera en tiendas minoristas</span><span class="sxs-lookup"><span data-stu-id="f3f83-103">Financial reconciliation in retail stores</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f3f83-104">En Microsoft Dynamics 365 Commerce versión 10.0.10 y anteriores, la funcionalidad que el cliente de punto de venta (PDV) proporciona para los procesos de fin de día en las tiendas minoristas, permite que los empleados y gerentes de las tiendas realicen las operaciones de fin de día.</span><span class="sxs-lookup"><span data-stu-id="f3f83-104">In Microsoft Dynamics 365 Commerce version 10.0.10 and earlier, the functionality that the point of sale (POS) client provides for end-of-day processes in retail stores lets store clerks and store managers perform end-of-day operations.</span></span> <span data-ttu-id="f3f83-105">Por ejemplo, pueden hacer declaraciones de licitación, turnos de cierre a ciegas, conciliar transacciones de turnos y cerrar turnos.</span><span class="sxs-lookup"><span data-stu-id="f3f83-105">For example, they can do tender declarations, blind-close shifts, reconcile shift transactions, and close shifts.</span></span> <span data-ttu-id="f3f83-106">Sin embargo, no hay capacidad en PDV para finalizar la información financiera para los turnos, de modo que pueda usarse para publicar los datos financieros en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-106">However, there is no capability in POS to finalize the financial information for shifts, so that it can be used to post the financials in Commerce headquarters.</span></span> <span data-ttu-id="f3f83-107">Por lo general, los gerentes de tienda son responsables de completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f3f83-107">Typically, store managers are responsible for completing this task.</span></span> <span data-ttu-id="f3f83-108">Antes de que puedan firmar un turno, deben revisar la información, hacer las correcciones necesarias y finalizar los totales de ese turno.</span><span class="sxs-lookup"><span data-stu-id="f3f83-108">Before they can sign off on a shift, they must review the information, make any corrections that are required, and finalize the totals for that shift.</span></span> <span data-ttu-id="f3f83-109">Los totales finalizados deben publicarse en módulos financieros en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-109">The finalized totals should then be posted in financial modules in Commerce headquarters.</span></span>

<span data-ttu-id="f3f83-110">Además, en Commerce versión 10.0.10 y anteriores, los gerentes de las tiendas pueden revisar y hacer algunos ajustes a las líneas de declaración en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-110">Additionally, in Commerce version 10.0.10 and earlier, store managers can review and make some adjustments to statement lines in Commerce headquarters.</span></span> <span data-ttu-id="f3f83-111">Sin embargo, la capacidad es limitada y los gerentes de las tiendas rara vez tienen acceso al cliente de la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-111">However, the capability is limited, and store managers rarely have access to the Commerce headquarters client.</span></span> <span data-ttu-id="f3f83-112">Además, la revisión y el ajuste de los estados financieros minoristas solo se pueden realizar cuando las instrucciones se crean en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-112">Moreover, financial retail statement review and adjustment can be done only when the statements are created in Commerce headquarters.</span></span> <span data-ttu-id="f3f83-113">Sin embargo, ese proceso es típicamente un proceso nocturno.</span><span class="sxs-lookup"><span data-stu-id="f3f83-113">However, that process is typically a nightly process.</span></span> <span data-ttu-id="f3f83-114">Por lo tanto, los gerentes de las tiendas deben esperar la firma del turno cuando se crean los estados financieros minoristas en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-114">Therefore, store managers must wait for the shift sign-off when financial retail statements are created in Commerce headquarters.</span></span>

<span data-ttu-id="f3f83-115">En Commerce versión 10.0.11 y posterior, los gerentes de las tiendas pueden revisar, ajustar y finalizar sus turnos en el propio cliente PDV.</span><span class="sxs-lookup"><span data-stu-id="f3f83-115">In Commerce version 10.0.11 and later, store managers can review, adjust, and finalize their shifts in the POS client itself.</span></span> <span data-ttu-id="f3f83-116">Esos datos se utilizan para crear y publicar declaraciones financieras minoristas en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-116">That data is then used to create and post financial retail statements in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="f3f83-117">La funcionalidad que está relacionada con la reconciliación financiera en las tiendas minoristas solo funciona si la creación de pedidos basada en alimentación lenta está activada.</span><span class="sxs-lookup"><span data-stu-id="f3f83-117">The functionality that is related to financial reconciliation in retail stores works only if trickle feed–based order creation is turned on.</span></span> <span data-ttu-id="f3f83-118">Para más información, consulte [Goteo en la creación de pedidos basados en fuente para transacciones de tienda](trickle-feed.md).</span><span class="sxs-lookup"><span data-stu-id="f3f83-118">For more information, see [Trickle feed-based order creation for retail store transactions](trickle-feed.md).</span></span>

## <a name="set-up-financial-reconciliation"></a><span data-ttu-id="f3f83-119">Configurar conciliación financiera</span><span class="sxs-lookup"><span data-stu-id="f3f83-119">Set up financial reconciliation</span></span>

<span data-ttu-id="f3f83-120">Siga estos pasos para comenzar a usar la funcionalidad de conciliación financiera.</span><span class="sxs-lookup"><span data-stu-id="f3f83-120">Follow these steps to use the financial reconciliation functionality.</span></span>

1. <span data-ttu-id="f3f83-121">En el espacio de trabajo **Gestión de funciones**, active la característica **Declaraciones minoristas: alimentación por goteo**.</span><span class="sxs-lookup"><span data-stu-id="f3f83-121">In the **Feature management** workspace, turn on the **Retail statements - Trickle feed** feature.</span></span>
1. <span data-ttu-id="f3f83-122">En el perfil de funcionalidad PDV para la tienda adecuada, establezca la opción **Habilitar la conciliación financiera en la tienda** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f3f83-122">In the POS functionality profile for the appropriate store, set the **Enable financial reconciliation in store** option to **Yes**.</span></span>

## <a name="more-information-about-financial-reconciliation"></a><span data-ttu-id="f3f83-123">Más información sobre la conciliación financiera</span><span class="sxs-lookup"><span data-stu-id="f3f83-123">More information about financial reconciliation</span></span>

<span data-ttu-id="f3f83-124">Cuando la funcionalidad de conciliación financiera está activada, algunos de los parámetros definidos en la ficha desplegable **Declaración / cierre** de la página **Tiendas minoristas** en la sede de Commerce se sincroniza con la base de datos del canal.</span><span class="sxs-lookup"><span data-stu-id="f3f83-124">When the financial reconciliation functionality is turned on, some of the parameters that are defined on the **Statement/closing** FastTab of the **Retail stores** page in Commerce headquarters are synced to the channel database.</span></span> <span data-ttu-id="f3f83-125">Se aplica el mismo conjunto de criterios de cálculo y umbrales de importe que se utilizan para los extractos minoristas.</span><span class="sxs-lookup"><span data-stu-id="f3f83-125">The same set of calculation criteria and amount thresholds that is used for retail statements is enforced.</span></span>

<span data-ttu-id="f3f83-126">Cuando se invoca la operación **Cerrar turno**, el sistema valida que las cantidades calculadas por el sistema y las cantidades declaradas coinciden.</span><span class="sxs-lookup"><span data-stu-id="f3f83-126">When the **Close shift** operation is invoked, the system validates that the system-computed amounts and the declared amounts match.</span></span> <span data-ttu-id="f3f83-127">Si difieren y la diferencia excede los umbrales definidos, se consulta al usuario y puede hacer los ajustes necesarios.</span><span class="sxs-lookup"><span data-stu-id="f3f83-127">If they differ, and the difference exceeds defined thresholds, the user is prompted and can make the required adjustments.</span></span>

<span data-ttu-id="f3f83-128">Se pueden hacer ajustes para cada oferta.</span><span class="sxs-lookup"><span data-stu-id="f3f83-128">Adjustments can be made for each tender.</span></span> <span data-ttu-id="f3f83-129">Cuando se selecciona una operación, el usuario puede ver los totales para diferentes tipos de transacciones y editar los totales para un tipo de transacción específico.</span><span class="sxs-lookup"><span data-stu-id="f3f83-129">When a tender is selected, the user can view the totals for different transaction types and edit the totals for a specific transaction type.</span></span> <span data-ttu-id="f3f83-130">Durante la edición, el sistema muestra la cantidad calculada original y la cantidad anulada para ese tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="f3f83-130">During editing, the system shows the original computed amount and the overridden amount for that transaction type.</span></span> <span data-ttu-id="f3f83-131">El usuario también puede capturar notas como parte del proceso de edición.</span><span class="sxs-lookup"><span data-stu-id="f3f83-131">The user can also capture notes as a part of the editing process.</span></span> <span data-ttu-id="f3f83-132">Las notas se pueden usar con fines de auditoría.</span><span class="sxs-lookup"><span data-stu-id="f3f83-132">Notes can be used for auditing purposes.</span></span>

<span data-ttu-id="f3f83-133">Los usuarios pueden ignorar las solicitudes y mensajes de validación y pueden proceder a cerrar el turno.</span><span class="sxs-lookup"><span data-stu-id="f3f83-133">Users can ignore the validation prompts and messages, and can proceed to close the shift.</span></span> <span data-ttu-id="f3f83-134">Sin embargo, si un usuario ignora las indicaciones de validación, surgirán los mismos problemas y deberán corregirse cuando el turno publique los estados financieros en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3f83-134">However, if a user ignores the validation prompts, the same issues will arise and will have to be fixed when the shift posts financial statements in Commerce headquarters.</span></span>

<span data-ttu-id="f3f83-135">La operación **Cerrar turno** en PDV también valida que todas las transacciones en la base de datos fuera de línea se sincronizan con la base de datos del canal.</span><span class="sxs-lookup"><span data-stu-id="f3f83-135">The **Close shift** operation in POS also validates that all transactions in the offline database are synced to the channel database.</span></span> <span data-ttu-id="f3f83-136">Si alguna transacción no se sincroniza, el usuario recibe un mensaje de advertencia, ya que esta situación puede hacer que las cantidades del sistema se calculen incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="f3f83-136">If any transactions aren't synced, the user receives a warning message, because this situation can cause the system amounts to be incorrectly computed.</span></span> <span data-ttu-id="f3f83-137">En esta situación, el usuario puede finalizar la operación **Cerrar turno** e intentar sincronizar las transacciones fuera de línea con la base de datos del canal.</span><span class="sxs-lookup"><span data-stu-id="f3f83-137">In this situation, the user can end the **Close shift** operation and try to sync the offline transactions to the channel database.</span></span> <span data-ttu-id="f3f83-138">Alternativamente, el usuario puede ajustar manualmente las cantidades calculadas por el sistema para tener en cuenta las transacciones que no están sincronizadas, de modo que el conjunto correcto de números financieros se finalice y se contabilice.</span><span class="sxs-lookup"><span data-stu-id="f3f83-138">Alternatively, the user can manually adjust the system-computed amounts to account for the transactions that aren't synced, so that the correct set of financial numbers is finalized and posted.</span></span> 

<span data-ttu-id="f3f83-139">Cuando se utiliza la contabilización de declaraciones de alimentación por goteo, de modo que la contabilización de transacciones se separa de la contabilización de datos financieros, puede elegir ajustar los importes calculados por el sistema para las transacciones sin conexión que faltan.</span><span class="sxs-lookup"><span data-stu-id="f3f83-139">When trickle feed statement posting is used, so that the posting of transactions is separated from the posting of financials, you can choose to adjust the system-computed amounts for missing offline transactions.</span></span> <span data-ttu-id="f3f83-140">De esta manera, se asegura de que las finanzas siempre se contabilicen y contabilicen correctamente, independientemente de las transacciones faltantes.</span><span class="sxs-lookup"><span data-stu-id="f3f83-140">In this way, you ensure that financials are always accounted and posted correctly, regardless of missing transactions.</span></span> <span data-ttu-id="f3f83-141">Las transacciones sin conexión se pueden sincronizar con la base de datos del canal y la sede de Commerce y luego publicarse más tarde, por separado de las contabilizaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="f3f83-141">Offline transactions can be synced to the channel database and Commerce headquarters, and then posted later, separately from the financial postings.</span></span>

<span data-ttu-id="f3f83-142">Los detalles de la conciliación financiera para un turno se sincronizan con la sede de Commerce mediante el uso del trabajo P.</span><span class="sxs-lookup"><span data-stu-id="f3f83-142">Details of the financial reconciliation for a shift are synced to Commerce headquarters by using the P-job.</span></span>

<span data-ttu-id="f3f83-143">Los extractos financieros minoristas en la sede de Commerce no calculan los totales para mostrar los detalles en las líneas de los extractos financieros.</span><span class="sxs-lookup"><span data-stu-id="f3f83-143">Financial retail statements in Commerce headquarters don't compute totals to show the details on the statement lines.</span></span> <span data-ttu-id="f3f83-144">En cambio, las cantidades finalizadas en el cliente PDV se utilizan para crear y publicar extractos financieros minoristas.</span><span class="sxs-lookup"><span data-stu-id="f3f83-144">Instead, the finalized amounts in the POS client are used to create and post financial retail statements.</span></span>