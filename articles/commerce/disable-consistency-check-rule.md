---
title: Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales
description: Este tema describe la funcionalidad para deshabilitar las reglas del comprobador de coherencia de transacción comercial en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: b11b901fafc3907e9d3cae5cd554cc9a868a414c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004352"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="78f28-103">Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales</span><span class="sxs-lookup"><span data-stu-id="78f28-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="78f28-104">Los minoristas pueden tener procesos y escenarios empresariales que son únicos para ellos.</span><span class="sxs-lookup"><span data-stu-id="78f28-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="78f28-105">Por tanto, no todas las reglas que se incluyen de forma predeterminada en el comprobador de coherencia de transacción de Commerce son aplicables a todos los minoristas.</span><span class="sxs-lookup"><span data-stu-id="78f28-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="78f28-106">Para adaptar diferencias, Microsoft Dynamics 365 Commerce proporciona una función que se puede usar para deshabilitar las reglas que no se pueden aplicar.</span><span class="sxs-lookup"><span data-stu-id="78f28-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="78f28-107">Para ver la lista de reglas disponibles en el comprobador de coherencia de transacción en su entorno y ver el estado de cada regla, vaya a **Venta minorista \> Retail y Commerce \> Parámetros \> Parámetros de Commerce** y seleccione la pestaña **Validación de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="78f28-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="78f28-108">De forma predeterminada, el estado de cada regla se establece en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="78f28-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="78f28-109">Por tanto, todas las reglas se utilizan para validar transacciones antes de que se incluyan en los extractos de Commerce.</span><span class="sxs-lookup"><span data-stu-id="78f28-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="78f28-110">Para deshabilitar una regla, cambie su estado a **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="78f28-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="78f28-111">No se consideran las reglas deshabilitadas cuando se validan las transacciones durante el proceso de cálculo de extractos.</span><span class="sxs-lookup"><span data-stu-id="78f28-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="78f28-112">Para omitir el proceso de validación completo, con independencia de las reglas habilitadas, vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de Commerce** y, a continuación, en la pestaña **Validación de transacciones**, establezca la opción **Deshabilitar comprobador de coherencia para transacciones de Commerce** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="78f28-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="78f28-113">Después de que esta opción se establezca en **No**, no se podrá volver a establecer en **Sí** desde la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="78f28-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
