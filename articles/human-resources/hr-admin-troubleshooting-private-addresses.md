---
title: Acceder a direcciones privadas por rol de seguridad
description: En este tema se explica cómo resolver el problema cuando un cliente no puede tener acceso a direcciones privadas.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0b96733946e4ef79de244730d0c442b9900426c1
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413348"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acceder a direcciones privadas por rol de seguridad

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
