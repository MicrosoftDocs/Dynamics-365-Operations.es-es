---
title: No se puede mover la matrícula de entidad de almacén si tiene una emisión en blanco y se permite una recepción en blanco
description: No puede mover una matrícula de entidad de almacén si el número de serie tiene una emisión en blanco y se permite una recepción en blanco. Esto se solucionará haciendo que el campo del número de serie sea opcional.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477516"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>No se puede mover la matrícula de entidad de almacén si el número de serie tiene una emisión en blanco y se permite una recepción en blanco

## <a name="symptoms"></a>Síntomas

No puede mover una matrícula usando un elemento de menú **Movimiento** si el número de serie tiene ajustes *Se permite un problema en blanco* y *Recibo en blanco permitido* en el grupo de dimensiones de seguimiento, y si hay varias placas de matrícula en la misma ubicación, algunas de las cuales tienen números de serie y otras no.

## <a name="resolution"></a>Resolución

Este problema se solucionará con los cambios implementados en [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Esos cambios harán que el campo opcional **Número de serie** cuando se permiten recibo en blanco y emisión en blanco.
