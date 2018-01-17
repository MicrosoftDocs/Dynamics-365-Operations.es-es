---
title: Solicitudes de presupuesto
description: "Este tema proporciona una visión general de solicitudes de presupuesto. Las organizaciones emiten solicitudes de presupuesto cuando desean recibir ofertas competitivas de varios proveedores para artículos o servicios que deben comprar."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 42ab7beb8a269cd37fd9100385bd302e4945c1e0
ms.contentlocale: es-es
ms.lasthandoff: 12/14/2017

---

# <a name="requests-for-quotation-rfqs"></a>Solicitudes de presupuesto

[!include[banner](../includes/banner.md)]

Este tema proporciona una visión general de solicitudes de presupuesto. Las organizaciones emiten solicitudes de presupuesto cuando desean recibir ofertas competitivas de varios proveedores para artículos o servicios que deben comprar. En una solicitud de presupuesto, se les pide a los proveedores que proporcionen precios y plazos de entrega para las cantidades de artículos especificadas. También puede solicitar que especifiquen si hay algunos gastos adicionales, como gastos de envío, o si el proveedor ofrece descuentos para pedidos cuantiosos o por pronto pago de la factura de proveedor.

El proceso de solicitud de presupuesto consta de las siguientes tareas:

1. La creación y el envío de una solicitud de presupuesto a uno o más proveedores.
2. Recibir y registrar respuestas a solicitudes de presupuesto (ofertas).
3. Transferir propuestas aceptadas a un pedido de compra, un acuerdo de compra o una solicitud de compra.

La ilustración siguiente muestra una visión general del proceso de solicitud de presupuesto.

[![Proceso RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Puede crear una solicitud de presupuesto desde pedidos planificados, desde una solicitud de compra o mediante una entrada manual. La solicitud de presupuesto que crea se denomina caso de solicitud de presupuesto. El caso de solicitud de presupuesto es el documento base que se usa para enviar una solicitud de presupuesto a cada proveedor.

Tras preparar el caso de solicitud de presupuesto y agregar proveedores, seleccione **Enviar** en el caso de solicitud de presupuesto. Se crea un diario de solicitud de presupuesto para cada proveedor al que se envía una solicitud de presupuesto. Puede configurar los parámetros de gestión de impresión para la acción de envío para imprimir un informe para cada proveedor en un archivo o enviar un informe a la dirección de correo electrónico de cada proveedor. Además, el diario de solicitud de presupuesto para cada proveedor se puede usar para generar un informe que se puede enviar o volver a enviar al proveedor más adelante. También puede configurar la acción de envío para generar una hoja de respuesta que el proveedor pueda completar.

Este tema cubre el proceso para gestionar solicitudes de presupuesto cuando la colaboración del proveedor no se utiliza. Si el sistema está configurado para la colaboración del proveedor, los proveedores pueden introducir propuestas directamente en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Para obtener más información, consulte [Colaboración de proveedor con clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).
 
Si debe enmendar una solicitud de presupuesto después de enviarla, puede volver a enviar la solicitud de presupuesto a los proveedores cuando haya terminado mediante los dos acciones de modificación: Crear y finalizar.

Cuando reciba propuestas por correo electrónico, debe incorporarlas en la página **Respuestas de solicitudes de presupuesto**. Si selecciona la opción **Copiar datos en respuesta**, los datos como la cantidad y las fechas del caso de solicitud de presupuesto se copian en la respuesta. Puede cambiar estos datos para reflejar la propuesta del proveedor.

Si se requiere una segunda iteración de una respuesta para un proveedor, seleccione **Devolver** en la página **Respuesta a solicitud de presupuesto**. La acción de devolución genera un diario nuevo y un informe que se imprimirá, archivará y enviará según la configuración de la gestión de impresión.

Si ha agregado criterios de puntuación a su caso de solicitud de presupuesto, la respuesta a la solicitud de presupuesto tendrá un panel de puntuación donde podrá especificar las puntuaciones. Las puntuaciones totales aparecerán al comparar las respuestas en la página **Comparar respuestas** . En esa página, también puede comparar otros datos de la respuesta, como el precio de la línea, la fecha de entrega, y precio total.

Después de elegir una propuesta o propuestas parciales, puede aceptarlas y rechazar el resto. Los diarios de aceptación, diarios de rechazo y los informes correspondientes se generarán, imprimirán, archivarán y enviarán según la configuración de la gestión de impresión. Al aceptar una propuesta o líneas específicas de una propuesta, se genera un acuerdo de compra o un pedido de compra, o se actualiza una solicitud de compra, en función del tipo de compra de la solicitud de presupuesto. Puede crear un acuerdo comercial que podrá usar más adelante para cualquier respuesta, independientemente de si las acepta o las rechaza.

El estado de una solicitud de presupuesto aparece en el encabezado de la solicitud de presupuesto y depende de los estados de las líneas de la solicitud de presupuesto. El estado indica hasta qué punto se ha procesado dicha solicitud de presupuesto. Cada solicitud de presupuesto tiene dos valores para el estado: el estado más bajo y el estado más alto. El estado más bajo es la fase menos avanzada de cualquier línea de solicitud de presupuesto, y el estado más alto, la fase más avanzada. Por ejemplo, si la fase menos avanzada de una solicitud de presupuesto es para una línea que se ha creado, el estado más bajo de la solicitud de presupuesto es **Creado**. Si la fase más avanzada de la solicitud de presupuesto es para una línea que se ha enviado a proveedores, el estado más alto de la solicitud de presupuesto es **Enviado**. Los estados se actualizan automáticamente mientras se procesa la solicitud de presupuesto.

Puede ver los estados más altos y más bajos de un encabezado de solicitud de presupuesto en la página **Todas las solicitudes de presupuesto**. Puede ver los estados más altos y más bajos de una línea de solicitud de presupuesto en la ficha **Líneas** de la página **Solicitud de presupuestos**.

Esta es la secuencia de estados para el procesamiento de una solicitud de presupuesto:

1. **Creado**
2. **Enviada**
3. **Recibido**
4. **Aceptada**, **Cancelada** o **Rechazada**

Estos estados se describirán más detalladamente más adelante en este tema.

## <a name="setting-up-rfq-functionality"></a>Configuración de la funcionalidad de solicitud de presupuesto

Antes de poder crear un caso de solicitud de presupuesto, debe configurar la información de la solicitud de presupuesto en la página **Parámetros de adquisición y abastecimiento**. Cuando se crea un caso de solicitud de presupuesto, puede especificar los valores predeterminados que se copian a la solicitud de presupuesto. Puede especificar los siguientes valores predeterminados:

- El tipo de compra de nuevas solicitudes de presupuesto: **Pedido de compra** o **Acuerdo de compra**.
- La fecha y hora de vencimiento
- La información de entrega y las condiciones de pago
- Los campos que se deben incluir en la respuesta a la solicitud de presupuesto.

Puede anular estos valores para un caso de solicitud de presupuesto específico.

También debe configurar el proceso de modificación. Como parte de esta configuración, puede habilitar el bloqueo de campos. Cuando se activa el bloqueo de un campo, si un profesional de compras quiere enmendar una solicitud de presupuesto, primero debe seleccionar **Crear** en la sección **Enmienda** de la pestaña **Presupuesto**. A continuación, una vez que la solicitud de presupuesto se haya actualizado con la modificación, el profesional de compras debe completar el proceso haciendo seleccionando **Finalizar**. La acción Finalizar genera un mensaje de correo electrónico que notifica a los proveedores la modificación de la solicitud de presupuesto.

En la página **Parámetros de adquisición y abastecimiento**, seleccione la plantilla para usar en la notificación de correo electrónico que se envía a los proveedores. Cuando se crea una plantilla, puede contener los tokens de sustitución siguientes:

- %Caso de solicitud de presupuesto%
- %Motivo para devolver la propuesta%
- %Motivo de la enmienda%
- %Enmienda preparada por%
- %Empresa%
- %Nombre del caso de solicitud de presupuesto%
- %ExpiryDateTime%
- %Fecha%

Los tokens %Motivo para devolver la propuesta% y %Motivo de la enmienda% se sustituirán por el texto que el profesional de compras especifique al completar la modificación en el asistente de **Enmienda**. Los valores de los tokens %Enmienda preparada por% y %Empresa% se toman automáticamente de la solicitud de presupuesto. El token %Fecha% se reemplaza por la fecha actual.

Una plantilla de correo electrónico también se requiere si desea cancelar una solicitud de presupuesto después de que se haya enviado. Esta plantilla de correo electrónico se usa para enviar la notificación de la cancelación a las personas de contacto del proveedor. La plantilla se debe seleccionar en la página **Parámetros de la adquisición y abastecimiento**. Cuando se crea la plantilla, puede contener los tokens de sustitución siguientes:

- %Motivo de la cancelación%
- %Caso de solicitud de presupuesto% 
- %Solicitud de presupuesto cancelada por%
- %Empresa%
- %Nombre del caso de solicitud de presupuesto%
- %Fecha%

El token de %Motivo de la cancelación% se sustituye por el texto que el profesional de compras especifique en el asistente de **Cancelación**. El token %Fecha% se reemplaza por la fecha actual.

Si desea usar códigos de motivo en una respuesta a una solicitud de presupuesto para indicar por qué se ha rechazado o aceptado, debe configurar códigos de motivo en la página **Motivos de proveedor**.

En la página **Configuración de formulario**, en Adquisición y abastecimiento, puede configurar el aspecto de los documentos de solicitud de presupuesto impresos o almacenados.

> [!NOTE]
> Para una configuración del sector público, debe utilizar el proceso de modificación para modificar una solicitud de presupuesto que ya se ha enviado. Cuando se envía una solicitud de presupuesto, los campos están bloqueados. Por lo tanto, para realizar cambios en la solicitud de presupuesto, debe seleccionar **Crear** para iniciar el proceso de modificación, según lo descrito anteriormente. El comportamiento del bloqueo se controla mediante la opción**Bloquear solicitud de presupuesto cuando se envía** en la página **Parámetros de adquisición y abastecimiento**. De forma predeterminada, este parámetro se establece en **Sí** y, para una configuración del sector público, este valor predeterminado no se puede cambiar. Por lo tanto, aunque el proceso de la modificación se puede gestionar manualmente en una configuración de sector no público, se debe usar para una configuración sector público.

Al crear una solicitud de presupuesto para un pedido de compra y agregar un artículo de inventario a la solicitud de presupuesto, se genera una transacción de inventario con el estado de recepción **Recepción de presupuesto**. Solo las líneas de la solicitud de presupuesto con este estado se tienen en cuenta al usar un plan maestro para calcular suministros. Si desea que el plan maestro incluya líneas de solicitud de presupuesto como recepción prevista, debe configurar este comportamiento en la configuración de planificación maestra.

Un agente o responsable de compras, puede crear y mantener tipos de solicitud que se adapten a los requisitos de compras de su organización. Cada tipo de la solicitud se puede asociar a un método de puntuación. Los métodos de puntuación consisten en un conjunto de criterios que se pueden usar al puntuar propuestas. Debe configurar tipos de solicitud, métodos de puntuación y criterios de puntuación en las páginas **Tipo de solicitud** y **Método de puntuación**.

## <a name="creating-and-sending-an-rfq"></a>Creación y envío de una solicitud de presupuesto

Cree la solicitud de presupuesto, seleccione los proveedores que desee que hagan una propuesta a dicha solicitud y envíesela. Puede usar la gestión de impresión para dirigir los informes de solicitud de presupuesto y hojas de respuesta a su destino preferido.

Puede crear una solicitud de presupuesto para el tipo de compra **Pedido de compra** o **Acuerdo de compra**.

Si la solicitud de presupuesto es del tipo **Pedido de compra**, se produce el comportamiento siguiente:

- Cuando se crean líneas de solicitud de presupuesto, se generan transacciones de inventario con estado de recepción **Recepción de presupuesto**.
- Al aceptar una propuesta, se genera un pedido de compra.

Si la solicitud de presupuesto es del tipo **Acuerdo de compra**, se produce el comportamiento siguiente:

- La solicitud de presupuesto se usa para un contrato para comprar una cantidad o valor de producto específicos en el tiempo. Debe seleccionar el intervalo de fechas que se aplica al acuerdo de compra y el nombre de la persona que gestiona el acuerdo de compra.
- Al aceptar una propuesta, se genera un acuerdo de compra.

Si se genera la solicitud de presupuesto desde una solicitud de compra, se asigna automáticamente el tipo **Solicitud de compra**. No puede crear manualmente una solicitud de presupuesto del tipo **Solicitud de compra**.

Puede crear una solicitud de presupuesto a partir de una solicitud de compra solo si el estado de la solicitud de compra es **En revisión** y le han asignado la realización de la siguiente tarea de flujo de trabajo. Las líneas de la solicitud de compra se actualizan automáticamente al aceptar líneas de las respuestas a solicitudes de presupuesto (propuestas) que recibe de los proveedores. No puede completar, rechazar, aprobar ni realizar ninguna otra acción en la solicitud de compra mientras se esté procesando la solicitud de presupuesto.

Cuando crea una solicitud de presupuesto, puede seleccionar un tipo de solicitud. El tipo de la solicitud determina el conjunto de criterios de puntuación que se usan para puntuar las respuestas a la solicitud de presupuesto.

Puede agregar un cuestionario a un caso de solicitud de presupuesto. Este cuestionario aparece después en todas las respuestas después de enviar la solicitud de presupuesto.

Hay tres maneras de seleccionar a los proveedores que agregar a un caso de solicitud de presupuesto:

- Agregar a los proveedores de uno en uno.
- Buscar a todos los proveedores que cumplan con criterios específicos.
- Agregar automáticamente a todos los proveedores aprobados para las categorías de compras que se usan en las líneas de la solicitud de presupuesto.

Cuando el caso de solicitud de presupuesto esté listo, seleccione **Enviar**. La acción de envío genera diarios e informes que se imprimirán, archivarán y enviarán según la configuración de la gestión de impresión.

Si ha establecido **Usar proveedor para volver a calcular los precios** y **Usar información de artículo específico del proveedor** en **Sí** en la página **Enviar solicitud de presupuesto**, cuando envíe la solicitud de presupuesto a los proveedores, se introducirá automáticamente cierta información específica del proveedor. Puede modificar esta información en la página **Respuesta a solicitud de presupuesto**.

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto al crear una solicitud de presupuesto y enviarla a los proveedores.

| Acción                             | Estado más bajo del encabezado de la solicitud de presupuesto | Estado más alto del encabezado de la solicitud de presupuesto                        | Estado más bajo de la línea de la solicitud de presupuesto | Estado más alto de la línea de solicitud de presupuesto |
|------------------------------------|--------------------------|--------------------------------------------------|------------------------|-------------------------|
| Crear la línea y el encabezado de RFQ.    | Creado                  | Creado                                          | Creado                | Creado |
| Envíe la solicitud de presupuesto a un proveedor específico. | Enviado                     | Enviado                                             | Enviado                   | Enviado |
| Agregue a otro proveedor.                | Creado                  | Enviado (La solicitud de presupuesto se ha enviado solo a un proveedor.) | Creado                | Enviado |
| Enviar la solicitud de presupuesto al segundo proveedor. | Enviado                     | Enviado                                             | Enviado                   | Enviado |

> [!NOTE]
> Puede agregar más proveedores a una solicitud de presupuesto en cualquier momento, y los estados más altos y más bajos se actualizarán para reflejar los nuevos proveedores. Por ejemplo, si recibió propuestas de todos los proveedores y aceptó al menos una línea en una propuesta, el estado más bajo del encabezado de la solicitud es **Rechazado** y el estado más alto es **Aceptado**. Si agrega un nuevo proveedor, el estado más bajo de cualquier línea es ahora **Creado**. Por lo tanto, el estado más bajo del encabezado de la solicitud de presupuesto se actualiza a **Creado** pero el más alto permanece en **Aceptado**.

## <a name="amending-an-rfq"></a>Modificación de una solicitud de presupuesto

En ocasiones deberá cambiar una solicitud de presupuesto tras haberla enviado. Podría tener que cambiar una solicitud de presupuesto si, por ejemplo, las fechas de entrega han cambiado, desee productos adicionales o diferentes cantidades de productos. Puede configurar el proceso de modificación de modo que sea más o menos restrictivo.

Si el configura el proceso de modificación de modo que sea más restrictivo, antes de poder modificar los campos de un caso de solicitud de presupuesto que ya se haya enviado, debe seleccionar **Crear** en el caso de solicitud de presupuesto para iniciar una modificación. Una vez que haya terminado de realizar cambios, debe seleccionar **Finalizar**. A continuación se le guiará por el proceso para agregar información para el mensaje de correo electrónico que se envía para notificar sobre la modificación a los proveedores. El informe de la solicitud de presupuesto actualizado, que incluye una nota de enmienda, se vincula automáticamente al mensaje de correo electrónico.

Si configura el proceso de modificación para que sea menos restrictivo, no tiene que seleccionar **Crear** antes de poder modificar los campos de un caso de solicitud de presupuesto que se haya enviado ya. No obstante, debe agregar manualmente una nota de enmienda a la solicitud de presupuesto y enviar el caso de nuevo. Tenga en cuenta que este enfoque solo se puede utilizar si no se ha editado ninguna de las respuestas (propuestas). Si ha especificado una respuesta y se encuentra en estado **Recibido**, el botón **Enviar** no está disponible. En este caso, debe seleccionar **Crear** y luego **Finalizar**, como debe hacer en el proceso más restrictivo. La respuesta se restablece para reflejar los cambios al caso de solicitud de presupuesto. 

Si los proveedores utilizan la interfaz de colaboración del proveedor para especificar propuestas, debe usar siempre el proceso de modificación para notificar a los proveedores sobre cambios al caso de solicitud de presupuesto. Este requisito ayuda a evitar la situación en la que los proveedores hagan una oferta de un caso de solicitud de presupuesto obsoleto mientras que la oferta está en curso. Para obtener más información acerca de la colaboración de proveedores, consulte [Colaboración con proveedores externos](vendor-collaboration-work-external-vendors.md). 

Si desea para invitar a proveedores adicionales para hacer una propuesta y no ha realizado ningún cambio en el caso de solicitud de presupuesto, puede usar el botón **Enviar**. Los proveedores que se han agregado aparecerán en la página **Enviar** y recibirán el correo electrónico de invitación.

## <a name="receiving-and-registering-rfq-replies"></a>Recepción y registro de respuestas a solicitudes de presupuesto

Cuando se envía una solicitud de presupuesto, se genera una hoja de respuesta automáticamente. A medida que recibe respuestas a la solicitud de presupuesto (propuestas), debe especificar la información de cada proveedor en hoja de una respuesta a la solicitud de presupuesto específica para cada proveedor. Si ha agregado criterios de puntuación, puede puntuar las respuestas. Después se comparan las propuestas de los proveedores y se clasifican según sus criterios de puntuación, como el mejor precio total o el mejor plazo de entrega total.

Si el cuestionario se vincula al caso de solicitud de presupuesto, debe especificar manualmente las respuestas a las preguntas en la hoja de respuestas.

También puede especificar las líneas alternativas, si el caso de solicitud de presupuesto permite líneas alternativas. En la ficha desplegable **Líneas de presupuesto de compras**, seleccione **Agregar línea**. A continuación, especifique la información del producto, como el número de artículo o la categoría de compra, cantidad, precio y descuento.

Si ha especificado una respuesta pero requiere una nueva propuesta del proveedor, puede volver a enviar la solicitud de presupuesto. Se generará un nuevo diario e informe y podrá usarlos para solicitar cambios del proveedor.

Puede ver una descripción de todas las solicitudes de presupuesto y sus estados de respuesta en la página **Seguimiento de solicitud de presupuesto**.

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto a medida que recibe propuestas y registra la información en la hoja de respuesta a la solicitud de presupuesto.

| Acción                                         | Estado más bajo de la oferta | Estado más alto de la oferta | Estado más bajo del encabezado de la solicitud de presupuesto | Estado más alto del encabezado de la solicitud de presupuesto | Estado más bajo de la línea de la solicitud de presupuesto | Estado más alto de la línea de solicitud de presupuesto |
|------------------------------------------------|-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Registre una oferta de proveedor y guárdela.        | Enviada              | Recibida           | Enviada                     | Recibida                  | Enviada                   | Recibida |
| Registre una segunda oferta de proveedor y guárdela. | Recibida          | Recibida           | Recibida                 | Recibida                  | Recibida               | Recibido |

> [!NOTE]
> Si devuelve una propuesta a un proveedor para seguir negociando, los estados más bajos y más altos siguen siendo **Recibido**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Aceptación y rechazo de propuestas y transferencia de propuestas aceptadas a documentos descendentes

Una vez identificada la mejor propuesta, como la que ofrece el mejor precio total, acepta la propuesta. Puede aceptar algunas líneas en una propuesta y rechazar otras. También puede aceptar líneas de diferentes proveedores. Tenga en cuenta que, si acepta algunas líneas, se le pedirá que rechace el resto de líneas. Por lo tanto, si desea aceptar otras líneas, debe seleccionar **Cancelar** cuando reciba el mensaje. El estado de la respuesta a la solicitud de presupuesto para cada proveedor que acepta propuestas o las líneas se actualiza a **Aceptado**. 

Al aceptar una propuesta o líneas específicas de una propuesta, se genera automáticamente un pedido de compra o un acuerdo de compra. A continuación puede rechazar las propuestas de todos los otros proveedores.

En la respuesta puede agregar un código de motivo para explicar por qué se aceptó o rechazó una propuesta.

Al aceptar una respuesta a una solicitud de presupuesto con el tipo **Solicitud de compra**, las líneas de respuesta a la solicitud de presupuesto actualizan las líneas de solicitud de compra con la siguiente información:

- Precio unitario
- Porcentaje de descuento
- Importe del descuento
- Gastos de compra
- Gastos de línea
- Proveedor
- Número externo
- Descripción externa

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto a medida que se aceptan y rechazan propuestas de los proveedores.

| Acción                      | Estado más bajo de la propuesta | Estado más alto de la propuesta | Estado más bajo del encabezado de la solicitud de presupuesto | Estado más alto del encabezado de la solicitud de presupuesto | Estado más bajo de la línea de la solicitud de presupuesto | Estado más alto de la línea de solicitud de presupuesto |
|-------------------------    |-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Acepte una de las ofertas.     | Recibida          | Aceptada           | Recibida                 | Aceptada                  | Recibida               | Aceptada |
| Rechazar todas las otras propuestas.  | Rechazado          | Aceptada           | Rechazado                 | Aceptada                  | Rechazado               | Aceptado |

