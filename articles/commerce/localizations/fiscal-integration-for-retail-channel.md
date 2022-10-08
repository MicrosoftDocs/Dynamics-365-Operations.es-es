---
title: Información general de la integración fiscal para canales de Commerce
description: Este artículo proporciona una visión general de las capacidades fiscales de integración disponibles en Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1812405db3c1e58eaf7cd1df3896f786e7bf026f
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631250"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Información general de la integración fiscal para canales de Commerce

[!include [banner](../includes/banner.md)]

Este artículo es una visión general de las capacidades fiscales de integración disponibles en Dynamics 365 Commerce. 

La integración fiscal incluye la integración con distintos dispositivos fiscales y servicios que habilitan el registro fiscal de la venta de acuerdo con las leyes fiscales locales que se dirijan que impiden fraude fiscal en el sector minorista. A continuación aparecen varias situaciones de ejemplo habituales que se pueden cubrir mediante inclusión de la integración fiscal:

- Registrar una venta en un dispositivo fiscal que está conectado al punto de venta (PDV), como una impresora fiscal, e imprimir un recibo fiscal para el cliente.
- Enviar la información relacionada con las ventas y las devoluciones que se completan en Retail POS a un servicio Web externa que sea operado por la autoridad fiscal de forma segura.
- Ayudar a garantizar la inalterabilidad de los datos de transacción de ventas a través de firmas digitales.

La funcionalidad fiscal de la integración de ventas es un marco que ofrece una solución común para el desarrollo y la personalización adicionales de la integración entre Retail POS y dispositivos y servicios fiscales. La funcionalidad también incluye los ejemplos fiscales de integración que admiten los escenarios básicos para los países o regiones específicos, y que funcionan con los dispositivos o servicios fiscales específicos. Un ejemplo fiscal de la integración consta de varias extensiones de componentes de Commerce y se incluye en el kit de desarrollo de software (SDK). Para obtener más información sobre los ejemplos de integración fiscal, consulte [Ejemplos de integración fiscal en el SDK de Commerce](#fiscal-integration-samples-in-the-commerce-sdk). Para obtener información sobre cómo instalar y usar el SDK de Commerce, consulte [Arquitectura del kit de desarrollo de software (SDK) de Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Para admitir otros escenarios que no son compatibles por un ejemplo fiscal de la integración, para integrar Retail POS con otros dispositivos o servicios fiscales, o cubrir los requisitos de otros países o regiones, debe remitir un ejemplo fiscal existente de integración o crear un nuevo ejemplo mediante un ejemplo existente como un ejemplo.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos y servicios fiscales

Un proceso de registro fiscal en Retail POS puede estar formado por uno o más pasos. Cada paso implica el registro de transacciones fiscales o de eventos específicos en un dispositivo manual o servicio fiscal. Los siguientes componentes de la solución participan en el registro fiscal en un dispositivo o servicio fiscal:

- **Proveedor de documentos fiscales**: este componente serializa la transacción/datos de eventos en el formato que también se usa para la interacción con el dispositivo o servicio fiscal, analiza respuestas del dispositivo o servicio fiscal, y almacena las respuestas en la base de datos del canal. La extensión también define las transacciones y los eventos específicos que deben estar registrados.
- **Conector fiscal**: este componente inicializa la comunicación con el dispositivo fiscal, envía solicitudes y comandos directos al dispositivo o servicio fiscal basado en la transacción/los datos de eventos de la información del documento o servicio fiscal y recibe respuestas del dispositivo o servicio fiscal.

Un ejemplo fiscal de integración para un dispositivo fiscal podría contener el Commerce runtime (CRT) y extensiones de la estación de hardware para un proveedor fiscal de documentos y conector fiscal. También contiene las siguientes configuraciones de componentes:

- **Configuración del proveedor fiscal del documento** La configuración define un método de salida y el formato de los documentos fiscales. También contiene una asignación de datos para los impuestos y los métodos de pago, para hacer que los datos del Retail POS sean compatibles con los valores que están predefinidas en el firmware fiscal del dispositivo o servicio.
- **Configuración de conector fiscal** La configuración define la comunicación con física el dispositivo o servicio fiscal específico.

Un proceso de registro fiscal para un registro de PDV específico se define mediante un valor correspondiente del perfil de funcionalidad del PDV. Para obtener más información acerca de cómo configurar un proceso de registro fiscal, cargar el proveedor fiscal de documento y las configuraciones de conector fiscales, y cambiar los parámetros de configuración, consulte [Configurar un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Si necesita dispositivos para operaciones no fiscales, como la búsqueda de catálogos de productos, la búsqueda de clientes o la creación de borradores de transacciones, puede seleccionarlos como registros con restricciones de procesos fiscales. Para más información, ver [Configurar registros con restricciones de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

El siguiente flujo de registro fiscal típico comienza con un evento en el POS (por ejemplo, la finalización de una transacción de venta) e implementa una secuencia predefinida de pasos que involucra otros componentes de Commerce (como el CRT y la estación de hardware).

1. El POS solicita un documento fiscal del marco de integración fiscal (FIF).
1. El FIF determina si el evento actual requiere el registro fiscal.
1. Según la configuración del proceso de registro fiscal, FIF identifica un conector fiscal y un proveedor fiscal correspondiente del documento que desee utilizar para el registro fiscal.
1. El FIF ejecuta el proveedor del documento fiscal que genera un documento fiscal (por ejemplo, un documento XML) que represente la transacción o el evento.
1. El FIF devuelve el documento fiscal generado al TPV.
1. El POS solicita que el FIF presente el documento fiscal al dispositivo o servicio fiscal.
1. El FIF ejecuta el conector fiscal que procesa el documento fiscal y lo envía al dispositivo o servicio fiscal.
1. El FIF devuelve la respuesta fiscal (es decir, la respuesta del dispositivo o servicio fiscal) al TPV.
1. El PDV analiza la respuesta fiscal para determinar si el registro fiscal ha tenido éxito. Según sea necesario, el POS solicita que el FIF maneje cualquier error que haya ocurrido. 
1. El TPV solicita que el FIF procese y guarde la respuesta fiscal.
1. El proveedor del documento fiscal procesa la respuesta fiscal. Como parte de este procesamiento, el proveedor del documento fiscal analiza la respuesta y extrae datos ampliados de ella.
1. El FIF guarda la respuesta y los datos ampliados en la base de datos del canal.
1. Según sea necesario, el POS imprime un recibo a través de una impresora de recibos normal que está conectada a la estación de hardware. El recibo puede contener datos requeridos de la respuesta fiscal.
 
Los ejemplos siguientes muestran flujos fiscales de la ejecución de registro para dispositivos o servicios fiscales típicos.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>El registro fiscal se realiza a través de un dispositivo conectado a la estación de Hardware

Esta configuración se utiliza cuando un dispositivo fiscal físico, como una impresora fiscal, está conectado a la estación de hardware. También es aplicable cuando la comunicación con un dispositivo o servicio fiscal se realiza a través de un software instalado en la estación de Hardware. En este caso, el proveedor de documentos fiscales se encuentra en la CRT y el conector fiscal se encuentra en la estación de hardware.

![El registro fiscal se realiza a través de un dispositivo conectado a la estación de Hardware](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>El registro fiscal se realiza a través de un servicio externo

Esta configuración se utiliza cuando el registro fiscal se realiza a través de un servicio externo, como un servicio web operado por la autoridad fiscal. En este caso, el proveedor de documentos fiscales y el conector fiscal se encuentran en la CRT.

![El registro fiscal se realiza a través de un servicio externo.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>El registro fiscal se realiza internamente en el CRT

Esta configuración se utiliza cuando no se requiere ningún dispositivo o servicio fiscal externo para el registro fiscal. Por ejemplo, se utiliza cuando el registro fiscal se realiza a través de la firma digital de transacciones de venta. En este caso, el proveedor de documentos fiscales y el conector fiscal se encuentran en la CRT.

![El registro fiscal se realiza internamente en el CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>El registro fiscal se realiza a través de un dispositivo o servicio en la red local

Esta configuración se utiliza cuando un dispositivo fiscal físico o un servicio fiscal está presente en la red local de la tienda y proporciona una interfaz de programación de aplicaciones (API) HTTPS. En este caso, el proveedor de documentos fiscales se encuentra en la CRT y el conector fiscal se encuentra en el PDV.

![El registro fiscal se realiza a través de un dispositivo o servicio en la red local.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Control de errores

El marco fiscal de la integración proporciona las opciones siguientes para gestionar los errores durante el registro fiscal:

- **Reintentar** – El operador puede usar esta opción cuando el error se puede resolver rápidamente y el registro fiscal se puede volver a ejecutar. Por ejemplo, esta opción se puede usar cuando el dispositivo fiscal no está conectado, la impresora fiscal se encuentra sin papel, o hay un atasco de papel en la impresora fiscal.
- **Cancelar** La opción permite al operador aplazar el registro fiscal de la transacción actual o del evento si falla. Después de que se aplace el registro, el transportista puede continuar trabajando en el PDV y puede completar todas las operaciones para las que el registro fiscal no sea necesario. Cuando cualquier evento que requiera el registro fiscal aparece en el sistema PDV (por ejemplo, se abre una nueva transacción), el cuadro de diálogo de tratamiento de errores aparece automáticamente para notificar el operador que la transacción anterior no se registró correctamente y para proporcionar las opciones de procesamiento de errores.
- **Omitir** – El operador puede utilizar esta opción cuando no es posible completar el registro fiscal de la transacción o evento actual, por ejemplo, si la impresora fiscal está fuera de servicio **y** el registro fiscal se puede omitir bajo condiciones específicas. Por ejemplo, esta opción se puede usar cuando una transacción de ventas que no se registró se puede registrar en un diario de papel especial. Después de omitir el registro fiscal, se puede continuar con las operaciones regulares en el PDV. 
- **Marcar como registrado** – El operador puede usar esta opción cuando se registró la transacción o evento actual realmente en el dispositivo fiscal, por ejemplo, se ha impreso un recibo fiscal, pero se produjo un error cuando la respuesta fiscal se guardada en la base de datos de canal. Después de marcar la transacción o evento actual como registrado, se puede continuar con las operaciones regulares en el PDV.
- **Posponer** – El operador puede utilizar esta opción cuando la transacción no se ha registrado porque el dispositivo o servicio de registro no estaba disponible **y** se aplica una de las siguientes opciones:
    - Hay una opción de registro fiscal de respaldo y es posible continuar el proceso de registro fiscal para la transacción actual. Por ejemplo, un [dispositivo fiscal](./latam-bra-cf-e-sat.md#scenario-4-make-a-cash-and-carry-sale-of-goods-by-using-sat-as-contingency-mode) local puede ser una opción de respaldo para un servicio de registro fiscal en línea cuando el servicio no está disponible.
    - El registro fiscal se puede realizar posteriormente por medios distintos al marco de integración fiscal. Por ejemplo, las transacciones pospuestas se pueden registrar fiscalmente en un lote mediante una [funcionalidad independiente](./latam-bra-nfce.md#scenario-3-make-a-cash-and-carry-sale-of-goods-in-offline-contingency-mode).
    
    Después de posponer la transacción o evento actual, se puede continuar con las operaciones regulares en el PDV.

> [!WARNING]
> Las opciones **Omitir**, **Marcar como registrado** y **Posponer** se deben considerar opciones de emergencia y usarse solo en casos excepcionales. Consulte estas opciones de gestión de errores con su asesor jurídico o fiscal y aplique su buen criterio antes de habilitarlas. Las opciones se deben activar en el proceso de registro fiscal antes usarse. Para asegurarse de que los operadores no las utilicen de forma habitual, se deben otorgar los permisos correspondientes a los operadores.

Se crea una [transacción fiscal](#storing-fiscal-response-in-fiscal-transaction) cuando las opciones **Omitir**, **Marcar como registrado**, o **Posponer** están seleccionadas, pero la transacción fiscal no contiene ninguna respuesta fiscal. Esto le permite capturar el evento de error de registro fiscal. Estas opciones también activan códigos de información para capturar cierta información específica acerca del error, como el motivo del error o una justificación para omitir el registro fiscal o marcar la transacción como registrada. Para obtener más información sobre cómo gestionar los parámetros de gestión de errores, consulte [Establecer valores de gestión de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Registro fiscal opcional

El registro fiscal puede ser obligatorio para algunas operaciones pero opcional para otras. Por ejemplo, el registro fiscal de ventas y de devolución regulares puede ser obligatorio, pero el registro fiscal de las operaciones relacionadas con los depósitos de cliente puede ser opcional. En este caso, no finalizar el registro fiscal de una venta puede bloquear otras ventas, pero no finalizar el registro fiscal de un depósito de cliente no debe bloquear otras ventas. Para distinguir operaciones obligatorias y opcionales, se recomienda que las gestione a través de distintos proveedores de documentos distintos, y que configure los pasos individuales para el proceso de registro fiscal para dichos proveedores. El parámetro **Continuar con errores** debe estar habilitado para cualquier paso relacionada con el registro fiscal opcional. Para obtener más información sobre cómo gestionar los parámetros de gestión de errores, consulte [Establecer valores de gestión de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Volver a ejecutar el registro fiscal de forma manual

Si el registro fiscal de una transacción o de un evento se ha aplazado después de un error (por ejemplo, si el operador ha seleccionado **Cancelar** en el cuadro de diálogo de gestión de errores), puede volver a ejecutar manualmente el registro fiscal invocando una operación correspondiente. Para más información, consulte [Habilitar la ejecución manual del registro fiscal aplazado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).

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

Cuando el registro fiscal de una transacción o de un evento se ha realizado correctamente, una transacción fiscal se crea en la base de datos del canal y se vincula a la transacción o el evento original. De forma similar, si la opción **Omitir**, **Marcar como registrado** o **Posponer** se selecciona para un registro fiscal con errores, esta información se almacena en una transacción fiscal. Una transacción fiscal conserva la respuesta fiscal del dispositivo o servicio fiscal. Si el proceso de registro fiscal consta de varios pasos, una transacción fiscal se crea para cada paso del proceso que ha provocado un registro correcto o error.

Las transacciones fiscales son transferidas a la sede central por *P-trabajo*, junto con las transacciones. En el FastTab **Transacciones fiscales** de la página **Transacciones de la tienda** , puede ver las transacciones fiscales que se vinculan a las transacciones.

Una transacción fiscal almacena los siguientes datos:

- Detalles fiscales del proceso de registro (proceso, grupo conector, conector, etc.). También guarda el número de serie del dispositivo fiscal en el campo **Número de registro** , si esta información se incluye en la respuesta fiscal.
- El estado del registro fiscal: **Completado** para registros correctos, **Omitido** si el operador ha seleccionado la opción **Omitir** para un registro defectuoso, o **Marcado como registrado** si el operador ha seleccionado la opción **Marcar como registrado** o **Pospuesto** si ha seleccionado la opción **Posponer**.
- Código de información de las transacciones relacionadas con una transacción fiscal seleccionada. Para ver las transacciones de código de información en el FastTab **Transacciones fiscales**, seleccione una transacción fiscal que tiene un estado **Omitido**, **Marcado como registrado** o **Pospuesto**, y después seleccione **Código de información de transacciones**.

Si selecciona **Datos extendidos**, también puede ver algunas propiedades de la transacción fiscal. La lista de propiedades que se pueden ver es específica de la funcionalidad de registro fiscal que generó la transacción fiscal. Por ejemplo, puede ver la firma digital, el número secuencial, la huella digital del certificado, la identificación del algoritmo hash y otras propiedades de transacciones fiscales para la funcionalidad de firma digital de Francia.

## <a name="fiscal-texts-for-discounts"></a>Textos fiscales para descuentos

Algunos países o regiones tienen requisitos especiales sobre los textos adicionales que se deben imprimir en recibos fiscales cuando se aplican los diferentes tipos de descuentos. La funcionalidad fiscal de la integración permite configurar un texto especial para un descuento que se imprime después de una línea de descuento en un recibo fiscal. Para descuentos manuales, puede configurar un texto fiscal para la información codificada especificado como la **Descuento del producto** codificada en el perfil de funcionalidad del PDV. Para obtener más información acerca de cómo configurar los textos fiscales para descuentos, consulte [Instalación de textos fiscales para descuentos](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Imprimir X y Z informes fiscales

La funcionalidad fiscal de la integración admite la generación de informes de final del día que son específicas para el dispositivo o servicio fiscal integrado:

- Los nuevos botones que funcionan con las operaciones correspondientes se deben agregar al diseño de pantalla del PDV. Para obtener más información, consulte [Configurar informes fiscales X/Z de PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- En el ejemplo fiscal de la integración, estas operaciones deben coincidir a las operaciones correspondientes del dispositivo fiscal.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Ejemplos de integración fiscal en el SDK de Commerce

Los siguientes ejemplos de integración fiscal están disponibles actualmente en el SDK de Commerce:

- [Ejemplo de integración de impresora fiscal para Italia](./emea-ita-fpi-sample.md)
- [Ejemplo de integración de impresora fiscal para Polonia](./emea-pol-fpi-sample.md)
- [Ejemplo de integración de servicio de registro para Austria](./emea-aut-fi-sample.md)
- [Ejemplo de integración de servicio de registro fiscal para la República Checa](./emea-cze-fi-sample.md)
- [Muestra de integración de unidad de control para Suecia](./emea-swe-fi-sample.md)
- [Ejemplo de integración de servicio de registro fiscal para Alemania](./emea-deu-fi-sample.md)
- [Ejemplo de integración de impresora fiscal para Rusia](./rus-fpi-sample.md)

La siguiente funcionalidad de integración fiscal también se implementa mediante el marco de integración fiscal, pero está disponible lista para usar y no se incluye en el SDK de Commerce:

- [Registro fiscal para Brasil](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Firma digital para Francia](./emea-fra-cash-registers.md)

La siguiente funcionalidad de integración fiscal también está disponible en el SDK de Commerce, pero no utiliza actualmente el marco de integración fiscal. La migración de esta funcionalidad fiscal al marco de integración está prevista para actualizaciones posteriores.

- [Firma digital para Noruega](./emea-nor-cash-registers.md)

La siguiente funcionalidad de integración fiscal heredada que está disponible en el SDK de Commerce no utiliza el marco de integración fiscal y quedará en desuso en actualizaciones posteriores:

- [Muestra de integración de unidad de control para Suecia (heredada)](./retail-sdk-control-unit-sample.md)
- [Firma digital para Francia (heredada)](./emea-fra-deployment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
