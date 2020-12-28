---
title: El cliente se desconecta
description: Este artículo explica qué hacer si el cliente está desconectado del entorno y no sabe por qué.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2088706baf8735fa371960955a2ffc3240ccac76
ms.sourcegitcommit: a26e4963d40796da21ce6581cfb2f4d9db4f6776
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "4420501"
---
# <a name="client-disconnects"></a>El cliente se desconecta

**Detalles del entorno** 

Este problema puede aparecer en todos los entornos.
 
**Síntoma** 

el cliente está desconectado del entorno y no sabe por qué. El cliente recibe uno de los mensajes de error siguientes:

- Hemos perdido la conexión. Haga clic en Cerrar para continuar trabajando.
- Parece que perdió la conectividad de red. Haga clic en Reintentar para intentarlo de nuevo.

**Indicador rojo**

Este problema se produce a menudo cuando los usuarios se encuentran en la etapa de implementación, comparan información a través de entornos de la producción y entornos de pruebas, y se olvidan de que se mueven entre las sesiones. Si los usuarios se encuentran en esta etapa, experimentarán probablemente este error.

**Emisión** 

**Tipos de explorador:** Google Chrome, Internet Explorer y Microsoft Edge

Microsoft Dynamics 365 Human Resources desconecta a usuarios cuando dos sesiones están abiertas a la vez para el mismo usuario y el mismo tipo de explorador. (Por ejemplo, el usuario A está viendo el entorno 1 y el entorno 2 en Chrome.) No importa si los usuarios abren las distintas ventanas del explorador o diferentes fichas. Si las mismas credenciales del usuario se utilizan para iniciar sesión en el entorno 1 y el entorno 2 al mismo tiempo y en el mismo tipo de explorador, Human Resources desconectará una de las sesiones.

**Solución**

Asegúrese de que sólo un entorno esté abierto al mismo tiempo para un tipo de explorador dado. Los usuarios pueden abrir variras sesiones en el mismo entorno (es decir, varias fichas en el mismo explorador).

Los usuarios que desean desplazarse entre dos entornos al mismo tiempo deben abrir cada entorno en un tipo de explorador diferente. (Por ejemplo, el usuario A puede ver el entorno 1 en Chrome y el entorno 2 en Microsoft Edge.)
