---
title: Mejoras de cXML de compra
description: La característica Mejoras de cXML de compra se basa en la funcionalidad de catálogo externo existente, llamada marcaje de salida, que se utiliza para las solicitudes de compra.
author: dasani-madipalli
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatCXMLParameters, CatCXMLPurchRequest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f3bc63fd4b1017a5c96116ff6c9bbcc387869927
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825287"
---
# <a name="purchasing-cxml-enhancements"></a>Mejoras de cXML de compra

[!include [banner](../includes/banner.md)]

La característica _Mejoras de cXML de compra_ se basa en la [funcionalidad de catálogo externo existente](set-up-external-catalog-for-punchout.md) que se utiliza para las solicitudes de compra. Esta funcionalidad existente se conoce como _marcaje de salida_. Aunque un pedido de compra no tiene que originarse a partir de una solicitud de compra, debe haber una conexión entre el proveedor en un pedido de compra y los parámetros que se utilizan para enviar el documento del pedido de compra.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>Activar la característica Mejoras de cXML de compra

Para activar la característica, abra la página **[Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y busque la característica denominada *Mejoras de cXML de compra*. Seleccione la característica y, a continuación, seleccione **Habilitar ahora** para activarla.

Después de activar la característica, debe establecer su configuración en las tres áreas siguientes:

- **[Parámetros de cXML](#cxml-parameters)**: use esta opción de configuración para establecer algunos de los parámetros globales para la funcionalidad de envío de pedidos de compra.
- **[Configuración de proveedor](#vendor-setup)**: si hubiera que utilizar el lenguaje de marcado extensible comercial (cXML) de forma predeterminada para todos los pedidos de compra nuevos que se crean para cualquier proveedor, establezca la opción **Enviar pedido de compra a través de cXML** en _Sí_ para ese proveedor.
- **[Catálogos externos](#external-catalog-setup)**: use la nueva opción configuración **Propiedades del pedido** para definir el formato del documento del pedido de compra y establecer cómo se envía.

En la siguiente ilustración se resume esta configuración.

![Áreas para configurar características cXML](media/cxml-settings-areas.png "Áreas para configurar características cXML")

Además, debe configurar el [Trabajo por lotes de solicitud de pedido de compra](#po-batch). Este trabajo por lotes se utiliza para enviar los pedidos de compra confirmadas.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a>Configurar parámetros de cXML globales

Use la página **Parámetros de cXML** para establecer algunas opciones de configuración globales que se aplican a la funcionalidad de envío de pedidos de compra.

![Página de parámetros de cXML](media/cxml-parameters.png "Página de parámetros de cXML")

Vaya a **Adquisiciones y abastecimiento \> Preparar \> Administración de cXML \> Parámetros de cXML** y establezca los siguientes parámetros:

- **Modo de prueba cXML**: este parámetro global afecta la forma en que los pedidos de compra se envían físicamente desde el trabajo por lotes. Seleccione uno de los siguientes valores:

    - **Prueba**: en este modo, el trabajo por lotes puede estar en ejecución, y el documento XML para el mensaje se genera, pero no se envía. En su lugar, se guarda en la solicitud de pedido de compra para fines de revisión. Este modo es útil cuando se está en una implementación inicial y se desea ver cómo se introducen los datos en el mensaje cXML. Es posible que también desee generar mensajes de ejemplo que se pueden enviar a los proveedores para la validación inicial.
    - **En directo**: en este modo, la característica utiliza la [configuración de catálogo externo](#external-catalog-setup) para transmitir físicamente cada documento al proveedor.

- **Enviar actualizaciones de solicitudes de compra**: establezca esta opción en *Sí* para enviar un mensaje de actualización para pedidos de compra. Establézcala en *No* para evitar que se envíe el mensaje. La mayoría de los proveedores prefieren no recibir mensajes de actualización. En cambio, requieren que los clientes se comuniquen con ellos por teléfono o correo electrónico para cambiar un pedido de compra. Este parámetro es un parámetro global, por lo que no se puede especificar ninguna anulación en el catálogo externo para cada proveedor. Un pedido de compra se marcará como actualizado si se registra una segunda confirmación en un pedido de compra y la primera confirmación ya ha sido enviada y confirmada por el proveedor. Si hay una segunda confirmación, pero no se ha enviado la primera confirmación, la segunda confirmación se tratará como un documento nuevo. Puede confirmar un pedido de compra tantas veces como desee hasta que se envíe una confirmación. La siguiente confirmación se tratará como un mensaje de actualización.
- **Enviar eliminaciones de solicitudes de compra**: establezca esta opción en *Sí* para enviar un un mensaje de eliminación para pedidos de compra. Establézcala en *No* para evitar que se envíe el mensaje. La mayoría de los proveedores prefieren no recibir mensajes de eliminación. En cambio, requieren que los clientes se comuniquen con ellos por teléfono o correo electrónico en caso de que se haya enviado por error un pedido de compra. Este parámetro es un parámetro global, por lo que no se puede especificar ninguna anulación en el catálogo externo para cada proveedor. Un pedido de compra se marcará como eliminado si cancela el pedido de compra en Supply Chain Management.
- **Archivo de almacenamiento**: especifique la ruta del archivo donde desea exportar y guardar los documentos cXML archivados. La ruta se usa cuando ejecuta la función de depuración desde la página **Solicitud de pedido de compra**.
- **Número máximo de caracteres para la línea de dirección**: escriba el número máximo de caracteres que se pueden usar en el campo de dirección para las direcciones del documento cXML. Este parámetro global afecta a todos los proveedores a menos que se especifique una anulación en las propiedades del catálogo externo.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a>Configurar pedidos de compra de proveedor para usar cXML

Cada vez que confirma un pedido de compra donde la opción **Enviar pedido de compra a través de cXML** esté establecida en _Sí_, el sistema genera automáticamente el mensaje cXML y se lo entrega al proveedor asociado a ese pedido de compra. Hay dos formas de controlar esta opción para sus pedidos de compra:

- Para configurar un proveedor de forma que utilice automáticamente cXML para todos los pedidos de compra nuevos que se crean a partir de una solicitud, vaya a **Adquisiciones y abastecimiento \> Proveedores \> Todos los proveedores** y seleccione o cree un proveedor para abrir su página de detalles. En la ficha desplegable **Valores predeterminados del pedido de compra**, establezca la opción **Enviar pedido de compra a través de cXML** en _Sí_. Si también hubiera que usar cXML automáticamente para nuevos pedidos de compra que **no** se han creado a partir de una solicitud, debe establecer la propiedad **ENABLEMANUALPO** del pedido en _Verdadero_ para el catálogo externo relacionado, como se describe en la sección [Establecer las propiedades del pedido](#set-order-properties) más adelante en este tema.
- Para pedidos de compra individuales, vaya a **Adquisiciones y abastecimiento \> Pedidos de compra \> Todos los pedidos compra** y seleccione o cree un pedido de compra para abrir su página de detalles. Cambie a la vista **Encabezado** y, en la ficha desplegable **Preparar**, establezca la opción **Enviar pedido de compra a través de cXML** según sea necesario.

![Configuración predeterminada para pedidos de compra de proveedores](media/cxml-order-defaults.png "Configuración predeterminada para pedidos de compra de proveedores")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a>Configurar un catálogo externo para usar cXML

En la página **Catálogos externos** para cada uno de sus catálogos, puede configurar la funcionalidad de marcaje de salida y la funcionalidad para enviar pedidos de compra. Para encontrar la configuración relevante, vaya a **Adquisiciones y abastecimiento \> Catálogos \> Catálogos externos**. Empiece por [configurar cada catálogo como de costumbre](set-up-external-catalog-for-punchout.md). Este proceso incluye la asignación de un proveedor, la selección de las categorías que el proveedor puede suministrar y la activación del catálogo. A continuación, configure los ajustes adicionales que se describen en esta sección.

> [!NOTE]
> Cuando confirma un pedido de compra que se puede enviar a través de cXML, el sistema busca el proveedor que está asociado con el pedido de compra y busca el primer catálogo externo activo que está asociado con ese proveedor. El sistema utiliza la configuración de ese catálogo externo para enviar el pedido de compra. Si se configuran varios catálogos externos, el sistema utiliza solo el primer catálogo externo que encuentra, según el proveedor del pedido de compra. Por lo tanto, le recomendamos que cree un solo catálogo externo por cada proveedor.

![Configuración de catálogo externo](media/cxml-supplier-catalog.png "Configuración de catálogo externo")

### <a name="set-the-punchout-protocol-type"></a>Establecer el tipo de protocolo de marcaje de salida

En la ficha desplegable **General** de la página **Catálogos externos**, establezca el campo **Tipo de protocolo de marcaje de salida** en _cXML_. Esta opción será la única disponible, a menos que un partner haya ampliado la funcionalidad y proporcione una opción adicional en la extensión.

Si también utiliza el catálogo para marcaje de salida, debe [configurar el formato de mensajes](set-up-external-catalog-for-punchout.md). El formato de mensaje se utiliza para establecer la conexión con el proveedor en la transacción de marcaje de salida desde la solicitud. Cuando se envía un pedido de compra, las propiedades del pedido se utilizarán para establecer la conexión con un proveedor.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a>Establecer las propiedades del pedido

la característica _Mejoras de cXML de compra_ agrega una nueva ficha desplegable **Propiedades del pedido** para catálogos externos. Esta ficha desplegable proporciona una cuadrícula en la que puede definir las propiedades del pedido. También proporciona una barra de herramientas. Esta barra de herramientas contiene los siguientes tres botones que puede utilizar para administrar las propiedades del pedido:

- **Propiedades predeterminadas**: al configurar un nuevo catálogo, seleccione este botón para agregar a la cuadrícula una colección predefinida de propiedades usadas habitualmente.
- **Nuevo**: agregar una nueva propiedad a la cuadrícula.
- **Eliminar**: eliminar de la cuadrícula la propiedad seleccionada actualmente. Si elimina accidentalmente una propiedad predeterminada, seleccione **Propiedades predeterminadas** para restaurar todas las propiedades que faltan.

Cada vez que agregue una o más propiedades a la cuadrícula, use la columna de la derecha para especificar un valor para cada una.

Utilice las propiedades predeterminadas de la siguiente manera:

- **BUYER\_COOKIE**: este campo de seguimiento se puede utilizar para indicar información específica para su empresa. A menos que tenga un acuerdo con el proveedor sobre cómo se usa esta propiedad, no tiene mucho sentido al enviar un pedido de compra. Por lo tanto, debe establecerlo en un valor simple.
- **DELIVERTO**: cuando se especifica la dirección de envío en el documento del pedido de compra, el campo **Información de advertencia** se utiliza para establecer el campo en **Entregar a** en el mensaje XML. Si necesita que este valor sea un nombre de solicitante y va a establecer el campo del solicitante en el encabezado del pedido de compra, especifique el valor _REQUESTER_ para esta propiedad de modo que se introduzca el nombre del solicitante en el campo **Entregar a** del código XML. En este caso, la dirección de correo electrónico principal y el número de teléfono que se utilizan serán del solicitante, no del ordenante.
- **DEPLOYMENTMODE**: establezca esta propiedad según lo requiera el proveedor. Los valores suelen ser _PRODUCTION_ o _TEST_. Establezca el valor según su comunicación con el proveedor. Por lo general, debe coincidir con el sistema previsto detrás del **ORDERCHECKURL** que el proveedor indica como sistema de pruebas o de producción.
- **FIXEDBILLADDRESSID**: cuando el campo **addressID** del mensaje XML está establecido, usa la ubicación que se especifica en la dirección. Si el valor de id. que ha comunicado al proveedor difiere del valor en la ubicación de la dirección por algún motivo, puede forzar una anulación especificando el valor aquí. Se supone que usará solo una dirección con el proveedor y que la dirección está configurada en el sistema del proveedor. La dirección de facturación es la dirección de facturación principal que se especifica para la entidad jurídica en Supply Chain Management.
- **FIXEDSHIPADDRESSID**: cuando el campo **addressID** del mensaje XML está establecido, usa la ubicación que se especifica en la dirección. Si el valor de id. que ha comunicado al proveedor difiere del valor en la ubicación de la dirección por algún motivo, puede forzar una anulación especificando el valor aquí. Se supone que usará solo una dirección con el proveedor y que la dirección está configurada en el sistema del proveedor. La dirección de envío es la dirección que se especifica en el encabezado del pedido de compra. La mayoría de los proveedores aceptan solo direcciones de encabezado, no direcciones de línea. Aunque hay campos para direcciones de línea en el código XML, se establecerán en la dirección del encabezado.
- **FROM\_DOMAIN**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **FROM\_IDENTITY**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **ORDERCHECKURL**: escriba la dirección URL a la que hay que transmitir los documentos de pedidos de compra. Esta dirección URL empieza por `https://` y la suministra el proveedor.
- **PAYLOAD\_ID**: especifique un valor de prefijo para el id. de carga útil, según sea necesario para los procesos empresariales establecidos para el proveedor actual.
- **SENDER\_DOMAIN**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **SENDER\_IDENTITY**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **SHARED\_SECRET**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **STREETLENGTH**: especifique un número que represente el número máximo de caracteres que el proveedor aceptará como nombre de calle. Si se especifica un valor aquí, anula el valor especificado en la página de **Parámetros de cXML**. El sistema quitará los saltos de línea y los espacios para intentar ajustar la dirección estándar en Supply Chain Management según el número de caracteres especificado aquí. Los caracteres adicionales se truncarán.
- **TO\_DOMAIN**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **TO\_IDENTITY**: especifique el valor que se utiliza para enviar documentos de pedidos de compra. Este valor lo proporciona el proveedor.
- **USERAGENT**: escriba un valor para identificar el sistema que está utilizando. Por ejemplo, escriba _Dynamics 365 Supply Chain Management_.
- **VERSION**: escriba un número de versión de cXML si el proveedor solicita esta información. La versión predeterminada es *1.2.008*. Esta versión es estable y la aceptan la mayoría de los proveedores.
- **RESPONSETEXT**: escriba cualquier texto personalizado que espera que el proveedor devuelva en el mensaje de respuesta cXML después de que se haya enviado el pedido. De esta forma, el sistema puede marcar el mensaje como _Confirmado_. Si la respuesta no coincide con el texto estándar o el texto del cliente que escriba aquí, la solicitud se marcará como _Error_.
- **RESPONSETEXTSUB**: establecer esta propiedad en _TRUE_ si desea buscar en el texto de respuesta del proveedor los valores especificados en el campo **RESPONSETEXT**. Por ejemplo, el proveedor puede devolver una cadena larga que incluya "OK" en la respuesta. En este caso, puede escribir _OK_ en el campo **RESPONSETEXT** y establecer **RESPONSETESTSUB** en _TRUE_ para buscar "OK" en cualquier parte de la respuesta. Una vez hecho esto, se puede establecer el pedido como _Admitido_.
- **CONTENTTYPE**: en una configuración de catálogo típica, no es necesario establecer esta propiedad. Si recibe un error 500 del servidor del sistema de un proveedor al enviar un pedido de compra, puede realizar pruebas configurando esta propiedad en _FALSO_. Ese valor cambiará una opción de configuración en la solicitud web y podría permitir el envío del mensaje para algunas plataformas.
- **ENABLEHEADERS**: establezca esta propiedad en _TRUE_ para enviar encabezados junto con el pedido de compra. Solo debe establecer esta propiedad si el proveedor lo requiere. Si establece esta propiedad en _TRUE_, agregue propiedades personalizadas adicionales basadas en los nombres que proporciona el proveedor, y anteponga _H\__. Algunos ejemplos típicos son **H\_USERID**, **H\_PASSWORD**, **H\_RECEIVERID** y **H\_ACTIONREQUEST**. Las siguientes propiedades personalizadas se incluyen en las propiedades predeterminadas:

    - **H\_USERID**: si el partner comercial requiere que envíe una identificación de usuario como parte de la dirección URL para enviar un pedido de compra, especifique su valor aquí.
    - **H\_PASSWORD**: si el partner comercial requiere que envíe una contraseña como parte de la dirección URL para enviar un pedido de compra, especifique su valor aquí.

- **ENABLEMANUALPO**: si esta propiedad se establece en _TRUE_, cuando los usuarios crean manualmente pedidos de compra (es decir, cuando no se crean a partir de una solicitud), esos pedidos de compra heredarán la configuración de la opción **Enviar pedido de compra a través de cXML** del proveedor. Si esta propiedad no se establece, o si se establece en _FALSE_, la opción **Enviar pedido de compra a través de cXML** no se establecerá en el encabezado del pedido de compra para los pedidos de compra creados manualmente. Para los pedidos de compra que se crean a partir de una solicitud, la configuración de la opción **Enviar pedido de compra a través de cXML** siempre se hereda del proveedor, con independencia de cuál sea la configuración de esta propiedad. Para obtener más información, consulte la sección [Configurar pedidos de compra de proveedor para usar cXML](#vendor-setup) más arriba en este tema.
- **PUNCHOUTPOONLY**: si esta propiedad se establece en _TRUE_, solo las líneas de solicitud de compra que se crean a partir del proceso de marcaje de salida establecerán la opción **Enviar pedido de compra a través de cXML** en el encabezado del pedido de compra. Además, el tipo de línea de la solicitud de compra de todas las líneas del pedido de compra debe ser _Elemento de catálogo externo_. De lo contrario, no se puede crear el pedido de compra cXML.
- **PUNCHOUTSHIPTO**: si esta propiedad se establece en _TRUE_, la dirección predeterminada de la entidad jurídica se agregará al mensaje de solicitud de configuración de marcaje de salida cuando el usuario abra un catálogo externo. Esta dirección se agrega como la dirección para **Enviar a**. Los proveedores utilizarán la dirección para **Enviar a** a fin de mostrar los precios según la ubicación de la empresa.
- **TRACEPUNCHOUT**: establezca esta propiedad en _TRUE_ si recibe un mensaje de error cuando intenta buscar un catálogo externo de la solicitud. A continuación se rellena la información de seguimiento para los mensajes **PunchOutSetupRequest** y **PunchOutResponse** que se envían entre Supply Chain Management y el sitio del proveedor. Puede ver esta información en la página **Registro de mensajes de carro de cXML**, que puede abrir desde la página **Configuración de catálogo externo** del catálogo de proveedores con el que tiene problemas. Solo debe establecer esta propiedad en _TRUE_ si está solucionando problemas, ya que crea una gran sobrecarga de rendimiento en la base de datos para cada marcaje de salida. Para obtener más información, consulte la sección [Ver el registro de mensajes de carro de cXML para el marcaje de salida del catálogo externo](#message-log) más adelante en este tema.
- **REPLACENEWLINE**: establezca esta propiedad en _TRUE_ en caso de que se produzca un problema debido a que el sistema de un proveedor envía un mensaje **PunchOutResponse** que incluye caracteres de nueva línea (\\n). Este problema puede producirse si los mensajes del proveedor se analizan a través de middleware o de un centro de compras. Si tiene un problema con la configuración de un nuevo proveedor, establezca la propiedad **TRACEPUNCHOUT** en _TRUE_ para ver el mensaje **PunchOutResponse** y determine si las etiquetas XML están divididas por caracteres de nueva línea.
- **POCOMMENTS**: establezca esta propiedad en _TRUE_ si desea que el documento cXML incluya notas adjuntas al pedido de compra en Supply Chain Management. El texto adjunto se incluye en los comentarios del encabezado en el mensaje del pedido de compra. Para obtener más información sobre cómo el sistema selecciona y procesa estos archivos adjuntos, consulte la sección [Adjuntar notas a un pedido de compra](#attach-po-notes) más adelante en este tema.
- **VENDCOMMENTS**: establezca esta propiedad en _TRUE_ si desea que el documento cXML incluya notas adjuntas al pedido de compra en Supply Chain Management. El texto adjunto se incluye en los comentarios del encabezado en el mensaje del pedido de compra. Para obtener más información sobre cómo el sistema selecciona y procesa estos archivos adjuntos, consulte la sección [Adjuntar notas a un pedido de compra](#attach-po-notes).
- **CLEANAMP**: establezca esta propiedad en _TRUE_ si recibe un mensaje de error al intentar hacer un marcaje de salida a un proveedor, y la dirección URL de retorno del proveedor incluye símbolos "et" (\&) codificados incorrectamente.
- **PUNCHOUTTZ**: establezca esta propiedad en _TRUE_ si el proveedor con el que está trabajando utiliza el estándar 8601 de la Organización Internacional de Normalización (ISO) para realizar una validación específica de la fecha y hora del mensaje de solicitud de marcaje de salida. Supply Chain Management utiliza la fecha de la hora universal coordinada (UTC) en el mensaje **PunchOutSetupRequest**. Por lo tanto, cuando establezca esta propiedad en _TRUE_, se agrega *+00:00* al formato de fecha/hora.
- **WMSADDRESSID**: establezca esta propiedad en _TRUE_ para utilizar el número de almacén en el encabezado del pedido de compra como valor de **addressID** en la dirección para **Enviar a** de la solicitud de pedido de compra que se envía al proveedor. Si establece un valor para la propiedad **FIXEDSHIPADDRESSID**, este valor tendrá prioridad. Por lo tanto, debe usar una propiedad u otra para establecer el valor de **addressID** en la dirección para **Enviar a** del documento.
- **PUNCHOUTSHIPTOUSER**: esta propiedad funciona junto con la propiedad **PUNCHOUTSHIPTO**. Si se establece **PUNCHOUTSHIPTO** en _TRUE_, se selecciona la dirección de la entidad jurídica. Si **PUNCHOUTSHIPTOUSER** se establece en _TRUE_, se utiliza la dirección principal del usuario de marcaje de salida en lugar de la dirección de la entidad jurídica.

### <a name="activate-the-external-catalog"></a>Activar el catálogo externo

Cuando haya terminado de configurar todas las propiedades y de establecer otras opciones configuración para su catálogo externo, vuelva a la ficha desplegable **General** de la página **Catálogos externos** y establezca la opción **Activo** en *Si*.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a>Adjuntar notas a un pedido de compra

Como se mencionó en la sección [Establecer las propiedades del pedido](#set-order-properties), si desea que el cXML entregado incluya texto de notas que se adjuntan al pedido de compra relevante o a los registros de proveedores, puede establecer las propiedades **POCOMMENTS** y/o **VENDCOMMENTOS** en _TRUE_ en la configuración del catálogo externo. Esta sección proporciona más detalles sobre cómo el sistema selecciona y procesa estos archivos adjuntos, si los usa.

Para configurar los tipos de notas que buscará el sistema, vaya a **Adquisiciones y abastecimiento \> Preparar \> Formularios \> Desde la configuración**. En la ficha **Pedido de compra** configure el campo **Incluir documentos de tipo** como el tipo de nota que desea poder incluir. Solo se incluirán notas de texto, no documentos adjuntos.

![Página de configuración de formulario](media/cxml-form-setup.png "Página de configuración de formulario")

Los archivos adjuntos solo se incluirán con un pedido de compra si el campo **Tipo** se establece en el valor que seleccione en el campo **Incluir documentos de tipo**, y si el campo **Restricción** está establecido en _Externa_. Para crear, ver o editar los archivos adjuntos de un pedido de compra, vaya a **Adquisiciones y abastecimiento \> Todos los pedidos de compra**, seleccione o cree un pedido de compra y luego haga clic en el botón **Archivos adjuntos** (símbolo de un clip) en la esquina superior derecha.

![Nota adjunta que está configurada para enviarse a un proveedor](media/cxml-note-to-vendor.png "Nota adjunta que está configurada para enviarse a un proveedor")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a>Ver el registro de mensajes de carro de cXML para el marcaje de salida del catálogo externo

Al establecer el campo **Tipo de protocolo de marcaje** en _cXML_ para un catálogo externo, el sistema capturará un registro de mensaje de los carros que regresan de los proveedores. Este registro se puede utilizar para solucionar problemas y para otros fines relacionados con datos.

Para abrir el registro de un catálogo externo, seleccione el catálogo relevante y, en el panel de acciones, seleccione **Registro de mensajes de carro de cXML**. La página **Registro de mensajes de carro de cXML** muestra una lista de carros que se han devuelto, el código XML relacionado con esos carros y las líneas que se crearon en la solicitud de compra relacionada.

![Página de registro de mensajes de carro de cXML](media/cxml-cart-message-log.png "Página de registro de mensajes de carro de cXML")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>Establecer los elementos extrínsecos para el marcaje de salida del catálogo externo

Al establecer el campo **Tipo de protocolo de marcaje** en *cXML* para un catálogo externo, puede agregar elementos extrínsecos personalizados que se insertarán en el lugar correcto del mensaje XML de solicitud.

Para agregar elementos extrínsecos a un catálogo externo, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Catálogos \> Catálogos externos**.
1. Seleccione el catálogo relevante.
1. En la ficha desplegable **Formato de mensajes**, en la sección **Extrínsecos**, seleccione **Agregar** para agregar una fila a la cuadrícula para cada elemento extrínseco que desee incluir. En cada fila, establezca los siguientes campos:

    - **Nombre**: escriba un nombre para el elemento. Este valor se convertirá en el valor del atributo **name** para el elemento XML **Extrínseco** creado por cada fila. Por lo general, trabajará con el proveedor para acordar el nombre de cada elemento extrínseco.
    - **Valor**: seleccione un valor para el elemento. Este valor se convertirá en el valor del elemento XML creado por cada fila. Los siguientes valores están disponibles:

        - **Nombre de usuario**: use el nombre del usuario que realiza el marcaje de salida. Este nombre es el nombre de inicio de sesión para Supply Chain Management.
        - **Correo electrónico de usuario**: use la dirección de correo electrónico del usuario que realiza el marcaje de salida. Esta dirección es la dirección que el usuario ha configurado en la pestaña **Cuenta** de la página **Opciones de usuario**.
        - **Valor aleatorio**: utilice un valor aleatorio único.
        - **Nombre completo del usuario**: utilice el nombre completo de la persona de contacto asociada al usuario que accede al catálogo externo.
        - **Nombre**: utilice el nombre de la persona de contacto asociada al usuario que accede al catálogo externo.
        - **Apellido**: utilice el apellido de la persona de contacto asociada al usuario que accede al catálogo externo.
        - **Número de teléfono**: utilice el número de teléfono principal de la persona de contacto asociada al usuario que accede al catálogo externo.

![Configuración de elementos extrínsecos](media/cxml-extrinsics.png "Configuración de elementos extrínsecos")

El usuario o administrador no verá los elementos extrínsecos, porque no se agregan hasta que el usuario realiza un marcaje de salida. Se insertarán automáticamente entre los elementos **BuyerCookie** y **BrowserFromPost** en el mensaje de solicitud de configuración cXML. Por lo tanto, no tiene que configurarlos manualmente en el código XML al configurar el catálogo externo.

![Elementos extrínsecos agregados al código XML](media/cxml-extrinsics-xml.png "Elementos extrínsecos agregados al código XML")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a>Crear y procesar un pedido de compra

Al crear un pedido de compra para un proveedor, heredará la configuración de la opción **Enviar pedido de compra a través de cXML** de ese proveedor. Sin embargo, el ajuste permanece disponible en la ficha desplegable **Preparar** en la vista **Encabezado** del pedido de compra, para que pueda cambiarla más tarde según sea necesario.

![Pedido de compra configurado para usar cXML](media/cxml-purchase-order.png "Pedido de compra configurado para usar cXML")

Al crear un pedido de compra a partir de una solicitud de compra que proviene de un flujo de marcaje de salida, se rellenarán todos los detalles de la línea requerida. Después puede agregar manualmente líneas de pedido de compra o copiarlas de otros pedidos de compra. Asegúrese de configurar todos los campos obligatorios. Estos campos obligatorios incluyen el número de referencia externo, que es el número de proveedor que se utilizará en el mensaje cXML.

![Ejemplo de un número de referencia externo](media/cxml-line-details.png "Ejemplo de un número de referencia externo")

Cuando haya terminado de rellenar todos los detalles del pedido de compra, asegúrese de confirmarlo. No se envía ningún mensaje a menos que se confirme el pedido de compra. Para confirmar un pedido de compra, en el panel de acciones, en la pestaña **Compra**, en el grupo **Acciones**, seleccione **Confirmar** para confirmar el pedido de compra. 

Una vez confirmado el pedido de compra, puede ver el estado de la confirmación a través de los diarios **Confirmaciones de pedidos de compra**. En el panel de acciones, en la ficha **Compra**, en el grupo **Diarios**, haga clic en **Confirmaciones de pedidos de compra**.

Cada pedido de compra puede tener muchas confirmaciones. Cada confirmación está marcada con un número incremental. En la siguiente ilustración, el pedido de compra es *00000275* y la confirmación es *00000275-1*. Esta numeración refleja la funcionalidad estándar de Supply Chain Management, en la que los cambios en una pedido de compra y, por lo tanto, el tipo de mensaje cXML que debe enviarse al proveedor, se identifican en función de la confirmación. Como muestra la ilustración, la página **Confirmaciones de pedidos de compra** también incluye los campos **Estado de envío del pedido** y **Estado de proveedor de solicitud de pedido**. Para obtener más información sobre los distintos valores de estado que puede ver en esta página, consulte la sección [Supervisar las solicitudes de pedido de compra](#monitor-po-requests) más adelante en este tema.

![Página de confirmaciones de pedidos de compra](media/cxml-po-confirmations.png "Página de confirmaciones de pedidos de compra")

Para ver más información sobre el documento, seleccione **Solicitud de pedido de compra** encima de la cuadrícula.

La página **Solicitud de pedido de compra** incluye dos cuadrículas. La cuadrícula en la parte superior de la página tiene un registro para cada pedido de compra que esté marcada para enviar. La cuadrícula de la ficha **Historial de solicitudes de pedido de compra** en la parte inferior de la página puede tener varios registros para el pedido de compra seleccionado, a fin de indicar el estado de cada confirmación. La siguiente ilustración muestra el pedido de compra 00000275 en la cuadrícula superior y el documento 00000275-1 en la cuadrícula de la ficha **Historial de solicitudes de pedido de compra**.

![Página de solicitud de pedido de compra](media/cxml-po-request.png "Página de solicitud de pedido de compra")

Si el trabajo por lotes está configurado y en ejecución, se enviará el documento. Puede ver el cambio de estado después de que se haya enviado el documento. En la siguiente ilustración, el campo **Estado de envío del pedido** está establecido en _Enviado_. El campo **Estado de proveedor de solicitud de pedido** está establecido en _Confirmado_ para indicar que el proveedor recibió el documento y pudo leerlo y almacenarlo en su sistema. La cuadrícula de la pestaña **Historial de solicitudes de pedido de compra** muestra la hora a la que se envió el documento. Para obtener más información sobre los distintos valores de estado que puede ver en esta página, consulte la sección [Supervisar las solicitudes de pedido de compra](#monitor-po-requests).

![Mensajes de estado en la página Solicitud de pedido de compra](media/cxml-po-request-2.png "Mensajes de estado en la página Solicitud de pedido de compra")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a>Programar el trabajo por lotes de solicitud de pedido de compra

Para activar el trabajo por lotes para enviar solicitudes de pedido de compra, vaya a **Adquisiciones y abastecimiento \> Preparar \> Administración de cXML \> Solicitud de pedido de compra** y, a continuación, en el panel de acciones, en la pestaña **Solicitud de pedido de compra**, en el grupo **Lote**, seleccione **Enviar trabajo** para abrir el cuadro de diálogo **Preparar y enviar solicitud de compra**. Puede usar este cuadro de diálogo para configurar la recurrencia, como hace habitualmente para los trabajos por lotes en Supply Chain Management. Seleccione un intervalo, según el volumen de su pedido. Aunque puede ejecutar el trabajo por lotes cada minuto, probablemente sea mejor enviar lotes durante el día laboral, según los períodos de recepción de pedidos que coincidan con los horarios de sus proveedores.

Por ejemplo, su proveedor tiene una directiva que establece que todos los pedidos que se reciban antes de las 13:00 se enviarán el mismo día. En este caso, es posible que tenga que ejecutar el lote solo unas pocas veces durante la mañana para comunicar los pedidos que tenga. Los pedidos restantes se enviarán al día siguiente. Esta decisión es meramente empresarial. Puede revisarlo y configurar los parámetros correspondientes.

El proceso buscará documentos de solicitud de pedido de compra que tengan el estado *En espera*. Si tiene un pedido que debe enviar a un proveedor inmediatamente, puede seleccionar **Enviar trabajo** y establecer la opción **Procesamiento por lotes** en *No*.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a>Supervisar las solicitudes de pedidos de compra

### <a name="view-the-status-of-a-purchase-order"></a>Ver el estado de un pedido de compra

Cuando se confirman los pedidos que se pueden enviar a través de cXML, pasan a estado _En espera_. Como se describió en la sección [Crear y procesar un pedido de compra](#create-po), puede ver el estado del pedido de compra en la página **Solicitud de pedido de compra**. Cada solicitud de pedido de compra puede tener uno de varios estados, según sus parámetros y datos. Esta sección describe los distintos tipos de estado y los valores que pueden tener. Esta información puede ayudarle a administrar problemas y a comprender el estado de sus pedidos de compra.

![Estado de pedido de compra en la página Solicitud de pedido de compra](media/cxml-monitor-po-request.png "Estado de pedido de compra en la página Solicitud de pedido de compra")

La cuadrícula en la parte superior de la página **Solicitud de pedido de compra** puede mostrar los siguientes valores de estado:

- **Estado de envío de pedido**: este campo puede tener uno de los siguientes valores:

    - **En espera**: el documento está a la espera de ser enviado.
    - **Enviado**: el documento ha sido enviado.
    - **Detenido**: el documento se ha marcado como _Detenido_ antes de enviarse. (Para marcar un documento como _Detenido_, seleccione **Detener** en el panel de acciones de la página **Solicitud de compra**).
    - **Archivar**: el documento se ha depurado. (Para depurar un documento, seleccione **Depurar** en el panel de acciones de la página **Solicitud de compra**).

- **Estado de proveedor de solicitud de pedido**: este campo puede tener uno de los siguientes valores:

    - **En espera**: el documento está a la espera de ser enviado.
    - **Confirmado**: el proveedor ha confirmado que ha recibido el documento. Puede revisar el mensaje XML detallado que devuelve el proveedor seleccionando la pestaña **XML de respuesta** en la parte inferior de la página.
    - **Error**: se envió el documento al proveedor, pero se produjo un error. Puede revisar el mensaje de error seleccionando la pestaña **XML de respuesta** en la parte inferior de la página.

La cuadrícula de la pestaña **Historial de solicitudes de pedido de compra** en la parte inferior de la página **Solicitud de pedido de compra** puede mostrar los siguientes valores:

- **Tipo de solicitud de pedido**: este campo puede tener uno de los siguientes valores:

    - **Nueva**: la línea se marca como nueva inmediatamente después de que se confirme el pedido de compra.
    - **Actualización**: si ya se ha enviado una confirmación y el proveedor la ha reconocido, la siguiente confirmación se marcará como _Actualización_. Solo se enviarán actualizaciones si la opción **Enviar actualizaciones de solicitud de compra** está configurada en *Sí* en los [parámetros de cXML globales](#cxml-parameters).
    - **Eliminar**: si ya se ha enviado una confirmación y el proveedor la ha confirmado, pero el pedido de compra está cancelado, la confirmación que está en espera se marcará como _Eliminar_. Solo se enviarán eliminaciones si la opción **Enviar eliminación de solicitud de compra** está configurada en *Sí* en los [parámetros de cXML globales](#cxml-parameters).

- **Hora de solicitud**: la hora en la que se creó la confirmación del pedido. Puede comparar la hora de la solicitud con la hora del estado del pedido para determinar el tiempo transcurrido entre la confirmación y el reconocimiento del proveedor.
- **Estado de envío del pedido**: este campo es el mismo que el campo **Estado de envío del pedido** de la parte superior de la página. Se repite aquí para facilitar la visualización del estado en el nivel de confirmación. Si el campo **Tipo de solicitud de pedido** está establecido en *Nuevo* y el pedido de compra se vuelve a confirmar antes de enviar una confirmación, el campo **Estado de envío del pedido** se establece en *Archivar*.
- **Hora del estado del pedido**: la hora en que se actualizó por última vez el registro del historial de solicitudes de pedidos de compra. (Las actualizaciones incluyen cambios de estado).
- **Estado de proveedor de solicitud de pedido**: este campo es el mismo que el campo **Estado de proveedor de solicitud de pedido** de la parte superior de la página. Se repite aquí para facilitar la visualización del estado en el nivel de confirmación.
- **Hora de reenvío**: la hora a la que se volvió a enviar el registro.
- **Recuento de reenvío**: el número de veces que se ha vuelto a enviar el registro. Un número elevado indica múltiples errores y, por lo tanto, podría indicar un problema en la configuración de sus datos o en la configuración de datos del proveedor.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>Ver el código XML de un mensaje de solicitud de pedido de compra

Para ver el XML del mensaje de solicitud de pedido de compra, seleccione la pestaña **Texto de XML de solicitud** en la parte inferior de la página **Solicitud de pedido de compra**. La información de esta pestaña puede ser útil durante las pruebas o la validación de errores. Para que la información sea más fácil de leer, puede verla como un mensaje formateado. Copie el contenido de la pestaña en un archivo de texto y luego visualícelo en un editor XML.

![Pestaña Texto de XML de solicitud](media/cxml-request-xml-text.png "Pestaña Texto de XML de solicitud")

### <a name="view-the-details-of-the-vendor-response"></a>Ver los detalles de la respuesta del proveedor

Para ver el contenido de una confirmación de proveedor o una respuesta de error, seleccione la pestaña **XML de respuesta** en la parte inferior de la página **Solicitud de pedido de compra**.

![Pestaña XML de respuesta](media/cxml-response-xml.png "Pestaña XML de respuesta")

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar un catálogo externo para la adquisición electrónica de marcaje de salida](set-up-external-catalog-for-punchout.md)
- [Usar catálogos externos para la adquisición electrónica de marcaje de salida](use-external-catalogs-for-punchout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]