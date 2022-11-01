---
title: Limitar el uso del símbolo (token) de pago
description: Este artículo describe la característica que limita cómo se utilizan los tokens de pago en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709670"
---
# <a name="limit-payment-token-usage"></a>Limitar el uso del símbolo (token) de pago

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artículo describe la característica que limita cómo se utilizan los tokens de pago en Microsoft Dynamics 365 Commerce. El uso del token está restringido al alcance de una orden de venta o, si se otorga el consentimiento del cliente, se almacena como una tarjeta en el archivo.

## <a name="key-terms"></a>Términos clave

| Condición | Description |
|---|---|
| Token | Un blob XML al que se hace referencia en el sistema Dynamics 365 que almacena referencias de pago con fines transaccionales. |
| Tarjeta en archivo | Un token de referencia de tarjeta guardado que se acuerda para uso futuro en el sistema Dynamics 365 o la pasarela de pago y que es específico para la cuenta de un cliente. |

Los límites en el uso de tokens de pago se aplican a cualquier entorno que utilice un servicio de pasarela de pago donde se emplean tokens recurrentes. El [Conector de pago de Dynamics 365 para Adyen](adyen-connector.md) listo para usar utiliza tokens de pago recurrentes para realizar acciones de pedidos posteriores, como ajustes de autorización y reautorizaciones.

Para ayudar a controlar cómo se utilizan estos tokens de pago recurrente en todo el sistema, la característica **Restringir el uso del token de pago al contexto del pedido** limita el uso de un token recurrente al alcance de una orden de venta en el sistema. Cuando está habilitada, la característica modifica la interfaz de usuario (IU) de Commerce headquarters al actualizar las páginas de entrada de pago y limitar la capacidad de seleccionar referencias de pago de clientes anteriores para usar en nuevas instancias de transacción.

Esta característica ayuda a cumplir con las reglas de uso de algunos emisores de pagos, como Visa. En sus [Reglas principales de Visa y Reglas de productos y servicios de Visa](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf), Visa especifica que el uso de tokens de pago debe restringirse al alcance de una transacción a menos que el titular de la tarjeta acuerde lo contrario.

La característica **Restringir el uso del token de pago al contexto del pedido** es relevante solo si está utilizando un servicio de pasarela de pago que emplea referencias de token de pago recurrentes.

## <a name="enable-the-feature"></a>Habilitar la característica

Para habilitar la característica **Restringir el uso del token de pago al contexto del pedido**, en Commerce headquarters para su entorno, vaya a **Espacios de trabajo \> Gestión de características**, busque y seleccione **Restringir el uso del token de pago al contexto del pedido** en la lista y luego seleccione **Habilitar ahora**.

## <a name="limit-payment-token-usage"></a>Limitar el uso del símbolo (token) de pago

Cuando la función está habilitada, las páginas de Commerce headquarters que se utilizan para la captura de métodos de pago actualizarán la forma en que hacen referencia a los métodos de pago del cliente que están archivados para el cliente. Esta actualización afectará principalmente a dos áreas de operación:

- Cómo se ingresa una tarjeta de cliente registrada en nombre de un cliente
- Cómo se almacena la información de pago contra un cliente para futuras entradas de pago de órdenes de venta

Cuando un cliente realiza una transacción en los canales de Commerce, los detalles de pago se almacenan con un contexto de pedido de ventas. El contexto del pedido de ventas limita el token de pago para que no se utilice como referencia de pago en el registro del cliente en las páginas de pago para pagos de pedidos de ventas nuevos o editados en Commerce headquarters.

### <a name="payment-form-changes"></a>Cambios en la forma de pago

Cuando un usuario del centro de llamadas o de Commerce headquarters realiza un pago para un cliente contra un pedido de ventas, la página de pago presenta los detalles de selección del método de pago. Cuando la función **Restringir el uso del token de pago al contexto del pedido** está habilitada, si un usuario selecciona el signo más (**+**) en la página de pago, solo se muestran los registros de "tarjeta en archivo" guardados. Los cambios requieren que el centro de llamadas o el usuario de Commerce headquarters ingrese los detalles de pago completos que el cliente proporcionó cuando completó el formulario en la página **Ingresar la información de pago del cliente** para la nueva transacción de orden de venta.

La lista de valores para el campo **Número** incluye solo las referencias de tarjeta que están asociadas con el cliente que tiene la tarjeta registrada. Filtra cualquier referencia de pago anterior que no esté en el ámbito de un pedido de ventas.

El signo más (**+**) bajo el campo **Número** permanece disponible y se puede usar para ingresar la información de pago que el cliente proporcionó para la transacción asociada con el pedido de ventas que se está procesando.

### <a name="how-cards-on-file-work"></a>Cómo funcionan las tarjetas en archivo

Cuando la función **Restringir el uso del token de pago al contexto del pedido** está habilitada, una tarjeta registrada es un token de pago recurrente que se guarda en el registro de un cliente y no se limita al alcance de una orden de venta. Una tarjeta registrada permite una referencia rápida para los usuarios de Commerce headquarters cuando completan la página de pago para un nuevo pago de pedido de ventas. Esta referencia de token solo se aplica al entorno de Dynamics 365. Para canales en línea que usan un servicio de pasarela de pago que permite a los usuarios guardar un método de pago para usarlo en el futuro en el módulo iFrame de pagos, la pasarela de pago almacena de forma segura estas referencias como una referencia separada a la tarjeta de Dynamics 365 en el archivo.

Por ejemplo, si el Dynamics 365 Commerce Payment Connector para Adyen se utiliza en un canal en línea, los clientes que ingresan la información de su tarjeta de crédito en el modulo iFrame de pago solo ven las referencias de tarjetas guardadas del servicio de puerta de enlace para su próxima compra en línea cuando se autentican. No ven la tarjeta almacenada en el archivo del entorno de Dynamics 365 como una opción en el módulo iFrame de pago. De manera similar, cuando los compradores realizan un pedido a través del centro de atención telefónica, las referencias de sus tarjetas guardadas en línea no se presentan como opciones para el usuario del centro de atención telefónica. El usuario del centro de llamadas solo ve la tarjeta anterior en las referencias del archivo del sistema Dynamics 365 (según lo acordado por el cliente) para guardarlas para futuros pedidos.

Los usuarios de Commerce headquarters pueden guardar una tarjeta en el archivo de un cliente yendo a **Venta minorista y comercio \> Clientes** y seleccionando el registro de la cuenta del cliente. En la sección **Cliente \> Configurar**, los usuarios que tienen permisos para procesar las páginas de pago pueden utilizar la página de entrada de **Tarjetas de crédito** para ingresar una tarjeta de pago que se almacenará en el archivo para transacciones futuras. Esta operación ayuda a ahorrar tiempo cuando se procesan pagos de órdenes de venta futuras para el cliente. Los usuarios del centro de llamadas y de Commerce headquarters deben ingresar la tarjeta en los detalles de la tarjeta de archivo solo si el cliente acepta usar la referencia de la tarjeta para transacciones futuras.

La casilla de verificación **Guardar para uso futuro** en la parte inferior de las páginas de pago de Commerce headquarters permite a los usuarios guardar la tarjeta en un archivo para usarla en el futuro. Esta casilla de verificación debe usarse solo si el cliente acepta usar la tarjeta registrada para transacciones futuras. Puede mostrar o restringir la casilla de verificación **Guardar para uso futuro** mediante la opción **Permitir tarjeta de cliente en archivo** en la pestaña **Pago** de la página **Parámetros del centro de llamadas** en Commerce headquarters. Cuando esta opción se establece en **Sí**, los usuarios de Commerce headquarters que tienen permisos para procesar páginas de pago pueden guardar una tarjeta en archivo mediante la casilla **Guardar para uso futuro**. Cuando la opción se establece en **No**, la casilla de verificación no está disponible para los usuarios de Commerce headquarters que tienen permisos para procesar páginas de pago. La opción **Permitir tarjeta de cliente en archivo** se puede usar si su empresa desea restringir el uso de tokens recurrentes en Commerce headquarters, pero aún no desea permitir que se guarde una tarjeta en el archivo sin un procedimiento para garantizar que se otorgue el consentimiento del cliente.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>Páginas de Commerce headquarters donde se aplican las restricciones de tokens recurrentes

El alcance de la restricción de tokens afecta las siguientes áreas en Commerce headquarters cuando la función está habilitada:

- Información de pago del cliente en **Órdenes de venta \> Pagos \> Introducir pago del cliente**
- Pedidos de continuidad
- Planes de pagos
- Pagos de tarjeta de crédito de clientes

### <a name="manage-payment-tokens-archiving-or-removal"></a>Administrar tokens de pago (archivo o eliminación)

Los tokens de pago que se crearon antes de que el indicador de función **Restringir el uso del token de pago al contexto del pedido** estuviese habilitado (o mientras la función estaba deshabilitada) permanecerá "sin alcance" en el sistema y se puede hacer referencia en las listas de selección en la página de pago de Commerce headquarters. Estos tokens se pueden eliminar regularmente de dos maneras en Commerce headquarters:

- Utilizar la página **Archivar datos de transacciones de tarjetas de crédito** para configurar un trabajo que purgue o archive periódicamente los tokens de pago. Si configura la opción **Eliminar datos sin archivar** como **Sí**, los tokens que cumplen con la **Edad mínima de transacción (en días)** se eliminarán. Para obtener más información, consulte [Archivar datos de transacciones de tarjeta de crédito](archive-cc-data.md).
- Usar la nueva página **Purgar tokens de tarjetas de crédito** (**Cuentas por cobrar \> Consultas e informes \> Limpiar \> Purgar tokens de tarjetas de crédito**), que le permite ejecutar o configurar un trabajo por lotes que elimina tokens de pago. Configure los siguientes parámetros:

    - El valor **Edad mínima del token en días** debe ser de 90 días o más.
    - La configuración de **Ejecutar en segundo plano** se puede utilizar para definir los ajustes de **Reaparición** o **Alertas**.
    - Se puede asignar un grupo de lotes para ejecutar la tarea para un grupo específico.
    - Si la opción **Privado** está configurada como **Sí**, solo el usuario que crea el trabajo puede ejecutarlo.
    - Un ajuste de **Sí** para la opción **Trabajo crítico** garantiza que el sistema realice un seguimiento activo del estado del trabajo.

Los tokens eliminados no se pueden recuperar. Seleccione el campo **Edad mínima del token en días** con un rango que se adapte a la vida transaccional de mayor duración para su entorno (desde la autorización hasta la captura o el reembolso).

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas frecuentes sobre pagos](payments-retail.md)

[Módulo de finalización de compra](../add-checkout-module.md)

[Módulo de pago](../payment-module.md)
