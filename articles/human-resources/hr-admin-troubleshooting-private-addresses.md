---
title: Acceder a direcciones privadas por rol de seguridad
description: En este artículo se explica cómo resolver el problema cuando un cliente no puede tener acceso a direcciones privadas.
author: twheeloc
ms.date: 09/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c1db052937b03817f22b37c50b9f1b319579cb2
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702125"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acceder a direcciones privadas por rol de seguridad


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emisión**

Después de que un cliente duplique un rol de seguridad e inicie sesión como dicho nuevo rol, el cliente no puede ver las direcciones que fueron marcadas como privadas.

**Resolución**

Para solucionar el problema, el cliente debe seguir estos pasos para el rol de seguridad duplicado.

1. Vaya a **Administración de la organización \> Libreta de direcciones global \> Parámetros de libreta de direcciones global**.
2. En la pestaña **Seguridad de ubicación privada** , mueva el nuevo rol de seguridad desde la lista **Roles disponibles** a la lista **Roles seleccionados**.
3. Seleccione **Guardar**.

![Página de parámetros de la libreta de direcciones global.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
