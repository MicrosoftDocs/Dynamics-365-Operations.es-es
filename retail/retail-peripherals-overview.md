---
title: "Visión general de ventas al por menor periféricos"
description: "Este tema explica los conceptos relacionados con los periféricos de ventas al por menor. Describe las distintas maneras que periféricos se pueden conectar al punto de venta (POS) y componentes que es responsable de gestionar la conexión con Retail POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Visión general de ventas al por menor periféricos

Este tema explica los conceptos relacionados con los periféricos de ventas al por menor. Describe las distintas maneras que periféricos se pueden conectar al punto de venta (POS) y componentes que es responsable de gestionar la conexión con Retail POS.

<a name="concepts"></a>Conceptos
--------

### <a name="pos-registers"></a>Registros de PDV

Exploración: Haga clic en ** al por menor y comercio ** &gt; ** canal configurar ** &gt; ** Configuración de PDV ** &gt; ** ** registros. El registro de (POS) de punto de venta es una entidad que se usa para definir las características de una instancia específica de Retail POS. Estas características incluyen el perfil de hardware o la configuración de periféricos al por menor que se usarán en el registro, el almacén que el registro está asignado a, y la experiencia visual del usuario que iniciar sesión en ese registro.

### <a name="devices"></a>Dispositivos

Exploración: Haga clic en ** al por menor y comercio ** &gt; ** canal configurar ** &gt; ** Configuración de PDV ** &gt; ** dispositivos **. Un dispositivo es una entidad que representa una instancia física de un dispositivo que está asignado a un registro de PDV. Cuando se crea un dispositivo, ha asignado a un registro de Retail POS. La entidad de dispositivo realiza un seguimiento de información acerca de cuándo se activa un registro de PDV, el tipo de cliente que se utiliza y el paquete de aplicación que se ha implementado en un dispositivo específico. Los dispositivos se pueden asignar a los tipos de aplicación siguientes: PDV moderno al por menor, nube PDV, ventas al por menor – PDV moderno Windows, puede ventas al por menor – moderno PDV Android, y Retail moderno al por menor – IOS de ventas al por menor.

### <a name="retail-modern-pos"></a>Retail Modern POS

PDV moderno es el programa de PDV de Microsoft Windows. Puede implementar en Windows 10 sistemas operativos (OSs).

### <a name="cloud-pos"></a>PDV en la nube

La nube PDV es una versión explorador- basada moderno del programa de PDV que se puede alcanzar en un explorador web.

### <a name="modern-pos-for-ios"></a>PDV para el moderno IOS

PDV para el moderno IOS es una versión IOS- basada moderno del programa de PDV que se puede implementar en dispositivos de IOS.

### <a name="modern-pos-for-android"></a>PDV moderno para Android

PDV moderno para Android es una versión Android- basada moderno del programa de PDV que se puede implementar en los dispositivos de Android.

### <a name="pos-peripherals"></a>Periférico de PDV

Los periféricos de PDV son los dispositivos que explícitamente se admiten para las funciones de Retail POS. Estos periféricos se suelen dividir en las clases específicas. Para obtener más información sobre estas clases, consulte la sección “de las clases de dispositivo” de este tema.

### <a name="hardware-station"></a>Estación de hardware

Exploración: Haga clic en ** al por menor y comercio ** &gt; ** canales ** &gt; ** tiendas al por menor ** &gt; ** todas comercios **. Seleccione una tienda y, a continuación, haga clic en la ficha desplegable **Estaciones de hardware**. ** Emisora de hardware ** el valor es un valor de canal- nivel que se usa para definir las instancias en la lógica periférica al por menor será implementada. Este valor en el nivel de canal se usa para determinar las funciones de la emisora del hardware. También se usa para mostrar las emisoras de hardware que están disponibles para una instancia moderna de PDV en un almacén determinado. La emisora de hardware se ha especificado en el programa moderno de PDV para Windows. La emisora de hardware también se puede implementar independientemente como programa independiente de Microsoft Internet Information Services (IIS). En este caso, puede tener acceso mediante una red.

### <a name="hardware-profile"></a>Perfil de hardware

Exploración: Haga clic en ** al por menor y comercio ** &gt; ** canal configurar ** &gt; ** Configuración de PDV ** &gt; ** PDV perfiles ** &gt; ** los perfiles de hardware **. El perfil de hardware es una lista de dispositivos que se configuran para un registro de Retail POS o una emisora del hardware. El perfil de hardware se puede asignar directamente a un registro de PDV o una emisora del hardware.

## <a name="devices-classes"></a>Clases de dispositivos
Los periféricos de PDV se suelen dividir en clases. Esta sección describe y ofrece una visión general de los dispositivos que admite moderno PDV.

### <a name="printer"></a>Impresora

Las impresoras incluyen las impresoras tradicionales de recepción de PDV e impresoras a toda plana. Los a la impresora a través de objeto que vincula y que inserta automáticamente para las interfaces del controlador de PDV OPDV (y) de Microsoft Windows. Hasta dos impresoras se pueden utilizar el mismo tiempo. Esta capacidad admite las situaciones en las que los recibos de cliente de las tiendas de ventas al contado se imprimen en impresoras de recepción, mientras que los pedidos de cliente, que conllevan obtener más información, se imprimen en una impresora para toda plana. Las impresoras de recepción se pueden conectar directamente con un equipo mediante USB, conectar con una red mediante Ethernet, o conectarse mediante Bluetooth.

### <a name="scanner"></a>Escáner

Hasta dos escáneres de código de barras se pueden utilizar el mismo tiempo. Esta capacidad admite escenarios donde un escáner con mayor móvil se requiere para escanear mayor o los artículos pesados, mientras que un escáner incrustado fijo se usa para la mayoría de los elementos norma- calibrados, para acelerar los tiempos de desprotección. Los escáneres se admiten a través de OPDV, de la plataforma (UWP) de Windows, o universal de interfaces de la cuña de teclado. USB o Bluetooth se puede usar para conectar un escáner un equipo.

### <a name="msr"></a>MSR

Un lector (MSR) de banda magnética de USB se puede configurar mediante los conductores de OPDV. Si desea usar MSR independiente para las transacciones de pago de (EFT) de transferencia electrónica de fondos, MSR se debe gestionar por un Connector de pago. Los MSRs independientes se pueden usar para la entrada de fidelidad del cliente, el empleado inicio en, y la entrada de la tarjeta regalo, independientemente de Connector de pago.

### <a name="cash-drawer"></a>Caja registradora

Dos cajas registradoras se admiten por Perfil de hardware. Esta capacidad permite a dos activa cambia por el registro esté disponible al mismo tiempo. En el caso de un cambio compartidos, o una caja registradora que usa los dispositivos móviles múltiples de PDV al mismo tiempo, sólo una caja registradora se permite por Perfil de hardware. Las cajas registradoras se pueden conectar directamente con un equipo mediante USB, conectar con una red, o conectar a una impresora de recibos mediante una interfaz RJ12. En algunos casos, las cajas registradoras también se pueden conectar a través de Bluetooth.

### <a name="line-display"></a>Visualización de líneas

Se usará las pantallas de línea muestre los productos, los saldos de transacciones, y otra información útil al cliente durante una transacción. Una visualización de líneas puede ser conectada al equipo mediante USB mediante los conductores de OPDV.

### <a name="signature-capture"></a>Captura de firma

Los dispositivos de digitalizador de firmas se pueden conectar directamente con un equipo mediante USB mediante los conductores de OPDV. Cuando se configura la captura de la firma, se pedirá al firmar cliente en el dispositivo. Después de que se proporcione la firma, se ha al cajero la aceptación.

### <a name="scale"></a>Escala

Las escalas se pueden conectar al equipo mediante USP mediante los conductores de OPDV. Cuando un producto que se marca como producto “pesado” se agrega a una transacción, el sistema POS lee el peso de la escala, agrega el producto a la transacción, y la cantidad a la escala que ha proporcionado.

### <a name="pin-pad"></a>Terminal para ingreso de PIN

Las trayectorias de (PIN) del número de identificación personal se admiten con OPDV, pero que se tratan a través de un Connector de pago.

### <a name="secondary-display"></a>Pantalla secundaria

Cuando configuran una pantalla secundaria, se utilizará la visualización de Windows del número 2 para mostrar la información básica. El propósito de la pantalla secundaria es permitir la (ISV) de extensión de proveedor independiente de software, porque el listo para usar, la pantalla secundaria no se puede configurar y no muestra el contenido limitado.

### <a name="payment-device"></a>Dispositivo de pago

La compatibilidad con el dispositivo de pago se implementa a través de Connector de pago. Los dispositivos de pago pueden realizar una o varias de las funciones que otras clases de dispositivo ofrece. Por ejemplo, un dispositivo de pago puede funcionar como un lector de MSR/card, una pantalla de línea, un dispositivo de digitalizador de firmas, o ingreso de PIN. La compatibilidad de los dispositivos de pago se implementa independientemente de soporte del dispositivo independiente que se ofrece por otros dispositivos que se incluyen en el perfil de hardware.

## <a name="supported-interfaces"></a>Interfaces compatibles
### <a name="opos"></a>OPDV

Para ayudar a garantizar que el intervalo mayor de dispositivos se puede usar con Microsoft Dynamics 365 para las operaciones (al por menor, OLE para el estándar del sector de PDV es la plataforma al por menor principal de dispositivos periféricos que se admite en Microsoft Dynamics 365 para las operaciones (al por menor. OLE para la norma de PDV se produjo con la federación al por menor Nacional (NRF), que liquida los protocolos de comunicación estándar del sector para los dispositivos periféricos de ventas al por menor. OPDV es una implementación adoptada enormemente de OLE para la norma de Retail POS. Este importe ha en mediados de 1990 s desarrollada y se ha actualizado desde varias veces continuación. OPDV proporciona una arquitectura del controlador de dispositivo que habilitar la integración fácil de hardware de PDV con los sistemas POS basados en Windows. Comunicación de identificador de controles de OPDV entre el hardware compatible y el software de Retail POS. Control de OPDV consta de dos partes:

-   ** El objeto del control – ** el objeto de control para una clase de dispositivo (como pantallas de línea) ofrece la interfaz del programa de software. Monroe Consulting Services (www.monroecs.com [] (http://www.monroecs.com/)) proporciona un conjunto normalizado de objetos de control de OPDV denominadas los objetos (CCOs) de control de existencias. El CCOs se usa para probar el componente de PDV de Microsoft Dynamics 365 para las operaciones (al por menor. Por lo tanto, ayuda de la prueba garantizan que, si Microsoft Dynamics 365 para las operaciones (al por menor admite una clase de dispositivo con OPDV, muchos tipos de dispositivo puede ser compatible, siempre que el proveedor proporciona un objeto de servicio que se construya para OPDV. No es necesario probar explícitamente cada tipo de dispositivo.
-   ** El objeto de servicio – ** el objeto de servicio proporciona la comunicación entre el objeto de control (CCO) y el dispositivo. Normalmente, el objeto de servicio para un dispositivo se proporciona por el fabricante del dispositivo. Sin embargo, en algunos casos, es posible que tenga que descargar el objeto de servicio de la página Web del proveedor. Por ejemplo, un objeto de servicio más reciente esté disponible. Para encontrar la dirección de la página Web del proveedor, vea la documentación de hardware.

[objeto y objeto de servicio del control![] (. /media/retail_peripherals_overview01.png])(. La compatibilidad de /media/retail_peripherals_overview01.png) para la implementación de OPDV de OLE para ayuda de PDV garantiza que, si los fabricantes de dispositivos y los editores de PDV implementan la norma correctamente, los sistemas POS y dispositivos admitidos pueden trabajar conjuntamente, incluso si no se probados anteriormente conjuntamente. ** Nota: ** La compatibilidad de OPDV no garantiza el soporte para todos los dispositivos que tienen controladores de OPDV. Microsoft Dynamics 365 para las operaciones (la necesidad de atención al por menor que primero tipo de dispositivo, o clase, con OPDV. Además, los objetos de servicio no pueden ser siempre actualizados con la última versión del CCOs. También debe tener en cuenta que, los objetos de la calidad de servicio varían normalmente.

### <a name="windows"></a>Windows

La impresión de recibos en el sistema POS se optimiza para OPDV. OPDV tiende a ser mucho más rápida que la impresión a través de Windows. Por lo tanto, es recomendable usar OPDV, especialmente en entornos en la que se imprimen 40 recibos de la columna y los tiempos de la transacción se rápida. Para la mayoría de los dispositivos, deberá utilizar los controles de OPDV. Sin embargo, las impresoras de recepción de algún OPDV también admiten los controladores de Windows. Uso de Windows controlador, puede tener acceso a las últimas suministros y la impresora de una red para varios registros. Sin embargo, existen desventajas para poder usar los conductores de Windows. A continuación se muestran algunos ejemplos de estas desventajas:

-   Cuando se usan los conductores de Windows, se generan las imágenes antes de que aparezca el imprimir. Por lo tanto, el imprimir tiende a ser más lento que se encuentra en impresoras que usan los controles de OPDV.
-   Los dispositivos conectados a través de la impresora (“margarita- encadenado ") no pueden funcionar correctamente cuando se usan los conductores de Windows. Por ejemplo, la caja registradora no puede abrir, o la impresora del resguardo no puede redactar como espera.
-   OPDV también admite un conjunto de cuenta más variables que son específicas vender impresoras de recepción al por menor, como impresión de papel de fallo o del albarán.

Si los controles de OPDV están disponibles para la impresora de Windows que usa la, la impresora debe aún correctamente trabajar con Microsoft Dynamics 365 para las operaciones (al por menor.

### <a name="universal-windows-platform"></a>Plataforma de Windows universal

UWP, en el caso de periféricos al por menor, está relacionado con el soporte de Windows para los dispositivo Plug and Play. Cuando un dispositivo Plug and Play se conecta con una versión del SO de Windows que soporte ese tipo de dispositivo, no se requiere ningún controlador para que el dispositivo se usará como lo previsto. Por ejemplo, si Windows detecta un dispositivo de orador de Bluetooth, el SO sabe que tiene el dispositivo ** orador ** el tipo de clase. Por lo tanto, pero ese dispositivo trata como orador. No se requiere ninguna configuración adicional. En el caso de los dispositivos de PDV, muchos dispositivos USB se pueden enchufar, y Windows reconocerá como los dispositivos (HIDs) de la interfaz humana. Sin embargo, es posible que no pueda determinar las capacidades que proporciona el dispositivo, ya que el dispositivo no especifica la clase, o, tipo de dispositivo. En Windows 10, las clases de dispositivo para los escáneres de código de barras y los MSRs se han agregado. Por lo tanto, si un dispositivo a declarar a Windows 10 como dispositivo de una de estas clases, Windows estará atentos eventos de dispositivo en los tiempos adecuados. PDV moderno admite UWP MSRs y escáneres. Por lo tanto, cuando está listo para la entrada desde uno de estos dispositivos, y un dispositivo que pertenezca a una de estas clases se conecta, el dispositivo se podrá utilizar. Por ejemplo, si un escáner de códigos de barras de UWP se tapa en un equipo de Windows 10, y código de barras de inicio en está configurado para moderno PDV, el escáner de códigos de barras estará activo en inicio en la pantalla. No se requiere ninguna configuración adicional. Las clases adicionales de punto de dispositivos de servicio UWP se están agregando a Windows. Estas clases incluyen las clases para las cajas registradoras e impresoras de recepción. La compatibilidad para estas nuevas clases de dispositivo en el sistema POS moderno está pendiente.

### <a name="keyboard-wedge"></a>Cuña de teclado

Los dispositivos de la cuña de teclado envían datos al equipo como si que los datos se hubiera escrito en un teclado. Por lo tanto, de forma predeterminada, el campo que está activo en PDV recibirá los datos que se escanea o gastar. En algunos casos, este comportamiento puede producir incorrecto el tipo de datos que se digitalizarán en el campo incorrecto. Por ejemplo, un código de barras se puede escanear en un campo que se ha creado para la entrada de los datos de la tarjeta de crédito. En muchos casos, hay lógica de PDV que determina si los datos que se escanea o gastar es un una tarjeta de código de barras o de tarjeta. Por lo tanto, los datos se gestionan correctamente. Sin embargo, cuando los dispositivos se configura como OPDV en lugar de los dispositivos de la cuña de teclado, hay más control sobre cómo los datos de los dispositivos se pueden consumir, porque más “ya se conoce” sobre el dispositivo de que los datos origen. Por ejemplo, los datos de un escáner de códigos de barras automáticamente se reconoce como código de barras, y el registro asociado en la base de datos se encuentra más fácilmente más rápidamente y que si una búsqueda de cadenas genérica se usó, como en el caso de los dispositivos de la cuña de teclado.

### <a name="native-printer"></a>Impresora nativa

Mientras denominan el tipo en el perfil de hardware) impresoras integradas (“o” dispositivo se pueden configurar preguntar al usuario seleccionar una impresora que está configurada para el equipo. Cuando una impresora ** dispositivo ** del tipo se configura PDV, si moderno encuentra un comando de impresión, se pedirá al usuario seleccionar una impresora en una lista. Este comportamiento diferencia de comportamiento de los conductores de Windows, porque ** Windows ** el tipo de impresora en el perfil de hardware no muestra una lista de impresoras. En su lugar, requiere una impresora denominada se proporcionada en ** nombre de dispositivo ** el campo.

### <a name="windows"></a>Windows

** Windows ** usan el tipo de dispositivo para las impresoras únicamente. Cuando una impresora de Windows se configura en el perfil de hardware, el nombre de impresora específica debe ser ofrecido. Cuando detecta modernos de PDV imprimen eventos, si se configura una impresora de Windows, el evento se transfirieron a la especificada impresora de Windows. No se pedirá al usuario seleccione una impresora.

### <a name="network"></a>Red

las cajas registradoras Red- direccionables, impresoras de recepción, y terminales de pago se pueden usar en una red, ya sea directamente a través de la emisora de hardware de las comunicaciones entre procesos (IPC) que se especifica en moderno PDV para la aplicación para Windows o a través de la emisora de hardware de IIS para otros clientes modernos de Retail POS.

## <a name="hardware-station-deployment-options"></a>Opciones de implementación de la emisora de hardware
### <a name="ipc-built-in"></a>Costes indirectos de producción (accesorio)

La emisora de hardware de las comunicaciones entre procesos (IPC) se especifica en moderno PDV para la aplicación para Windows. Para usar la emisora de hardware de costes indirectos de producción, asigne un perfil de hardware a un registro que utilice PDV moderno para la aplicación para Windows. A continuación cree una emisora de hardware ** dedicado ** del tipo para el almacén en el que el registro se usará. Al iniciar Retail POS, la moderno emisora de hardware de IPC estará activo, y periféricos de PDV que se han configurado se listos para usar. Si no necesita temporalmente el hardware local por algún motivo, utilice ** gestionar las emisoras de hardware ** la operación para desactivar las capacidades de la emisora del hardware. PDV moderno puede usar la emisora de hardware de costes indirectos de producción directamente para comunicarse con periféricos de la red.

### <a name="iis"></a>IIS

Puede usar IIS o la versión independiente de la emisora de hardware de dos maneras. Descriptor “IIS” implica que la aplicación de PDV se conecta a la emisora de hardware mediante Microsoft Internet Information Services. La aplicación de PDV se conecta a la emisora de hardware de IIS mediante los servicios Web que se ejecutan en un equipo donde los dispositivos se conectan. Cuando se usa IIS, periféricos al por menor asociados a una emisora de hardware se puede usar cualquier registro de PDV que esté en la misma que la red emisora de hardware de IIS. Dado que sólo moderno PDV para Windows incluye el soporte de accesorio de periféricos al por menor, el resto de Aplicaciones modernas de PDV deben usar la emisora de hardware de IIS para comunicarse con los periféricos de PDV que se configuran en el perfil de hardware. Por lo tanto, cada instancia de la emisora de hardware de IIS requiere un equipo que ejecute el servicio Web y la aplicación que comunica con dispositivos. La emisora de hardware de IIS se requiere para todas las aplicaciones modernas de PDV de WINDOWS.

#### <a name="dedicated"></a>Dedicado

PDV moderno usa las emisoras de hardware ** dedicado ** del tipo para detectar periféricos se vinculan directamente con el equipo donde se usa la aplicación. Sin embargo, ** dedicado ** el tipo también se pueden usar para las emisoras de hardware de IIS. En un escenario tradicional, fija de PDV que utilice la nube PDV como la aplicación del PDV, ** dedicado ** usan el tipo de la emisora de hardware para las emisoras de hardware de IIS implementadas en el mismo equipo que ejecuta la nube PDV. De una perspectiva al por menor periféricos, la emisora dedicada de hardware de IIS tiene mejor soporte el periféricos para los escenarios tradicionales, fijas de Retail POS. Las emisoras dedicadas de hardware admiten todos los periféricos que se admitan en el perfil de hardware.

#### <a name="shared"></a>Compartido

Las emisoras compartidas de hardware se utilizan para su uso por dispositivos múltiples de PDV a través del curso del día. Las emisoras compartidas de hardware se optimizan para admitir sólo las cajas registradoras, impresoras de recepción, y terminales de pago. No puede conectar directamente los escáneres de código de barras independientes, MSRs, pantallas de línea, escalas, u otros dispositivos. Si no, aparecerán los conflictos cuando intento múltiple de los dispositivos del sistema POS para demandar los periféricos al mismo tiempo. Aquí es cómo los conflictos se gestionan de los dispositivos admitidos:

-   ** La caja registradora – ** la caja registradora se abre mediante un evento que se envía al dispositivo. El único problema que puede ocurrir cuando se denomina una caja registradora aparece si la caja registradora ya está abierto. En el caso de las emisoras compartidas de hardware, la caja registradora se debe establecer en ** compartido ** en el perfil de hardware. Este valor impide que Retail POS compruebe si la caja registradora ya está abierto cuando registra comandos abierto.
-   ** La impresora de recibos ** – si registran dos comandos de la impresión de recibos a la emisora de hardware al mismo tiempo, uno de los siguientes comandos se puede perder, en función del dispositivo. Algunos dispositivos tienen memoria interna o limitación de solicitudes que puedan evitar este problema. Si un comando de impresión no se ha realizado correctamente, el cajero recibe un mensaje de error y puede reintentar el comando de impresión de Retail POS.
-   ** El terminal de pago – ** si los intentos de un cajero para obtener una transacción en un terminal de pago que se usen ya, un mensaje notifica al cajero que se está utilizando el terminal y se solicita al cajero intente de nuevo más adelante. Normalmente, los cajeros pueden ver un terminal que se usa y esperará ya hasta que se complete la otra transacción antes de que intenten para obtener de nuevo.

La validación está previsto que una versión futura, para detectar si los dispositivos no admitido se configuran para un perfil de hardware asignada a una emisora compartida del hardware. Si se detectan dispositivos algunos no admitido, el usuario recibirá un mensaje que indique que los dispositivos no se llevan para las emisoras compartidas del hardware. En el caso de las emisoras compartidas de hardware, seleccione ** sobre el ofrecimiento ** la opción está establecida ** Sí ** a nivel de registro. A continuación se pedirá al usuario de Retail POS seleccione una emisora de hardware cuando una propuesta se activa para una transacción en el sistema POS. Cuando la emisora de hardware sólo se selecciona en el momento de propuesta, la selección de emisora de hardware se agrega directamente al flujo de trabajo de PDV para los escenarios móviles. Como prestación adicional, no se utilizará la visualización de líneas en el terminal de pago para los escenarios compartidas. Si el terminal de pago se usa como visualización de líneas, otros usuarios podrían ser bloqueados de usar el terminal hasta que la transacción se completa. En escenarios móviles, las líneas se pueden agregar a una transacción durante un período más largo. Por lo tanto, seleccione ** sobre el ofrecimiento ** la opción se requiere para proteger disponibilidad óptima del dispositivo.

### <a name="network-peripherals"></a>Periférico de la red

La designación de la red de los dispositivos en el perfil de hardware habilita las cajas registradoras, impresoras de recepción, y terminales de pago que se conectarán mediante una conexión de red.

#### <a name="modern-pos-for-windows"></a>PDV moderno para Windows

Puede especificar direcciones IP de periféricos de la red en dos ubicaciones. Si el cliente Windows moderno de PDV utiliza un único conjunto de periféricos de la red, debe establecer direcciones IP para dichos dispositivos mediante ** configuración IP ** la opción en el panel de acciones para el registro en sí. En el caso de los dispositivos de red que se van a compartir entre PDV, registra un perfil de hardware que tenga los dispositivos de red asignados al puede ser asignado directamente en una emisora compartida del hardware. Para asignar a las direcciones IP, seleccionar qué la emisora de hardware ** en comercios ** la página y, a continuación utiliza ** configuración IP ** la opción en las ** emisoras de hardware ** la sección de especificar los dispositivos de red asignados a ella emisora del hardware. Para las emisoras de hardware sólo tienen dispositivos de red, no es necesario implementar la propia emisora del hardware. En este caso, la emisora de hardware se requiere para agrupar sólo los dispositivos conceptual red- direccionables según su ubicación en la tienda al por menor.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>Núblese PDV, el sistema POS para el moderno IOS, y Retail moderno para Android

La lógica que controla físicamente en línea y los periféricos red- direccionables contiene la emisora del hardware. Por lo tanto, para todos los clientes de PDV excepto PDV moderno para Windows, una emisora de hardware de IIS debe ser introducida y activo para permitir a PDV para comunicarse con los periféricos, independientemente de si los periféricos físicamente se vinculan con una emisora de hardware o dirigidos acerca de la red.

## <a name="setup-and-configuration"></a>Establecimiento y configuración
### <a name="hardware-station-installation"></a>Instalación de la emisora de hardware

Para obtener más información, consulte [configuración y la configuración en el por menor retail-hardware-station-configuration-installation.md] () de la emisora del hardware.

### <a name="modern-pos-for-windows-setup-and-configuration"></a>PDV moderno para la instalación de Windows y la configuración

Para obtener más información, consulte [configuración y la configuración modernas al por menor] () retail-modern-pos-device-activation.md de Retail POS.

### <a name="opos-device-setup-and-configuration"></a>Establecimiento y configuración de dispositivo de OPDV

Para obtener más información sobre los componentes de OPDV, consulte la sección “de las interfaces admitidas” de este documento. Normalmente, los controladores de OPDV suministran el fabricante del dispositivo. Cuando un controlador de dispositivo de OPDV está instalado, agrega una clave al Registro de Windows en una de las siguientes ubicaciones:

-   ** sistema de 32 bits: ** VALOR LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS de\_HKEY
-   ** sistema 64 bits: ** VALOR LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS de\_HKEY

Dentro de la ubicación del registro de ServiceOPOS, los dispositivos configurados se organizan según la clase de dispositivo de OPDV. Se guardan los controladores de dispositivo operaciones.

## <a name="supported-scenarios-by-hardware-station-type"></a>Situaciones de ejemplo admitidas del tipo emisora de hardware
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Soporte del cliente – emisora de hardware de IPC con la emisora de hardware de IIS

En la tabla siguiente se muestran las topologías y los escenarios de implementación que se admiten.

| Cliente      | Emisora de hardware de IPC | Emisora de hardware de IIS |
|-------------|----------------------|----------------------|
| Aplicación de Windows | Sí                  | Sí                  |
| PDV en la nube   | No                   | Sí                  |
| Android     | No                   | Sí                  |
| IOS         | No                   | Sí                  |

### <a name="network-peripherals"></a>Periférico de la red

Los periféricos de red se admiten directamente a través de la emisora de hardware que se especifica en moderno PDV para la aplicación para Windows. Para todos los demás clientes, debe implementar una emisora de hardware de IIS.

| Cliente      | Emisora de hardware de IPC | Emisora de hardware de IIS |
|-------------|----------------------|----------------------|
| Aplicación de Windows | Sí                  | Sí                  |
| PDV en la nube   | No                   | Sí                  |
| Android     | No                   | Sí                  |
| IOS         | No                   | Sí                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Tipos de dispositivo admitidos del tipo emisora de hardware
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>PDV moderno para Windows con una emisora de hardware de costes indirectos de producción (accesorio)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase de dispositivo compatible</th>
<th>Interfaces compatibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impresora</td>
<td><ul>
<li>OPDV</li>
<li>Controlador de Windows</li>
<li>Dispositivo</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="even">
<td>Impresora 2</td>
<td><ul>
<li>OPDV</li>
<li>Controlador de Windows</li>
<li>Dispositivo</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualización de líneas</td>
<td>OPDV</td>
</tr>
<tr class="even">
<td>Dos visualizaciones</td>
<td>Controlador de Windows</td>
</tr>
<tr class="odd">
<td>MSR</td>
<td><ul>
<li>OPDV</li>
<li>UWP (no se requiere ninguna configuración).</li>
<li>Cuña de teclado (no se requiere ninguna configuración).</li>
</ul></td>
</tr>
<tr class="even">
<td>Librador</td>
<td><ul>
<li>OPDV</li>
<li>La red <strong>Nota:</strong> librador un sólo se puede configurar si <strong>Cambio uso compartido</strong> se configura en el librador.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Cajón 2</td>
<td><ul>
<li>OPDV</li>
<li>La red <strong>Nota:</strong> librador un sólo se puede configurar si <strong>Cambio uso compartido</strong> se configura en el librador.</li>
</ul></td>
</tr>
<tr class="even">
<td>Escáner</td>
<td><ul>
<li>OPDV</li>
<li>UWP (no se requiere ninguna configuración).</li>
<li>Cuña de teclado (no se requiere ninguna configuración).</li>
</ul></td>
</tr>
<tr class="odd">
<td>Escáner 2</td>
<td><ul>
<li>OPDV</li>
<li>UWP (no se requiere ninguna configuración).</li>
<li>Cuña de teclado (no se requiere ninguna configuración).</li>
</ul></td>
</tr>
<tr class="even">
<td>Escala</td>
<td>OPDV</td>
</tr>
<tr class="odd">
<td>Terminal para ingreso de PIN</td>
<td>OPDV (el soporte se proporciona con personalización de Connector de pago.)</td>
</tr>
<tr class="even">
<td>Captura de firma</td>
<td>OPDV</td>
</tr>
<tr class="odd">
<td>Terminal de pago </td>
<td><ul>
<li>Compatibilidad con el dispositivo personalizada</li>
<li>Red (para obtener más información, consulte la documentación de Connector de pago.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Todos los clientes modernos de PDV que tienen una emisora dedicada de hardware de IIS

** Nota: ** Cuando la emisora de hardware de IIS dedicada es “,” existe una relación unívoca entre el cliente de PDV y la emisora del hardware.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase de dispositivo compatible</th>
<th>Interfaces compatibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impresora</td>
<td><ul>
<li>OPDV</li>
<li>El controlador de Windows <strong>Nota:</strong> para las impresoras de Windows en una red, el usuario del emisora de hardware debe tener permiso para tener acceso a la impresora.</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="even">
<td>Impresora 2</td>
<td><ul>
<li>OPDV</li>
<li>Controlador de Windows</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualización de líneas</td>
<td>OPDV</td>
</tr>
<tr class="even">
<td>MSR</td>
<td>OPDV</td>
</tr>
<tr class="odd">
<td>Librador</td>
<td><ul>
<li>OPDV</li>
<li>La red <strong>Nota:</strong> sólo librador por un perfil de hardware se puede configurar si <strong>Cambio uso compartido</strong> se configura en el librador.</li>
</ul></td>
</tr>
<tr class="even">
<td>Cajón 2</td>
<td><ul>
<li>OPDV</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="odd">
<td>Escáner</td>
<td>OPDV</td>
</tr>
<tr class="even">
<td>Escáner 2</td>
<td>OPDV</td>
</tr>
<tr class="odd">
<td>Escala</td>
<td>OPDV</td>
</tr>
<tr class="even">
<td>Terminal para ingreso de PIN</td>
<td>OPDV (el soporte se proporciona con personalización de Connector de pago.)</td>
</tr>
<tr class="odd">
<td>Sig. capturar</td>
<td>OPDV</td>
</tr>
<tr class="even">
<td>Terminal de pago </td>
<td><ul>
<li>Compatibilidad con el dispositivo personalizada</li>
<li>Red (para obtener más información, consulte la documentación de Connector de pago.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Todos los clientes modernos de PDV que tienen una emisora compartida del hardware de IIS

** Nota: ** Cuando se debe compartir la emisora de hardware de IIS”,” los dispositivos varios usuarios de la empresa emisora de hardware al mismo tiempo. Para este escenario, debe usar solamente los dispositivos que se muestran en la tabla siguiente. Si intenta para compartir los dispositivos que no se enumeran aquí, como los escáneres de código de barras y los MSRs los errores, aparecerán cuando intento múltiple de los dispositivos para demandar el mismo periféricos. En el futuro, tal configuración explícitamente se impedirá.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase de dispositivo compatible</th>
<th>Interfaces compatibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impresora</td>
<td><ul>
<li>OPDV</li>
<li>El controlador de Windows <strong>Nota:</strong> para las impresoras de Windows en una red, el usuario del emisora de hardware debe tener permiso para tener acceso a la impresora.</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="even">
<td>Impresora 2</td>
<td><ul>
<li>OPDV</li>
<li>Controlador de Windows</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="odd">
<td>Librador</td>
<td><ul>
<li>OPDV</li>
<li>La red <strong>Nota:</strong> sólo librador por un perfil de hardware se puede configurar si <strong>Cambio uso compartido</strong> se configura en el librador.</li>
</ul></td>
</tr>
<tr class="even">
<td>Cajón 2</td>
<td><ul>
<li>OPDV</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="odd">
<td>Terminal de pago </td>
<td><ul>
<li>Compatibilidad con el dispositivo personalizada</li>
<li>Red (para obtener más información, consulte la documentación de Connector de pago.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configuración para los escenarios compatibles
Para obtener más información sobre cómo crear perfiles de hardware, defina [ver y mantener los clientes del canal, incluidos los registros y las emisoras] de hardware (define-maintain-channel-clients-registers-hw-stations.md). ** Nota: ** Para Microsoft Dynamics 365 para la versión 1611 de las operaciones, el perfil de la emisora de hardware ya no se usa. Los atributos que configuró anteriormente en el perfil de la emisora de hardware son ahora la parte de la emisora de hardware en sí.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>PDV moderno para Windows con una emisora de hardware de costes indirectos de producción (accesorio)

Esta configuración es más la configuración típica para los registros tradicionales, fijos de Retail POS. Para este escenario, la información de perfil de hardware se asigna directamente al registro en sí. El número de terminal de EFT se debe establecer en el registro propiamente dicho. Para configurar esta configuración, siga estos pasos.

1.  Crear un perfil de hardware donde se configuran todos los periféricos necesarios.
2.  Asigne el perfil de hardware al registro de Retail POS.
3.  Crear una emisora de hardware ** dedicado ** del tipo para la tienda al por menor en el registro de PDV se usará. Una descripción es opcional. ** Nota: ** No es necesario establecer ninguna otra propiedades en la emisora del hardware. El resto de la información requerida, como el perfil de hardware, vendrá de registro propiamente dicho.
4.  Haga clic en ** al por menor y comercio ** &gt; ** TI al por menor ** &gt; ** programación de distribución **.
5.  Seleccione ** 1090 ** la programación de la distribución a la sincronización el nuevo perfil de hardware a la tienda. Haga clic en ejecución ** ahora ** a los cambios de sincronización a PDV.
6.  Seleccione ** 1040 ** la programación de la distribución a la sincronización la nueva emisora de hardware a la tienda. Haga clic en ejecución ** ahora ** a los cambios de sincronización a PDV.
7.  Instalar y activar PDV moderno para Windows.
8.  Iniciar PDV moderno para Windows, y comience para utilizar los dispositivos periféricos conectados.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Todos los clientes modernos de PDV que tienen una emisora dedicada de hardware de IIS

Esta configuración se puede utilizar para todos los clientes modernos de PDV que tengan una emisora de hardware que se usará exclusivamente por un registro de Retail POS. Para configurar esta configuración, siga estos pasos.

1.  Crear un perfil de hardware donde se configuran todos los periféricos necesarios.
2.  Crear una emisora de hardware ** dedicado ** del tipo para la tienda al por menor en el registro de PDV se usará.
3.  En la emisora dedicada de hardware, establezca las siguientes propiedades:
    -   ** Nombre de host – ** el nombre del equipo donde la host emisora de hardware ejecutará. ** Nota: ** La nube POS puede resolver ** localhost ** para determinar el equipo local en la nube PDV está ejecutando. Sin embargo, el certificado necesario para emparejar la nube PDV con la emisora de hardware también debe tener “Localhost” como el nombre del equipo. Para evitar problemas, se recomienda que anota una instancia de cada emisora dedicada de hardware para el almacén, según convenga. Para cada emisora de hardware, el nombre de host debe ser el nombre de equipo específico donde la emisora de hardware será implementada.
    -   ** Puerto – ** el puerto a utilizar para que la emisora de hardware comunicarse el cliente moderno de Retail POS.
    -   ** El perfil de hardware ** – si el perfil de hardware no se proporciona en la propia emisora de hardware, el perfil de hardware asignado al registro se usará.
    -   ** Número de PDV de EFT – ** El identificador terminal de EFT para usar cuando se registran las autorizaciones de EFT. Este identificador se proporciona por el procesador de tarjetas de crédito.
    -   ** Nombre del embalaje – ** el paquete de la emisora de hardware para utilizar cuando se implementa la emisora del hardware.

4.  Haga clic en ** al por menor y comercio ** &gt; ** TI al por menor ** &gt; ** programación de distribución **.
5.  Seleccione ** 1090 ** la programación de la distribución a la sincronización el nuevo perfil de hardware a la tienda. Haga clic en ejecución ** ahora ** a los cambios de sincronización a PDV.
6.  Seleccione ** 1040 ** la programación de la distribución a la sincronización la nueva emisora de hardware a la tienda. Haga clic en ejecución ** ahora ** a los cambios de sincronización a PDV.
7.  Instalar la emisora del hardware. Para obtener más información sobre cómo instalar la emisora de hardware, consulte [configuración y la configuración en el por menor retail-hardware-station-configuration-installation.md] () de la emisora del hardware.
8.  Instalar y activar moderno PDV. Para obtener más información sobre cómo instalar PDV, consulte moderno [configuración y la configuración modernas al por menor] () retail-modern-pos-device-activation.md de Retail POS.
9.  Iniciar sesión en moderno PDV, y seleccione ** realice las operaciones de fuera del librador **.
10. Iniciar ** administrar las emisoras de hardware ** la operación.
11. Haga clic en ** gestionar **.
12. En la página de la gestión de emisora de hardware, defina la opción para activar la emisora del hardware.
13. Seleccione la emisora de hardware para utilizar, y haga clic en ** pares **.
14. Una vez que se empareje la emisora de hardware, haga clic ** ** cierre.
15. En la página de selección de emisora de hardware, haga clic en la emisora recientemente seleccionado de hardware para convertirlo el activo.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Todos los clientes modernos de PDV que tienen una emisora compartida del hardware de IIS

Esta configuración se puede utilizar para todos los clientes modernos de PDV que comparten las emisoras de hardware con otros dispositivos. Para configurar esta configuración, siga estos pasos.

1.  Crear un perfil de hardware donde se configuren los periféricos necesarios.
2.  Crear una emisora de hardware ** compartido ** del tipo para la tienda al por menor en el registro de PDV se usará.
3.  En la emisora compartida del hardware, establezca las siguientes propiedades:
    -   ** Nombre de host – ** el nombre del equipo donde la host emisora de hardware ejecutará.
    -   ** La descripción ** – texto que ayude a identificar la emisora de hardware, por ejemplo ** devoluciones ** o ** frente ** de la tienda.
    -   ** Puerto – ** el puerto a utilizar para que la emisora de hardware comunicarse el cliente moderno de Retail POS.
    -   ** El perfil de hardware ** – para las emisoras compartidas de hardware, cada emisora de hardware debe tener un perfil de hardware. Los perfiles de hardware se pueden compartir entre varias emisoras de hardware, pero se debe asignar a cada emisora del hardware. Además, se recomienda usar cambios compartidos cuando los dispositivos varios utilizan el mismo emisora compartida del hardware. Para configurar un cambio compartidos, haga clic en ** al por menor y comercio ** &gt; ** el canal configurar ** &gt; ** Configuración de PDV ** &gt; ** el PDV ** &gt; ** los perfiles de hardware **. Para cada perfil de hardware compartido, seleccione la caja registradora, y establecer ** librador compartido de cambio ** la opción ** Sí **.
    -   ** Número de PDV de EFT – ** El identificador terminal de EFT para usar cuando se registran las autorizaciones de EFT. Este identificador se proporciona por el procesador de tarjetas de crédito.
    -   ** Nombre del embalaje – ** el paquete de la emisora de hardware para utilizar cuando se implementa la emisora del hardware.

4.  Repita los pasos 2 y 3 para cada emisora de hardware adicional necesaria en el almacén.
5.  Haga clic en ** al por menor y comercio ** &gt; ** TI al por menor ** &gt; ** programación de distribución **.
6.  Seleccione ** 1090 ** la programación de la distribución a la sincronización el nuevo perfil de hardware a la tienda. Haga clic en ejecución ** ahora ** a los cambios de sincronización a PDV.
7.  Seleccione ** 1040 ** la programación de la distribución a la sincronización la nueva emisora de hardware a la tienda. Haga clic en ejecución ** ahora ** a los cambios de sincronización a PDV.
8.  Instalar la emisora de hardware en cada equipo host que configure en los pasos 2 y 3. Para obtener más información sobre cómo instalar la emisora de hardware, consulte [configuración y la configuración en el por menor retail-hardware-station-configuration-installation.md] () de la emisora del hardware.
9.  Instalar y activar moderno PDV. Para obtener más información sobre cómo instalar PDV, consulte moderno [configuración y la configuración modernas al por menor] () retail-modern-pos-device-activation.md de Retail POS.
10. Iniciar sesión en moderno PDV, y seleccione ** realice las operaciones de fuera del librador **.
11. Iniciar ** administrar las emisoras de hardware ** la operación.

12. Haga clic en ** gestionar **.
13. En la página de la gestión de emisora de hardware, defina la opción para activar la emisora del hardware.
14. Seleccione la emisora de hardware para utilizar, y haga clic en ** pares **.
15. Repita el paso 14 para cada emisora de hardware que utilice moderno PDV.
16. Después de crear todas las emisoras necesarias de hardware, se emparejan clic ** ** cierre.
17. En la página de selección de emisora de hardware, haga clic en la emisora recientemente seleccionado de hardware para convertirlo el activo. ** Nota: ** Si los dispositivos utilizan a menudo distintas emisoras de hardware, recomendamos que configure PDV moderno para preguntar a los cajeros seleccione una emisora de hardware al iniciar el proceso de la propuesta. Haga clic en ** al por menor y comercio ** &gt; ** canal configurar ** &gt; ** Configuración de PDV ** &gt; ** ** registros. Seleccione el registro, y establece ** seleccione acerca de propuesta ** la opción ** Sí **. Use ** 1090 ** la programación de distribución a los cambios de sincronización a la base de datos de canal.

## <a name="extensibility"></a>Extensibilidad
Para obtener información sobre los escenarios de la extensibilidad para la emisora de hardware, consulte la extensibilidad [] de la emisora de hardware revelador (- itpro/hardware-station-extensibility.md).

## <a name="security"></a>Seguridad
Según las normas actuales de seguridad, los valores siguientes se deben usar en un entorno de producción: ** Nota: ** El instalación de la emisora de hardware automáticamente hará estos ediciones de registro como parte de la instalación a través de autoservicio.

-   La capa de sockets seguros (SSL) debería deshabilitarse.
-   Únicamente la versión 1.2 de (TLS) de seguridad de la capa de transporte (o la versión más alta actual) debe estar habilitada y utilizarla. ** Nota: ** De forma predeterminada, SSL y toda la versión de TLS excepto TLS 1.2 se deshabilitan. Para editar o habilitar estos valores, siga estos pasos:
    1.  Presione el logotipo de Windows para abrir key+R a ** ejecución ** ventana.
    2.  En ** Abrir ** campo, escriba Regedit ** **, y haga clic en ** éste **.
    3.  Si aparece a ** Control de cuentas de usuario ** cuadro de mensaje, haga clic en Sí ** **.
    4.  En ** Editor de Registro ** la ventana, desplácese ** VALOR LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols de HKEY **\_. Las teclas siguientes automáticamente se han especificado para permitir sólo TLS 1.2:
        -   TLS 1.2Server: Enabled=1
        -   TLS 1.2Server: DisabledByDefault=0
        -   TLS 1.2Client: Enabled=1
        -   TLS 1.2Client: DisabledByDefault=0
        -   TLS 1.1Server: Enabled=0
        -   TLS 1.1Client: Enabled=0
        -   TLS 1.0Server: Enabled=0
        -   TLS 1.0Client: Enabled=0
        -   SSL 3.0Server: Enabled=0
        -   SSL 3.0Client: Enabled=0
        -   SSL 2.0Server: Enabled=0
        -   SSL 2.0Client: Enabled=0
-   Ninguno puertos de red adicionales deben abrirse, a menos que se necesitan para conoce, los motivos especificadas.
-   el uso compartido de recursos de Cruce- origen se debe deshabilitar y debe especificar los orígenes permitidos que se aceptan.
-   Solo las entidades emisoras de certificados de confianza deben ser utilizadas para recopilar los certificados que se usarán en los equipos que ejecutan la emisora del hardware.

** Nota: ** Es muy importante que revise las instrucciones de la seguridad de IIS y los requisitos de (PCI) del sector de la tarjeta de pago.

## <a name="peripheral-simulator"></a>Simulador periférico
Para obtener más información, consulte [el simulador periféricos al por menor retail-peripheral-simulator.md] ().

## <a name="microsofttested-peripheral-devices"></a>Dispositivos periféricos de Microsofttested
### <a name="ipc-built-in-hardware-station"></a>Emisora de hardware de costes indirectos de producción (accesorio)

Los siguientes periféricos probados se mediante la emisora de hardware de costes indirectos de producción que se especifica en moderno PDV para Windows.

#### <a name="printer"></a>Impresora

| Fabricante | Modelo    | Interfaz | Comentarios                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | OPDV      |                         |
| Epson        | TM-T88V  | OPDV      |                         |
| Estrella         | TSP650II | OPDV      |                         |
| Estrella         | TSP650II | Personalizar    | Conectado a través de la red   |
| Estrella         | mPOP     | OPDV      | Conectado mediante Bluetooth |
| HP           | F7M67AA  | OPDV      | Accionado USB             |

#### <a name="bar-code-scanner"></a>Escáner de código de barras

| Fabricante  | Modelo         | Interfaz | Comentarios |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPDV      |          |
| Honeywell     | 1900          | UWP       |          |
| Símbolo        | LS2208        | OPDV      |          |
| HP integró | E1L07AA       | OPDV      |          |
| Datalogic     | Magellan 8400 | OPDV      |          |

#### <a name="pin-pad"></a>Terminal para ingreso de PIN

| Fabricante | Modelo  | Interfaz | Comentarios                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPDV      | Requiere personalización de Connector de pago |

#### <a name="payment-terminal"></a>Terminal de pago 

| Fabricante | Modelo | Interfaz | Comentarios                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizar    | Requiere personalización de Connector de pago                                |
| VeriFone     | MX925 | Personalizar    | Requiere personalización de Connector de pago; conectado a través de la red y USB |
| VeriFone     | MX915 | Personalizar    | Requiere personalización de Connector de pago; conectado a través de la red y USB |

#### <a name="cash-drawer"></a>Caja registradora

| Fabricante | Modelo     | Interfaz | Comentarios                |
|--------------|-----------|-----------|-------------------------|
| Estrella         | mPOP      | OPDV      | Conectado mediante Bluetooth |
| APG          | Atwood    | Personalizar    | Conectado a través de la red   |
| Estrella         | SMD2-1317 | OPDV      |                         |
| HP           | QT457AA   | OPDV      |                         |

#### <a name="line-display"></a>Visualización de líneas

| Fabricante  | Modelo   | Interfaz | Comentarios |
|---------------|---------|-----------|----------|
| HP integró | G6U79AA | OPDV      |          |
| Epson         | M58DC   | OPDV      |          |

#### <a name="signature-capture"></a>Captura de firma

| Fabricante | Modelo  | Interfaz | Comentarios |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPDV      |          |

#### <a name="scale"></a>Escala

| Fabricante | Modelo         | Interfaz | Comentarios |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPDV      |          |

#### <a name="msr"></a>MSR

| Fabricante | Modelo       | Interfaz | Comentarios |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPDV      |          |
| HP           | IDRA-334133 | OPDV      |          |

### <a name="dedicated-iis-hardware-station"></a>Emisora dedicada de hardware de IIS

Los siguientes se periféricos probar () mediante una emisora no compartida dedicada de hardware de IIS así como PDV moderno para Windows y la nube PDV.

#### <a name="printer"></a>Impresora

| Fabricante | Modelo    | Interfaz | Comentarios                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPDV      |                           |
| Epson        | TM-T88V  | OPDV      |                           |
| Estrella         | TSP650II | OPDV      |                           |
| Estrella         | TSP650II | Personalizar    | Conectado a través de la red     |
| Estrella         | TSP100   | OPDV      | Requiere los controladores de TSP650II |
| HP           | F7M67AA  | OPDV      | Accionado USB               |

#### <a name="bar-code-scanner"></a>Escáner de código de barras

| Fabricante  | Modelo   | Interfaz | Comentarios |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPDV      |          |
| Símbolo        | LS2208  | OPDV      |          |
| HP integró | E1L07AA | OPDV      |          |

#### <a name="pin-pad"></a>Terminal para ingreso de PIN

| Fabricante | Modelo  | Interfaz | Comentarios                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPDV      | Requiere personalización de Connector de pago |

#### <a name="payment-terminal"></a>Terminal de pago 

| Fabricante | Modelo | Interfaz | Comentarios                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personalizar    | Requiere personalización de Connector de pago                                |
| VeriFone     | MX925 | Personalizar    | Requiere personalización de Connector de pago; conectado a través de la red y USB |
| VeriFone     | MX915 | Personalizar    | Requiere personalización de Connector de pago; conectado a través de la red y USB |

#### <a name="cash-drawer"></a>Caja registradora

| Fabricante | Modelo     | Interfaz | Comentarios              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizar    | Conectado a través de la red |
| Estrella         | SMD2-1317 | OPDV      |                       |
| HP           | QT457AA   | OPDV      |                       |

#### <a name="line-display"></a>Visualización de líneas

| Fabricante  | Modelo   | Interfaz | Comentarios |
|---------------|---------|-----------|----------|
| HP integró | G6U79AA | OPDV      |          |
| Epson         | M58DC   | OPDV      |          |

#### <a name="signature-capture"></a>Captura de firma

| Fabricante | Modelo  | Interfaz | Comentarios |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPDV      |          |

#### <a name="scale"></a>Escala

| Fabricante | Modelo         | Interfaz | Comentarios |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPDV      |          |

#### <a name="msr"></a>MSR

| Fabricante | Modelo       | Interfaz | Comentarios |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPDV      |          |
| HP           | IDRA-334133 | OPDV      |          |

### <a name="shared-iis-hardware-station"></a>Emisora compartida del hardware de IIS

Los siguientes periféricos probados se mediante una emisora compartida del hardware de IIS así como PDV moderno para Windows y la nube PDV. ** Nota: ** Únicamente se admiten una impresora, un terminal de pago, y una caja registradora.

#### <a name="printer"></a>Impresora

| Fabricante | Modelo    | Interfaz | Comentarios                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPDV      |                           |
| Epson        | TM-T88V  | OPDV      |                           |
| Estrella         | TSP650II | OPDV      |                           |
| Estrella         | TSP650II | Personalizar    | Conectado a través de la red     |
| Estrella         | TSP100   | OPDV      | Requiere los controladores de TSP650II |
| HP           | F7M67AA  | OPDV      | Accionado USB               |

#### <a name="payment-terminal"></a>Terminal de pago 

| Fabricante | Modelo | Interfaz | Comentarios                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personalizar    | Requiere personalización de Connector de pago; conectado a través de la red y USB |
| VeriFone     | MX915 | Personalizar    | Requiere personalización de Connector de pago; conectado a través de la red y USB |

#### <a name="cash-drawer"></a>Caja registradora

| Fabricante | Modelo     | Interfaz | Comentarios              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizar    | Conectado a través de la red |
| Estrella         | SMD2-1317 | OPDV      |                       |
| HP           | QT457AA   | OPDV      |                       |

## <a name="troubleshooting"></a>Solución de problemas
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>PDV moderno puede detectar la emisora de hardware en su lista de selección, pero no puede completar el emparejamiento

** Solución: ** Compruebe la siguiente lista de puntos potencial de error:

-   El equipo que es PDV moderno actual confía el certificado que se usa en el equipo que ejecute la emisora del hardware.
    -   Para verificar esta configuración, en un explorador web, vaya a la dirección URL siguiente: nombre&lt;de https://Computer&gt;:&lt;Número&gt;de puerto HardwareStation//ping.
    -   Esta dirección URL utiliza un ping para comprobar que el equipo puede tener acceso, y el explorador indica si el certificado está confirmado. (Por ejemplo, en Internet Explorer, un icono de bloqueo aparece en la barra de dirección. Al hacer clic en este icono, Internet Explorer comprueba si el certificado se comprometa actualmente. Es posible instalar el certificado en el equipo local viendo los detalles del certificado que se muestra.)
-   En el equipo que ejecute la emisora de hardware, el puerto que se usará en la emisora de hardware se abre en firewall.
-   La emisora de hardware correctamente ha instalado la información de la cuenta mercantil a través de la herramienta mercantil de la información de la instalación que las ejecuciones al final del hardware colocan el instalador.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>PDV moderno no puede detectar la emisora de hardware en su lista de selección

** Solución: ** Cualquiera de los factores siguientes puede producir este problema:

-   La emisora de hardware no se ha configurado correctamente en Headquarters. Use los pasos anteriores de este tema para comprobar que el perfil de la emisora de hardware y la emisora de hardware ya se especifiquen correctamente.
-   Los trabajos no se han ejecutado de actualizar la configuración del canal. En este caso, ejecute el trabajo 1070 para la configuración del canal.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>PDV no moderno refleja nuevos parámetros en la caja registradora

** Solución: ** Cierra el lote actual. Los cambios en la caja registradora no se actualizan a PDV moderno hasta que el lote está cerrado actual.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>PDV moderno está notificando un problema con un periféricos de ventas al por menor

** Solución: ** Aquí hay algunas causas típica para este problema:

-   Asegúrese de que estén cerradas otras utilidades de configuración del controlador del dispositivo. Si estas utilidades están abiertas, que puede ser para impedir que PDV moderno o la emisora de hardware demande el dispositivo.
-   Si el periféricos al por menor se comparte con dispositivos múltiples del PDV, asegúrese de que pertenezca a una de las categorías siguientes:
    -   Caja registradora
    -   Impresora de recibos
    -   Terminal de pago 

    Si el periféricos no pertenece a una de estas categorías, la emisora de hardware no está diseñada para habilitar el que se periféricos responsable entre los dispositivos múltiples de Retail POS.
-   A veces, los controladores de dispositivo pueden realizar los objetos (CCOs) de control de existencias para dejar de trabajar correctamente. Si un dispositivo se ha instalado recientemente, pero no funciona correctamente o observa otros elementos, puede a menudo resolver el problema reinstalando el CCOs. Para descargar el CCOs, visite< http://monroecs.com/oposccos_current.htm>.
-   Si realiza cambios frecuentes periféricos durante las pruebas o la solución de problemas, puede que tenga que IIS restablecer en lugar de esperar la caché para actualizarse. Para restablecer IIS, siga estos pasos:
    1.  ** ** Inicio del menú, tipo CMD ** **.
    2.  En los resultados de la búsqueda, haga clic con el botón secundario ** símbolo del sistema **, haga clic en ** ejecución como administrador **.
    3.  En ** símbolo del sistema ** la ventana, el tipo iisreset ** /Restart ** y presione INTRO.
    4.  Una vez que haya reiniciado IIS, reinicie moderno PDV.
-   A medida que está creando cambios frecuentes a los dispositivos periféricos, si selecciona también con frecuencia comienza y dejar el cliente del PDV, el proceso de dllhost de sesión anterior de POS puede interferir con la sesión actual. En este caso, un dispositivo no esté utilizable hasta que se cierre que el biblioteca de vínculos dinámicos (DLL) aloja encargado de la sesión anterior. Para cerrar el host DLL, siga estos pasos:
    1.  ** ** Inicio del menú, tipo ** administrador de tareas **.
    2.  En los resultados de la búsqueda, haga clic en ** administrador de tareas **.
    3.  En administrador de tareas, en ** los detalles ** la ficha, haga clic en el encabezado de columna que se etiqueta ** ** nombre para la tabla ordenar alfabéticamente por nombre.
    4.  Desplace siguiente hasta encontrar dllhost.exe.
    5.  Seleccione cada host DLL, y haga clic en ** tarea del final **.
    6.  Una vez que se haya cerrado los host DLL, reinicie moderno PDV.


<a name="see-also"></a>Consulte también
--------

[Simulador periféricos al por menor retail-peripheral-simulator.md] ()


