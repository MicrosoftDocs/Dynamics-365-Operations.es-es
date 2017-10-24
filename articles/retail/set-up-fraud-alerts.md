---
title: Configurar avisos de fraude
description: "En este tema se explica cómo configurar reglas para avisar a los representantes de servicio al cliente de la existencia de información potencialmente fraudulenta al procesar pedidos. También puede definir códigos específicos que puede usar para poner en espera los pedidos sospechosos automática o manualmente."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="d4522-104">Configurar avisos de fraude</span><span class="sxs-lookup"><span data-stu-id="d4522-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="d4522-105">En este tema se explica cómo configurar reglas para avisar a los representantes de servicio al cliente de la existencia de información potencialmente fraudulenta al procesar pedidos.</span><span class="sxs-lookup"><span data-stu-id="d4522-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="d4522-106">También puede definir códigos específicos que puede usar para poner en espera los pedidos sospechosos automática o manualmente.</span><span class="sxs-lookup"><span data-stu-id="d4522-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="d4522-107">Antes de configurar y usar reglas de comprobación de fraudes, debe habilitar la comprobación de fraudes y definir los valores básicos de comprobación de fraudes en los parámetros del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d4522-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="d4522-108">Existen dos tipos de reglas de fraude:</span><span class="sxs-lookup"><span data-stu-id="d4522-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="d4522-109">**Reglas estáticas** usa un valor específico, como un número de teléfono que está en la lista negra.</span><span class="sxs-lookup"><span data-stu-id="d4522-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="d4522-110">**Reglas dinámicas** puede estar compuesto de variables y de condiciones.</span><span class="sxs-lookup"><span data-stu-id="d4522-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="d4522-111">Antes de crear una regla dinámica, debe crear las variables y condiciones que definen a quién se aplica la regla y cuándo se debe aplicar la regla.</span><span class="sxs-lookup"><span data-stu-id="d4522-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="d4522-112">Por ejemplo, desea crear una regla para requerir que cuando el cliente 1202 realice un pedido de ventas por valor de 1.000,00 o más, el pedido de ventas se deba poner en espera hasta que se pueda comprobar el pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="d4522-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="d4522-113">En este caso, las variables son el cliente 1202 y un total de 1.000,00 del pedido.</span><span class="sxs-lookup"><span data-stu-id="d4522-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="d4522-114">La condición especifica de que si el cliente 1202 configura un pedido, y el importe total del pedido es igual a o mayor de 1.000,00, el pedido de ventas debe estar en espera hasta que el pago del cliente pueda ser verificado.</span><span class="sxs-lookup"><span data-stu-id="d4522-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>




