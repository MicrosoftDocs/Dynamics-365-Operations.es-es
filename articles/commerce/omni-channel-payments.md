---
title: Información general de pagos omnicanal
description: Este tema proporciona una visión general de los pagos de omnicanal en Dynamics 365 Commerce.
author: rubendel
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 8.1.3
ms.openlocfilehash: 80eaf36fb382e0ebe0a66383ea17ab76faa07dfa
ms.sourcegitcommit: 084eda1d5503be83e97e2e428e67ef5393535fab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "3819822"
---
# <a name="omni-channel-payments-overview"></a>Información general de pagos omnicanal

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general de los pagos de omnicanal en Dynamics 365 Commerce. Incluye una lista completa de escenarios admitidos, información sobre funcionalidad, configuración, soluciones de problemas y las descripciones de problemas habituales.

## <a name="key-terms"></a>Términos clave

| Condición | Descripción |
|---|---|
| Token | Una cadena de datos que un procesador de pago proporciona como referencia. Los tokens pueden representar los números de la tarjeta de pago, las autorizaciones de pago y las capturas anteriores del pago. Los tokens son importantes pues ayudan a mantener datos confidenciales fuera del sistema de punto de venta (POS). A veces también se conocen como *referencias*. |
| Token de tarjeta | Un token que un procesador de pago proporciona para el almacenamiento en el sistema POS. Un token de tarjeta solo puede usarlo el comerciante que lo recibe. Los tokens de tarjeta a veces también se conocen como *referencias de tarjeta*. |
| Token de autorización (auth) | Identificador único que un proceso de pago proporciona como parte de la respuesta que envía a un sistema POS después de que el sistema POS haga una solicitud de autorización. Un token de autorización se puede usar más adelante si llaman al procesador para realizar acciones como invertir o anular la autorización. Sin embargo, se usa más a menudo para capturar fondos al completar un pedido o finalizar una transacción. Los tokens de autorización a veces también se conocen como *referencias de autorización*. |
| Token de captura | Una referencia que un procesador de pago proporciona a un sistema POS cuando finaliza o se obtiene un pago. El token de la captura se puede utilizar para hacer referencia a la captura de pago en operaciones posteriores, como solicitudes de devolución. | 
| Tarjeta no presente | Un término que hace referencia a las transacciones de pago en que una tarjeta física no se muestra. Por ejemplo, estas transacciones se pueden aparecer en comercio electrónico o escenarios de centro de llamadas. Para estas transacciones, la información relacionada pago- se especifica manualmente en una página Web de comercio electrónico en un flujo de centro de llamadas o en el POS o terminal de pago. |
| Tarjeta presente | Un término que hace referencia a las transacciones de pago en una tarjeta física se mostrará y se usa en un terminal de pago que está conectado al sistema Microsoft Dynamics 365 POS. |

## <a name="overview"></a>Información general

El término *pagos de omnicanal* describe la capacidad de crear un pedido en un canal y de satisfacerla en otro canal. La clave de compatibilidad de pago de omnicanal es mantener los detalles del pago así como el resto de los detalles de pedido y, a continuación usar esos detalles del pago cuando el pedido se recupere o se procesa en otro canal. Un ejemplo clásico es el escenario "Comprar en línea, recoger en la tienda". En esta situación se agregan los detalles del pago cuando el pedido se crea en línea. A continuación se devuelven al sistema PDV para cargar la tarjeta de pago del cliente en el momento de recogida. 

Todas las situaciones que se describen en este tema se pueden implementar mediante el kit de desarrollo de software estándar (SDK) de los pagos que se ofrece con Commerce. El [Conector de pago de Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) ofrece una implementación del componente estándar de cada escenario que se describe aquí. 

### <a name="prerequisites"></a>Requisitos previos

Cada escenario que se describe en este tema requiere un conector de pago que admita pagos de omnicanal. El conector de Adyen también está listo para usarse, ya que admite escenarios que estará disponible con los pagos SDK. Para obtener más información sobre la implementación los conectores de pago, y sobre la SDK de Retail en general, visite [Página principal de Retail para profesionales de TI y desarrolladores](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors).

#### <a name="supported-versions"></a>Versiones admitidas

Las capacidades de pago de omnicanal que se describen en este tema se publicaron como parte de la versión 8.1.3 de Microsoft Dynamics 365 for Retail. 

#### <a name="card-present-and-card-not-present-connectors"></a>Conectores "Tarjeta presente" y "Tarjeta ausente"

Los pagos SDK dependen de dos conjuntos de interfaces de programación de aplicaciones (APIs) para los pagos. El primer conjunto de API se llama **iPaymentProcessor**. Se usaba para implementar conectores de pago de "tarjeta ausente” que se pueden usar en los centros de llamadas y con la plataforma de comercio electrónico Microsoft Dynamics. Para obtener más información acerca de la interfaz **iPaymentProcessor**, consulte la documentación [Implementar un conector de pago y un dispositivo de pago](https://download.microsoft.com/download/e/2/7/e2735c65-1e66-4b8d-8a3c-e6ef3a319137/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device_update.pdf) que cubre los pagos. 

El segundo conjunto de API se llama **iNamedRequestHandler**. Admite la implementación de las integraciones de pagos de "tarjeta presente“que usa un terminal de pago. Para obtener más información acerca de la interfaz **iNamedRequestHandler**, consulte [Crear una integración de pago para un terminal de pago](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension). 

### <a name="setup-and-configuration"></a>Establecimiento y configuración

Los siguientes componentes y pasos de configuración son necesarios:

- **Integración de comercio electrónico:** la integración con Commerce se requiere para admitir los escenarios donde un pedido se origina en un escaparate en línea. Para obtener más información acerca del SDK del comercio electrónico de Retail, consulte [Kit de desarrollo de software (SDK) de la plataforma de comercio electrónico](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk). En un entorno de demostración, el escaparate de referencia admite escenarios de pago de omnicanal. 
- **Configuración de los pagos en línea:** la configuración del canal conectado debe incluir un conector de pago que se ha actualizado para admitir pagos de omnicanal. Como alternativa, puede usar el conector de pago tal cual. Para obtener información sobre cómo configurar el conector de pago Adyen para tiendas en línea, consulte [Conector de pago de Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce). Además de los pasos de configuración del comercio electrónico que se describen en este tema, el parámetro **Permitir guardar de la información de pago en comercio electrónico** se debe establecer en **Verdad** en la configuración del conector Adyen. 
- **Configuración de pagos de omnicanal:** en la oficina administrativa, vaya a **Retail y Commerce \> Configuración de sede \> Parámetros \> Parámetros compartidos de Commerce**. A continuación, en la pestaña **Pagos de omnicanal**, establezca la opción **Usar pagos omnicanal** en **Sí**. En las versiones 10.0.12 y posteriores de Commerce, esta configuración está en el espacio de trabajo **Administración de características**. Seleccione la característica **Pagos omnicanal** y haga clic **Habilitar ahora**. 
- **Servicios de pago:** el centro de llamadas usa el conector de pago predeterminado en la página **Servicios de pago** para procesar los pagos. Para admitir escenarios como “Comprar en centro de llamadas, recoger en tienda,” este conector de pago predeterminado debe ser el conector de pago Adyen o un conector de pago que cumple con los requisitos de implementación de los pagos de omnicanal.
- **Servicio EFT:** los pagos a través de un terminal de pago se deben configurar en la ficha desplegable **Servicio EFT** del perfil de hardware. El connector de Adyen admite escenarios de pagos omnicanal listos para usarse. Otros conectores de pago que admiten la interfaz **iNamedRequestHandler** también pueden usarse si admiten pagos omnicanal.
- **Disponibilidad de conector de pago:** cuando se recuperar un pedido, las líneas de la propuesta de pago que se vuelven a llamar junto con la inclusión del pedido el nombre del conector de pago usado para crear las autorizaciones que están asociados a este orden. Cuando se cumple el pedido, el SDK de los pagos intentará usar el mismo conector usado para crear la autorización original. Por lo tanto, un conector de pago con las mismas propiedades mercantil debe estar disponible para la captura. 
- **Tipos de tarjeta:** para que las escenarios de omnicanal funcionen correctamente, cada canal debe tener la misma configuración para los tipos de forma de pago que se pueden usar para el omnicanal. Esta configuración incluye identificadores de método de pago y tipo de tarjeta. Por ejemplo, si el tipo de forma de pago **Tarjetas** tiene un identificador **2** en la configuración de la tienda en línea, debe tener el mismo identificador en la configuración de la tienda minorista. El mismo requisito se aplica a los identificadores de tipo de tarjeta. Si el número de tarjeta **12** se establece en **VISA** en la tienda en línea, el mismo identificador se debe configurar para la tienda al por menor. 
- Retail Modern POS para Windows o Android con una estación de hardware integrada o
- Modern POS para iOS o Cloud POS con estación de hardware compartida conectada. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>Principio básico que admite pagos de omnicanal

Los conectores de pago y los procesadores de pago usan tokens, o referencias, para hacer referencia a las interacciones relacionados con los pagos de tarjeta. Por ejemplo, cuando se requiera una autorización de pago, se proporciona una referencia a la autorización. Por lo tanto, la autorización se puede referenciar más adelante, cuando los fondos se capturan a la hora de cumplimiento. Esta autorización es exclusiva el comerciante, el conector de pago y el procesador. 

Si un pedido que se creó en línea se está cogiendo en el almacén, los mismos datos de pago para dicho pedido se deben recuperar y utilizar. Cuando los detalles originales se proporcionan como parte de la solicitud para capturar un pago con la autorización original, el procesador de pago podrá gestionar la solicitud y capturar el pago. 

Para hacer referencia correctamente el pedido en línea, el conector de pago de "tarjeta ausente" que admite el mismo procesador debe también estar disponible. De esta manera, el sistema PDV puede tener un procesador para los pagos "tarjeta presente“, pero puede acceder a otros conectores de pago de modo que pueda cumplir los pedidos creados en otros mediante varios canales procesadores de pago. 

## <a name="supported-scenarios"></a>Escenarios admitidos

Se admiten los siguientes escenarios de pago de omnicanal:

- Comprar en línea, recoger en la tienda
- Comprar en el centro de llamadas, recoger en la tienda
- Comprar en la tienda A, recoger en la tienda B
- Comprar en la tienda A, enviar al cliente

    > [!NOTE]
    > Los pagos realizados en el centro de llamadas que se asignan a la función de pago "Normal" deben marcarse como **Pagar por adelantado** = **Sí** para que se reflejen en el importe adeudado al retirar el pedido en el PDV. Los pagos sin prepago de tipo "Normal" no se reconocen cuando se retira el pedido en el PDV. 

Las variaciones de estos casos también se admiten. Por ejemplo, un pedido en línea puede incluir ambas líneas que se registrarán en el cliente y las líneas que se recogerán en una tienda. Todas las opciones de cumplimiento de pedido se admiten a través de pagos de omnicanal. 

En las secciones siguientes se describen los pasos para cada escenario y se presenta cómo trabajar con la situación de ejemplo con datos de prueba. 

### <a name="buy-online-pick-up-in-store"></a>Comprar en línea, recoger en la tienda

Antes de empezar, asegúrese de que se cumplan los siguientes requisitos previos:

- Tiene un escaparate de referencia donde se configura el conector Adyen.
- La opción **Pagos de omnicanal** en la página **Parámetros compartidos de Commerce** se establece en **Verdadero**. En versiones posteriores, esta característica se pasa al espacio de trabajo **Administración de características** donde puede seleccionar la característica **Pagos omnicanal** característica y hacer clic en **Habilitar ahora**. 
- El connector de pago de Adyen está configurado para el registro de Houston PDV.
- Retail Modern POS para Windows o Android con una estación de hardware integrada o
- Modern POS para iOS o Cloud POS con estación de hardware compartida conectada. 

Para ejecutar el escenario, siga estos pasos:

1. En el escaparate de referencia, cree un pedido para la recogida en almacén. Asegúrese de seleccionar la tienda **Houston**. 
2. Pase a través de los pasos de finalización de la compra y pague usando un número de tarjeta de crédito de prueba. Puede encontrar números de tarjeta de crédito de prueba en [Página de números de tarjeta de prueba de Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description).
3. En Commerce, utilice el trabajo por lotes **Sincronizar los pedidos** y la programación de la distribución **P-001** para crear los pedidos en el área de operaciones.
4. En el PDV, en la página de inicio, seleccione la operación **Pedidos a recoger** para ver los pedidos para recoger en el almacén. 
5. Seleccione una o más líneas del pedido que se ha creado en el escaparate de referencia y, a continuación seleccione **Recoger**.

    El pedido se recupera de la oficina administrativa. 

6. Cuando los detalles de la línea de pedido se recuperan de la oficina y se detecta un pago de tarjeta que se puede usar para el omnicanal, se le informará de que un método de pago está disponible.
7. Seleccione **Usar método de pago disponible** para completar la transacción mediante los detalles de la tarjeta que se especificaron en el escaparate de referencia.

    Las líneas de pedido se cargan en la página de la transacción, y el saldo pendiente es 0 (cero). 

8. Seleccione la pestaña **Pagos** para la línea de pago que se sacó del pedido en línea. 
9. Seleccione cualquier método de pago para completar la transacción. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Comprar en el centro de llamadas, recoger en la tienda

1. En Commerce, en la página **Servicio al cliente**, especifique **Karen Berg** en la barra de búsqueda y, a continuación, seleccione **Buscar**. 
3. Seleccione **Karen Berg** en los resultados de la búsqueda.
4. Una vez que Karen se carga sobre la página **Servicio al cliente**, seleccione **Nuevo pedido de ventas**.
5. En la nueva página del pedido de ventas, seleccione **Encabezado** para ver el encabezado del pedido. 
6. En la página **Encabezado del pedido**, establezca el sitio en **Central** y el almacén en **Houston**.
7. En la pestaña **Entrega**, establezca el campo **Modo de entrega** a **60** para la recogida del cliente.
8. Seleccione **Líneas**, y luego agregue una o más líneas al pedido. 
9. Seleccione **Completar** para especificar el flujo de la finalización del pedido.
10. Desplácese hasta la sección de los pagos, seleccione **Agregar** y seleccione una línea que en la que el tipo de método de pago sea **Tarjetas**. 
11. Seleccione el signo más (**+**) para agregar un pago de tarjeta. 
12. Introduzca los detalles de un número de tarjeta de crédito de prueba que puede encontrar en [Página de números de tarjeta de la prueba de Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description) y a continuación seleccione **Aceptar**.

    > [!NOTE]
    > Si la marca de tarjeta para el número de tarjeta especificado difiere de la marca que se activó cuando el pago se ha iniciado, el pago todavía continuará. Sin embargo, se registrará en las cuentas asignadas a la marca de la tarjeta que seleccionó en el paso 10.

12. Seleccione **Aceptar** de nuevo para cerrar el cuadro **Pagos de la finalización del pedido**.
13. En la página **Resumen de pedido de ventas**, seleccione **Enviar**.
14. En el PDV, en la página de inicio, seleccione la operación **Pedidos a recoger** para ver los pedidos para recoger en el almacén. 
15. Seleccione una o más líneas del pedido que se ha creado en el escaparate de referencia y, a continuación seleccione **Recoger**.

    El pedido se recupera de la oficina administrativa. 

16. Cuando los detalles de la línea de pedido se recuperan de la oficina y se detecta un pago de tarjeta que se puede usar para el omnicanal, se le informará de que un método de pago está disponible.
17. Seleccione **Usar método de pago disponible** para completar la transacción mediante los detalles de la tarjeta que se especificaron en el escaparate de referencia.

    Las líneas de pedido se cargan en la página de la transacción, y el saldo pendiente es 0 (cero).

18. Seleccione la pestaña **Pagos** para la línea de pago que se sacó del pedido en línea. 
19. Seleccione cualquier método de pago para completar la transacción. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Comprar en la tienda A, recoger en la tienda B

1. Iniciar el sistema PDV para la tienda de Houston.
2. En la página **Transacción**, agregue Karen Berg a la transacción mediante el teclado numérico especificando **2001**.
3. Agregue una o más líneas a la transacción.
4. Seleccione **Pedidos** para ver opciones de pedido.
5. Seleccione **Recoger todos** y, a continuación, cuando el sistema lo solicite, seleccione **Pedido de cliente**.
6. En la barra de búsqueda, introduzca **Seattle**, y seleccione la tienda de **Seattle** para la recogida. 
7. Seleccione **Aceptar** para aceptar la fecha actual como la fecha de la recogida.
9. Seleccionar **Pagar con tarjeta** para iniciar el pago.
10. Introduzca la cantidad del pago por tarjeta que se debe depositar. 
11. Complete el pago de depósito en el terminal de pago. 
12. Una vez que el depósito se pague, seleccione la opción de usar la misma tarjeta para el cumplimiento, y espere a que el pedido esté completado. 
13. Iniciar el sistema PDV para la tienda de Seattle.
14. En el PDV, en la página de inicio, seleccione la operación **Pedidos a recoger** para ver los pedidos para recoger en el almacén. 
15. Seleccione una o más líneas del pedido que se ha creado en el escaparate de referencia y, a continuación seleccione **Recoger**.

    El pedido se recupera de la oficina administrativa. 

16. Cuando los detalles de la línea de pedido se recuperan de la oficina y se detecta un pago de tarjeta que se puede usar para el omnicanal, se le informará de que un método de pago está disponible.
17. Seleccione **Usar método de pago disponible** para completar la transacción mediante los detalles de la tarjeta que se especificaron en el escaparate de referencia.

    Las líneas de pedido se cargan en la página de la transacción, y el saldo pendiente es 0 (cero).

18. Seleccione la pestaña **Pagos** para la línea de pago que se sacó del pedido en línea. 
19. Seleccione cualquier método de pago para completar la transacción. 

### <a name="buy-in-store-a-ship-to-customer"></a>Comprar en la tienda A, enviar al cliente

1. Iniciar el sistema PDV para la tienda de Houston.
2. En la página **Transacción**, agregue Karen Berg a la transacción mediante el teclado numérico especificando **2001**.
3. Agregue una o más líneas a la transacción.
4. Seleccione **Pedidos** para ver opciones de pedido.
5. Seleccione **Enviar todo** y, a continuación, cuando el sistema lo solicite, seleccione **Pedido de cliente**.
6. En la página del método de envío, seleccione **Estándar nocturno** y después seleccione **Aceptar** para aceptar la fecha actual como fecha de envío. 
7. Seleccione **Aceptar** para aceptar la fecha actual como la fecha de la recogida.
8. Seleccionar **Pagar con tarjeta** para iniciar el pago.
9. Introduzca la cantidad del pago por tarjeta que se debe depositar. 
10. Complete el pago de depósito en el terminal de pago. 
11. Una vez que el depósito se pague, seleccione la opción de usar la misma tarjeta para el cumplimiento, y espere a que el pedido esté completado.

Cuando el pedido sea recogido, empaquetado y facturado en el área de operaciones,, los detalles de pago que se proporcionan en el sistema PDV se usarán para recuperar los fondos de mercancías que se envían al cliente. 

## <a name="scenario-details"></a>Detalles del escenario

Además de los escenarios básicas que se acaban de describir, se han realizado varios mejoras al SDK de pagos para admitir pagos de omnicanal. 

### <a name="pos"></a>PDV

#### <a name="single-swipedip-for-customer-orders"></a>Solos una pasada/toque por pedido del cliente

Antes de que la característica de los pagos de omnicanal fuera implementada, cuando los pedidos de cliente que incluían depósitos se creaban en el PDV, requerían a la los clientes pasar (o tocar) su tarjeta dos veces: una vez para el pago del depósito y otra para crear el token de tarjeta para el cumplimiento posterior del pedido. Cuando está activada la función de tokenization de omncanal, los clientes deben pasar la tarjeta sólo una vez al pagar el depósito y autorizar el importe debido por las mercancías que se entregarán posteriormente. En el momento del cumplimiento, se obtienen los fondos autorizados. Antes de que la función de tokenization de omnicanal fuera implementada, sólo un token recurrente de la tarjeta se creaba para el cumplimiento posterior del pedido. Por lo tanto, los fondos para el cumplimiento pendiente no se autorizaban, y ya que los fondos no eran retenidos para esa compra específica, era menos probable que pudieran se recuperarán posteriormente.

> [!NOTE]
> Un único pase una tarjeta no se admite en la versión 8.1.3 comercial. Los pedidos de cliente en la versión 8.1.3 usan el mismo flujo usado antes de que la función de tokenization de omnicanal fuera implementada. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Tarjetas que no pueden emitir tokens de tarjeta recurrentes

Algunas tarjetas no se pueden usar para los pagos de omnicanal, ya que no admiten emitir tokens de tarjetas recurrentes. Cuando un pedido se crea en el PDV, si el depósito se paga mediante una tarjeta que no soporte tokens de tarjeta recurrentes, se usa el flujo anterior de tokenización de tarjeta. Por lo tanto, un cliente que desea proporcionar un pago que se usará para la posterior del pedido debe presentar una segunda tarjeta. Si la segunda tarjeta no admite a tokens de tarjeta recurrentes, la acción de tokenización se rechazará, y se le solicitará al cajero pedir al cliente que proporcione otra tarjeta. 

### <a name="using-a-different-card"></a>Usar una tarjeta distinta

Un cliente que llega a la tienda para la recogida del pedido tiene la opción de usar otra tarjeta. Cuando el cajero recibe la consulta **Usar método de pago disponible** en el momento de recogida del pedido, puede preguntar si el cliente desea usar la misma tarjeta. Si el cliente ha perdido la tarjeta que se usó para crear el pedido y desea pagar la orden mediante otra tarjeta, el cajero puede seleccionar **Usar otro método de pago**. Si el cliente vuelve después para recoger más elementos para el mismo pedido, si la autorización original de la tarjeta no es válida, el cajero puede preguntar de nuevo si el cliente desea usar esa tarjeta.

### <a name="invalid-authorizations"></a>Autorizaciones no válidas

Si la tarjeta que se usó para crear una orden ya no es válida, cuando los productos se seleccionan para la recogida la solicitud de captura de pago fracasará. El conector de pago del PDV intentará entonces crear una nueva autorización y captura con los detalles de la misma tarjeta. Si falla la nueva autorización o captura, el cajero será informado de que el pago no ha podido ser procesado. El cajero debe a continuación obtener un nuevo pago del cliente. 

### <a name="multiple-available-payments"></a>Pagos múltiples disponibles

Cuando un pedido que tenga varias líneas y formas de pago se recoge, primero el cajero recibe el mensaje **Usar método de pago disponible**. Si hay varios tarjetas, cuando el cajero selecciona **Usar método de pago disponible**, las líneas existentes de forma de pago con tarjeta se capturarán hasta que el saldo se cumpla para las mercancías que se están recogiendo. El cajero no tendrá la opción de seleccionar la tarjeta que se debe usar para las mercancías que se están recogiendo. 

## <a name="related-topics"></a>Temas relacionados

- [Preguntas frecuentes sobre pagos](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Conector de pago de Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
- [Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-bopis)

