---
title: Procesamiento por lotes de alertas
description: Este tema proporciona información acerca del procesamiento por lotes de alertas.
author: tjvass
manager: AnnBe
ms.date: 09/10/2010
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: d57586cb18c581e4a462d93a64a88310e251a7af
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798607"
---
# <a name="batch-processing-of-alerts"></a>Procesamiento por lotes de alertas

[!include [banner](../includes/banner.md)]

Las alertas se procesan con la funcionalidad de procesamiento por lotes. Debe configurar el proceso por lotes antes de las alertas de proceso y entrega.

La función de procesamiento por lotes admite dos tipos de eventos:

- Eventos desencadenados por eventos basados en cambios. Estos eventos también se denominan eventos de creación/eliminación y eventos de actualización.
- Eventos desencadenados por fechas de vencimiento.

Puede configurar procesos por lotes para cada tipo de evento.

## <a name="batch-processing-for-change-based-events"></a>Procesamiento de lotes para eventos basados en cambios

El sistema lee todos los eventos basados en cambios que se han producido desde que se ejecutó por última vez el procesamiento por lotes. Los eventos basados en cambios incluyen actualizaciones a campos, la eliminación de registros y la creación de registros. Estos eventos se comparan con las condiciones que ha configurado en las reglas de alertas. Cuando un evento coincide con las condiciones de una regla, el proceso por lotes genera una alerta.

### <a name="frequency-for-change-based-events"></a>Frecuencia para los eventos basados en cambios

Para los eventos basados en cambios, puede configurar un trabajo por lotes que desencadene el procesamiento de un evento tan pronto como el sistema registre el evento. Si configura el trabajo por lotes para que se repita a menudo, los usuarios reciben sus alertas más pronto una vez que se produce los cambios. Sin embargo, una frecuencia alta para el procesamiento por lotes puede afectar de manera negativa el rendimiento del sistema.

Por otra parte, un trabajo por lotes que se repite con menor frecuencia, y que programa para ocasiones en que la carga del sistema es baja, puede ayudar a mejorar el rendimiento del sistema. Sin embargo, una baja frecuencia para el procesamiento por lotes podría no cumplir las demandas de los usuarios para las alertas oportunas.

Por lo tanto, al configurar la frecuencia del procesamiento por lotes para eventos basados en cambios, piense en la relevancia temporal de las alertas y el rendimiento de todo el sistema. Estas consideraciones se vuelven más relevantes a medida que disminuye el número de usuarios que crean reglas de alertas. La frecuencia no afecta al número de eventos que procesa el sistema. Sin embargo, si varios usuarios crean reglas, el proceso ejecuta más comprobaciones. Este tipo de intercambio de datos puede afectar al rendimiento del sistema.

#### <a name="the-risks-of-low-batch-frequency"></a>Los riesgos de una frecuencia de lote baja

Si establece una baja frecuencia para el procesamiento por lotes para eventos basados en cambios, los datos pertinentes para las condiciones de las reglas de alerta podrían cambiar antes del procesamiento. Por lo tanto, es posible que pierda alertas.

Por ejemplo, crea una alerta que se desencadena cuando el evento es **contacto de cliente cambia** y la condición es **cliente = BB**. Dicho de otra forma, cuando el contacto del cliente para el cliente BB se cambia, el proceso registra el evento. Sin embargo, el sistema de procesamiento por lotes se configura de modo que se produzca el procesamiento por lotes con menor frecuencia que la entrada de datos. Si el nombre del cliente cambia de **BB** a **AA** antes de que se procese el evento, los datos de la base de datos ya no coincidirán con la condición de la regla, **cliente = BB**. Por lo tanto, cuando el evento se procese finalmente, no se generará ninguna alerta.

### <a name="set-up-processing-for-change-based-alerts"></a>Configurar el procesamiento de alertas basadas en cambios

1. Vaya a **Administración del sistema** &gt; **Tareas periódicas** &gt; **Alertas** &gt; **Alertas basadas en cambios**.
2. En el cuadro **Cambio basado en avisos** , especifique la información adecuada.

## <a name="batch-processing-for-due-date-events"></a>Procesamiento de lotes para eventos de fecha de vencimiento

El sistema detecta todos los eventos provocados por las fechas de vencimiento y estos eventos se comparan con las condiciones establecidas en las reglas de alertas. El proceso por lotes genera una alerta cuando un evento coincide con las condiciones de una regla.

### <a name="frequency-for-due-date-events"></a>Frecuencia para los eventos de fecha de vencimiento

Es posible que para eventos de fecha de vencimiento, para equilibrar la carga del sistema, quiera establecer que los trabajos por lotes se ejecuten durante la noche o a unas determinadas horas. Se recomienda configurar el trabajo por lotes para ejecutarlo el menos una vez al día. Si debe enviar alertas con la mayor brevedad posible, configure el procesamiento por lotes para que se produzca inmediatamente después de que cambie la fecha del sistema. Si desea que se generen alertas para eventos de fecha de vencimiento que tienen lugar después de que un trabajo por lotes haya procesado ya las alertas, puede ejecutar el trabajo por lotes de nuevo durante el mismo día.

Por ejemplo, un trabajo por lotes se ha ejecutado en un día concreto. A continuación, crea un pedido de compra que tiene una fecha de vencimiento que debería desencadenar una alerta ese mismo día. Para recibir la alerta ese día, debe ejecutar el trabajo por lotes de nuevo una vez se ha creado el pedido de compra. Sin embargo, si no ejecuta el trabajo por lotes otra vez ese día, el trabajo por lotes del día siguiente detecta los eventos de fecha de vencimiento que no se han procesado en los días anteriores.

> [!NOTE]
> El hecho de que un proceso por lotes se ejecute más de una vez al día no significa que se dupliquen las alertas que notifiquen las mismas condiciones y fechas de vencimiento. Solo se generan alertas para las fechas vencidas debido a los cambios producidos en el sistema después de la última ejecución del trabajo por lotes.

### <a name="batch-processing-window"></a>Ventana de procesamiento por lotes

El procesamiento de las reglas de alertas en una empresa se puede detener por varios motivos. Estas razones incluyen vacaciones, errores del sistema u otros problemas que impiden ejecutar trabajos por lotes durante algún tiempo.

Para evitar que las alertas de fecha de vencimiento se vuelvan obsoletas debido a que el trabajo por lotes no se ha ejecutado durante varios días, puede configurar una ventana de procesamiento por lotes. Una ventana de procesamiento por lotes se puede utilizar para evitar que un trabajo por lotes se ejecute durante un número específico de días.

Si configura una ventana de procesamiento por lotes, se envía una alerta cuando se procesa la regla de alertas, aunque la alerta supere el límite de tiempo que se define en los criterios de fecha de vencimiento. Se continúa enviando una alerta siempre que no se supere el período definido por este límite de tiempo más la ventana de procesamiento por lotes. Sin embargo, cuando el período supera el valor que se define por el momento más la ventana de procesamiento por lotes, ya no se enviará una alerta.

### <a name="set-up-processing-for-due-date-alerts"></a>Configurar el procesamiento para alertas de fecha de vencimiento

1. Vaya a **Administración del sistema** &gt; **Tareas periódicas** &gt; **Alertas** &gt; **Alertas de fecha de vencimiento**.
2. En el cuadro **Avisos de fecha de vencimiento**, especifique la información adecuada.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]