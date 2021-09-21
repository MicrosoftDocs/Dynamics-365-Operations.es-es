---
title: Las órdenes de compra importadas muestran números de línea incorrectos
description: Cuando los pedidos de compra se importan a través de la administración de datos, los números de línea del pedido de compra no siguen el incremento definido en los parámetros del sistema
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
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477479"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Las órdenes de compra importadas muestran números de línea incorrectos

## <a name="symptoms"></a>Síntomas

De forma predeterminada, los números de línea generados automáticamente para las líneas de pedido de compra que se importan a través de la entidad de datos *Líneas de pedido de compra V2* no usan el incremento de número de línea del sistema que se especifica en los parámetros del sistema. Si crea manualmente un pedido de compra y agrega líneas a través de la interfaz de usuario, los números de línea se incrementan correctamente. Sin embargo, si usa el marco de administración de datos (DMF), no se incrementan correctamente.

Este problema se produce porque, cuando importa líneas a través de DMF, si los números de línea aún no están asignados en la entidad importada, el sistema usa el método de DMF para asignarlos. Ese método siempre incrementa los números de línea en una unidad.

## <a name="workaround"></a>Solución alternativa

Asegúrese de que los números de línea deseados ya estén incluidos en los campos de número de línea de la entidad de datos cuando importe las líneas del pedido de compra. En este caso, DMF no sobrescribirá los números de línea.
