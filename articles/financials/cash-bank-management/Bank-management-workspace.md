---
title: Espacio de trabajo para la gestión bancaria
description: Este tema proporciona información acerca del espacio de trabajo Gestión bancaria. Este espacio de trabajo muestra la información relacionada con las cuentas bancarias de la empresa e incluye una vista resumida y una página de análisis. La vista resumida muestra las fichas del resumen, la información de cuentas bancarias, un gráfico de saldos e información relacionada. La página de Análisis utiliza las capacidades de Microsoft Power BI para mostrar las representaciones visuales relacionados con los saldos de la cuenta bancaria.
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fdc0d1e5ea02cdcff9f7f5ede4ab685f54365698
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "348374"
---
# <a name="bank-management-workspace"></a><span data-ttu-id="43c9d-106">Espacio de trabajo para la gestión bancaria</span><span class="sxs-lookup"><span data-stu-id="43c9d-106">Bank management workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43c9d-107">El espacio de trabajo **Gestión bancaria** muestra la información relacionada con las cuentas bancarias de la empresa.</span><span class="sxs-lookup"><span data-stu-id="43c9d-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="43c9d-108">Este espacio de trabajo incluye un vista **Resumen** y una página **Análisis** .</span><span class="sxs-lookup"><span data-stu-id="43c9d-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="43c9d-109">La vista **Resumen** muestra las fichas del resumen, la información de cuentas bancarias, un gráfico de saldos e información relacionada.</span><span class="sxs-lookup"><span data-stu-id="43c9d-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="43c9d-110">La página de **Análisis** utiliza las capacidades de Microsoft Power BI para mostrar las representaciones visuales relacionados con los saldos de la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="43c9d-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="43c9d-111">Vista de resumen</span><span class="sxs-lookup"><span data-stu-id="43c9d-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="43c9d-112">Resumen</span><span class="sxs-lookup"><span data-stu-id="43c9d-112">Summary</span></span>

<span data-ttu-id="43c9d-113">Los mosaicos en la sección **Resumen** ofrecen una visión general de las cuentas bancarias y acceso rápido a las páginas que utiliza con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="43c9d-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="43c9d-114">La información de conciliación bancaria es específica de las funcionalidades avanzadas de conciliación bancaria.</span><span class="sxs-lookup"><span data-stu-id="43c9d-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="43c9d-115">La información solo se incluye para aquellas cuentas bancarias que tengan la opción **Conciliación bancaria avanzada** establecida en **Sí** en la página **Cuenta bancaria**.</span><span class="sxs-lookup"><span data-stu-id="43c9d-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="43c9d-116">En la sección **Resumen** , puede importar archivos bancarios electrónicos para las cuentas bancarias en todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="43c9d-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="43c9d-117">Cuentas bancarias</span><span class="sxs-lookup"><span data-stu-id="43c9d-117">Bank accounts</span></span>

<span data-ttu-id="43c9d-118">Cada cuenta bancaria en la entidad jurídica se representa mediante una tarjeta en la sección **Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="43c9d-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="43c9d-119">Se muestran los saldos actuales y puede explorar en profundidad las transacciones que componen dicho importe de saldo de resumen.</span><span class="sxs-lookup"><span data-stu-id="43c9d-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="43c9d-120">El importe de **Transacciones puente** también le permite explorar en profundidad las transacciones que componen dicho importe de resumen.</span><span class="sxs-lookup"><span data-stu-id="43c9d-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="43c9d-121">Las transacciones puente son las transacciones pendientes que se han registrado con la funcionalidad de puente, pero que aún no se han borrado.</span><span class="sxs-lookup"><span data-stu-id="43c9d-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="43c9d-122">El importe de **Saldo pendiente** es el saldo actual menos las transacciones puente o pendientes.</span><span class="sxs-lookup"><span data-stu-id="43c9d-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="43c9d-123">La tarjeta también muestra cuando la cuenta bancaria se concilió por última vez.</span><span class="sxs-lookup"><span data-stu-id="43c9d-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="43c9d-124">Se muestra esta información solo si la conciliación bancaria avanzada está habilitada para la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="43c9d-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="43c9d-125">Saldo</span><span class="sxs-lookup"><span data-stu-id="43c9d-125">Balance</span></span>

<span data-ttu-id="43c9d-126">El gráfico **Saldo** muestra la información histórica del saldo de la cuenta bancaria seleccionada en la sección **Cuentas bancarias** o un resumen de la información histórica de saldo para todas las cuentas bancarias en la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="43c9d-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="43c9d-127">Esta información está disponible para varios períodos: la semana actual, el mes actual, el año actual, los últimos cinco años y todos los períodos (el historial completo de la cuenta bancaria).</span><span class="sxs-lookup"><span data-stu-id="43c9d-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="43c9d-128">Si está viendo el gráfico **Saldo** para una sola cuenta bancaria, los saldos históricos se muestran en la divisa de la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="43c9d-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="43c9d-129">Si está viendo el gráfico para todas las cuentas bancarias en la entidad jurídica, los saldos históricos se muestran en la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="43c9d-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="43c9d-130">La información sobre cuándo los datos se actualizaron por última vez aparece en la parte superior del gráfico.</span><span class="sxs-lookup"><span data-stu-id="43c9d-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="43c9d-131">Puede actualizar los datos según necesite.</span><span class="sxs-lookup"><span data-stu-id="43c9d-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="43c9d-132">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="43c9d-132">Related information</span></span>

<span data-ttu-id="43c9d-133">En la sección **Información relacionada**, puede abrir la página **Diario general** para completar las transferencias bancarias.</span><span class="sxs-lookup"><span data-stu-id="43c9d-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="43c9d-134">También puede abrir rápidamente las páginas **Transacciones bancarias** y **Transacciones puente** .</span><span class="sxs-lookup"><span data-stu-id="43c9d-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="43c9d-135">Vista de análisis</span><span class="sxs-lookup"><span data-stu-id="43c9d-135">Analytics view</span></span>

<span data-ttu-id="43c9d-136">La página **Análisis** proporciona métricas importantes sobre las cuentas bancarias de la empresa actual.</span><span class="sxs-lookup"><span data-stu-id="43c9d-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="43c9d-137">Las visualizaciones siguientes están disponibles en la página:</span><span class="sxs-lookup"><span data-stu-id="43c9d-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="43c9d-138">Saldo bancario total en divisa del sistema</span><span class="sxs-lookup"><span data-stu-id="43c9d-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="43c9d-139">Saldo por entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="43c9d-139">Balance by legal entity</span></span>
-   <span data-ttu-id="43c9d-140">Saldo real de hoy frente al saldo previsto en la divisa de la cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="43c9d-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="43c9d-141">Saldo por cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="43c9d-141">Balance by bank account</span></span>
-   <span data-ttu-id="43c9d-142">Saldo por divisa</span><span class="sxs-lookup"><span data-stu-id="43c9d-142">Balance by currency</span></span>

<span data-ttu-id="43c9d-143">Puede ver los análisis del banco en todas las empresas en el espacio de trabajo **Visión general del efectivo para todas las empresas**.</span><span class="sxs-lookup"><span data-stu-id="43c9d-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span>
