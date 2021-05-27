---
title: La inversión de notificar como terminado crea una transacción abierta inesperada
description: La inversión de las notificaciones como terminado que tienen marcas crea una transacción abierta en la que la cantidad invertida tiene las mismas dimensiones de inventario que la transacción invertida.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026893"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="71d17-103">La inversión de notificar como terminado crea una transacción abierta inesperada</span><span class="sxs-lookup"><span data-stu-id="71d17-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="71d17-104">Número de KB: 4612469</span><span class="sxs-lookup"><span data-stu-id="71d17-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="71d17-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="71d17-105">Symptoms</span></span>

<span data-ttu-id="71d17-106">Si invierte las notificaciones como terminado que tienen marcas, el sistema crea una transacción abierta en la que la cantidad invertida tiene las mismas dimensiones de inventario que la transacción invertida.</span><span class="sxs-lookup"><span data-stu-id="71d17-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="71d17-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="71d17-107">Resolution</span></span>

<span data-ttu-id="71d17-108">Cuando invierte una operación de notificación como terminado, la dimensión de inventario se inicializa desde el diario de producción.</span><span class="sxs-lookup"><span data-stu-id="71d17-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="71d17-109">Por lo tanto, obtiene el número de lote.</span><span class="sxs-lookup"><span data-stu-id="71d17-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="71d17-110">Debido a la marca, las transacciones de pedidos de ventas heredarán el número de lote.</span><span class="sxs-lookup"><span data-stu-id="71d17-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="71d17-111">La dimensión se puede restablecer cuando se publica la notificación como terminado.</span><span class="sxs-lookup"><span data-stu-id="71d17-111">The dimension can be reset when the reporting as finished is posted.</span></span>
