---
title: Acceder a direcciones privadas por rol de seguridad
description: El artículo explica cómo resolver la incidencia cuando un cliente no puede acceder a direcciones privadas.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
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
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: facfd17f007b2c9e6f068d0ec4c5ce45b85a1b78
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010490"
---
# <a name="access-to-private-addresses-by-security-role"></a>Acceder a direcciones privadas por rol de seguridad

**Emisión**

Después de que un cliente duplique un rol de seguridad e inicie sesión como dicho nuevo rol, el cliente no puede ver las direcciones que fueron marcadas como privadas.

**Resolución**

Para solucionar el problema, el cliente debe seguir estos pasos para el rol de seguridad duplicado.

1. Vaya a **Administración de la organización \> Libreta de direcciones global \> Parámetros de libreta de direcciones global**.
2. En la pestaña **Seguridad de ubicación privada** , mueva el nuevo rol de seguridad desde la lista **Roles disponibles** a la lista **Roles seleccionados**.
3. Seleccione **Guardar**.

![Página de parámetros de la libreta de direcciones global](media/GAD-parameters.png)
