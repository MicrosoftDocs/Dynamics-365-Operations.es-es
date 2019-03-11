---
title: Crear reglas de alertas
description: Este tema proporciona información acerca de alertas y explica la manera de crear una regla de alerta para notificarle eventos como una fecha que se aproxima o un cambio concreto que aparezca.
author: tjvass
manager: AnnBe
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: cbf4917424e72a70a6d513b5daf45f6bf9cd57c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "329422"
---
# <a name="create-alert-rules"></a>Crear reglas de alertas

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>Introducción

Antes de configurar una regla de alerta, decida cuándo o en qué situaciones desea recibir las alertas. Cuando sepa acerca de qué evento desea que se le avise, en Microsoft Dynamics 365 for Finance and Operations, encuentre la página en donde aparecen los datos que provocan la aparición del evento. El evento puede ser una fecha que llega o un cambio específico que se produce. Por tanto, debe buscar la página donde se especifica la fecha o donde se muestra el campo que cambia o el registro nuevo. Cuando tenga esta información, puede crear la regla de alerta.

Al crear una regla de alertas, puede definir los criterios que deben cumplirse antes de que se desencadene una alerta. Puede pensar en los criterios como una coincidencia entre el caso de que se produzca evento y el cumplimiento de condiciones concretas. Cuando se produce un evento, el sistema empieza a realizar una comprobación en función de las condiciones que se configuran en Finance and Operations.

## <a name="events"></a>Eventos

El evento que desencadena una regla de alertas puede ser una fecha que llega o un cambio específico que se produce. Los desencadenadores para los eventos se definen en la ficha desplegable **Avisar cuando** del cuadro **Crear regla de alertas**. Los eventos que están disponibles para un campo determinado dependen del desencadenador que se selecciona.

Por ejemplo, si está configurando una regla de alerta para el campo **Fecha de inicio**, los eventos de fecha de vencimiento son adecuados. Por lo tanto, el tipo de evento **vencimiento es** está disponible para este campo. Sin embargo, para un campo como **Centro de coste**, un evento de fecha de vencimiento no es adecuado. Por lo tanto, el tipo de evento **vencimiento es** no está disponible. En su lugar, el tipo de evento **ha cambiado** está disponible.

## <a name="event-types"></a>Tipos de evento

Se pueden producir tres tipos de eventos:

- **Eventos de tipo crear y de tipo eliminar** Estos eventos activan una alerta cuando se crea o se elimina un registro.
- **Eventos de tipo actualización** Estos eventos activan una alerta cuando cambian los datos de un campo específico.
- **Eventos de tipo Fecha de vencimiento**: estos eventos desencadenan una alerta cuando llega una fecha.
    
Los cambios que se producen se pueden iniciar por un usuario. Por ejemplo, un usuario cambia la fecha de entrega de un pedido de compra. Como alternativa, los cambios se pueden producir como parte de un proceso. Por ejemplo, el campo **Estado** de una página cambia para reflejar el ciclo de vida de varios procesos en el sistema.

## <a name="conditions"></a>Condiciones

En la ficha desplegable **Avisar para** del cuadro de diálogo **Crear regla de alertas**, puede usar condiciones para controlar cuándo desea que se le avise sobre eventos.

Por ejemplo, puede especificar que el sistema debería alertarle cuando el estado de los pedidos de compra cambie, pero únicamente si el estado coincide con un conjunto determinado de condiciones. En concreto, desea que le avisen cuando el estado de un pedido de compra se establece en **Recibido**. Este cambio en el estado es el evento que desencadena la alerta.

A continuación, debe decidir acerca de sobre qué pedidos de compra desea recibir una alerta. Por ejemplo, puede seleccionar una de los siguientes opciones. Estas opciones definen las condiciones de la regla de alertas.

- **Registro actual seleccionado**: Recibe una alerta cuando el estado de un pedido de compra específico cambia a **Recibido**.
- **Todos los registros** Recibirá una alerta cuando cambie el estado de un pedido de compra de un artículo en la vista de la página activa. Puede usar el filtrado avanzado que está disponible en la página para crear reglas para un conjunto de registros específico. Por ejemplo, puede crear una alerta que se active para todos los pedidos de compras para clientes de un grupo de clientes específico.
    
## <a name="expiry-of-rule"></a>Vencimiento de la regla

En la ficha desplegable **Avisar hasta** del cuadro de diálogo **Crear regla de alertas**, puede especificar el tiempo que la regla de alerta debe estar activa.

## <a name="alert-contents"></a>Contenido de la alerta

En la ficha desplegable **Avisar con** del cuadro de diálogo **Crear regla de alertas**, puede especificar el texto del asunto y del mensaje que deben usar las alertas.

## <a name="user-id"></a>Id. de usuario

En la ficha desplegable **Avisar a** del cuadro de diálogo **Crear regla de alertas**, puede especificar qué usuario debe recibir los mensajes de alerta. De forma predeterminada, se selecciona el id. de usuario. Esta opción se limita a los administradores de la organización.

## <a name="create-an-alert-rule"></a>Cree una regla de alerta

1. Abra la página que incluye los datos para supervisar.
2. En el Panel de acciones, en la ficha **Opciones**, en el grupo **Compartir**, seleccione **Crear regla de alertas**.
3. En el cuadro de diálogo **Crear regla de alertas**, en el campo **Campo**, seleccione el campo que desea supervisar.
4. En el campo **Evento**, seleccione el tipo de evento.
5. En la ficha desplegable **Avisar para** , seleccione una opción.
6. Si desea que la regla de alerta esté inactiva en una fecha concreta, seleccione una fecha final en la ficha desplegable **Avisar hasta**.
7. En la ficha desplegable **Avisar con**, en el campo **Asunto**, acepte el encabezado de asunto predeterminado para el mensaje de correo electrónico o escriba un nuevo asunto. El texto se usa como el encabezado de asunto del mensaje de correo electrónico que recibe cuando se desencadena una alerta.
8. En el campo **Mensaje**, Inserte un mensaje opcional. El texto se usa como el mensaje que recibe cuando se desencadene la alerta.
9. Seleccione **Aceptar** para guardar la configuración y crear la regla de alertas.
