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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436808"
---
# <a name="troubleshoot-sales-quotations"></a><span data-ttu-id="f2cca-103">Solución de problemas de presupuestos de ventas</span><span class="sxs-lookup"><span data-stu-id="f2cca-103">Troubleshoot sales quotations</span></span>

<span data-ttu-id="f2cca-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con presupuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="f2cca-104">This topic describes how to fix issues that you might encounter while you work with sales quotations.</span></span>

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a><span data-ttu-id="f2cca-105">No puedo cambiar la cantidad de ventas de un presupuesto de venta para un artículo de servicio.</span><span class="sxs-lookup"><span data-stu-id="f2cca-105">I can't change the sales quantity of a sales quotation for a service item.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f2cca-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f2cca-106">Issue description</span></span>

<span data-ttu-id="f2cca-107">Si intenta establecer una cantidad de ventas (campo **SalesQty**) para un elemento de tipo *Servicio* en una línea de presupuesto de ventas, verá el siguiente mensaje: "Actualización no permitida para el campo Cantidad".</span><span class="sxs-lookup"><span data-stu-id="f2cca-107">If you try to set a sales quantity (**SalesQty** field) for an item of the *Service* type on a sales quotation line, you will receive the following message: "Update not allowed for field Quantity."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f2cca-108">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f2cca-108">Issue resolution</span></span>

<span data-ttu-id="f2cca-109">No puede establecer una cantidad de ventas para productos que son artículos de servicio.</span><span class="sxs-lookup"><span data-stu-id="f2cca-109">You can't set a sales quantity for products that are service items.</span></span> <span data-ttu-id="f2cca-110">Por ejemplo, si ofrece un servicio para instalar un artículo, no tiene sentido registrar una cantidad, porque no hay un artículo físico.</span><span class="sxs-lookup"><span data-stu-id="f2cca-110">For example, if you offer a service to install an item, it doesn't make sense to record a quantity, because there is no physical item.</span></span> <span data-ttu-id="f2cca-111">Solo hay un servicio.</span><span class="sxs-lookup"><span data-stu-id="f2cca-111">There is only a service.</span></span>

