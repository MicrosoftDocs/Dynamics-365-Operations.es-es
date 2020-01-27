---
title: Acceder a direcciones privadas por rol de seguridad
description: Este tema explica cómo resolver el problema en que el cliente no puede tener acceso a direcciones privadas.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897106"
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
