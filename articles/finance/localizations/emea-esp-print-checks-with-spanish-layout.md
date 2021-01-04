---
title: Imprimir cheques con diseño español
description: Este tema proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.
author: neserovleo
manager: AnnBe
ms.date: 05/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeLayout, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 274753
ms.search.region: Spain
ms.author: v-lenest
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 16eaa340a2796dca48ffdfb073ea66c9004507c9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407806"
---
# <a name="print-checks-by-using-the-spanish-layout"></a><span data-ttu-id="7ab99-103">Imprimir cheques con diseño español</span><span class="sxs-lookup"><span data-stu-id="7ab99-103">Print checks by using the Spanish layout</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ab99-104">Este tema proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.</span><span class="sxs-lookup"><span data-stu-id="7ab99-104">This topic provides information about how to print checks that follow the standards that are required in Spain.</span></span>

<span data-ttu-id="7ab99-105">Para utilizar la funcionalidad de cheques junto con diseño español, debe tener en cuenta los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7ab99-105">To use the checks functionality together with the Spanish layout, you should consider the following settings:</span></span>

-   <span data-ttu-id="7ab99-106">Para aplicar la gramática correcta al importe en letras (texto), debe seleccionar el género correcto para la divisa en la página **Divisas**.</span><span class="sxs-lookup"><span data-stu-id="7ab99-106">To apply the correct grammar to the literal (text) amount, you must select the correct gender for the currency on the **Currencies** page.</span></span> <span data-ttu-id="7ab99-107">Por ejemplo, seleccione **Masculino** para el Euro (EUR) y **Femenino** para la libra esterlina (GBP).</span><span class="sxs-lookup"><span data-stu-id="7ab99-107">For example, select **Masculine** for euro (EUR) and **Feminine** for British pound (GBP).</span></span>
-   <span data-ttu-id="7ab99-108">Para el método de pago, use el formato de archivo de exportación **Cheque**.</span><span class="sxs-lookup"><span data-stu-id="7ab99-108">For the method of payment, use the **Check** export file format.</span></span>
-   <span data-ttu-id="7ab99-109">Para la cuenta bancaria, use **Diseño de cheques para España** en la sección **Diseño de cheques** de la página **Cuenta bancaria** (**Configuración** &gt; **Diseño** &gt; **Cheque**).</span><span class="sxs-lookup"><span data-stu-id="7ab99-109">For the bank account, use **Spanish check layout** in the **Check layout** section of the **Bank account** page (**Setup** &gt; **Layout** &gt; **Check**).</span></span> <span data-ttu-id="7ab99-110">Además, establezca el campo **Otras divisas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7ab99-110">Additionally, set the **Other currencies** field to **Yes**.</span></span>

<span data-ttu-id="7ab99-111">Para generar cheques con diseño español, se utiliza la funcionalidad básica del diario de pagos (proveedores).</span><span class="sxs-lookup"><span data-stu-id="7ab99-111">To generate the checks by using the Spanish layout, basic Payment journal (vendors) functionality is used.</span></span> <span data-ttu-id="7ab99-112">Para obtener más información, consulte [Resumen de pagos del proveedor](../cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7ab99-112">For more information, see [Vendor payment overview](../cash-bank-management/tasks/vendor-payment-overview.md).</span></span> <span data-ttu-id="7ab99-113">Después de ejecutar la función de pagos Generar y seleccionar todos los parámetros necesarios como se describe en este tema, se generan los cheques.</span><span class="sxs-lookup"><span data-stu-id="7ab99-113">After you run the Generate payments function and select all required parameters as described in this topic, the checks are generated.</span></span> <span data-ttu-id="7ab99-114">Si la divisa en la línea de diario de pago es distinta de la cuenta bancaria, puede generar un cheque igualmente, siempre y cuando el diseño del cheque esté configurado para poder usar otras divisas.</span><span class="sxs-lookup"><span data-stu-id="7ab99-114">If the currency on the payment journal line differs from the currency of the bank account, you can still generate a check if the check layout is set up to use other currencies.</span></span>

