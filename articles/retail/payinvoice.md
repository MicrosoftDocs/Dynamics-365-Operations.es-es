---
title: Configurar situaciones de pago de facturas
description: En este tema se describe cómo configurar Dynamics 365 for Retail para diversos escenarios relacionados con el pago de facturas.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 158d8ca8a97c473e940f76dd3f35cecc4e9dd7f4
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517161"
---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="94c43-103">Configurar situaciones de pago de facturas</span><span class="sxs-lookup"><span data-stu-id="94c43-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="94c43-104">La funcionalidad de pago de facturas de Dynamics 365 for Retail se ha ampliado para permitir:</span><span class="sxs-lookup"><span data-stu-id="94c43-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>

- <span data-ttu-id="94c43-105">El pago de varias facturas de pedidos de ventas en una sola transacción de PDV.</span><span class="sxs-lookup"><span data-stu-id="94c43-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="94c43-106">El pago de diversos tipos de factura de cliente, incluidas las facturas de servicios, las facturas basadas en proyectos y las notas de abono.</span><span class="sxs-lookup"><span data-stu-id="94c43-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="94c43-107">Para habilitar estas situaciones, debe configurarse el perfil de funcionalidad para las tiendas como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="94c43-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>

1. <span data-ttu-id="94c43-108">Vaya a **Retail \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad** y seleccione un perfil que esté vinculado a las tiendas para las que desea realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="94c43-108">Go to **Retail \> Channel setup \> POS setup \> POS profiles \> Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>
2. <span data-ttu-id="94c43-109">En la pestaña **Funciones**, configure los siguientes parámetros si es necesario.</span><span class="sxs-lookup"><span data-stu-id="94c43-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="94c43-110">**Factura de pedido de ventas**: seleccione **Sí** para permitir a los usuarios pagar una o más facturas de pedido de ventas en una sola transacción de PDV.</span><span class="sxs-lookup"><span data-stu-id="94c43-110">**Sales order invoice** – Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="94c43-111">**Factura de servicios**: seleccione **Sí** para permitir a los usuarios pagar una o más facturas de servicios en una sola transacción de PDV.</span><span class="sxs-lookup"><span data-stu-id="94c43-111">**Free text invoice** – Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="94c43-112">**Factura de proyecto**: seleccione **Sí** para permitir a los usuarios pagar una o más facturas de proyecto en una sola transacción de PDV.</span><span class="sxs-lookup"><span data-stu-id="94c43-112">**Project invoice** – Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="94c43-113">**Nota de abono de pedidos de ventas**: seleccione **Sí** para permitir a los usuarios liquidar varias notas de abono de pedido de ventas para facturas abiertas o procesar un reembolso al cliente para una nota de abono abierta.</span><span class="sxs-lookup"><span data-stu-id="94c43-113">**Sales order credit note** – Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="94c43-114">Aún no se admite el pago o liquidación de importes parciales.</span><span class="sxs-lookup"><span data-stu-id="94c43-114">Payment or settlement of partial amounts is not yet supported.</span></span>
