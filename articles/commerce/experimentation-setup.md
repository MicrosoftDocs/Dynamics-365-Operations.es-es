---
title: Configurar un experimento
description: Este tema describe cómo configurar un experimento en un servicio de terceros.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7453f0780d46ec1b3a09fe122938c8729c35aef6
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349241"
---
# <a name="set-up-an-experiment"></a>Configurar un experimento

Después [definir una hipótesis y determinar qué métricas de éxito desea utilizar](experimentation-identify.md), deberá configurar su experimento en el servicio de terceros. El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en temas separados.

[ ![Recorrido del usuario de experimentación: configurar.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configure su experimento en el servicio de terceros
A esta altura, debería haber elegido su servicio de terceros para ejecutar y supervisar su experimento, y configurar el conector de experimentación. Estos requisitos previos se enumeran en [Experimentación en Dynamics 365 Commerce](experimentation-overview.md).

Siga los pasos necesarios para crear su experimento en el servicio de terceros. Si el conector está configurado correctamente, la lista completa de experimentos que configuró en el servicio de terceros aparecerá en el generador de sitios de Commerce en aproximadamente 5 minutos.

## <a name="set-up-your-success-metrics"></a>Configure sus métricas de éxito
Todo experimento necesita métricas para medir el impacto de las variaciones y validar la hipótesis. Siga los pasos a continuación para habilitar el cálculo de métricas en el servicio de terceros utilizando eventos de telemetría en vivo de Dynamics 365 Commerce.

Para configurar sus métricas de éxito, siga estos pasos:

1. En el generador de sitios de Commerce, seleccione la pestaña **Páginas** en el panel de navegación izquierdo y luego seleccione la página para la que desea recopilar métricas. 
1. Vaya a la sección **ID de eventos para rastrear** en el panel de propiedades derecho de la página o módulo que desea rastrear.
1. Seleccione **Ver**. Se muestra una lista de todos los ID de eventos. Copie el evento que desea rastrear y pegue la clave del evento en la ubicación designada en el servicio de terceros. Si necesita más de un evento, copie las claves una por una. 
    - Para saber cómo ver todos los eventos y atributos disponibles, incluidas las visitas a la página y el seguimiento de ingresos, consulte [Eventos de componentes comerciales para diagnóstico y resolución de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Tome cualquier otro paso para realizar un seguimiento de las métricas según lo requiera el servicio de terceros.

## <a name="previous-step"></a>Paso anterior
[Identificar una hipótesis y determinar métricas para un experimento](experimentation-identify.md) 


## <a name="next-step"></a>Paso siguiente
[Conectar y editar un experimento](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]