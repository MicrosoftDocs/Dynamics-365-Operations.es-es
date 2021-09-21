---
title: No se puede volver liberar una carga enviada parcialmente al almacén
description: En versiones anteriores, no se podía volver a liberar una carga enviada parcialmente cuando se usaban ciertas funcionalidades con reservas incompletas. Se ha resuelto.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477541"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>No se puede volver liberar una carga enviada parcialmente al almacén

## <a name="symptoms"></a>Síntomas

No puede liberar una carga enviada parcialmente al almacén. Cuando realiza la liberación al almacén, aparece el mensaje "Operación completada", pero no ocurre nada y no se crea ningún trabajo para la cantidad restante. Este problema se produce cuando utiliza la función de carga de transporte y hay una reserva incompleta.

## <a name="resolution"></a>Resolución

[Problema de KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Las cargas enviadas parcialmente se pueden volver a agitar y volver a procesar") se corrige en la [versión 10.0.15](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15).
