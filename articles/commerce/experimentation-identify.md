---
title: Identificar una hipótesis y determinar métricas para un experimento
description: Este tema describe cómo identificar la hipótesis y las métricas de éxito para un experimento que ejecutará en un sitio web de comercio electrónico en Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99642861d69b7545f03c6ed2c2650eadeb377534
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930282"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Identificar una hipótesis y determinar métricas de éxito para un experimento
La primera fase del ciclo de vida de la experimentación incluye identificar la hipótesis para el experimento y determinar las métricas que rastreará para evaluar el éxito. El siguiente diagrama muestra todos los pasos necesarios para [configurar y ejecutar un experimento](experimentation-overview.md) en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en temas separados. 

[ ![Recorrido del usuario de experimentación: identificar](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

Una hipótesis es una declaración en la que predice el resultado del experimento. Muchos factores intervienen en la definición de una hipótesis, por ejemplo, la investigación sobre el comportamiento del usuario y los datos del sitio web que ha recopilado. Con la hipótesis, definirás la suposición o teoría que deseas validar con tu experimento. Un ejemplo de hipótesis para su experimento puede ser "*una imagen de una camiseta blanca en mi página de inicio generará una tasa de clics más alta que un suéter azul marino durante los meses de verano porque la gente quiere usar algo liviano y de colores claros en el verano*". En ese caso, creará variaciones que incluyen una camiseta blanca y un suéter azul marino, y publicará ambos al mismo tiempo.

Para validar una hipótesis, el éxito o el fracaso de un experimento debe estar directamente relacionado con las acciones del usuario; por ejemplo, si el usuario del sitio web hace clic en un enlace o botón. Estas acciones deben corresponder con eventos que se informarán al servicio de terceros que realiza el seguimiento del experimento. Con el tiempo, el porcentaje de usuarios que realizan la acción se contabilizará como una métrica que puede utilizar para generar informes y realizar análisis. Consulte el tema [Eventos de componentes comerciales para diagnóstico y resolución de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) para revisar todos los eventos y atributos disponibles.

## <a name="previous-step"></a>Paso anterior
[Experimentación en Dynamics 365 Commerce](experimentation-overview.md)


## <a name="next-step"></a>Paso siguiente
[Configurar un experimento](experimentation-setup.md)
