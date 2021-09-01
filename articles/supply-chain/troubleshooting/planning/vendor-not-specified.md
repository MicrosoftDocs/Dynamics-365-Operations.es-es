---
title: El proveedor no se especifica cuando se firman los pedidos planificados
description: Cuando intenta confirmar pedidos planificados, recibe un mensaje de error que indica que no hay ningún proveedor especificado.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4d523d57a862f67fcd40edd60a0fabf40ea7dabcf058f2d11af1fe003c9e304b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741989"
---
# <a name="vendor-isnt-specified-when-planned-orders-are-firmed"></a>El proveedor no se especifica cuando se firman los pedidos planificados

Código de error: SYS23532

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar pedidos planificados, recibe el siguiente mensaje de error:

> No se ha especificado el proveedor

## <a name="resolution"></a>Resolución

Para especificar un proveedor, siga estos pasos.

1. Abra la orden planificada a la que le falta un proveedor.
1. En la ficha desplegable **Suministro planificado**, seleccione el campo **Proveedor** y seleccione un proveedor.
