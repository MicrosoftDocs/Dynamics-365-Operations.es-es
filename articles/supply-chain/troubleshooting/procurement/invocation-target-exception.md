---
title: Se produce una excepción durante la contabilización de la factura del proveedor
description: Se produce una excepción de "Se ha lanzado una excepción por el destino de una invocación" durante la contabilización de la factura del proveedor.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ecc63cb7d0d2392105d8e4290f8e837945ae0781
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477520"
---
# <a name="an-exception-occurs-during-vendor-invoice-posting"></a>Se produce una excepción durante la contabilización de la factura del proveedor


## <a name="symptoms"></a>Síntomas

Recibe la siguiente excepción al registrar una factura de proveedor:

> El destino de una invocación ha lanzado una excepción

## <a name="cause"></a>Causa

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

## <a name="resolution"></a>Resolución

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
