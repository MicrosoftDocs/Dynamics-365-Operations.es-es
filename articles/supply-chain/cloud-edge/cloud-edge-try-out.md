---
title: Intentar escalar unidades en una topología híbrida distribuida
description: Este tema proporciona información sobre cómo probar las unidades de escalado en la nube y en el perímetro para cargas de trabajo de gestión de almacenes y fabricación.
author: perlynne
ms.date: 05/02/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 658948d94cd012b95812a786433967f5cadc3a15
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711897"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Intentar escalar unidades en una topología híbrida distribuida

[!include [banner](../includes/banner.md)]

El proceso de probar la topología híbrida distribuida es sencillo. Durante la primera etapa, debe validar las personalizaciones para asegurarse de que funcionen en la topología distribuida. Tiene dos opciones.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>Opción 1: evaluar las personalizaciones en entornos de desarrollo

Antes de comenzar a incorporar sus entornos de espacio aislado, le recomendamos que explore las unidades de escala en una configuración de desarrollo, como un entorno de una sola caja (también conocido como entorno de nivel 1), para que pueda validar procesos, personalizaciones, y soluciones. Durante esta etapa, los datos y las personalizaciones se aplicarán a los entornos one-box. Puede ejecutarse en un único entorno, que puede desempeñar la función tanto de centro empresarial como de unidad de escalado. Como alternativa, puede tener dos entornos de desarrollo, uno de los cuales asume la función de concentrador y el otro de los cuales asume la función de una unidad de escalado. Esta configuración proporciona la mejor manera de identificar y solucionar problemas. La última [compilación de versión preliminar](../../fin-ops-core/fin-ops/get-started/one-version.md#how-can-i-get-early-access-to-non-released-platform-updates) también se puede utilizar para completar esta etapa.

Debe usar las [herramientas de implementación de unidades de escalado para entornos de desarrollo de una sola caja](https://github.com/microsoft/SCMScaleUnitDevTools) para instalar y mantener los entornos. Estas herramientas le permiten configurar unidades de escalado y concentradores en uno o dos entornos de una sola caja. Las herramientas se proporcionan tanto como una versión binaria como en código fuente en GitHub. Estudie la wiki del proyecto, que incluye una [Guía de uso paso a paso](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) que describe cómo se usan las herramientas. Si está [implementando unidades de escalado de borde en hardware personalizado mediante el uso de datos comerciales locales (LBD)](cloud-edge-edge-scale-units-lbd.md), debe seguir un proceso diferente.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>Opción 2: Adquirir complementos e implementarlos en sus entornos de espacio aislado y de producción

Para probar la topología híbrida distribuida, debe tener dos entornos de espacio aislado (nivel 2), uno de los cuales tiene sus datos (centro de conectividad empresarial) y el otro es para la unidad de escalado y tiene "datos vacíos".

Debe adquirir complementos para al menos una unidad de escalado de nube o borde. Loa franjas de proyecto y entorno correspondientes se concederán en [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), para que los entornos de la unidad de escalado se puedan implementar mediante el [Portal de Scale Unit Manager](https://aka.ms/SCMSUM).

Póngase en contacto con el soporte técnico de Microsoft para solicitar que se habiliten los entornos de espacio aislado.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
