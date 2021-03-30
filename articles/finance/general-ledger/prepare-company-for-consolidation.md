---
title: Preparar una entidad jurídica para el proceso de consolidación
description: En una consolidación, se recopilan transacciones de varios conjuntos de cuentas de entidades jurídicas en un único conjunto de cuentas de entidades jurídicas. Este tema explica cómo preparar una entidad jurídica para una consolidación.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 07988e71276c6439e392bce2087f3a8923f5f40b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230211"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="4fdc3-104">Preparar una entidad jurídica para el proceso de consolidación</span><span class="sxs-lookup"><span data-stu-id="4fdc3-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4fdc3-105">En una consolidación, se recopilan transacciones de varios conjuntos de cuentas de entidades jurídicas en un único conjunto de cuentas de entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="4fdc3-106">Este tema explica cómo preparar una entidad jurídica para una consolidación.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="4fdc3-107">Le recomendamos que utilice Management Reporter para Microsoft Dynamics 365 Finance para combinar los resultados financieros de múltiples entidades jurídicas en un formato consolidado.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="4fdc3-108">Management Reporter le permite crear informes financieros consolidados en todas las entidades jurídicas, utilizar Excel para importar datos de consolidación de otros orígenes y traducir importes a cualquier número de divisas de notificación sin tener que ejecutar el proceso de consolidación en Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="4fdc3-109">Puede imprimir informes, como informes financieros, desde la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="4fdc3-110">Sin embargo, no puede usar la entidad jurídica consolidada para las transacciones diarias.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="4fdc3-111">Puede consolidar datos de las entidades jurídicas que usen distintas bases de datos que la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="4fdc3-112">Este proceso de consolidación se denomina *consolidación de importación*.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="4fdc3-113">Como alternativa, las entidades jurídicas pueden usar la misma base de datos que la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="4fdc3-114">Este proceso de consolidación se denomina *consolidación en línea*.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="4fdc3-115">La entidad jurídica consolidada recopila los resultados y los saldos de las filiales.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="4fdc3-116">Para preparar una entidad jurídica consolidada para una consolidación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="4fdc3-117">Vaya a **Contabilidad general \> Configuración \> Organización \> Entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="4fdc3-118">Seleccione **Nuevo** para crear la entidad jurídica que va a consolidar.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="4fdc3-119">Active la casilla **Usar para proceso de consolidación financiera** y, a continuación, introduzca la información sobre la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="4fdc3-120">Asegúrese de introducir esta información exactamente como desea que aparezca en los informes financieros para la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="4fdc3-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-121">Close the page.</span></span>
5. <span data-ttu-id="4fdc3-122">Seleccione la entidad jurídica consolidada en el campo de la esquina superior derecha de la página y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="4fdc3-123">Vaya a **Contabilidad general \> Configuración \> Contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="4fdc3-124">Seleccione el plan de cuentas, el calendario fiscal, la divisa de contabilidad, una divisa de notificación opcional y el tipo de cambio predeterminado para la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="4fdc3-125">Vaya a **Contabilidad general \> Configuración \> Divisa \> Tipos de cambio de divisas**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="4fdc3-126">Configure los tipos de cambio de divisa en períodos relevantes para las divisas de las entidades jurídicas filiales.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="4fdc3-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-127">Close the page.</span></span>
11. <span data-ttu-id="4fdc3-128">Si la entidad jurídica consolidada tiene filiales que utilicen las divisas extranjeras, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4fdc3-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="4fdc3-129">Vaya a **Contabilidad general \> Configuración \> Registro \> Cuentas para transacciones automáticas**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="4fdc3-130">En el campo **Tipo de registro**, seleccione una cuenta apropiada:</span><span class="sxs-lookup"><span data-stu-id="4fdc3-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="4fdc3-131">Si la entidad jurídica tiene subsidiarias extranjeras que son financiera u operativamente interdependientes con la entidad jurídica principal, seleccione una cuenta apropiada para el tipo de registro **Cuenta de pérdidas y ganancias para las diferencias de consolidación**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="4fdc3-132">Si está consolidando una filial que sea financieramente y operacionalmente independiente de la entidad jurídica principal, o una entidad jurídica que contenga los resultados de varias filiales que sean financieramente y operacionalmente independientes de la entidad jurídica principal, y si utiliza métodos de conversión para consolidar los datos, seleccione una cuenta adecuada para el tipo de registro **Cuenta de saldo para diferencias de consolidación**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="4fdc3-133">En el campo **Cuenta principal**, seleccione las cuentas principales que deben usarse para los ajustes de revalorización de divisa extranjera.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="4fdc3-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-134">Close the page.</span></span>

    <span data-ttu-id="4fdc3-135">Si crea la entidad jurídica consolidada previamente en un período, puede revalorizar los importes en divisa extranjera mientras que los tipos de cambio cambian durante el período de consolidación.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="4fdc3-136">Ya está configurada la entidad jurídica consolidada para el trabajo periódico **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="4fdc3-137">Puede realizar una consolidación de importación o una consolidación en línea.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="4fdc3-138">Para hacer una consolidación de importación, vaya a **Contabilidad general \> Periódico \> Consolidar \> Consolidar \[Importar de\]**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="4fdc3-139">Para realizar una consolidación en línea vaya a **Contabilidad general \> Periódico \> Consolidar \> Consolidar \[En línea\]**.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="4fdc3-140">Para poder procesar la consolidación, debe preparar las entidades jurídicas filiales para la consolidación.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="4fdc3-141">Para obtener más información, consulte [Configurar una entidad jurídica filial para la consolidación](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="4fdc3-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]