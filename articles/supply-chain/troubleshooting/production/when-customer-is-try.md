---
title: El número de lote se borra cuando se selecciona un nuevo Id. de lote
description: Cuando revisa una línea de diario de la lista de selección, el valor del campo Número de lote se borra si selecciona un nuevo valor en el campo Id. de lote.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026866"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>El número de lote se borra cuando se selecciona un nuevo Id. de lote

Número de KB: 4613107

## <a name="symptoms"></a>Síntomas

Cuando revisa una línea de diario de la lista de selección, el valor del campo **Número de lote** se borra si selecciona un nuevo valor en el campo **Id. de lote**.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. Si cambia el Id. de lote, cambia el contexto del artículo. Por lo tanto, se restablece el número de lote.

Para asociar el número de lote con un Id. de lote, primero debe configurar el Id. de lote.
