---
title: Preguntas frecuentes sobre entorno de evaluación de Dynamics 365 Commerce
description: Este tema proporciona respuestas a preguntas frecuentes acerca del entorno de evaluación de Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 637714e28b9f8f4aa66e251e709d8f78bff2739d
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599778"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Preguntas frecuentes sobre entorno de evaluación de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tema proporciona respuestas a preguntas frecuentes acerca del entorno de evaluación de Microsoft Dynamics 365 Commerce.

**¿Podemos usar el entorno de evaluación de Commerce como escaparate de comercio electrónico para los clientes que actualmente implementan Retail?**

N. º El entorno de evaluación de Commerce sirve solo para la evaluación. Si necesita un entorno para un cliente que implementa Retail, póngase en contacto con Microsoft.

**¿Se puede usar el entorno de evaluación de Commerce para aprovisionar las características de comercio electrónico además de una aplicación / entorno existente que implementa Retail?**

No (mayormente). Los componentes de evaluación de Commerce están disponibles solo para entornos que coinciden con las configuraciones que se especifican en los requisitos previos y la guía de aprovisionamiento. Además, los datos de demostración base requeridos no estarán disponibles en entornos implementados con una versión inicial anterior a 10.0.8. 

**¿Qué costos están involucrados en la implementación del entorno de evaluación de Commerce en Microsoft Azure vía Microsoft Dynamics Lifecycle Services (LCS)?**

Se alojará en su suscripción de Azure un entorno de demostración de sedes centrales de Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce (máquina virtual \[VM\]). Puede usar la [Calculadora de precios de Azure ](https://azure.microsoft.com/pricing/calculator/) para estimar este coste.

Otros componentes como Commerce Scale Unit, el generador de sitios de Commerce y su sitio de comercio electrónico estarán disponibles como software como servicio (SaaS) y estarán alojados por Microsoft.

**¿Qué geografías de Azure son compatibles actualmente para el entorno de evaluación de Commerce?**

El entorno de evaluación de Commerce solo se puede implementar en la geografía de Norteamérica.

**¿Existe un disco duro virtual descargable (VHD) que tenga la opción completa de máquina virtual (VM) OneBox?**

Dynamics 365 Commerce y Commerce Scale Unit son completamente software como servicio (SaaS) y deben estar alojados en la nube.

**¿Cuánto tiempo se puede usar el entorno de evaluación de Commerce?**

El entorno de evaluación de Commerce tiene un límite de tiempo de 30 días a partir de la fecha en que se aprovisionan componentes de SaaS como Commerce Scale Unit, el generador de sitios de Commerce y su sitio de comercio electrónico.

**¿Puedo extender el límite de tiempo para mi entorno de evaluación de Commerce?**

La extensión del límite de tiempo es una excepción a la norma y se considera caso por caso. Póngase en contacto con su partner de Microsoft si requiere asistencia.

## <a name="additional-resources"></a>Recursos adicionales

[Información general del entorno de evaluación de Dynamics 365 Commerce](cpe-overview.md)

[Aprovisionar un entorno de evaluación de Dynamics 365 Commerce](provisioning-guide.md)

[Configurar un entorno de evaluación de Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce](cpe-bopis.md)

[Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce](cpe-optional-features.md)
