---
title: Solicitud de presupuestos
description: "Este artículo proporciona información general de solicitudes de presupuesto, que las organizaciones emiten cuando deben comprar artículos o servicios y desean recibir ofertas competitivas de varios proveedores. En una solicitud de presupuesto, se les pide a los proveedores que proporcionen precios y plazos de entrega para las cantidades de artículos especificadas. También puede solicitar que especifiquen si hay algunos gastos adicionales, como gastos de envío, o si el proveedor ofrece descuentos para pedidos cuantiosos o por pronto pago de la factura de proveedor."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d681f4c107a9dbc1ea8c5e1de38b2d45cf19bcfa
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="request-for-quotations-rfqs"></a>Solicitud de presupuestos

[!include[banner](../includes/banner.md)]


Este artículo proporciona información general de solicitudes de presupuesto, que las organizaciones emiten cuando deben comprar artículos o servicios y desean recibir ofertas competitivas de varios proveedores. En una solicitud de presupuesto, se les pide a los proveedores que proporcionen precios y plazos de entrega para las cantidades de artículos especificadas. También puede solicitar que especifiquen si hay algunos gastos adicionales, como gastos de envío, o si el proveedor ofrece descuentos para pedidos cuantiosos o por pronto pago de la factura de proveedor.

El proceso de solicitud de presupuesto cubre las tareas siguientes:

-   Crear y enviar una solicitud de presupuesto a uno o más proveedores.
-   Recibir y registrar respuestas a dichas solicitudes (propuestas).
-   Transferir propuestas aceptadas a un pedido de compra, un acuerdo de compra o una solicitud de compra.

La ilustración siguiente muestra una visión general del proceso de solicitud de presupuesto.  

[![Proceso de solicitud de presupuesto](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)  

Puede crear una solicitud de presupuesto desde pedidos planificados, desde una solicitud de compra o desde una entrada manual. La solicitud de presupuesto que crea se denomina un caso de solicitud de presupuesto, y se trata del documento base que se usa para emitir una solicitud de presupuesto a cada proveedor. Tras preparar el caso de solicitud de presupuesto y agregar proveedores, haga clic en **Enviar** en el caso de solicitud de presupuesto; se genera un diario de solicitud de presupuesto para cada proveedor al que envíe la solicitud de presupuesto. Puede configurar los parámetros de gestión de impresión para la acción de envío para imprimir un informe para cada proveedor en un archivo o enviar un informe a la dirección de correo electrónico de cada proveedor. Además, el diario de solicitud de presupuesto por cada proveedor se puede usar para generar un informe que se puede enviar o volver a enviar a un proveedor más adelante. También puede configurar la acción de envío para generar una hoja de respuesta que el proveedor pueda completar.  

Si debe modificar una solicitud de presupuesto después de haberla enviado, puede volver a enviar la solicitud de presupuesto a los proveedores cuando haya terminado.  

Cuando reciba propuestas, debe incorporarlas en la página **Respuestas de solicitudes de presupuesto**. Si selecciona la opción **Copiar datos en respuesta**, los datos como la cantidad y las fechas del caso de solicitud de presupuesto se copian en la respuesta. Puede cambiar estos datos para reflejar la propuesta del proveedor.  

Si se requiere una segunda iteración de una respuesta para un proveedor concreto, haga clic en **Devolución**en la página**Respuesta a solicitud de presupuesto**. La acción de devolución genera un diario nuevo y un informe que se imprimirá, archivará y enviará según la configuración de la gestión de impresión.  

Si ha agregado criterios de puntuación a su caso de solicitud de presupuesto, la respuesta a la solicitud de presupuesto tendrá un panel de puntuación donde podrá especificar las puntuaciones. Las puntuaciones totales aparecerán al comparar las respuestas en la página **Comparar respuestas,**donde también puede comparar otros datos de respuesta, como el precio de línea, la fecha de entrega y el precio total.  

Después de tomar una decisión sobre una propuesta o propuestas parciales, puede aceptarlas y rechazar el resto. Se generan los diarios de aceptación, los diarios de rechazo y los informes correspondientes. Estos se imprimirán, archivarán y enviarán según la configuración de gestión de impresión. Al aceptar una propuesta o líneas específicas de una propuesta, se genera un acuerdo de compra o el pedido de compra, o se actualiza una solicitud de compra, en función del tipo de compra de la solicitud de presupuesto. Puede crear un acuerdo comercial que podrá usar más adelante para cualquier respuesta, independientemente de si las acepta o las rechaza.  

El estado de una solicitud de presupuesto en el encabezado de la solicitud depende de los estados de las líneas de la solicitud de presupuesto. El estado indica hasta qué punto se ha procesado dicha solicitud. Cada solicitud de presupuesto tiene dos valores para el estado: el más bajo y el más alto. El estado más bajo es la fase menos avanzada de cualquier línea de solicitud de presupuesto, y el estado más alto, la fase más avanzada. Por ejemplo, si la fase menos avanzada de una solicitud de presupuesto es para una línea que se ha creado, el estado más bajo de la solicitud de presupuesto es **Creado**. Si la fase más avanzada de la solicitud de presupuesto es para una línea que se ha enviado a proveedores, el estado más alto de la solicitud de presupuesto es **Enviado**. Los estados se actualizan automáticamente mientras se procesa la solicitud de presupuesto.  

Puede ver los estados más altos y más bajos de un encabezado de solicitud de presupuesto en la página **Todas las solicitudes de presupuesto**. Puede ver los estados más altos y más bajos de una línea de solicitud de presupuesto en la ficha **Líneas** de la página **Solicitud de presupuestos**.  

Esta es la secuencia de estados para el procesamiento de una solicitud de presupuesto:

1.  **Creado**
2.  **Enviado**
3.  **Recibido**
4.  **Aceptada**/**Cancelada**/**Rechazada**

Los estados se describirán más detalladamente en secciones posteriores de este artículo.

## <a name="setting-up-rfq-functionality"></a>Configuración de la funcionalidad de solicitud de presupuesto
Antes de poder crear un caso de solicitud de presupuesto, debe configurar la información de la solicitud de presupuesto en la página **Parámetros de adquisición y abastecimiento**. Cuando se crea un caso de solicitud de presupuesto, puede especificar los valores predeterminados que se copian a la solicitud de presupuesto. Puede especificar los siguientes valores predeterminados:

-   El tipo de compra de nuevas solicitudes de presupuesto: **Pedido de compra** o **Acuerdo de compra**.
-   Los ajustes de fecha y hora de vencimiento.
-   La información de entrega y las condiciones de pago.
-   Los campos que se deben incluir en la respuesta a la solicitud de presupuesto.

Puede anular estos valores para un caso de solicitud de presupuesto específico. También debe configurar el proceso de modificación. Como parte de esta configuración, puede habilitar el bloqueo de campos. Cuando está habilitado el bloqueo de campos, el profesional de compras que desee modificar una solicitud de presupuesto debe primer lugar hacer clic en **Crear** en la sección **Enmienda** de la ficha **Presupuesto**. Después de que la solicitud de presupuesto se haya actualizado con la modificación, el profesional de compras debe terminar el proceso haciendo clic en **Finalizar**. La acción de finalización genera un mensaje de correo electrónico que notifica a los proveedores la modificación de la solicitud de presupuesto. La plantilla de la notificación por correo electrónico que se envía a los proveedores se selecciona en la página **Parámetros de adquisición y abastecimiento**. Cuando se crea una plantilla, puede contener los tokens de sustitución siguientes:

-   %Motivo para devolver la propuesta%
-   %Motivo de la enmienda%
-   %Enmienda preparada por%
-   %Empresa%

Los tokens %Motivo para devolver la propuesta% y %Motivo de la enmienda% se sustituirán por el texto que el profesional de compras especifique al completar la modificación en el asistente de **Enmienda**. Los valores de los tokens %Enmienda preparada por% y %Empresa% se toman automáticamente de la solicitud de presupuesto.  

Si desea usar códigos de motivo en una respuesta a una solicitud de presupuesto para indicar por qué se ha rechazado o aceptado, debe configurar códigos de motivo en la página **Motivos de proveedor**.  

Puede configurar el aspecto de los documentos de solicitud de presupuesto impresos o almacenados en la página **Configuración de formulario**, en Adquisición y abastecimiento.  

Al crear una solicitud de presupuesto para un pedido de compra y agregar un artículo de inventario a la solicitud de presupuesto, se genera una transacción de inventario con el estado de recepción **Recepción de presupuesto**. Solo las líneas de la solicitud de presupuesto con este estado se tienen en cuenta al usar un plan maestro para calcular suministros. Si desea que el plan maestro incluya líneas de solicitud de presupuesto como recepción prevista, debe configurar este comportamiento en la configuración de planificación maestra.  

Como agente o director de compras, puede crear y mantener tipos de solicitud que se adecuen con los requisitos de compras de su organización. Cada tipo de solicitud puede llevar métodos de puntuación. Los métodos de puntuación consisten en un conjunto de criterios que se pueden usar al puntuar propuestas. Debe configurar tipos de solicitud, métodos de puntuación y criterios de puntuación en las páginas **Tipo de solicitud** y **Método de puntuación**.

## <a name="creating-and-sending-an-rfq"></a>Creación y envío de una solicitud de presupuesto
Cree la solicitud de presupuesto, seleccione los proveedores que desee que hagan una propuesta a dicha solicitud y envíesela. Puede usar la gestión de impresión para dirigir los informes de solicitud de presupuesto y hoja de respuesta a su destino preferido.  

Puede crear una solicitud de presupuesto para el tipo de compra **Pedido de compra** o **Acuerdo de compra**.  

Si se genera la solicitud de presupuesto desde una solicitud de compra, se asigna automáticamente el tipo **Solicitud de compra**. No puede crear manualmente una solicitud de presupuesto del tipo **Solicitud de compra**. Si la solicitud de presupuesto es del tipo **Pedido de compra**:

-   Cuando se crean líneas de solicitud de presupuesto, se generan transacciones de inventario con estado de recepción **Recepción de presupuesto**.
-   Al aceptar una propuesta, se genera un pedido de compra.

Si la solicitud de presupuesto es del tipo **Acuerdo de compra**:

-   La solicitud de presupuesto se usa para un contrato para comprar una cantidad o valor de producto específicos en el tiempo. Debe seleccionar el intervalo de fechas que se aplica al acuerdo de compra y el nombre de la persona que gestiona el acuerdo de compra.
-   Al aceptar una propuesta, se genera un acuerdo de compra.

Puede crear una solicitud de presupuesto a partir de una solicitud de compra solo si el estado de la solicitud de compra es **En revisión**y le han asignado para realizar la tarea siguiente del flujo de trabajo. Las líneas de la solicitud de compra se actualizan automáticamente al aceptar líneas de las respuestas a solicitudes de presupuesto (propuestas) que recibe de los proveedores. No puede completar, rechazar, aprobar ni realizar ninguna otra acción en la solicitud de compra mientras se esté procesando la solicitud de presupuesto.  

Cuando se crea una solicitud de presupuesto, puede seleccionar un tipo específico de solicitud. El tipo de la solicitud determina el conjunto de criterios de puntuación que se usan para puntuar las respuestas a la solicitud de presupuesto.  

Puede agregar un cuestionario a un caso de solicitud de presupuesto. Este cuestionario aparece después en todas las respuestas después de enviar la solicitud de presupuesto.  

Hay tres maneras de seleccionar a los proveedores que agregar a un caso de solicitud de presupuesto:

-   Agregar a los proveedores de uno en uno.
-   Buscar a todos los proveedores que cumplan con criterios específicos.
-   Agregar automáticamente a todos los proveedores aprobados para las categorías de compras que se usan en las líneas de la solicitud de presupuesto.

Cuando el caso de solicitud de presupuesto esté listo, haga clic en **Enviar**. La acción de envío genera diarios e informes que se imprimirán, archivarán y enviarán según la configuración de la gestión de impresión.  

Si ha seleccionado las casillas y **Usar proveedor para volver a calcular los precios** y **Usar información de artículo específico del proveedor** en la página **Enviando solicitud de presupuesto**, cuando envíe la solicitud a los proveedores, se introduce automáticamente cierta información específica del proveedor. Puede modificar esta información en la página **Respuesta a solicitud de presupuesto**.  

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto al crear una solicitud de presupuesto y enviarla a los proveedores.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Acción**                         | **Estado más bajo del encabezado de la solicitud de presupuesto** | **Estado más alto del encabezado de la solicitud de presupuesto**                   | **Estado más bajo de la línea de la solicitud de presupuesto** | **Estado más alto de la línea de solicitud de presupuesto** |
| Crear la línea y el encabezado de RFQ.    | Creado                      | Creado                                         | Creado                    | Creado                     |
| Envíe la solicitud de presupuesto a un proveedor específico. | Enviado                         | Enviado                                            | Enviado                       | Enviado                        |
| Agregue a otro proveedor.                | Creado                      | Enviado (la solicitud de presupuesto se ha enviado solo a un proveedor.) | Creado                    | Enviado                        |
| Enviar la solicitud de presupuesto al segundo proveedor. | Enviado                         | Enviado                                            | Enviado                       | Enviado                        |

**Nota**: puede agregar más proveedores a una solicitud de presupuesto en cualquier momento, y los estados más altos y más bajos cambiarán para reflejar los nuevos proveedores. Por ejemplo, si recibió propuestas de todos los proveedores y aceptó al menos una línea en una propuesta, el estado más bajo del encabezado de la solicitud es **Rechazado** y el estado más alto es **Aceptado**. Si agrega un nuevo proveedor, el estado más bajo de cualquier línea es ahora **Creado**. Por lo tanto, el estado más bajo del encabezado de la solicitud de presupuesto cambia a **Creado** y el más alto permanece en **Aceptado**.

## <a name="amending-an-rfq"></a>Modificación de una solicitud de presupuesto
En ocasiones deberá cambiar una solicitud de presupuesto tras haberla enviado. Esto puede suceder porque, por ejemplo, las fechas de entrega hayan cambiado, o desee productos adicionales o diferentes cantidades de productos. Puede configurar el proceso de modificación de modo que sea más restrictivo o menos restrictivo.  

Si usa el proceso de modificación más restrictivo, debe hacer clic en **Crear** en el caso de solicitud de presupuesto para iniciar la modificación antes de poder modificar los campos del caso de solicitud de presupuesto. Una vez que haya terminado de realizar cambios, debe hacer clic en **Finalizar**. A continuación se le guiará por el proceso para agregar información para el mensaje de correo electrónico que se envía para notificar a los proveedores la modificación. El informe de la solicitud de presupuesto actualizado, que incluye una nota de enmienda, se vincula automáticamente al mensaje.  

Si usa el proceso de modificación menos restrictivo, no tiene que crear una modificación antes de poder modificar los campos de un caso de solicitud de presupuesto que se haya enviado ya. No obstante, debe agregar manualmente una nota de enmienda a la solicitud de presupuesto.

## <a name="receiving-and-registering-rfq-replies"></a>Recepción y registro de respuestas a solicitudes de presupuesto
Cuando se envía una solicitud de presupuesto, se genera una hoja de respuesta automáticamente. A medida que recibe respuestas a la solicitud de presupuesto (propuestas), debe especificar la información de cada proveedor en hoja de una respuesta a la solicitud de presupuesto específica para cada proveedor. Si ha agregado criterios de puntuación, puede puntuar las respuestas. Después se comparan las propuestas de los proveedores y se clasifican según sus criterios de puntuación, como el mejor precio total o el mejor plazo de entrega total.  

Si el cuestionario se vincula al caso de solicitud de presupuesto, debe especificar manualmente las respuestas a las preguntas en la hoja de respuesta.  

Si debe introducir líneas alternas, y el caso de solicitud de presupuesto lo permite, en la ficha desplegable **Líneas de presupuesto de compra**, haga clic en **Agregar línea**. A continuación, especifique la información del producto, como el número de artículo o la categoría de compra, cantidad, precio y descuento.  

Si ha especificado una respuesta pero requiere una nueva propuesta del proveedor, puede volver a enviar la solicitud de presupuesto. Esto generará un diario nuevo y el informe para solicitar cambios del proveedor.  

Puede ver una descripción de todas las solicitudes de presupuesto y sus estados de respuesta en la página **Seguimiento de solicitud de presupuesto**.  

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto a medida que recibe propuestas y registra la información de la hoja de respuesta a la solicitud de presupuesto.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Acción**                                     | **Estado más bajo de la propuesta** | **Estado más alto de la propuesta** | **Estado más bajo del encabezado de la solicitud de presupuesto** | **Estado más alto del encabezado de la solicitud de presupuesto** | **Estado más bajo de la línea de la solicitud de presupuesto** | **Estado más alto de la línea de solicitud de presupuesto** |
| Registre una oferta de proveedor y guárdela.        | Enviado                  | Recibido               | Enviado                         | Recibido                      | Enviado                       | Recibido                    |
| Registre una segunda oferta de proveedor y guárdela. | Recibido              | Recibido               | Recibido                     | Recibido                      | Recibido                   | Recibido                    |

**Nota**: si devuelve una propuesta a un proveedor para seguir negociando, los estados más bajos y más altos siguen siendo **Recibido**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Aceptación y rechazo de propuestas y transferencia de propuestas aceptadas a documentos descendentes

Una vez identificada la mejor propuesta, como la que ofrece el mejor precio total, acepta la propuesta. El estado de la respuesta a la solicitud de presupuesto del proveedor se actualizará a **Aceptado**. Al aceptar una propuesta o líneas específicas de una propuesta, se genera automáticamente un pedido de compra o un acuerdo de compra, y puede rechazar las propuestas de los otros proveedores.  

Al aceptar una respuesta a una solicitud de presupuesto con el tipo **Solicitud de compra**, las líneas de respuesta a la solicitud de presupuesto actualizan las líneas de solicitud de compra con la siguiente información:

-   Precio unitario
-   Porcentaje de descuento
-   Importe del descuento
-   Gastos de compra
-   Gastos de línea
-   Proveedor
-   Número externo
-   Descripción externa

En la respuesta puede agregar un código de motivo para explicar por qué se aceptó o rechazó una propuesta.  

Puede aceptar algunas líneas en una propuesta y rechazar otras. También puede aceptar líneas de diferentes proveedores. Solo tenga en cuenta que, si acepta algunas líneas, se le pedirá que rechace el resto de líneas. Por lo tanto, si desea aceptar otras líneas, debe hacer clic en **Cancelar** cuando reciba el mensaje.  

La tabla siguiente muestra cómo cambia el estado de la solicitud de presupuesto a medida que se aceptan y rechazan propuestas de los proveedores.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Acción**              | **Estado más bajo de la propuesta** | **Estado más alto de la propuesta** | **Estado más bajo del encabezado de la solicitud de presupuesto** | **Estado más alto del encabezado de la solicitud de presupuesto** | **Estado más bajo de la línea de la solicitud de presupuesto** | **Estado más alto de la línea de solicitud de presupuesto** |
| Acepte una de las ofertas. | Recibido              | Aceptado               | Recibido                     | Aceptado                      | Recibido                   | Aceptado                    |
| Rechazar las otras propuestas.  | Rechazadas              | Aceptado               | Rechazadas                     | Aceptado                      | Rechazadas                   | Aceptado                    |






