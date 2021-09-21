---
title: No se puede procesar la corrección de la nota de entrega
description: Si intenta corregir una nota de entrega después de su publicación, recibirá un error. Esta página explica cómo corregir los albaranes publicados para los artículos habilitados para WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477550"
---
# <a name="delivery-note-correction-cant-be-processed"></a>No se puede procesar la corrección de la nota de entrega

## <a name="symptoms"></a>Síntomas

Después de publicar un albarán de entrega, no puede cancelarlo porque el botón **Cancelar** no está disponible. Tampoco puede corregir el albarán de entrega. Si lo intenta, recibe el siguiente mensaje de error:

> No se puede procesar la corrección de la nota de entrega. La nota de entrega solo contiene artículos que están sujetos a procesos de gestión de almacén, ya que estos no son compatibles con la corrección de la nota de entrega.

## <a name="resolution"></a>Resolución

Para corregir las notas de empaque publicadas para los artículos que están habilitados para gestión avanzada de almacenes (WMS), debe hacer la publicación desde la carga, no desde el pedido.
