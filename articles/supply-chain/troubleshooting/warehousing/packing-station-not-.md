---
title: La estación de empaquetado no muestra las notas del producto
description: La estación de empaquetado no muestra las notas del producto.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSPack
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 18c8d2d392b7950ee2d5fc388fc3f365b52a6795c908f9ed8cac12dc7b481c60
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760355"
---
# <a name="packing-station-doesnt-show-product-notes"></a>La estación de empaquetado no muestra las notas del producto

Número de KB: 4614615

## <a name="symptoms"></a>Síntomas

Las notas de empaquetado no se muestran en el formulario de empaquetado cuando las instrucciones de empaquetado se agregan como un archivo adjunto a un producto maestro o una variante del producto.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado.

La lógica actual para mostrar notas de empaquetado en el formulario de empaquetado requiere que las notas estén asociadas con los envíos.
