---
title: Visión general de la integración fiscal para canales de Commerce
description: Este tema proporciona una visión general de las capacidades fiscales de integración disponibles en Dynamics 365 Commerce.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2019-1-16
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2f1abf29058e773f1645301fcd7a960df488d92b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017476"
---
# <a name="overview-of-fiscal-integration-for-commerce-channels"></a>Visión general de la integración fiscal para canales de Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introducción

Este tema es una visión general de las capacidades fiscales de integración disponibles en Dynamics 365 Commerce. La integración fiscal incluye la integración con distintos dispositivos fiscales y servicios que habilitan el registro fiscal de la venta de acuerdo con las leyes fiscales locales que se dirijan que impiden fraude fiscal en el sector minorista. A continuación aparecen varias situaciones de ejemplo habituales que se pueden cubrir mediante inclusión de la integración fiscal:

- Registrar una venta en un dispositivo fiscal que está conectado al punto de venta (PDV), como una impresora fiscal, e imprimir un recibo fiscal para el cliente.
- Enviar la información relacionada con las ventas y las devoluciones que se completan en Retail POS a un servicio Web externa que sea operado por la autoridad fiscal de forma segura.
- Ayudar a garantizar la inalterabilidad de los datos de transacción de ventas a través de firmas digitales.

La funcionalidad fiscal de la integración de ventas es un marco que ofrece una solución común para el desarrollo y la personalización adicionales de la integración entre Retail POS y dispositivos y servicios fiscales. La funcionalidad también incluye los ejemplos fiscales de integración que admiten los escenarios básicos para los países o regiones específicos, y que funcionan con los dispositivos o servicios fiscales específicos. Un ejemplo fiscal de la integración consta de varias extensiones de componentes de Commerce y se incluye en el kit de desarrollo de software (SDK). Para obtener más información acerca de los ejemplos de integración fiscal, consulte [Ejemplos de integración fiscal en el SDK de Retail](#fiscal-integration-samples-in-the-retail-sdk). Para obtener información sobre cómo instalar y usar la ventas al por menor SDK, consulte [Kit de desarrollo de software (SDK) al por menor](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Para admitir otros escenarios que no son compatibles por un ejemplo fiscal de la integración, para integrar Retail POS con otros dispositivos o servicios fiscales, o cubrir los requisitos de otros países o regiones, debe remitir un ejemplo fiscal existente de integración o crear un nuevo ejemplo mediante un ejemplo existente como un ejemplo.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices"></a>Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos fiscales

Un proceso de registro fiscal en Retail POS puede estar formado por uno o más pasos. Cada paso implica el registro de transacciones fiscales o de eventos específicos en un dispositivo manual o servicio fiscal. Los siguientes componentes de la solución participan en el registro fiscal en un dispositivo fiscal asociado a una estación de hardware:

- **Extensión de Commerce runtime (CRT)**: este componente serializa la transacción/datos de eventos en el formato que también se usa para la interacción con el dispositivo fiscal, analiza respuestas del dispositivo fiscal, y almacena las respuestas en la base de datos del canal. La extensión también define las transacciones y los eventos específicos que deben estar registrados. Este componente suele denominarse como un *proveedor del documento fiscal*.
- **Extensión de la estación de hardware** Este componente inicializa la comunicación con el dispositivo fiscal, envía solicitudes y comandos directos al dispositivo fiscal basado en la transacción/los datos de eventos de la información del documento fiscal y recibe respuestas del dispositivo fiscal. Este componente suele denominarse como un *conector fiscal*.

Un ejemplo fiscal de integración para un dispositivo fiscal contiene el CRT y extensiones de la estación de hardware para un proveedor fiscal de documentos y conector fiscal, respectivamente. También contiene las siguientes configuraciones de componentes:

- **Configuración del proveedor fiscal del documento** La configuración define un método de salida y el formato de los documentos fiscales. También contiene una asignación de datos para los impuestos y los métodos de pago, para hacer que los datos del Retail POS sean compatibles con los valores que están predefinidas en el firmware fiscal del dispositivo.
- **Configuración de conector fiscal** La configuración define la comunicación con física el dispositivo fiscal específico.

Un proceso de registro fiscal para un registro de PDV específico se define mediante un valor correspondiente del perfil de funcionalidad del PDV. Para obtener más información acerca de cómo configurar un proceso de registro fiscal, cargar el proveedor fiscal de documento y las configuraciones de conector fiscales, y cambiar los parámetros, consulte [Configurar un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

El ejemplo siguiente muestra un flujo fiscal típico de la ejecución de registro para un dispositivo fiscal. El flujo empieza con un evento en PDV (por ejemplo, finalización de una transacción de ventas) e implementa la siguiente secuencia de pasos:

1. El PDV solicita un documento fiscal del CRT.
2. El CRT determina si el evento actual requiere el registro fiscal.
3. Según los valores fiscales del proceso de registro, CRT identifica un conector fiscal y un proveedor fiscal correspondiente del documento que desee utilizar para el registro fiscal.
4. CRT ejecuta el proveedor del documento fiscal que genera un documento fiscal (por ejemplo, un documento XML) que represente la transacción o el evento.
5. El PDV envía el documento fiscal que el CRT prepara para una estación de hardware.
6. La estación de hardware ejecuta el conector fiscal que procesa el documento fiscal y lo comunica al dispositivo o servicio fiscal.
7. El PDV analiza la respuesta del dispositivo o servicio fiscal para determinar si el registro fiscal ha tenido éxito.
8. El CRT guarda la respuesta en la base de datos del canal.

![Esquema de la solución](media/emea-fiscal-integration-solution.png "Esquema de la solución")

## <a name="error-handling"></a>Control de errores

El marco fiscal de la integración proporciona las opciones siguientes para gestionar los errores durante el registro fiscal:

- **Reintentar** – Los operadores pueden usar esta opción cuando el error puede resolver rápidamente, y el registro fiscal se puede volver a ejecutar. Por ejemplo, esta opción se puede usar cuando el dispositivo fiscal no está conectado, la impresora fiscal se encuentra sin papel, o hay un atasco de papel en la impresora fiscal.
- **Cancelar** La opción permite operadores posponer el registro fiscal de la transacción actual o del evento si falla. Después de que se posponga el registro, el transportista puede continuar trabajando en el PDV y puede completar todas las operaciones para las que el registro fiscal no sea necesario. Cuando cualquier evento que requiera el registro fiscal aparece en el sistema PDV (por ejemplo, se abre una nueva transacción), el cuadro de diálogo de tratamiento de errores aparece automáticamente para notificar el operador que la transacción anterior no se registró correctamente y para proporcionar las opciones de procesamiento de errores.
- **Omitir** – Los operadores pueden usar esta opción cuando el registro fiscal se puede omitir bajo condiciones específicas y las operaciones regulares se pueden continuar en el PDV. Por ejemplo, esta opción se puede usar cuando una transacción de ventas que no se registró se puede registrar en un diario de papel especial.
- **Marcar como registrado** – Los operadores pueden usar esta opción cuando se registró la transacción realmente en el dispositivo fiscal (por ejemplo, un recibo fiscal se imprimió), pero se produjo un error cuando la respuesta fiscal se guardada en la base de datos de canal.

> [!NOTE]
> Las opciones **Omitir** y **Marcar como registrado** se deben activar en el proceso de registro fiscal antes usarse. Además, los permisos correspondientes se deben conceder a los operadores.

Las opciones **Omitir** y **Marcar como registrado** activan códigos de información para capturar cierta información específica acerca del error, como el motivo del error o de una justificación para saltarse el registro fiscal o marcar la transacción como registrada. Para obtener más información sobre cómo gestionar los parámetros de gestión de errores, consulte [Establecer valores de gestión de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Registro fiscal opcional

El registro fiscal puede ser obligatorio para algunas operaciones pero opcional para otras. Por ejemplo, el registro fiscal de ventas y de devolución regulares puede ser obligatorio, pero el registro fiscal de las operaciones relacionadas con los depósitos de cliente puede ser opcional. En este caso, no finalizar el registro fiscal de una venta puede bloquear otras ventas, pero no finalizar el registro fiscal de un depósito de cliente no debe bloquear otras ventas. Para distinguir operaciones obligatorias y opcionales, se recomienda que las gestione a través de distintos proveedores de documentos distintos, y que configure los pasos individuales para el proceso de registro fiscal para dichos proveedores. El parámetro **Continuar con errores** debe estar habilitado para cualquier paso relacionada con el registro fiscal opcional. Para obtener más información sobre cómo gestionar los parámetros de gestión de errores, consulte [Establecer valores de gestión de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-running-fiscal-registration"></a>Ejecutar el registro fiscal de forma manual

Si el registro fiscal de una transacción o de un evento se ha aplazado después de un error (por ejemplo, si el transportista ha seleccionado **Cancelar** en el cuadro de diálogo de tratamiento de errores), puede volver a ejecutar manualmente el registro fiscal invocando una operación correspondiente. Para más información, consulte [Habilitar la ejecución manual del registro fisca postpuesto](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="fiscal-registration-health-check"></a>Comprobación del registro fiscal

El procedimiento de comprobación de estado de los registros fiscales verifica la disponibilidad del dispositivo fiscal o el servicio cuando se produzcan eventos específicos. Si el registro fiscal no se puede completar actualmente, se notifica al operador por adelantado.

El PDV ejecuta la comprobación de estado cuando se producen los siguientes eventos:

- Se abre una nueva transacción.
- Se recupera una transacción suspendida.
- Se concluye una transacción de ventas o devolución.

Si la comprobación de estado falla, el sistema PDV muestra el cuadro de diálogo de comprobación de estado. Este cuadro de diálogo proporciona los siguientes botones:

- **Aceptar** Este botón permite omitir el operador un error comprobación de estado y continuar procesando la operación. Los operadores pueden seleccionar este botón si el permiso **Permite omitir error de comprobaciónde estado** está habilitado para ellos.
- **Cancelar** Si el operador selecciona este botón, el sistema PDV cancela la última acción (por ejemplo, un artículo no se agrega a una nueva transacción).

> [!NOTE]
> La comprobaciónde estado solo se ejecuta si la operación actual requiere el registro fiscal, y si el parámetro **Continuar con errores** se deshabilita para el paso actual del proceso de registro fiscal. Para más información, consulte [Establecer configuraciónde tratamiento de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Almacenar respuesta fiscal en la transacción fiscal

Cuando el registro fiscal de una transacción o de un evento se ha realizado correctamente, una transacción fiscal se crea en la base de datos del canal y se vincula a la transacción o el evento original. De forma similar, si **Omitir** o la opción **Marcar como registrado** se selecciona para un registro fiscal defectuoso, esta información se almacena en una transacción fiscal. Una transacción fiscal conserva la respuesta fiscal del dispositivo o servicio fiscal. Si el proceso de registro fiscal consta de varios pasos, una transacción fiscal se crea para cada paso del proceso que ha provocado un registro correcto o error.

Las transacciones fiscales son transferidas a la sede central por *P-trabajo*, junto con las transacciones. En el FastTab **Transacciones fiscales** de la página **Transacciones de la tienda** , puede ver las transacciones fiscales que se vinculan a las transacciones.

Una transacción fiscal almacena los siguientes datos:

- Detalles fiscales del proceso de registro (proceso, grupo conector, conector, etc.). También guarda el número de serie del dispositivo fiscal en el campo **Número de registro** , si esta información se incluye en la respuesta fiscal.
- El estado del registro fiscal: **Completado** para registros correctos, **Omitido** si el operador ha seleccionado la opción **Omitir** para un registro defectuoso, o **Marcado como registrado** si el operador ha seleccionado la opción **Marcar como registrado** .
- Código de información de las transacciones relacionadas con una transacción fiscal seleccionada. Para ver las transacciones de código de información en el FastTab **Transacciones fiscales** , seleccione una transacción fiscal que tiene un estado **Omitido** o **Marcado como registrado**, y después seleccione **Código de información de transacciones**.

## <a name="fiscal-texts-for-discounts"></a>Textos fiscales para descuentos

Algunos países o regiones tienen requisitos especiales sobre los textos adicionales que se deben imprimir en recibos fiscales cuando se aplican los diferentes tipos de descuentos. La funcionalidad fiscal de la integración permite configurar un texto especial para un descuento que se imprime después de una línea de descuento en un recibo fiscal. Para descuentos manuales, puede configurar un texto fiscal para la información codificada especificado como la **Descuento del producto** codificada en el perfil de funcionalidad del PDV. Para obtener más información acerca de cómo configurar los textos fiscales para descuentos, consulte [Instalación de textos fiscales para descuentos](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Imprimir X y Z informes fiscales

La funcionalidad fiscal de la integración admite la generación de informes de final del día que son específicas para el dispositivo o servicio fiscal integrado:

- Los nuevos botones que funcionan con las operaciones correspondientes se deben agregar al diseño de pantalla del PDV. Para obtener más información, consulte [Configurar informes fiscales X/Z de PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- En el ejemplo fiscal de la integración, estas operaciones deben coincidir a las operaciones correspondientes del dispositivo fiscal.

## <a name="fiscal-integration-samples-in-the-retail-sdk"></a>Ejemplos fiscales de integración en el SDK al por menor

Los ejemplos siguientes fiscales de integración están disponibles actualmente en el SDK de Retail:

- [Ejemplo de integración de impresora fiscal para Italia](emea-ita-fpi-sample.md)
- [Ejemplo de integración de impresora fiscal para Polonia](emea-pol-fpi-sample.md)
- [Ejemplo de integración de servicio de registro para Austria](emea-aut-fi-sample.md)
- [Ejemplo de integración de servicio de registro fiscal para la República Checa](emea-cze-fi-sample.md)
- [Muestra de integración de unidad de control para Suecia](./emea-swe-fi-sample.md)
- [Ejemplo de integración de servicio de registro fiscal para Alemania](./emea-deu-fi-sample.md)

La siguiente funcionalidad fiscal de integración también está disponible en el SDK al por menor pero no se aprovecha actualmente del marco fiscal de integración. La migración de esta funcionalidad fiscal al marco de integración está prevista para actualizaciones posteriores.


- [Firma digital para Francia](emea-fra-cash-registers.md)
- [Firma digital para Noruega](emea-nor-cash-registers.md)

La siguiente funcionalidad de integración fiscal heredada que está disponible en el SDK de Retail no utiliza el marco de integración fiscal y quedará en desuso en actualizaciones posteriores:

- [Muestra de integración de unidad de control para Suecia (heredada)](./retail-sdk-control-unit-sample.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]