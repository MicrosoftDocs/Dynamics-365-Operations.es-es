---
title: Solicitudes de presupuesto
description: Este tema proporciona una visión general de solicitudes de presupuesto. Las organizaciones emiten solicitudes de presupuesto cuando desean recibir ofertas competitivas de varios proveedores para artículos o servicios que deben comprar.
author: mkirknel
manager: AnnBe
ms.date: 06/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a904529dccbe392793d0d108335b623bb1ed8b2
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742551"
---
# <a name="requests-for-quotation-rfqs"></a>Solicitudes de presupuesto

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general de solicitudes de presupuesto. Las organizaciones emiten solicitudes de presupuesto cuando desean recibir ofertas competitivas de varios proveedores para artículos o servicios que deben comprar. En una solicitud de presupuesto, se les pide a los proveedores que proporcionen precios y plazos de entrega para las cantidades de artículos especificadas.
También puede solicitar que especifiquen si hay algunos gastos adicionales, como gastos de envío, o si el proveedor ofrece descuentos para pedidos cuantiosos o por pronto pago de la factura de proveedor.

El proceso de solicitud de presupuesto consta de las siguientes tareas:

1.  La creación y el envío de una solicitud de presupuesto a uno o más proveedores.

2.  Recibir y registrar ofertas (respuestas a solicitudes de presupuesto).

3.  Transferir propuestas aceptadas a un pedido de compra, un acuerdo de compra o una solicitud de compra.

La ilustración siguiente muestra una visión general del proceso de solicitud de presupuesto.

[![Proceso RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Puede crear un caso de solicitud de presupuesto desde pedidos planificados, desde una solicitud de compra o mediante una entrada manual. El caso de solicitud de presupuesto es el documento base que se usa para enviar una solicitud de presupuesto a cada proveedor.+

Tras preparar el caso de solicitud de presupuesto y agregar proveedores, seleccione **Enviar** (**Registrar y publicar** para el sector público) en el caso de solicitud de presupuesto. Se crea un diario de solicitud de presupuesto para cada proveedor al que se envía una solicitud de presupuesto. Puede configurar las Opciones de impresión para la acción de envío para imprimir un informe para cada proveedor en un archivo o enviar un informe a la dirección de correo electrónico de cada proveedor. Además, el diario de solicitud de presupuesto para cada proveedor se puede usar para generar un informe que se puede enviar o volver a enviar al proveedor más adelante. También puede configurar la acción de envío para generar una hoja de respuesta que el proveedor pueda completar.

Este tema cubre el proceso para gestionar solicitudes de presupuesto cuando la colaboración del proveedor no se utiliza. Si el sistema está configurado para la colaboración del proveedor, los proveedores pueden especificar propuestas directamente en Microsoft Dynamics 365 for Finance and Operations. Para obtener más inofrmación, consulte [Colaboración de proveedor con los clientes](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) y [Colaboración de proveedor con proveedores externos](vendor-collaboration-work-external-vendors.md).

Si debe enmendar una solicitud de presupuesto después de enviarla, puede volver a enviar la solicitud de presupuesto a los proveedores cuando haya terminado mediante los dos acciones de modificación: Crear y finalizar.+

Cuando reciba ofertas por correo electrónico, puede gestionarlas en la página **Solicitud de presupuestos**.

Si se requiere una segunda iteración de una respuesta de un proveedor, seleccione **Devolver** en la página **Solicitud de presupuesto**. La acción de devolución genera un diario nuevo y un informe que se imprimirá, archivará y enviará según la configuración de impresión.

> [!NOTE]
> Se ha cambiado el nombre de la página **Solicitud de presupuesto**. En versiones anteriores de Dynamics 365 for Finance and Operations, esta página se llamaba **Respuesta a solicitud de presupuestos**.

Si ha agregado criterios de puntuación a su caso de solicitud de presupuesto, la solicitud de presupuesto tendrá un panel de puntuación donde podrá especificar las puntuaciones. Las puntuaciones totales aparecerán en la solicitud de presupuesto y al comparar las respuestas en la página **Comparar respuestas** . En la página **Comparar respuestas**, también puede comparar otros datos de la respuesta, como el precio de la línea, la fecha de entrega y el precio total.

Tras elegir una oferta o un número de líneas en una oferta, puede aceptar todas o algunas líneas y rechazar el resto. Los diarios de aceptación, diarios de rechazo y los informes correspondientes se generarán, imprimirán, archivarán y enviarán según la configuración de impresión. Al aceptar una propuesta o líneas específicas de una propuesta, se genera un acuerdo de compra o un pedido de compra, o se actualiza una solicitud de compra, en función del tipo de compra de la solicitud de presupuesto. Puede crear un acuerdo comercial que podrá usar más adelante para cualquier respuesta, independientemente de si las acepta o las rechaza.

Un caso de solicitud de presupuesto tiene dos estados: el más bajo y el más alto, puede ver el estado en la página de lista para **Todas las solicitudes de presupuesto**. El estado más bajo es la fase menos avanzada de cualquier línea del caso de solicitud de presupuesto, y el estado más alto, la fase más avanzada. Por ejemplo, digamos que un caso de solicitud de presupuesto con tres líneas se envía a dos proveedores, por lo tanto hay dos solicitudes de presupuesto, cada una con tres líneas. Todas las líneas son **Enviado**. Ahora se introduce una oferta de uno de los proveedores y líneas de la solicitud de presupuesto obtienen el estado **Recibido**. Esto significa que fuera de las tres líneas del caso de solicitud de presupuesto, todas son **Enviado** para una solicitud de presupuesto y **Recibido** para otra solicitud de presupuesto. El estado más bajo será **Enviado** y el estado más alto es **Recibido.**

Estos estados se describirán más detalladamente más adelante en este tema.

## <a name="setting-up-rfq-functionality"></a>Configuración de la funcionalidad de solicitud de presupuesto

Antes de poder crear un caso de solicitud de presupuesto, debe configurar la información de la solicitud de presupuesto en la página **Parámetros de adquisición y abastecimiento**. Cuando se crea un caso de solicitud de presupuesto, puede especificar los valores predeterminados que se copian a la solicitud de presupuesto. Puede especificar los siguientes valores predeterminados:

-   El tipo de compra de nuevas solicitudes de presupuesto: **Pedido de compra** o **Acuerdo de compra**.

-   La fecha de vencimiento y la compensación de tiempo desde el día en que se crea el caso de solicitud de presupuesto

-   Tipo de solicitud, que puede establecer de manera predeterminada un método de puntuación específico para el caso de solicitud de presupuesto

-   La información de entrega y las condiciones de pago

-   Los campos que se deben incluir en la oferta

Puede anular estos valores para un caso de solicitud de presupuesto específico.

También debe configurar el proceso de modificación. Como parte de esta configuración, puede habilitar el bloqueo de campos. Cuando está habilitado el bloqueo de campos, el profesional de compras que desee modificar una solicitud de presupuesto debe seleccionar primero **Crear** en la sección **Enmienda** de la pestaña **Presupuesto** en el caso de solicitud de presupuesto. A continuación, cuando el caso de solicitud de presupuesto se haya actualizado con la modificación, el profesional de compras debe completar el proceso seleccionando **Finalizar**. La acción Finalizar genera un mensaje de correo electrónico que notifica a los proveedores la modificación de la solicitud de presupuesto.

En la página **Parámetros de adquisición y abastecimiento**, seleccione la plantilla para usar en la notificación de correo electrónico que se envía a los proveedores. Cuando se crea una plantilla en **Plantillas de correo electrónico**, puede contener los tokens de sustitución siguientes:

-   %Caso de solicitud de presupuesto%

-   %Motivo para devolver la propuesta%

-   %Motivo de la enmienda%

-   %Enmienda preparada por%

-   %Empresa%

-   %Nombre del caso de solicitud de presupuesto%

-   %Hora y fecha de caducidad%

-   %Fecha%

Los tokens %Motivo para devolver la propuesta% y %Motivo de la enmienda% se sustituirán por el texto que el profesional de compras especifique al completar la modificación en el asistente de **Enmienda**. Los valores de los tokens %Enmienda preparada por% y %Empresa% se toman automáticamente de la solicitud de presupuesto. El token %Fecha% se reemplaza por la fecha actual.

Si desea cancelar una solicitud de presupuesto una vez que se haya enviado, puede hacerlo desde el caso de solicitud de presupuesto. Para cancelar una plantilla de correo electrónico es necesario enviar la notificación de cancelación a las personas de contacto del proveedor. La plantilla se debe seleccionar en la página **Parámetros de la adquisición y abastecimiento**. Cuando se crea la plantilla, puede contener los tokens de sustitución siguientes:

-   %Motivo de la cancelación%

-   %Caso de solicitud de presupuesto%

-   %Solicitud de presupuesto cancelada por%

-   %Empresa%

-   %Nombre del caso de solicitud de presupuesto%

-   %Fecha%

El token de %Motivo de la cancelación% se sustituye por el texto que el profesional de compras especifique en el asistente de **Cancelación**. El token %Fecha% se reemplaza por la fecha actual.

Si desea usar códigos de motivo en una oferta para indicar por qué se ha rechazado o aceptado, debe configurar códigos de motivo en la página **Motivos de proveedor**.

En la página **Configuración de formulario**, en Adquisición y abastecimiento, puede configurar el aspecto de los documentos de solicitud de presupuesto impresos o almacenados.

> [!NOTE]
> Para una configuración del sector público, debe utilizar el proceso de modificación para modificar una solicitud de presupuesto que ya se ha enviado. Cuando se envía una solicitud de presupuesto, los campos están bloqueados.
Por lo tanto, para realizar cambios en la solicitud de presupuesto, debe seleccionar **Crear** para iniciar el proceso de modificación, según lo descrito anteriormente. El comportamiento del bloqueo se controla mediante la opción **Bloquear solicitud de presupuesto cuando se envía** en la página **Parámetros de adquisición y abastecimiento**. De forma predeterminada, este parámetro se establece en **Sí** y, para una configuración del sector público, este valor predeterminado no se puede cambiar. Por lo tanto, aunque el proceso de la modificación se puede gestionar manualmente en una configuración de sector no público, se debe usar para una configuración sector público.

Al crear un caso de solicitud de presupuesto del tipo Pedido de compra y agregar un artículo de inventario a la solicitud de presupuesto, se genera una transacción de inventario con el estado de recepción **Recepción de presupuesto**. Solo las líneas del caso de solicitud de presupuesto con este estado se tienen en cuenta al usar un plan maestro para calcular suministros. Si desea que el plan maestro incluya líneas del caso de solicitud de presupuesto como recepción prevista, debe configurar este comportamiento en la configuración de planificación maestra.

Un agente o responsable de compras, puede crear y mantener tipos de solicitud que se adapten a los requisitos de compras de su organización. Cada tipo de la solicitud se puede asociar a un método de puntuación. Los métodos de puntuación consisten en un conjunto de criterios que se pueden usar al puntuar propuestas. Debe configurar tipos de solicitud, métodos de puntuación y criterios de puntuación en las páginas **Tipo de solicitud** y **Método de puntuación**.

## <a name="creating-and-sending-an-rfq"></a>Creación y envío de una solicitud de presupuesto

Cree un caso de solicitud de presupuesto, seleccione los proveedores que desee que hagan una oferta a dicho caso de solicitud y envíesela. Puede usar la configuración de impresión para dirigir los informes de solicitud de presupuesto y hojas de respuesta a su destino preferido.

Puede crear manualmente un caos de solicitud de presupuesto para el tipo de compra **Pedido de compra** o **Acuerdo de compra**.

Si el caso de solicitud de presupuesto es del tipo **Pedido de compra**, se produce el siguiente comportamiento que se desvía de otros tipos de casos de solicitud de presupuesto:

-   Cuando se crean líneas de un caso de solicitud de presupuesto, se generan transacciones de inventario con estado de recepción **Recepción de presupuesto**.

-   Al aceptar una propuesta, se genera un pedido de compra.

Si la solicitud de presupuesto es del tipo **Acuerdo de compra**, se produce el siguiente comportamiento que se desvía de los otros casos de solicitud de presupuesto:

-   El caso de solicitud de presupuesto se usa para un contrato para comprar una cantidad o valor de producto específicos en el tiempo. Debe seleccionar el intervalo de fechas que se aplica al acuerdo de compra y el nombre de la persona que gestiona el acuerdo de compra.

-   Al aceptar una propuesta, se genera un acuerdo de compra.

Si se genera el caso de solicitud de presupuesto desde una solicitud de compra, se asigna automáticamente el tipo **Solicitud de compra**. No puede crear manualmente un caso de solicitud de presupuesto del tipo **Solicitud de compra**.

Puede crear un caso de solicitud de presupuesto a partir de una solicitud de compra solo si el estado de la solicitud de compra es **En revisión** y le han asignado la realización de la siguiente tarea de flujo de trabajo. Las líneas de la solicitud de compra se actualizan automáticamente al aceptar líneas de las ofertas (repuestas a solicitudes de presupuesto) que recibe de los proveedores. No se puede completar, rechazar, aprobar o realizar ninguna otra acción en la solicitud de compra hasta que se actualice la línea de solicitud con una línea de solicitud de presupuesto aceptada o se cancele el caso de solicitud de presupuesto.

Cuando crea un caso de solicitud de presupuesto, puede seleccionar un tipo de solicitud. El tipo de la solicitud determina el conjunto de criterios de puntuación que se usan para puntuar las respuestas a la solicitud de presupuesto para el caso de solicitud de presupuesto.

Puede agregar un cuestionario a un caso de solicitud de presupuesto. Este cuestionario aparece después en todas las respuestas a la solicitud de presupuesto después de enviar la solicitud de presupuesto. La finalización del cuestionario es una tarea obligatoria antes de que se pueda enviar la oferta.


Hay tres maneras de seleccionar a los proveedores que agregar a un caso de solicitud de presupuesto:

- Agregar a los proveedores de uno en uno.
- Buscar a todos los proveedores que cumplan con criterios específicos.
- Agregar automáticamente a todos los proveedores aprobados para las categorías de compras que se usan en las líneas del caso de solicitud de presupuesto.

Cuando el caso de solicitud de presupuesto esté listo, seleccione **Enviar**. La acción de envío genera diarios e informes que se imprimirán, archivarán y enviarán según la configuración de impresión.

Si ha establecido **Usar proveedor para volver a calcular los precios** y **Usar información de artículo específico del proveedor** en **Sí** en la página **Enviar solicitud de presupuesto**, cuando envíe la solicitud de presupuesto a un proveedores, se introducirá automáticamente cierta información específica del proveedor en la solicitud de presupuesto para ese proveedor.


## <a name="amending-an-rfq-case"></a>Modificación de un caso de solicitud de presupuesto

En ocasiones deberá cambiar un caso de solicitud de presupuesto tras haberlo enviado. Podría tener que cambiar un caso de solicitud de presupuesto si, por ejemplo, las fechas de entrega han cambiado, desee productos adicionales o diferentes cantidades de productos. Puede configurar el proceso de modificación de modo que sea más o menos restrictivo.

Si el configura el proceso de modificación de modo que sea más restrictivo, antes de poder modificar los campos de un caso de solicitud de presupuesto que ya se haya enviado, debe seleccionar **Crear** en el caso de solicitud de presupuesto para iniciar una modificación. Una vez que haya terminado de realizar cambios, debe seleccionar **Finalizar**. A continuación se le guiará por el proceso para agregar información para el mensaje de correo electrónico que se envía para notificar sobre la modificación a los proveedores. El informe de la solicitud de presupuesto actualizado, que incluye una nota de enmienda, se vincula automáticamente al mensaje de correo electrónico.

Si configura el proceso de modificación para que sea menos restrictivo, no tiene que seleccionar **Crear** antes de poder modificar los campos de un caso de solicitud de presupuesto que se haya enviado ya. No obstante, debe agregar manualmente una nota de enmienda a la solicitud de presupuesto y enviar el caso de nuevo. Tenga en cuenta que este enfoque solo se puede utilizar si no se ha editado ninguna de las respuestas (propuestas). Si ha especificado una respuesta y se encuentra en estado **Recibido**, el botón **Enviar** no está disponible. En este caso, debe seleccionar **Crear** y luego **Finalizar**, como debe hacer en el proceso más restrictivo. La respuesta se restablece para reflejar los cambios al caso de solicitud de presupuesto.

Si los proveedores utilizan la interfaz de colaboración del proveedor para especificar propuestas, debe usar siempre el proceso de modificación para notificar a los proveedores sobre cambios al caso de solicitud de presupuesto. Este proceso ayuda a evitar la situación en la que los proveedores hagan una oferta de un caso de solicitud de presupuesto obsoleto mientras que la oferta está en curso. Para obtener más información acerca de la colaboración de proveedores, consulte [Colaboración con proveedores externos](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Si desea para invitar a proveedores adicionales para hacer una propuesta y no ha realizado ningún cambio en el caso de solicitud de presupuesto, puede usar el botón **Enviar**. Los proveedores que se han agregado aparecerán en la página **Enviar** y recibirán el correo electrónico de invitación.


## <a name="receiving-and-registering-rfq-replies"></a>Recepción y registro de respuestas a solicitudes de presupuesto

Cuando se envía una solicitud de presupuesto, se genera una hoja de respuesta automáticamente. A medida que reciba ofertas en una solicitud de presupuesto, debe incorporarlas mediante la página **Solicitud de presupuesto** haciendo clic en la acción **Editar respuesat a solicitud de presupuesto.** Esto le permitirá introducir la información de la oferta en un formulario de oferta dedicado. Inicialmente, el **Progreso de la respuesta** será **No iniciado**. Cuando haga clic en **Editar respuesta a solicitud de presupuesto,** el estado de progreso es **El comprador está realizando una actualización** hasta que se envíe la oferta. Haga clic en **Enviar** cuando haya introducido la información de la oferta. El estado Progreso de la respuesta cambiará a **Envío realizado por el comprador.** De forma similar, con la colaboración del proveedor habilitada, el **Progreso de la respuesta** se actualizará cuando el proveedor interactúe con la oferta. A continuación, el estado cambia de **El proveedor está realizando una actualización** a **Envío realizado por el proveedor**. Cuando se envía la oferta, se crea un diario como **Recibido**. La respuesta (oferta) tiene que enviarse para registrarse como recibida, y luego solamente se podrá procesar como aceptada o rechazada.

Si necesita actualizar la oferta, debe pasar por el mismo proceso que antes y enviarla de nuevo.

Tenga en cuenta que editar el formulario **Solicitud de presupuesto** solo se permite para información relacionada con el procesamiento de la oferta, no para introducir la oferta. Para introducir o modificar la oferta, haga clic en **Editar respuesta a solicitud de presupuesto.**

Al introducir la información de la oferta, y si el caso de solicitud de presupuesto permite líneas alternativas, puede agregar líneas alternativas para las líneas que tengan solo una categoría de compras y ningún artículo de catálogo especificado. Haga clic en **Agregar alternativa** para agregar líneas alternativas.

Si ha especificado una respuesta pero requiere una nueva propuesta del proveedor, puede devolver la solicitud de presupuesto. Se generan un nuevo diario y un informe, que se pueden enviar al proveedor.

Puede ver una descripción de todas las solicitudes de presupuesto y sus estado: **Enviado, Recibido, Aceptado, Rechazado, Cancelado, Denegado** en la página **Seguimiento de solicitud de presupuesto**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Aceptación y rechazo de propuestas y transferencia de propuestas aceptadas a documentos descendentes

Una vez identificada la mejor propuesta, como la que ofrece el mejor precio total, acepta la propuesta. Puede aceptar algunas líneas en una propuesta y rechazar otras.
También puede aceptar líneas de diferentes proveedores. Tenga en cuenta que, si acepta algunas líneas, se le pedirá que rechace el resto de líneas. Por lo tanto, si desea aceptar otras líneas, debe seleccionar **Cancelar** cuando reciba el mensaje. El estado de la respuesta a la solicitud de presupuesto para cada proveedor que acepta propuestas o las líneas se actualiza a **Aceptado**.

Si, mientras prepara el pedido de compra o el acuerdo de compra, necesita agregar una línea adicional a la solicitud de presupuesto, puede hacerlo haciendo click en **Agregar línea** en la cuadrícula de la línea de la página **Solicitud de presupuesto** . Solo puede ver y editar esta línea en la página **Solicitud de presupuesto**. Será visible en la página de la oferta cuando se acepte.

Al aceptar una oferta o una o más líneas en una oferta, se genera automáticamente un pedido de compra o un acuerdo de compra. A continuación puede rechazar las propuestas de todos los otros proveedores.

En la respuesta puede agregar un código de motivo para explicar por qué se aceptó o rechazó una propuesta.

Cuando se acepta una oferta del tipo **Solicitud de compra**, las líneas de la solicitud de compra se actualizarán con la siguiente información que refleja la información de la propuesta aceptada:

-   Precio unitario

-   Porcentaje de descuento

-   Importe de descuento

-   Gastos de compra

-   Gastos de línea

-   Proveedor

-  Número externo

-   Descripción externa


La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto a medida que se aceptan y rechazan propuestas de los proveedores.

<a name="statuses--highest-and-lowest"></a>Estados: más alto y más bajo
-----------------------------

En la pestaña Proveedor del caso de solicitud de presupuesto, puede ver las líneas con el estado más alto y más bajo para un proveedor concreto. Cuando agregue el proveedor, y aún no se hayan enviado líneas, el estado más bajo y el más alto es <strong>Creado.</strong>Cuando la solicitud de presupuesto se envíe al proveedor con todas las líneas, el estado de las dos líneas será <strong>Enviado</strong>. Si se aceptan algunas líneas en una oferta de un proveedor y se rechazan otras, las líneas rechazadas obtendrán el estado más bajo, que es <strong>Rechazado</strong>, y las líneas aceptadas obtendrán el estado más alto, que es <strong>Aceptado</strong>.

En las líneas del caso de solicitud de presupuesto, puede ver el estado más alto y el más bajo por línea en todos los proveedores. Si ha enviado una línea a todos los proveedores en el caso de solicitud de presupuesto y nadie ha respondido aún, el estado más bajo y más alto es **Enviado.** Cuando responde al menos un proveedor, el estado más alto cambiará a **Recibido**. Si agrega un nuevo proveedor al caso, el estado más bajo cambiará **Creado**

El estado más alto y más bajo en el caso de solicitud de presupuesto es una agregación del estado en la pestaña \<Proveedor y la pestaña Líneas.

Los estados se clasifican de la siguiente manera del más bajo al más alto: Creado, Enviado, Recibido, Rechazado, Aceptado, Denegado, Cancelado.

La tabla siguiente muestra cómo cambia el estado del caso solicitud de presupuesto al crear un caso de solicitud de presupuesto con líneas y luego enviarlo a los proveedores.

| **Acción**                                | **Estado del caso de solicitud de presupuesto más bajo** | **Estado del caso de solicitud de presupuesto más alto** | **Estado de la línea del caso de solicitud de presupuesto más bajo** | **Estado de la línea del caso de solicitud de presupuesto más alto** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Cree el encabezado y la línea del caso de solicitud de presupuesto.      | Creada                    | Creada                     | Creada                         | Creada                          |
| Envíe solicitudes de presupuesto a todos los proveedores en el caso de solicitud de presupuesto. | Enviada                       | Enviada                        | Enviada                            | Enviada                             |
| Agregue a otro proveedor.                       | Creada                    | Enviada                        | Creada                         | Enviada                             |
| Enviar la solicitud de presupuesto al segundo proveedor.        | Enviada                       | Enviada                        | Enviada                            | Enviada                             |

Todas las líneas de la solicitud de presupuesto relacionadas con el caso de solicitud de presupuesto estarán en el estado **Enviado** .

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto a medida que recibe propuestas y registra la información en la hoja de respuesta a la solicitud de presupuesto.

| **Acción**                                               | **Estado más bajo en todas las líneas de todas las solicitudes de presupuesto** | **Estado más alto en todas las líneas de todas las solicitudes de presupuesto** | **Estado del encabezado del caso de solicitud de presupuesto más bajo** | **Estado del encabezado del caso de solicitud de presupuesto más alto** | **Estado de la línea del caso de solicitud de presupuesto más bajo** | **Estado de la línea del caso de solicitud de presupuesto más alto** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Registre una oferta de proveedor para una solicitud de presupuesto y guárdela.        | Enviada                                           | Recibida                                        | Enviada                              | Recibida                           | Enviada                            | Recibida                         |
| Registre una segunda oferta de proveedor para una solicitud de presupuesto y guárdela. | Recibida                                       | Recibida                                        | Recibida                          | Recibida                           | Recibida                        | Recibida                         |


En el siguiente ejemplo puede ver el estado más alto y el estado más bajo en el caso de solicitud de presupuesto en el que se ha recibido una oferta y se ha aceptado la otra oferta. Si se rechaza una oferta recibida, el estado más bajo cambiará de recibido a rechazado en el encabezado y la línea del caso de solicitud de presupuesto.


|            <strong>Acción</strong>             | <strong>Estado más bajo en todas las líneas de todas las solicitudes de presupuesto</strong> | <strong>Estado más alto en todas las líneas de todas las solicitudes de presupuesto</strong> | <strong>Estado del encabezado del caso de solicitud de presupuesto más bajo</strong> | <strong>Estado del encabezado del caso de solicitud de presupuesto más alto</strong> | <strong>Estado de la línea del caso de solicitud de presupuesto más bajo</strong> | <strong>Estado de la línea del caso de solicitud de presupuesto más alto</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Acepte una de las ofertas. (o al menos una línea) |                          Recibida                           |                           Aceptada                           |                    Recibida                    |                    Aceptada                     |                   Recibida                   |                   Aceptada                    |
|           Rechazar todas las otras propuestas.           |                          Rechazado                           |                           Aceptada                           |                    Rechazado                    |                    Aceptada                     |                   Rechazado                   |                   Aceptado                    |

