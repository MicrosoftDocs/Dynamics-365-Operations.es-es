---
title: Trabajar con artículos serializados en el PDV
description: Este tema explica cómo administrar artículos serializados en la aplicación de punto de venta (POS).
author: boycezhu
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7b1b004d7a910e3b53eb584dbceb4d52d41fe409
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022692"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Trabajar con artículos serializados en el PDV

[!include [banner](includes/banner.md)]

Muchos minoristas venden productos que requieren control de serie. Estos productos se denominan *artículos serializados*. Algunos minoristas pueden querer mantener números de serie en la tienda o el inventario del almacén para fines de seguimiento. Otros minoristas pueden querer capturar números de serie durante el proceso de venta, para fines de servicio y garantía. Este tema explica cómo puede administrar artículos serializados en la aplicación de punto de venta (PDV) de Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configuración de número de serie

Un artículo se considera un artículo serializado si se le asigna un grupo de dimensiones de seguimiento configurado para permitir números de serie. En la central de Commerce, en la página **Seguimiento de grupos de dimensiones**, seleccione la opción **Activo** para habilitar los números de serie para el proceso de inventario, o seleccione la opción **Activo en proceso de venta** para habilitar números de serie para el proceso de venta.

En la ficha desplegable **Dimensiones de seguimiento**, active el parámetro **Recibo en blanco permitido** para permitir que el número de serie sea una entrada opcional durante el proceso de recepción de inventario de elemento serializado. La desactivación de este parámetro obliga a que el número de serie sea una entrada obligatoria. Del mismo modo, el parámetro **Problema en blanco permitido** controla si se requiere el número de serie durante el proceso de envío de inventario.

> [!NOTE]
> Para usar las operaciones de PDV **Inventario entrante** e **Inventario saliente** para registrar o validar números de serie frente a un artículo serializado, debe configurar ese artículo para que se asigne un grupo de dimensiones de seguimiento que esté configurado para permitir números de serie para la opción **Activo**, no la opción **Activo en el proceso de ventas**.

## <a name="serial-number-management-page"></a>Página de administración de números de serie

En las operaciones de PDV **Inventario entrante** e **Inventario saliente**, si el artículo que se selecciona, recibe o envía es un artículo serializado, el panel **Detalles** contiene una opción **Administrar número de serie** que se vincula con la página **Administración de números de serie** donde puede registrar o validar los números de serie del artículo. Alternativamente, puede abrir la página **Gestión del número de serie** bien seleccionando la acción **Número de serie** en la barra de aplicaciones de la vista de detalles del pedido o seleccionando la opción **Administrar número de serie** en el cuadro de diálogo que le aparecerá durante el proceso de recepción o envío. 

La página **Gestión del número de serie** enumera todas las líneas de número de serie abiertas que están pendientes de registro o validación. Puede haber dos pestañas en esta página: una para el artículo actual y otra para todos los artículos serializados del pedido.

El campo **Estado** de la página **Gestión del número de serie** proporciona información sobre la etapa actual en la que se encuentra cada número de serie:

- **No registrado**: el número de serie no se ha proporcionado o el número de serie registrado previamente aún no se ha validado (en el proceso de recepción).
- **Registrando**: el número de serie se ha registrado y guardado localmente en la base de datos de canales de la tienda, o se ha validado el número de serie registrado previamente. Solo los números de serie que tienen un estado de **Registrando** se enviarán a la sede de Commerce cuando termine de recibir o el cumplimiento.

## <a name="receive-serialized-items"></a>Recibir artículos serializados

La operación de PDV **Inventario entrante** permite a los usuarios realizar las siguientes tareas para los artículos serializados:

- Registre los números de serie con los artículos serializados cuando dichos artículos se reciban en la tienda mediante un pedido de compra.
- Valide los números de serie registrados previamente con los artículos serializados cuando dichos artículos se reciban en la tienda mediante un pedido de compra u orden de transferencia.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de serie frente a artículos serializados

Para una orden de compra, aparecerá un cuadro de diálogo con la opción **Administrar número de serie** durante el proceso de recepción de un artículo serializado. Puede seleccionar esa opción para abrir la página **Gestión del número de serie** y comenzar a registrar números de serie. También puede omitir este paso durante el proceso de recepción y proporcionar la entrada más tarde, antes de que se contabilice el recibo.

Por defecto, se muestra la pestaña para el artículo actual. Todas las líneas de números de serie tienen un valor de número de serie vacío y un estado de **No registrado**. Puede escanear códigos de barras de números de serie o puede seleccionar **Número de serie** en la barra de la aplicación para introducir continuamente números de serie. Los números de serie que introduce aparecen en la lista, y su estado se cambia a **Registrando**. El número máximo de números de serie que puede registrar en la lista es igual a la cantidad de recepción. Si comete un error, puede seleccionar **Editar** o **Limpiar** en el panel **Detalles** para realizar cambios en los números de serie que ha introducido.

También puede registrar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere registrar números de serie.

### <a name="validate-serial-numbers-on-serialized-items"></a>Validar números de serie en artículos serializados

Para una orden de transferencia, el lado de salida debe registrar previamente los números de serie de los artículos serializados durante el proceso de envío. Para un pedido de compra, el proveedor puede proporcionar información sobre el número de serie a través de un aviso de envío anticipado (ASN), y usted puede registrar previamente los números en los artículos que se enviarán. En ambos casos, los números de serie se conocen antes del recibo. Por lo tanto, en el lado de entrada, solo tiene que validar que recibió lo que se suponía que debía recibir.

Para validar los números de serie, puede abrir la página **Gestión del número de serie**, ya sea durante el proceso de recepción o en cualquier momento antes de que se contabilice el recibo. Para cada artículo serializado que tiene números de serie registrados previamente, todos los números de serie se configuran automáticamente en un estado inicial de **No registrado** en esta página. Para validar los números de serie, puede escanearlos o introducirlos. A medida que se introduce el número de serie, la aplicación valida si coincide con los números de serie registrados previamente. Si coinciden, sus estados cambian a **Registrando**. En caso contrario, recibirá un mensaje de error. Alternativamente, puede seleccionar directamente un número de serie y luego seleccionar la opción **Validar el número de serie** en el panel **Detalles** para marcar rápidamente ese número de serie como validado. El número máximo de números de serie que puede validar en la lista es igual a la cantidad de recepción.

También puede validar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere validar números de serie.

## <a name="ship-serialized-items"></a>Enviar artículos serializados

Puede usar la operación de PDV **Inventario saliente** para registrar números de serie respecto a artículos serializados al enviarlos fuera de la tienda actual mediante una orden de transferencia.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de serie frente a artículos serializados

Para transferir orden, aparecerá un cuadro de diálogo con la opción **Administrar número de serie** durante el proceso de envío de un artículo serializado. Puede seleccionar esa opción para abrir la página **Gestión del número de serie** y comenzar a registrar números de serie. También puede omitir este paso durante el proceso de envío y proporcionar la entrada más tarde, antes de que se registre el envío.

Por defecto, se muestra la pestaña para el artículo actual. Todas las líneas de números de serie tienen un valor de número de serie vacío y un estado de **No registrado**. Puede escanear códigos de barras de números de serie o puede seleccionar **Número de serie** en la barra de la aplicación para introducir continuamente números de serie. Los números de serie que introduce aparecen en la lista, y su estado se cambia a **Registrando**. El número máximo de números de serie que puede registrar en la lista es igual a la cantidad de recepción de envío. Si comete un error, puede seleccionar **Editar** o **Limpiar** en el panel **Detalles** para realizar cambios en los números de serie que ha introducido.

También puede registrar números de serie en la pestaña **Todos los artículos serializados** de la página **Gestión del número de serie**. En la lista, seleccione el artículo contra el que quiere registrar números de serie.

Opcionalmente, puede habilitar la validación de la disponibilidad del número de serie durante el registro del número de serie respecto a una orden de transferencia saliente. Con esta validación, si intenta enviar un número de serie que no está disponible en el inventario de la tienda de envío, recibirá un mensaje de error y deberá proporcionar un número diferente.

Para habilitar dicha validación, como requisito previo, debe programar los siguientes trabajos para que se ejecuten de forma periódica:

- **Retail y Commerce** > **Retail y Commerce IT** > **Productos e inventario** > **Disponibilidad de producto con dimensiones de seguimiento**
- **Retail y Commerce** > **Programas de distribución** > **1130** (**Disponibilidad del producto**)

## <a name="sell-serialized-items-in-pos"></a>Vender artículos serializados en PDV

Aunque la aplicación PDV siempre ha admitido la venta de artículos serializados, en la versión 10.0.17 de Commerce y posteriores, las organizaciones pueden habilitar la funcionalidad que mejora la lógica comercial que se activa al vender productos configurados para el seguimiento de números de serie.

Cuando la característica **Validación mejorada de números de serie en la captura y el procesamiento de pedidos de PDV** está habilitada, se evalúan las siguientes configuraciones de productos cuando se venden productos serializados en PDV:

- Configuración **Tipo serie** para el producto (**activo** o **activo en ventas**).
- Configuración de **Emisión en blanco permitida** para el producto.
- Configuración de **Inventario negativo físico** para el producto o el almacén de venta.

### <a name="active-serial-configurations"></a>Configuraciones de números de serie activas

Cuando se venden artículos en PDV que están configurados con una dimensión de seguimiento de números de serie **Activa**, PDV inicia la lógica de validación que evita que los usuarios completen la venta de un artículo serializado con un número de serie que no se encuentra en el inventario actual del almacén de venta. Hay dos excepciones a esta regla de validación:

- Si el artículo también está configurado con la opción **Emisión en blanco permitida** habilitada, los usuarios pueden omitir la entrada del número de serie y vender el artículo sin la designación del número de serie.
- Si el artículo o el almacén de venta están configurado con la opción **Inventario negativo físico** habilitada, la aplicación acepta y vende un número de serie que no se puede confirmar que esté en el inventario del almacén al que se vende. Esta configuración permite que la transacción de inventario para ese artículo/número de serie específico sea negativa y, por lo tanto, el sistema permitirá las ventas de números de serie desconocidos.

> [!IMPORTANT]
> Para asegurarse de que la aplicación PDV pueda validar correctamente si los números de serie que se venden para artículos de tipo serie **Activos** están en el inventario del almacén de venta, es necesario que las organizaciones ejecuten frecuentemente el trabajo **Disponibilidad de producto con dimensiones de seguimiento** en la sede central de Commerce y el trabajo de distribución de disponibilidad de producto **1130** acompañante a través de la sede central de Commerce. A medida que se recibe nuevo inventario serializado en los almacenes de venta, para que el PDV valide la disponibilidad de inventario de los números de serie que se venden, el maestro de inventario debe actualizar con frecuencia la base de datos del canal con los datos de disponibilidad de inventario más actualizados. El trabajo **Disponibilidad de producto con dimensiones de seguimiento** crear una instantánea actual del inventario maestro, incluidos los números de serie, para todos los almacenes de la empresa. El trabajo de distribución **1130** capta esa instantánea de inventario y la comparte con todas las bases de datos de canal configuradas.

### <a name="active-in-sales-process-serial-configurations"></a>Activar configuraciones serie en el proceso de ventas

Los elementos configurados con la dimensión de serie como **Activo en proceso de venta** no pasan por ninguna lógica de validación de inventario, ya que esta configuración implica que los números de serie del inventario no están registrados previamente en existencias y los números de serie solo se capturan en el momento de la venta.  

Si también está configurado **Emisión en blanco permitido** para elementos configurados como **Activo en proceso de venta**, se puede omitir la entrada del número de serie. Si la opción **Emisión en blanco permitida** no está configurada, la aplicación requiere que el usuario introduzca un número de serie, aunque no se validará con el inventario disponible.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Aplicar números de serie al crear transacciones de PDV

La aplicación PDV solicita inmediatamente a los usuarios la captura del número de serie cuando se venda un artículo serializado, pero la aplicación permite a los usuarios omitir la entrada de números de serie hasta cierto punto en el proceso de venta. Cuando el usuario comienza a capturar el pago, la aplicación aplica y requiere la introducción del número de serie para cualquier artículo que no esté configurado para su entrega en futuros envíos o recolecciones. Cualquier artículo serializado configurado para pago al contado sin entrega a domicilio o para reparto requiere que el usuario capture el número de serie (o acepte dejarlo en blanco si la configuración del artículo lo permite) antes de completar la venta.

Para artículos serializados vendidos para recogida o envío futuro, los usuarios de PDV pueden omitir la introducción del número de serie inicialmente y aún así completar la creación del pedido del cliente.   

> [!NOTE]
> Al vender o procesar productos serializados a través de la aplicación PDV, se aplica la cantidad "1" para los artículos serializados en la transacción de ventas. Este es el resultado de cómo se hace el seguimiento de la información de números de serie en la línea de ventas. Al vender o completar una transacción para varios artículos serializados a través de PDV, cada línea de ventas debe configurarse únicamente con una cantidad de "1". 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Aplicar números de serie durante el procesamiento o la recogida del pedido del cliente

Al procesar líneas de pedido de cliente para productos serializados mediante la operación **Procesamiento de pedido** en PDV, PDV impone la captura del número de serie antes del procesamiento final. Así, si no se proporcionó un número de serie durante la captura inicial del pedido, debe capturarse durante los procesos de recolección, empaquetamiento o envío en PDV. Se realiza una validación en cada paso y solo se le pedirá al usuario los datos del número de serie si este falta o ya no es válido. Por ejemplo, si un usuario omite los pasos de recoger o empaquetar, e inicia inmediatamente un envío sin que se haya registrado un número de serie para la línea, el PDV requerirá que se introduzca el número de serie antes de completar el paso final de la factura. Al aplicar la captura del número de serie durante las operaciones de procesamiento de pedidos en PDV, todas las reglas mencionadas anteriormente en este tema siguen siendo aplicables. Solo los artículos serializados configurados como **Activo** pasan por una validación de existencias de inventario de número de serie. Los artículos configurados como **Activo en proceso de ventas** no se validarán. Si se permite un **Inventario negativo físico** para productos **Activos**, se aceptará cualquier número de serie, con independencia de la disponibilidad en existencias. Para los artículos de tipo **Activo** y **Activo en proceso de ventas**, si se configura **Emisión en blanco permitida**, un usuario puede dejar los números de serie en blanco si lo desea durante los pasos de recogida, embalaje y envío.

Las validaciones de los números de serie también se producirán cuando un usuario realice las operaciones de recogida de los pedidos de los clientes en PDV. La aplicación PDV no permite finalizar la recogida de un producto serializado a menos que pase las validaciones, como se mencionó anteriormente. Las validaciones siempre se basan en la dimensión de seguimiento del producto y las configuraciones del almacén de venta. 

## <a name="additional-resources"></a>Recursos adicionales

[Operación de inventario entrante en PDV](./pos-inbound-inventory-operation.md)

[Operación de inventario de salida en PDV](./pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]