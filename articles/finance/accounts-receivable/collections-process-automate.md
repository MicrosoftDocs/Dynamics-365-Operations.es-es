---
title: Automatización del proceso de cobros
description: Este tema describe el proceso de configuración de estrategias de procesos de cobro que identifican automáticamente las facturas de los clientes que requieren un recordatorio por correo electrónico, una actividad de cobro o una carta de cobro que se enviará al cliente.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 59db852024faf457db7ac145b67619b31555aaf2
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "7486878"
---
# <a name="collections-process-automation"></a>Automatización del proceso de cobros

[!include [banner](../includes/banner.md)]

Este tema describe el proceso de configuración de estrategias de procesos de cobro que identifican automáticamente las facturas de los clientes que requieren un recordatorio por correo electrónico, una actividad de cobro (como una llamada telefónica) o una carta de cobro que se enviará al cliente. 

Las organizaciones a menudo dedican una cantidad significativa de tiempo a investigar informes de saldos antiguos, cuentas de clientes y facturas abiertas para determinar con qué clientes hay que contactar sobre una factura abierta o un saldo de cuenta. Esta investigación le quita tiempo al agente de cobros que dedica a comunicarse con los clientes para cobrar saldos deudores o resolver disputas de facturas. La automatización del proceso de cobros le permite configurar un enfoque basado en estrategias para su proceso de cobros. Esto le ayuda a aplicar las actividades de cobros de manera consistente al proporcionar recordatorios personalizados por correo electrónico o un proceso programado para enviar cartas de cobro. 

## <a name="collections-process-setup"></a>Configuración del proceso de cobros
Puede usar la página **Configuración del proceso de cobros** (**Crédito y cobros > Configuración > Configuración del proceso de cobros**) para crear un proceso de cobros automatizado que programará actividades, enviará mensajes de correo electrónico y creará y publicará cartas de cobro de clientes. Los pasos del proceso se basan en la factura abierta principal o más antigua. Cada paso utiliza esta factura para determinar qué comunicación o actividad debe realizarse con un cliente específico.  

Los equipos de cobranza generalmente envían un aviso temprano relacionado con cada factura pendiente, para que se notifique al cliente cuando la factura está a punto de vencer. La selección **Prereclamación** se puede configurar para permitir dar un paso en cada jerarquía de proceso cuando la temporización de la factura llega a ese momento.

### <a name="process-hierarchy"></a>Jerarquía de procesos
Cada grupo de clientes solo se puede asignar a una jerarquía de procesos. El rango de jerarquía de este paso identifica qué proceso tendrá prioridad si un cliente está incluido en más de un grupo que tiene asignada una jerarquía de procesos. El identificador del grupo determina qué clientes se asignarán al proceso. Cada jerarquía establecida solo se puede asignar a una automatización de proceso.

Los días tranquilos se utilizan para garantizar que no se contacte con un cliente con demasiada frecuencia, mediante el proceso automatizado. Por ejemplo, si los días tranquilos se establecen en dos, el proceso automatizado no se pondrá en contacto con un cliente durante al menos dos días, incluso si la factura principal original se ha liquidado en su totalidad. 

Para excluir a los clientes de la automatización del proceso si el saldo de antigüedad del cliente o el importe de la factura es menor que un valor definido, seleccione **Saldo de vencimiento del cliente menor que** o **Importe de la factura inferior a** en el campo **Excluir del proceso** e introduzca el valor de la cantidad.

Marque **Usar predicción** para crear actividades de cobros utilizando las predicciones de pago del cliente. Las actividades creadas utilizarán la plantilla Actividad de **Predicciones de pago** en la página **Parámetros de clientes**, pestaña **Automatización del proceso de cobro**. 

### <a name="process-details"></a>Detalles del proceso
Haga clic en **Nuevo** para agregar un nuevo detalle de proceso a la jerarquía. La **Descripción** se utiliza para identificar el propósito o el nombre del paso en la jerarquía. Seleccione el **Tipo de acción** para definir el paso que creará una actividad, enviará un correo electrónico o creará una carta de cobro. 

- El **Documento comercial** define la plantilla utilizada para crear el tipo de acción. Este documento puede ser una plantilla de actividad, una plantilla de correo electrónico o una carta de cobro enviada a cada cliente. La automatización del proceso de cobro solo crea cartas de cobro por cliente, independientemente de cómo se establezcan otros parámetros de cobro.
- **Cuando** define el paso del proceso que ocurrirá antes o después de la fecha de vencimiento de la factura principal (más antigua), y se utiliza junto con el número que se muestra en la columna **Días en relación con la fecha de vencimiento de la factura**. 
- Marque la opción **Prereclamación** para crear una acción para cada factura en un paso de una jerarquía de procesos. Las acciones de prereclamación son generalmente un aviso temprano relacionado con facturas pendientes, para notificar al cliente cuando la factura está a punto de vencer. La prereclamación solo se puede marcar para una actividad por jerarquía. Cuando selecciona un tipo de acción de correo electrónico, el destinatario se utilizará para definir si el mensaje de corro electrónico se envía a un contacto de cliente, grupo de ventas o agente de cobros. 
- El valor en el campo **Contacto de propósito comercial** determinará qué contacto de la cuenta de ese cliente recibirá la comunicación.

### <a name="business-document-details"></a>Detalles de documentos empresariales
Los detalles del documento empresarial variarán según el tipo de acción que se seleccione en los detalles del proceso. Cuando el tipo de acción es una actividad, se mostrarán los detalles de la plantilla de actividad. Estos detalles incluyen el nombre de la plantilla de la actividad, el tipo de actividad que se creará, el propósito de la actividad, el número de días programados para completar la actividad y los detalles de la actividad. Esta actividad luego se vinculará a la factura principal que informa al destinatario de la acción que se necesita para completar la actividad.

Si el tipo de acción es un correo electrónico en los detalles del proceso, esta sección contendrá dos fichas desplegables. La primera se utiliza para definir el identificador de la plantilla, la descripción del correo electrónico, el idioma predeterminado, el nombre de usuario que se asignará a los mensajes de correo electrónico que se envían automáticamente y la dirección de correo electrónico de los remitentes asociados. La segunda permitirá que el cuerpo del correo electrónico se cree después de que los valores en los campos **Idioma** y **Tema** se guarden seleccionando **Editar**. Esto abrirá una ventana que permite cargar contenido HTML. 

> [!Note]
> Puede guardar un mensaje de correo electrónico de Outlook que contenga el texto del cuerpo de la comunicación en formato HTML. Luego puede cargar el contenido del mensaje para implementar la plantilla. <br> <br> Si se selecciona el tipo de acción de carta de cobro, no habrá una sección de detalles del documento empresarial en la página de configuración.

Utilizar el botón **Historial del proceso de cobros** para ver el historial reciente de la jerarquía de procesos seleccionada. 

Haga clic en la acción **Asignación del proceso de cobros** para ver los clientes asignados a un proceso de cobros. Utilice **Vista previa de asignación del cliente** para ver la jerarquía a la que está asignada un cliente específico. Utilice **Vista previa de asignación de proceso** para obtener una vista previa de los clientes que se asignarán a una jerarquía cuando se ejecute. Haga clic en **Asignación manual** para ver los clientes que se han asignado manualmente a un proceso o seleccione los clientes para asignarlos a un proceso.

Haga clic en la acción **Simulación de proceso** para obtener una vista previa de las acciones que se crearán si la automatización del proceso seleccionado se ejecuta en este momento. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
