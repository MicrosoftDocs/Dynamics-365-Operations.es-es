---
title: Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales
description: Este tema describe la funcionalidad para deshabilitar las reglas del comprobador de coherencia de transacción comercial en Microsoft Dynamics 365 Retail.
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
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586306"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="a4be1-103">Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales</span><span class="sxs-lookup"><span data-stu-id="a4be1-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="a4be1-104">Los minoristas pueden tener procesos y escenarios empresariales que son únicos para ellos.</span><span class="sxs-lookup"><span data-stu-id="a4be1-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="a4be1-105">Por tanto, no todas las reglas que se incluyen de forma predeterminada en el comprobador de coherencia de transacción comercial son aplicables a todos los minoristas.</span><span class="sxs-lookup"><span data-stu-id="a4be1-105">Therefore, not all the rules that are included by default in the retail transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="a4be1-106">Para adaptar diferencias, Microsoft Dynamics 365 Retail proporciona una función que se puede usar para deshabilitar las reglas que no se pueden aplicar.</span><span class="sxs-lookup"><span data-stu-id="a4be1-106">To accommodate differences, Microsoft Dynamics 365 Retail provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="a4be1-107">Para ver la lista de reglas disponibles en el comprobador de coherencia de transacción comercial en su entorno y ver el estado de cada regla, vaya a **Venta minorista \> Configuración de sede central \> Parámetros \> Parámetros comerciales** y seleccione la pestaña **Validación de transacciones**.</span><span class="sxs-lookup"><span data-stu-id="a4be1-107">To view the list of rules that are available in the retail transaction consistency checker in your environment, and to see the status of each rule, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="a4be1-108">De forma predeterminada, el estado de cada regla se establece en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a4be1-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="a4be1-109">Por tanto, todas las reglas se utilizan para validar transacciones comerciales antes de que se incluyan en los extractos comerciales.</span><span class="sxs-lookup"><span data-stu-id="a4be1-109">Therefore, all the rules are used to validate retail transactions before they are pulled into the retail statements.</span></span> <span data-ttu-id="a4be1-110">Para deshabilitar una regla, cambie su estado a **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="a4be1-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="a4be1-111">No se consideran las reglas deshabilitadas cuando se validan las transacciones comerciales durante el proceso de cálculo de extractos.</span><span class="sxs-lookup"><span data-stu-id="a4be1-111">Disabled rules aren't considered when retail transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="a4be1-112">Para omitir el proceso de validación completo, con independencia de las reglas habilitadas, vaya a **Venta minorista \> Configuración de sede central \> Parámetros \> Parámetros comerciales** y, a continuación, en la pestaña **Validación de transacciones**, establezca la opción **Deshabilitar comprobador de coherencia para transacciones comerciales** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a4be1-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Retail transactions** option to **Yes**.</span></span> <span data-ttu-id="a4be1-113">Después de que esta opción se establezca en **No**, no se podrá volver a establecer en **Sí** desde la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="a4be1-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
