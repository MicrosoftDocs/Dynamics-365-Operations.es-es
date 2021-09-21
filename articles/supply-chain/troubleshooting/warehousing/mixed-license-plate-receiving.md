---
title: La recepción de matrículas mixtas no funciona para todos los códigos de disposición.
description: Cuando el campo Acción para un código de disposición se establece en Crédito o Chatarra, puede usar solo el elemento de menú Recepción de matrículas mixtas para procesar elementos devueltos.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b762255bc5ef6a1e15688a9c635940e92e67db3c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477549"
---
# <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-but-credit"></a>La recepción de matrículas mixtas no funciona para ningún código de disposición, excepto Crédito

## <a name="symptoms"></a>Síntomas

Cuando el campo **Acción** para un código de disposición se establece en *Crédito* o *Chatarra*, puede usar solo el elemento de menú [Recepción de matrículas mixtas](/dynamics365/supply-chain/warehousing/mixed-license-plate-receiving) para procesar elementos devueltos.

## <a name="resolution"></a>Resolución

Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Actualmente, solo se admiten [códigos de disposición](/dynamics365/supply-chain/service-management/set-up-disposition-codes) donde el campo **Acción** está configurado en *Crédito* o *Chatarra* para la recepción de matrículas mixtas.
