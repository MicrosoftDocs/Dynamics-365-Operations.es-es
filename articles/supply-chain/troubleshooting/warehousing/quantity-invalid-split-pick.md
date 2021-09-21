---
title: La cantidad no es válida para la unidad %1 cuando se realiza una selección dividida
description: Al realizar una selección dividida en varios lotes, puede recibir un error de que la cantidad no es válida para la unidad %1. Esta página ayuda a resolver el problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4627db7400d6ccd81f25f100de4696058ce35c42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477481"
---
# <a name="quantity-is-not-valid-when-performing-a-split-pick-across-multiple-batches"></a>La cantidad no es válida cuando se realiza una selección dividida en varios lotes

## <a name="symptoms"></a>Síntomas

Cuando intenta realizar una *selección dividida* en varios lotes, recibe este mensaje de error:

> La cantidad no es válida para la unidad %1.

## <a name="resolution"></a>Resolución

El trabajador del almacén debe utilizar el proceso de *picking corto* en la aplicación móvil Warehouse Management. Si está intentando elegir varios lotes de la misma ubicación, también puede utilizar la opción **Lleno** en la aplicación.
