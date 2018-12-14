---
title: "El usuario puede tener acceso a Core HR pero no a la aplicación Onboard ni Attract."
description: "Este tema explica cómo resolver el problema en el que un usuario puede tener acceso a Microsoft Dynamics 365 for Talent Core HR, pero no puede tener acceso a la aplicación Attract ni Onboard."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>El usuario puede tener acceso a Core HR pero no a la aplicación Onboard ni Attract.

[!include [banner](includes/banner.md)]

**Detalles del entorno**

- La implementación de Microsoft Dynamics Lifecycle Services (LCS) la realizó el usuario A.
- El usuario A agregó a B como usuario a Microsoft Dynamics 365 for Talent Core HR.

**Emisión**

El usuario B puede tener acceso a Core HR, pero no puede tener acceso a la aplicación Talent: Attract o la aplicación Talent: Onboard. Cuando el usuario intenta ir a **Aplicaciones de experiencia**, se le lleva en su lugar a un entorno de prueba.

**Solución**

El usuario B h de tener asignados derechos de ver el entorno de Microsoft PowerApps que el usuario A creó durante el proceso de abastecimiento.

Para obtener más información, consulte “Conceder acceso al entorno” en [Aprovisionar Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Solución a largo plazo**

Microsoft está considerando asignar automáticamente los derechos adecuados a Onboard y Attract cuando se agrega un usuario a Core HR.

