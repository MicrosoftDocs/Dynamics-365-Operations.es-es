---
title: Información general del entorno de evaluación de Dynamics 365 Commerce
description: Este tema ofrece una visión general del entorno de evaluación de Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415429"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Información general del entorno de evaluación de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tema ofrece una visión general del entorno de evaluación de Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Los entornos de evaluación de Commerce no suelen estar disponibles y se conceden a socios y clientes por solicitud. Para obtener más información, póngase en contacto con su partner de Microsoft.

## <a name="overview"></a>Información general

El entorno de evaluación de Commerce es un entorno integral opcional de Dynamics 365 Commerce que permite a partners y posibles clientes probar el producto de Commerce.

Los entornos de evaluación están parcialmente preconfigurados para reducir los pasos necesarios posteriores al aprovisionamiento.

Además de algunas limitaciones secundarias que no afectan a las características o a la funcionalidad, el entorno de evaluación de Commerce proporciona la experiencia completa de Commerce, y los clientes y partners de implementación pueden usarlo para evaluar el producto, proporcionar comentarios y realizar análisis de idoneidad/lagunas.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Limitaciones del entorno de evaluación de Commerce

Aunque el entorno de evaluación de Commerce proporciona el conjunto completo de características y funcionalidades de Commerce, hay algunas limitaciones secundarias:

- Aunque el entorno de evaluación de Commerce en sí no tiene limitaciones geográficas, los componentes del entorno, como el Retail Cloud Scale Unit (RCSU) y las aplicaciones de comercio electrónico, solo se deben aprovisionar en Estados Unidos.
- El entorno de evaluación de Commerce tiene un límite de tiempo de uso de 30 días a partir de la fecha de aprovisionamiento de comercio electrónico.
- El entorno de evaluación de Commerce solo se puede implementar e inicializar correctamente en un entorno que utiliza la topología de demostración, donde todos los componentes de un entorno se implementan en una sola máquina virtual hospedada en la nube (VM). La limitación principal de esta topología es el número de usuarios simultáneos que puede admitir el entorno.

## <a name="get-started"></a>Introducción

Para aprovisionar el entorno de evaluación de Commerce, consulte [Aprovisionar un entorno de evaluación de Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Recursos adicionales

[Aprovisionar un entorno de evaluación de Dynamics 365 Commerce](provisioning-guide.md)

[Configurar un entorno de evaluación de Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce](cpe-bopis.md)

[Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce](cpe-optional-features.md)

[Preguntas más frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce](cpe-faq.md)
