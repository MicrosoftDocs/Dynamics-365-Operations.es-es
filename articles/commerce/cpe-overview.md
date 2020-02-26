---
title: Información general del entorno de vista previa de Dynamics 365 Commerce
description: Este tema ofrece una visión general del entorno de vista previa de Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 1ff96aeb5963df9ddee56783a089dad129bbb71c
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024692"
---
# <a name="dynamics-365-commerce-preview-environment-overview"></a>Información general del entorno de vista previa de Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

Este tema ofrece una visión general del entorno de vista previa de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El entorno de vista previa de Commerce es un entorno de vista previa opcional de extremo a extremo de Dynamics 365 Commerce que permite a los clientes potenciales probar el producto de Commerce antes de su lanzamiento general al público.

Además de algunas limitaciones menores que no afectan las características o la funcionalidad, el entorno de vista previa de Commerce proporciona la experiencia completa de Commerce, y los clientes y socios de implementación pueden usarlo para evaluar el producto, proporcionar comentarios y hacer análisis de ajuste / brecha.

## <a name="limitations-of-the-commerce-preview-environment"></a>Limitaciones del entorno de vista previa de Commerce

Aunque el entorno de vista previa de Commerce proporciona el conjunto completo de características y funcionalidades de Commerce, existen algunas limitaciones menores:

- Aunque el entorno de vista previa de Commerce en sí no tiene limitaciones geográficas, los componentes del entorno, como el Retail Cloud Scale Unit (RCSU) y las aplicaciones de comercio electrónico, solo se pueden aprovisionar en los Estados Unidos.
- El entorno de vista previa de Commerce tiene un límite de tiempo de uso de 30 días a partir de la fecha de aprovisionamiento de comercio electrónico.
- El entorno de vista previa de Commerce se puede implementar e inicializar con éxito solo en un entorno que utiliza la topología de demostración, donde todos los componentes de un entorno se implementan en una sola máquina virtual (VM). La principal limitación de esta topología de OneBox VM es la cantidad de usuarios simultáneos que el entorno de vista previa puede admitir.
- El entorno de vista previa de Commerce solo se puede evaluar hasta la disponibilidad general (GA) del producto de Commerce. Nuevos entornos de demostración estarán disponibles después de GA.

## <a name="get-started"></a>Introducción

Para aprovisionar el entorno de vista previa de Commerce, vea [Provisión de un entorno de vista previa de Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Recursos adicionales

[Aprovisionar un entorno de vista previa de Dynamics 365 Commerce](provisioning-guide.md)

[Configurar un entorno de vista previa de Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar características opcionales para un entorno de vista previa de Dynamics 365 Commerce](cpe-optional-features.md)

[Preguntas frecuentes sobre el entorno de vista previa de Dynamics 365 Commerce](cpe-faq.md)
