---
title: Configurar un experimento
description: Este artículo describe cómo configurar un experimento en un servicio de terceros.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946175"
---
# <a name="set-up-an-experiment"></a>Configurar un experimento

Después [definir una hipótesis y determinar qué métricas de éxito desea utilizar](experimentation-identify.md), deberá configurar su experimento en el servicio de terceros. El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en artículos separados.

[ ![Recorrido del usuario de experimentación: configurar.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configure su experimento en el servicio de terceros
A esta altura, debería haber elegido su servicio de terceros para ejecutar y supervisar su experimento, y configurar el conector de experimentación. Estos requisitos previos se enumeran en [Experimentación en Dynamics 365 Commerce](experimentation-overview.md).

Siga los pasos necesarios para crear su experimento en el servicio de terceros. Si el conector está configurado correctamente, la lista completa de experimentos que configuró en el servicio de terceros aparecerá en el generador de sitios de Commerce en aproximadamente 5 minutos.

## <a name="set-up-your-success-metrics"></a>Configure sus métricas de éxito
Todo experimento necesita métricas para medir el impacto de las variaciones y validar la hipótesis. Siga los pasos a continuación para habilitar el cálculo de métricas en el servicio de terceros utilizando eventos de telemetría en vivo de Dynamics 365 Commerce.

Para configurar sus métricas de éxito para los módulos listos para usar, siga estos pasos.

1. En el generador de sitios de Commerce, seleccione la pestaña **Páginas** en el panel de navegación izquierdo y luego seleccione la página para la que desea recopilar métricas. 
1. Vaya a la sección **ID de eventos para rastrear** en el panel de propiedades derecho de la página o módulo que desea rastrear.
1. Seleccione **Ver**. Se muestra una lista de todos los ID de eventos de clic. Copie el evento que desea rastrear y luego pegue la clave del evento en la ubicación designada en el servicio de terceros. Si necesita más de un evento, copie las claves una por una. 
1. Para vistas de página, use el valor hash SHA-256 del nombre de la página en el generador de sitios anexado con `.PageView`. Por ejemplo, el ID de evento para `Homepage.PageView` sería `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Tome cualquier otro paso para realizar un seguimiento de las métricas según lo requiera el servicio de terceros.

Para los clics de módulos personalizados, siga estos pasos para instrumentar los eventos de clic:

1. Prepare un objeto **TelemetryContent** para el módulo utilizando la siguiente función. Esta función toma el nombre de la página, el nombre del módulo y el objeto de telemetría predeterminado proporcionado por el SDK como entradas.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    A continuación se muestra un ejemplo: 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Cree los datos de carga útil que contienen información sobre lo que debe capturarse. Para botones y otros controles estáticos, puede incluir **etext** como "Comprar ahora" o "Buscar". Y para componentes con clics, como hacer clic en una tarjeta de producto, puede enviar el **recid**, que es el ID de registro del producto o el ID del producto.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    Como ejemplo de controles estáticos, pase la cadena de texto del botón como se muestra a continuación:

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    Como ejemplo de clics de productos, pase el recordId de producto como se muestra a continuación:

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Llame a la función **OnClick** para registrar el evento.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    A continuación se muestra un ejemplo:

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Paso anterior
[Identificar una hipótesis y determinar métricas para un experimento](experimentation-identify.md) 


## <a name="next-step"></a>Paso siguiente
[Conectar y editar un experimento](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
