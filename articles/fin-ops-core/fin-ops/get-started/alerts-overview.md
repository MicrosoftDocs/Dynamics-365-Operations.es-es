---
title: Visión general de alertas
description: Este tema proporciona información general acerca de alertas. Puede usar alertas para permanecer informado acerca de los eventos de los que desea realizar un seguimiento durante el día laborable.
author: RichdiMSFT
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 5a92d84a5e8eaa2477d90df5065c0941d90dad5a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749861"
---
# <a name="alerts-overview"></a>Información general de alertas

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>Acerca de los avisos
Las alertas forman un sistema de notificaciones para eventos críticos en el sistema. Puede usar alertas para permanecer informado acerca de los eventos de los que desea realizar un seguimiento durante el día laborable. Puede crear con facilidad su propio conjunto de reglas de alertas para recibir alertas sobre las entregas vencidas, pedidos eliminados, precios que cambian u otros eventos a los que debe responder.

En (ERP) la planificación de recursos empresariales, hay varias situaciones habituales donde la función de avisos se puede usar. Aquí hay algunos ejemplos.

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>Escenario 1: crear una regla de alerta para los pedidos de ventas nuevos.

1. Abra la página **Todos los pedidos de venta**.
2. En el Panel de acciones, en la ficha **Opciones**, en el grupo **Compartir**, seleccione **Crear una alerta personalizada**.
3. En el cuadro **Crear regla de alertas**, en la ficha desplegable **Avisarme cuando**, en el campo **evento**, seleccione **El registro se ha creado**.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>Escenario 2: crear una regla de alerta para posponer una fecha de entrega

1. Abra la página **Todos los pedidos de compra**.
2. Seleccione un identificador del pedido de compra para acceder a los detalles del pedido de compra.
3. Expanda la ficha desplegable **Encabezado de pedido de compras**.
4. En el Panel de acciones, en la ficha **Opciones**, en el grupo **Compartir**, seleccione **Crear una alerta personalizada**.
5. En el cuadro **Crear regla de alertas**, en la ficha desplegable **Avisarme cuando**, en el campo **Campo**, seleccione **Fecha de entrega**.
6. En el campo **evento**, seleccione **se ha aplazado**.
    
Después de cerrar el cuadro de diálogo **Crear regla de alertas**, la regla aparece en la página **Administrar reglas de alertas**. Puede usar la página **Administrar reglas de alertas** para actualizar sus reglas de alertas existentes. Por ejemplo, puede modificar los desencadenadores de eventos, actualizar notificaciones de eventos y actualizar las fechas de vencimiento. Para abrir la página **Administrar reglas de alertas** , use el botón **Avisarme** en la pestaña **Opciones** del panel de acciones.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>¿Qué sucede cuando se crea una regla de alertas?

Cuando crea reglas de alertas, puede asociar un evento predefinido a un campo específico. Por ejemplo, cuando llega la fecha que se especifica en el campo o cuando cambia el contenido del campo. Como alternativa, puede asociar un evento a los registros en una página específica. Por ejemplo, se crea un registro o se elimina un registro.

Cuando se produce el evento seleccionado para el campo, o para un registro de la página, se le envía una alerta. Por ejemplo, crea una regla en la que asocia el campo **Fecha de entrega** a una línea de pedido de compras específica con el evento **ha vencido hace tiempo**. Establece el período de tiempo en cinco días. En este caso se envía una alerta cinco días después de la fecha de entrega de dicha línea de pedido de compra.

Además, puede limitar las reglas de alertas estableciendo condiciones. Por ejemplo, puede recibir una alerta acerca de los nuevos pedidos de compra que se crean para las cuentas de proveedor específicas.

## <a name="preparing-for-an-alert"></a>Preparación para una alerta

Antes de configurar una regla de alerta, decida cuándo o en qué situaciones desea recibir las alertas. Cuando sepa acerca de qué evento desea que se le avise, encuentre la página en donde aparecen los datos que provocan la aparición del evento. El evento puede ser una fecha que llega o un cambio específico que se produce. Por tanto, debe buscar la página donde se especifica la fecha o donde se muestra el campo que cambia o el registro nuevo. Cuando tenga esta información, puede crear la regla de alerta.

## <a name="components-of-an-alert-rule"></a>Componentes de una regla de alertas

Una regla de alertas tiene cinco componentes:

- **Evento**: El evento que desencadena una regla de alertas puede ser una fecha que llega o un cambio específico que se produce. Defina eventos en la ficha desplegable **Enviar alertas de correo electrónico para los cambios de estado de los trabajos** del cuadro **Crear regla de alertas**.
- **Condición** En la ficha desplegable **Avisar para** del cuadro de diálogo **Crear regla de alertas**, puede seleccionar el ámbito de la condición, para controlar cuándo desea que se le avise sobre eventos. Puede aplicar la regla al registro actual solamente o a todos los registros visibles de la página. Si la regla se aplica a todas las entidades jurídicas, puede establecer la opción **En toda la organización** en **Sí**.
- **Vencimiento de la regla** En la ficha desplegable **Avisar hasta** del cuadro de diálogo **Crear regla de alertas**, puede especificar el tiempo que la regla de alerta debe estar activa.
- **Contenido** En la ficha desplegable **Avisar con** del cuadro de diálogo **Crear regla de alertas**, puede especificar el texto del asunto y del mensaje que deben usar las alertas.
- **Usuario** En la ficha desplegable **Avisar a** del cuadro de diálogo **Crear regla de alertas**, puede especificar qué usuario debe recibir los mensajes de alerta. De forma predeterminada, se selecciona el id. de usuario.

    > [!NOTE]
    > Esta opción se limita a los administradores de la organización.

## <a name="videos"></a>Vídeos

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>Cómo utilizar Alertas para controlar datos filtrados

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

El vídeo [Cómo utilizar Alertas para controlar datos filtrados](https://youtu.be/ZYKMcv6kl9s) (ver arriba) se incluye en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

### <a name="alert-rule-options"></a>Opciones de reglas de alertas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

El vídeo [Opciones de reglas de alertas](https://youtu.be/cpzimwOjicM) (aparece más arriba) está incluido en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]