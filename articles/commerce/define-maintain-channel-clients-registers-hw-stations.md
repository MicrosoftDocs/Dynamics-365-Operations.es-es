---
title: Conectar periféricos al punto de venta (PDV)
description: Este tema trata de cómo conectar periféricos a su Retail POS.
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ec64cb8a7c490c6798a897fd20a56e5af5c8be3a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415454"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Conectar periféricos al punto de venta (PDV)

[!include [banner](includes/banner.md)]

Este tema trata de cómo conectar periféricos a su Retail POS.

> [!NOTE]
> Para obtener instrucciones de configuración específicas, consulte [Instalar y configurar Retail Hardware Station](retail-hardware-station-configuration-installation.md) y [Configurar, instalar y activar Modern POS (MPOS)](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Componentes clave

Se utilizan varios componentes para definir las relaciones entre un almacén, los registros o canales de punto de venta (PDV) dentro del almacén y los periféricos que esos registros o canales utilizan para procesar transacciones. En esta sección se describe cada componente y explica cómo se debe utilizar en una implementación de almacén.

### <a name="pos-registers"></a>Registros de PDV

Navegación: Haga clic en **Retail y Commerce** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Registros**.

El registro de PDV es una entidad que se utiliza para definir las características de una instancia específica del PDV. Entre estas características se incluyen el perfil de hardware o la configuración de los periféricos que se utilizarán en el registro, el almacén al que está asignado el registro y la experiencia visual para el usuario que inicia sesión en ese registro.

### <a name="devices"></a>Dispositivos

Navegación: Haga clic en **Retail y Commerce** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Dispositivos**.

Un dispositivo es una entidad que representa una instancia física de un dispositivo que está asignado a un registro de PDV. Cuando se crea un dispositivo, se asigna a un registro de PDV. La entidad de dispositivo realiza un seguimiento de información acerca de cuándo se activa un registro de PDV, el tipo de cliente que se utiliza y el paquete de aplicación que se ha implementado en un dispositivo específico. Los dispositivos pueden ser de dos tipos: **Retail Modern POS** (MPOS) o **Retail Cloud POS** (PDV en la nube).

#### <a name="mpos"></a>MPOS

MPOS es una aplicación de cliente de PDV que se instala en Windows 8.1 o un sistema operativo basado en PC posterior. Si se asigna el tipo de aplicación **Retail Modern POS** a un dispositivo, el paquete de descarga se puede especificar para un dispositivo concreto. El paquete de descarga se puede personalizar para incluir diferentes versiones del paquete de instalación. La capacidad de implementar diferentes paquetes proporciona flexibilidad en los casos donde diferentes registros de PDV podría necesitar diferentes integraciones. MPOS se implementa junto con una estación de hardware integrada.

#### <a name="cloud-pos"></a>PDV en la nube

PDV en la nube es un PDV basado en explorador. Dado que se ejecuta en el explorador, PDV en la nube no requiere Windows 8.1 o un sistema operativo basado en PC posterior. Si se asigna el tipo de aplicación **Retail Cloud POS** a un dispositivo específico en la sede central, dicho dispositivo se puede utilizar a través del explorador sin necesidad de descargar o instalar un paquete. PDV en la nube requiere una estación de hardware para utilizar hardware más allá del análisis de códigos de barras basado en teclado en cuña.

### <a name="hardware-profile"></a>Perfil de hardware

Navegación: haga clic en **Comercio** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de hardware**.

Un perfil de hardware identifica el hardware que está conectado a un registro de PDV o una estación de hardware. El perfil de hardware se utiliza también para especificar los parámetros del procesador de pagos que se deben utilizar durante la comunicación con el kit de desarrollo de software (SDK) de pago. (El SDK de pago se implementa como parte de la estación de hardware).

### <a name="hardware-station"></a>Hardware Station

Navegación: haga clic en **Retail y Commerce** &gt; **Canales** &gt; **Tiendas** &gt; **Todas las tiendas**. Seleccione una tienda y, a continuación, haga clic en la ficha desplegable **Estaciones de hardware**.

Una estación de hardware es una instancia de lógica de negocio que impulsa los periféricos de PC. Una estación de hardware se instala automáticamente junto con MPOS. De forma alternativa, la estación de hardware se puede instalar como componente independiente y, a continuación, acceder a ella mediante MPOS o PDV en la nube a través de un servicio web. La estación de hardware debe definirse en el nivel de canal.

### <a name="hardware-station-profile"></a>Perfil de la estación de hardware

Navegación: haga clic en **Comercio** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de la estación de hardware**.

Siempre que la propia estación de hardware esté especificada en el nivel de canal incluye información específica de la instancia, como la dirección URL de la estación de hardware, el perfil de la estación de hardware incluye información que puede ser estática o compartida entre varias estaciones de hardware. La información estática incluye el puerto que se debe utilizar, el paquete de la estación de hardware y el perfil de hardware. La información estática también incluye una descripción del tipo de estación de hardware que se está implementando, como **Finalización de la compra** o **Devoluciones**, en función del hardware que se requiere para cada estación de hardware específico.

## <a name="scenarios"></a>Situaciones

### <a name="mpos-with-connected-peripheral-devices"></a>MPOS con dispositivos periféricos conectados

[![Punto de venta fijo y tradicional](./media/traditional-300x279.png)](./media/traditional.png)

Para conectar periféricos de MPOS a PDV en un escenario de PDV fijo tradicional, navegue primero hasta el propio registro y asígnele un perfil de hardware. Encontrará registros de PDV en **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Registros**. 

Una vez que haya asignado el perfil de hardware, sincronice los cambios en la base de datos de canal mediante la programación de distribución de **Registros**. Puede encontrar las programaciones de distribución en **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programación de distribución**. 

A continuación, configure una estación de hardware "local" en el canal. Haga clic en **Retail y Commerce** &gt; **Canales** &gt; **Tiendas** &gt; **Todas las tiendas** y seleccione una tienda. 

A continuación, en la ficha desplegable **Estaciones de hardware**, haga clic en **Agregar** para agregar una estación de hardware. Escriba una descripción, escriba **localhost** como el nombre del host y, a continuación, sincronice los cambios realizados con el canal mediante la programación de distribución **Configuración del canal**. Puede encontrar las programaciones de distribución en **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programación de distribución**. 

Por último, en MPOS, utilice la operación **Seleccionar estación de hardware** para seleccionar la estación de hardware **localhost**. Establezca la estación de hardware en **Activa**. El perfil de hardware que se utiliza en este escenario debe provenir del propio registro de PDV. No se requiere un perfil de estación de hardware para este escenario.

> [!NOTE]
> Algunos cambios de perfil de hardware, como los cambios a las cajas registradoras, requieren que se abra un turno nuevo después de que los cambios se hayan sincronizado en el canal.
>
> Cloud POS debe utilizar la estación de hardware independiente para comunicarse con periféricos.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS o PDV en la nube con una estación de hardware independiente

[![Periféricos compartidos](./media/shared-300x254.png)](./media/shared.png)

En este escenario, se comparte una estación de hardware independiente entre los clientes de MPOS y PDV en la nube. Este escenario requiere la creación de un perfil de estación de hardware para especificar el paquete de descarga, el puerto y el perfil de hardware que la estación de hardware utiliza. Puede encontrar el perfil de estación de hardware en **Retail y Commerce** &gt; **Configuración del canal** &gt; **Configuración del PDV** &gt; **Perfiles del PDV** &gt; **Perfiles de la estación de hardware**. 

Una vez creado el perfil de la estación de hardware, navegue hasta el canal específico (**Retail y Commerce** &gt; **Canales** &gt; **Tiendas** &gt; **Todas las tiendas**) y agregue una nueva estación de hardware. Asigne esta nueva estación de hardware al perfil de la estación de hardware que se creó anteriormente. 

A continuación, proporcione una descripción que ayude al cajero a identificar la estación de hardware. En el campo **Nombre de host**, escriba la dirección URL del equipo host con el siguiente formato: `https://<MachineName:Port>/HardwareStation`. (Reemplace **&lt;NombredeEquipo:Puerto&gt;** por el nombre del equipo real de la estación de hardware y el puerto que se especifica en el perfil de la estación de hardware.) Para una estación independiente del hardware, también deberá especificar el identificador del terminal (EFT) de transferencia electrónica de fondos. Este valor identifica el terminal EFT que está conectado a la estación de hardware cuando el conector de pago se comunica con el proveedor de pagos. 

A continuación, desde el equipo de la estación de hardware real, desplácese al canal y seleccione la estación de hardware. A continuación, haga clic en **Descargar** e instale la estación de hardware. 

A continuación, desde MPOS o PDV en la nube, utilice la operación **Seleccionar estación de hardware** para seleccionar la estación de hardware que se instaló anteriormente. Seleccione **Emparejar** para establecer una relación segura entre el PDV y la estación de hardware. Este paso se debe completar una vez para cada combinación de PDV y una estación de hardware. 

Una vez se haya emparejado la estación de hardware, se lleva a cabo la misma operación para activar la estación de hardware mientras se utiliza. En este escenario, debe asignarse el perfil de hardware al perfil de la estación de hardware en lugar del propio registro. Si por alguna razón una estación de hardware no tiene un perfil de hardware asignado directamente, se utilizará el perfil de hardware asignado al registro.

## <a name="client-maintenance"></a>Mantenimiento del cliente

### <a name="registers"></a>Cajas registradoras

Los registros de PDV se administran principalmente a través de los propios registros y también mediante los perfiles que se asignan a los registros. Los atributos que son específicos de un registro individual se administran en el nivel de registro. Estos atributos incluyen la tienda donde se utiliza el registro, el número de registro, la descripción y el id. del terminal de EFT que es específico del propio registro.

### <a name="pos-profiles"></a>Perfiles de PDV

Puede encontrar los registros de PDV en **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV**. Es útil administrar muchos aspectos de un registro a través de perfiles, ya que los perfiles se pueden compartir entre muchos registros. Los perfiles se pueden asignar a un registro individual o bien, si un perfil es eficaz para todas las tiendas, a la tienda. Las secciones siguientes describen los perfiles PDV y cómo se utilizan.

#### <a name="offline-profile"></a>Perfil sin conexión

El perfil sin conexión se ajusta en el nivel de tienda. Se utiliza para especificar la configuración de carga para las transacciones que se realizan en un registro de PDV mientras que ese registro no está conectado a la base de datos de canales.

#### <a name="functionality-profile"></a>Perfil de funcionalidad

El perfil sin funcionalidad se ajusta en el nivel de tienda. Se utiliza para especificar la configuración de toda la tienda respecto a las funciones que se pueden realizarse en el PDV. Las siguientes capacidades se administran mediante el perfil de funcionalidad. Estas capacidades se organizan por ficha desplegable.

- Ficha desplegable **General**:

    - Organización internacional de normalización (ISO).
    - Cree un cliente en modo sin conexión.
    - Perfil de recepción de correo electrónico.
    - Autenticación de inicio de sesión de personal central.

- Ficha desplegable **Funciones**:

    - Administración de inicio de sesión e inicio de sesión extendido.
    - Aspectos financieros y relacionados con la moneda del PDV, como la capacidad de teclear precios y si son necesarios decimales para la moneda secundaria.
    - Habilitar el registro de horas a través del PDV.
    - Cómo aparecen los productos y los pagos en el PDV y en los recibos.
    - Gestión de final del día.
    - Parámetros de retención de transacciones de base de datos de canal.
    - Cómo se buscan y se crean los clientes desde el PDV.
    - Cómo se calculan los descuentos.

- Ficha desplegable **Cantidad**:

    - Los precios máximo y mínimo permitidos.
    - Cálculo y aplicación de descuentos.

- Ficha desplegable **Códigos de información**:

    - Todos los aspectos de cómo se administran los códigos de información en el PDV. Para obtener información detallada, consulte [Códigos de información y grupos de códigos de información](info-codes-retail.md).

- Ficha desplegable **Numeración de recepción**:

    - Especifique máscaras de numeración de recibos, que pueden incluir segmentos para el número de tienda, el número del terminal, constantes, y si se imprimen las ventas, devoluciones, pedidos de ventas y presupuestos en secuencias independientes, o si siguen todos la misma secuencia.

#### <a name="receipt-profiles"></a>Perfiles de recibo

Los perfiles de recibos se asignan a impresoras dentro del perfil de hardware. Se utilizan para especificar los tipos de recibos que se imprimen en una impresora específica. Los perfiles incluyen parámetros para los formatos de recibos y configuración que determina si el recibo se imprime siempre o si se le pide al cajero que decida si se debe imprimir el recibo. Diferentes impresoras también podrían utilizar perfiles de recibos diferentes. Por ejemplo, la impresora 1 es una impresora de recibos térmica estándar y, por tanto, tiene formatos de recibos más pequeños. Sin embargo, la impresora 2 es una impresora de tamaño completo que se utiliza para imprimir solo recibos de pedidos de clientes, que requieren más espacio.

#### <a name="hardware-profiles"></a>Perfiles de hardware

Los perfiles de hardware se ha explicado como un componente para la configuración del cliente anteriormente en este artículo. Los perfiles de hardware se asignan directamente al registro de PDV o a un perfil de estación de hardware. Se utilizan para especificar los tipos de registro que se usan por un registro de PDV o una estación de hardware específicos. Los perfiles de hardware también se usan para especificar la configuración de EFT que se utiliza para comunicarse con el SDK de pago.

#### <a name="visual-profiles"></a>Perfiles visuales

Los perfiles visuales se asignan en el nivel de registro. Se utilizan para especificar el tema para un registro específico. Entre los perfiles se incluyen valores para el tipo de aplicación que se utiliza (MPOS o PDV en la nube), el tema y el color de acento, el esquema de fuente, el fondo del inicio de sesión y el fondo del PDV.

### <a name="custom-fields"></a>Campos personalizados

Puede crear campos personalizados para agregar campos que no se proporcionan de inmediato al PDV. Para obtener más información sobre cómo usar campos personalizados, consulte la entrada de blog [Trabajar con campos personalizados](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Texto de idioma

Puede reemplazar las cadenas predeterminadas en el PDV con entradas de texto de idioma. Para reemplazar una cadena en el PDV, agregue una nueva línea de texto de idioma. A continuación, especifique un id., la cadena predeterminada que se debe anular y el texto que se debe mostrar en el PDV en lugar de la cadena predeterminada.

### <a name="hardware-station-profiles"></a>Perfiles de la estación de hardware

Los perfiles de la estación de hardware se explican anteriormente en este artículo. Se utilizan para asignar información que no es específica de instancia a las estaciones de hardware.

### <a name="channel-reports-configuration"></a>Configuración de informes de canal

Los informes que están disponibles en el canal comercial se configuran en la página **Configuración de informes de canal**. Puede crear nuevos informes proporcionando la definición de XML del informe y asignando el informe a un grupo de permisos específicos en el PDV.

### <a name="devices"></a>Dispositivos

Los dispositivos se explican anteriormente en este artículo. Se utilizan para gestionar la activación de un registro de PDV específico. Los dispositivos también se utilizan para especificar la aplicación que se utiliza para un registro específico y el paquete de instalación que se debe utilizar para instalar el cliente de MPOS. Estos son los estados de activación de dispositivo:

- **Pendiente**: el dispositivo está listo para activarse.
- **Activado**: el dispositivo se ha activado.
- **Desactivado**: el dispositivo se ha desactivado en la sede central o a través del PDV.
- **Deshabilitado**: el dispositivo se ha deshabilitado.

La información adicional relacionada con la activación incluye el trabajador que ha cambiado el estado de la activación para el dispositivo, una marca de tiempo para la activación y si se ha validado la configuración del dispositivo.

### <a name="client-data-synchronization"></a>Sincronización de datos del cliente

Todos los cambios a un cliente de PDV, excepto los cambios en el estado de activación del dispositivo, se deben sincronizar para que la base de datos de canales tenga efecto. Para sincronizar los cambios con la base de datos de canales, navegue hasta **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programación de distribución** y ejecute la programación de distribución requerida. Para los cambios de clientes, debe ejecutar las programaciones de distribución **Registros** y **Configuración del canal**.
