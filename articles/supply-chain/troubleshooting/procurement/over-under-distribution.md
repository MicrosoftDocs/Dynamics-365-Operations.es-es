---
title: Las distribuciones contables están distribuidas en exceso o en defecto
description: Una o más distribuciones contables están distribuidas en exceso o en defecto.
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
ms.openlocfilehash: 7ff0172469df50da9e4272b3fa3f75001a4eb7eb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477522"
---
# <a name="accounting-distributions-are-either-over--or-under-distributed"></a>Las distribuciones contables están distribuidas en exceso o en defecto


## <a name="symptoms"></a>Síntomas

Recibe el siguiente mensaje de error:

> Una o más distribuciones contables están distribuidas en exceso o en defecto

## <a name="cause"></a>Causa

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

## <a name="resolution"></a>Resolución

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
