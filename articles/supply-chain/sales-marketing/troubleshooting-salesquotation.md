---
title: Solución de problemas de presupuestos de ventas
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con presupuestos de ventas.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834421"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="b3014-103">Solución de problemas de presupuestos de ventas</span><span class="sxs-lookup"><span data-stu-id="b3014-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="b3014-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con presupuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="b3014-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="b3014-105">No puedo cambiar la cantidad de ventas de un presupuesto de venta para un artículo de servicio.</span><span class="sxs-lookup"><span data-stu-id="b3014-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b3014-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b3014-106">Issue description</span></span>

<span data-ttu-id="b3014-107">Si intenta establecer una cantidad de ventas (campo **SalesQty**) para un elemento de tipo *Servicio* en una línea de presupuesto de ventas, verá el siguiente mensaje: "Actualización no permitida para el campo Cantidad".</span><span class="sxs-lookup"><span data-stu-id="b3014-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b3014-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b3014-108">Issue resolution</span></span>

<span data-ttu-id="b3014-109">No puede establecer una cantidad de ventas para productos que son artículos de servicio.</span><span class="sxs-lookup"><span data-stu-id="b3014-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="b3014-110">Por ejemplo, si ofrece un servicio para instalar un artículo, no tiene sentido registrar una cantidad, porque no hay un artículo físico.</span><span class="sxs-lookup"><span data-stu-id="b3014-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="b3014-111">Solo hay un servicio.</span><span class="sxs-lookup"><span data-stu-id="b3014-111">There is only a service.</span></span>

