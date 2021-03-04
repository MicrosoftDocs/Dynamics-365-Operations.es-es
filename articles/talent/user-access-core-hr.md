---
title: El usuario puede acceder a Human Resources pero no a Onboard o Attract
description: Este tema explica cómo resolver el problema en el que un usuario puede tener acceso a Microsoft Dynamics 365 Talent - Human Resources, pero no puede tener acceso a Attract ni Onboard.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462454"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a>El usuario puede acceder a Human Resources pero no a Onboard o Attract

[!include [banner](includes/banner.md)]

**Detalles del entorno**

- La implementación de Microsoft Dynamics Lifecycle Services (LCS) la realizó el usuario A.
- El usuario A agregó a B como usuario a Microsoft Dynamics 365 Human Resources.

**Emisión**

El usuario B puede tener acceso a Human Resources, pero no puede tener acceso a la aplicación Talent: Attract o la aplicación Talent: Onboard. Cuando el usuario intenta ir a **Aplicaciones de experiencia**, se le lleva en su lugar a un entorno de prueba.

**Solución**

El usuario B de tener asignados derechos de ver el entorno de Microsoft Power Apps que el usuario A creó durante el proceso de abastecimiento.

Para obtener más información, consulte “Conceder acceso al entorno” en [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Solución a largo plazo**

Microsoft está considerando asignar automáticamente los derechos adecuados a Onboard y Attract cuando se agrega un usuario a Human Resources.


[!INCLUDE[footer-include](../includes/footer-banner.md)]