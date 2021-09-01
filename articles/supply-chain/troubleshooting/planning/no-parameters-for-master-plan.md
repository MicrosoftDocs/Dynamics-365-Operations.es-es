---
title: Los parámetros para el plan maestro no existen
description: Cuando intenta confirmar una orden planificada, recibe un mensaje de error que indica que no existen parámetros para el plan maestro.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d039b79684f87e7791fb9dae7cbdc6ced220bc092d9a0ab624616c1c345986da
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756784"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>Los parámetros para el plan maestro no existen

Código de error: SYS25368

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un pedido planificado, recibe el siguiente mensaje de error:

> Los parámetros para el plan maestro %1 no existen.

## <a name="cause"></a>Causa

Debido a problemas de configuración, el sistema no puede encontrar la configuración para el plan especificado.

## <a name="resolution"></a>Resolución

- Vaya a **Planificacion maestra \> Configuración \> Planes \> Planes maestros** y asegúrese de que exista un plan que tenga el nombre especificado.
