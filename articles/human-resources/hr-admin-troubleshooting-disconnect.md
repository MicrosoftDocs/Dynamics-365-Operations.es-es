---
title: El cliente se desconecta
description: Este artículo explica qué hacer si el cliente está desconectado del entorno y no sabe por qué.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fcb7e5e3230aee9f6c04e4854c8eea836ae14c7f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053428"
---
# <a name="client-disconnects"></a>El cliente se desconecta

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Detalles del entorno** 

Este problema puede aparecer en todos los entornos.
 
**Síntoma** 

El cliente está desconectado del entorno y no sabe por qué. El cliente recibe uno de los mensajes de error siguientes:

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]