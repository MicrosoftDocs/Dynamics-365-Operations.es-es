---
title: Periféricos
description: En este artículo explica los conceptos relacionados con los periféricos de Commerce.
author: BrianShook
ms.date: 09/08/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.custom:
- "268444"
- intro-internal
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: b3113626b18ad7f074c808d7631d13b09071bef2
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460004"
---
# <a name="peripherals"></a>Periféricos

[!include[banner](includes/banner.md)]

En este artículo explica los conceptos relacionados con los periféricos de tiendas. Describe las distintas maneras en que se pueden conectar los periféricos al punto de venta (PDV) y los componentes responsables de gestionar la conexión con el PDV.

## <a name="concepts"></a>Conceptos

### <a name="pos-registers"></a>Registros de PDV

Navegación: vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Registros**. El registro del punto de venta PDV es una entidad que se utiliza para definir las características de una instancia específica del PDV. Entre estas características se incluyen el perfil de hardware o la configuración de los periféricos que se utilizarán en el registro, el almacén al que está asignado el registro y la experiencia visual para el usuario que inicia sesión en ese registro.

### <a name="devices"></a>Dispositivos

Navegación: vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Dispositivos**. Un dispositivo es una entidad que representa una instancia física de un dispositivo que está asignado a un registro de PDV. Cuando se crea un dispositivo, se asigna a un registro de PDV. La entidad de dispositivo realiza un seguimiento de información acerca de cuándo se activa un registro de PDV, el tipo de cliente que se utiliza y el paquete de aplicación que se ha implementado en un dispositivo específico. 

Los dispositivos se pueden asignar a los tipos de aplicación siguientes: Retail Modern POS, Retail Cloud POS, Retail Modern POS – Android y Retail Modern POS – iOS.

### <a name="modern-pos"></a>Modern POS

Modern POS es el programa de PDV para Microsoft Windows. Se puede implementar en sistemas operativos Windows 10 y Windows 11.

### <a name="cloud-pos"></a>PDV en la nube

Cloud POS es una versión basada en explorador del programa Modern POS al que se puede acceder a través de un explorador web.

### <a name="modern-pos-for-ios"></a>Modern POS para iOS

Modern POS para iOS es una versión basada en iOS del programa Modern POS que se puede implementar en dispositivos iOS.

### <a name="modern-pos-for-android"></a>Modern POS para Android

Modern POS para Android es una versión basada en Android del programa Modern POS que se puede implementar en dispositivos Android.

### <a name="pos-peripherals"></a>Periféricos de PDV

Los periféricos de PDV son dispositivos que admiten explícitamente las funciones del PDV. Estos periféricos se suelen dividir en clases específicas. Para obtener más información sobre estas clases, consulte la sección sobre clases de dispositivos de este artículo.

### <a name="hardware-station"></a>Estación de hardware

Navegación: vaya a **Retail y Commerce \> Canales \> Tiendas \> Todas las tiendas**. Seleccione una tienda y, a continuación, elija la ficha desplegable **Estaciones de hardware**. La configuración de la **Estación de hardware** es un valor a nivel de canal que se usa para definir las instancias donde se implementará la lógica periférica. Este valor a nivel de canal se usa para determinar las características de la estación de hardware. También se usa para mostrar las estaciones de hardware que están disponibles para una instancia de Modern POS en una tienda determinada. La estación de hardware se ha incluido en el programa Modern POS para Windows y Android. La estación de hardware también se puede implementar independientemente como programa independiente de Microsoft Internet Information Services (IIS). En este caso, se tiene acceso a través de una red.

### <a name="hardware-profile"></a>Perfil de hardware

Navegación: vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware**. El perfil de hardware es una lista de dispositivos que están configurados para un registro de PDV o una estación de hardware. El perfil de hardware se puede asignar directamente a un registro de PDV o a una estación de hardware.

## <a name="devices-classes"></a>Clases de dispositivos
Los periféricos de PDV se suelen dividir en clases. Esta sección describe y ofrece una descripción general de los dispositivos que admite Modern POS.

### <a name="printer"></a>Impresora

Las impresoras incluyen impresoras tradicionales de recibos de PDV e impresoras a toda página. Se ofrece compatibilidad con las impresoras a través de las interfaces del controlador de la vinculación e incrustación de objetos para Retail POS (OPDV) y Microsoft Windows. Se pueden utilizar hasta dos impresoras al mismo tiempo. Esta funcionalidad admite las situaciones en las que los recibos de clientes por ventas al contado sin envío a domicilio se imprimen en impresoras de recibos, mientras que los pedidos de los clientes, que tienen más información, se imprimen en una impresora a toda página. Las impresoras de recibos se pueden conectar directamente con un equipo mediante USB, a una red mediante Ethernet o a través de Bluetooth.

### <a name="scanner"></a>Escáner

Se pueden utilizar hasta dos escáneres de código de barras al mismo tiempo. Esta capacidad admite escenarios donde se requiere un escáner con mayor movilidad para escanear artículos pesados o de mayor tamaño, mientras que se puede usar un escáner incrustado fijo para la mayoría de los elementos de tamaño normal para agilizar los plazos de salida. Se puede prestar compatibilidad a los escáneres a través de OPDV, la plataforma de Windows universal (UWP) o las de interfaces de cuña de teclado. Se puede usar USB o Bluetooth para conectar un escáner a un equipo.

### <a name="msr"></a>MSR

Se puede configurar un lector de banda magnética (MSR) de USB mediante los controladores de OPDV. Si desea usar un MSR independiente para las transacciones de pago a través de transferencias electrónicas de fondos (EFT), el MSR se debe gestionar por un conector de pago. Los MSR independientes se pueden usar para datos de fidelización de clientes, inicio de sesión de empleados y especificación de tarjetas regalo, independientemente del conector de pago.

### <a name="cash-drawer"></a>Caja registradora

Dos cajas registradoras se admiten por perfil de hardware. Esta capacidad permite que dos turnos activos por el registro estén disponibles al mismo tiempo. En el caso de turnos compartidos o una caja registradora que usan varios dispositivos de PDV móviles al mismo tiempo, solo una caja registradora se permite por perfil de hardware. Las cajas registradores se pueden conectar directamente con un equipo mediante USB o a una impresora de recibos a través de una interfaz RJ12. En algunos casos, las cajas registradoras también se pueden conectar a través de Bluetooth.

### <a name="line-display"></a>Visualización de líneas

Se usarán pantallas de línea para mostrar los productos, los saldos de transacciones y otra información útil para el cliente durante una transacción. Una pantalla de línea se puede conectar al equipo mediante USB con controladores de OPDV.

### <a name="signature-capture"></a>Captura de firma

Los dispositivos de digitalizador de firmas se pueden conectar directamente con un equipo mediante USB mediante los conductores de OPDV. Cuando se configura la captura de la firma, se pedirá al cliente que firme en el dispositivo. Después de firmar, se muestra al cajero para la aceptación.

### <a name="scale"></a>Balanza

Las balanzas se puede conectar al equipo mediante USB con controladores de OPDV. Cuando un producto que se marca como producto pesado se agrega a una transacción, el PDV lee el peso de la balanza, agrega al producto a la transacción y utiliza la cantidad ha proporcionado la balanza.

### <a name="pin-pad"></a>Terminal para introducción de PIN

Las terminales para el ingreso del número de identificación personal (PIN) se admiten a través de OPDV, pero deben administrarse a través de un conector de pago.

### <a name="secondary-display"></a>Pantalla secundaria

Cuando se configura una pantalla secundaria, se utilizará el número 2 de pantalla de Windows para mostrar la información básica. De forma predeterminada, la pantalla secundaria no se puede configurar y muestra contenido limitado. El propósito de la pantalla secundaria es admitir una extensión de proveedor de software independiente (ISV). 

### <a name="payment-device"></a>Dispositivo de pago

La compatibilidad con el dispositivo de pago se implementa a través del conector de pago. Los dispositivos de pago pueden realizar una o varias de las funciones que ofrecen otras clases de dispositivo. Por ejemplo, un dispositivo de pago puede funcionar como un lector de tarjetas/MSR, una pantalla de línea, un dispositivo de captura de firmas o una terminal de ingreso de PIN. La compatibilidad de los dispositivos de pago se implementa independientemente de la del dispositivo independiente que se ofrece para otros dispositivos que se incluyen en el perfil de hardware.

## <a name="supported-interfaces"></a>Interfaces admitidas
### <a name="opos"></a>OPDV

Para ayudar a garantizar que se pueden utilizar la mayor variedad posible de dispositivos con Commerce, la norma OLE del sector de PDV es la plataforma principal de dispositivos periféricos para aplicaciones que se admite. La norma OLE para PDV la creó la National Retail Federation (NRF), la cual establece los protocolos de comunicación estándares del sector para los dispositivos periféricos para aplicaciones de comercio. OPDV es una implementación ampliamente adoptada de norma OLE para PDV. Se desarrolló a mitad de los años 90 y se ha actualizado varias veces desde entonces. OPDV proporciona una arquitectura de controlador de dispositivos que habilita la integración fácil de hardware de PDV con los sistemas de PDV basados en Windows. Los controles de OPDV gestionan la comunicación entre el hardware compatible y el software de PDV. El control de OPDV consta de dos partes:

-   **Objeto de control**: el objeto de control para una clase de dispositivo (como pantallas de línea) ofrece la interfaz para el programa de software. Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) proporciona un conjunto normalizado de objetos de control de OPDV denominados Common Control Objects (CCO). Los CCO se usan para probar el componente de PDV de Commerce. Por lo tanto, las pruebas ayudan a garantizar que, si Commerce admite una clase de dispositivo con OPDV, muchos tipos de dispositivo pueden ser compatibles, siempre que el proveedor proporcione un objeto de servicio que se genere para OPDV. No es necesario probar explícitamente cada tipo de dispositivo.
-   **Objeto de servicio**: el objeto de servicio proporciona comunicación entre el objeto de control (CCO) y el dispositivo. Por lo general, el objeto de servicio para un dispositivo lo proporciona el fabricante del dispositivo. Sin embargo, en algunos casos, es posible que tenga que descargar el objeto de servicio de la página web del fabricante. Por ejemplo, un objeto de servicio más reciente puede estar disponible. Para encontrar la dirección de la página web del fabricante, vea la documentación de hardware.

[![Objeto de control y objeto de servicio.](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) La compatibilidad para la implementación de OPDV de OLE para PDV ayuda a garantizar que, si los fabricantes de dispositivos y los editores de PDV implementan la norma correctamente, los sistemas de PDV y los dispositivos admitidos pueden trabajar conjuntamente, incluso si no se probaron antes conjuntamente. 

> [!NOTE]
> La compatibilidad de OPDV no garantiza que se admitan todos los dispositivos que tienen controladores de OPDV. Commerce debe primero admitir ese tipo de dispositivo, o clase, con OPDV. Además, los objetos de servicio no siempre pueden actualizarse con la última versión del CCO. También debe tener en cuenta que, en general, la calidad de los objetos del servicio varía.

### <a name="windows"></a>Windows

La impresión de recibos en el PDV se optimiza para OPDV. OPDV tiende a ser mucho más rápido que imprimir a través de Windows. Por tanto, es recomendable usar OPDV, especialmente en entornos donde se imprimen recibos de 40 columnas y los tiempos de transacción tienen que ser rápidos. Para la mayoría de los dispositivos, deberá utilizar controles de OPDV. Sin embargo, algunas impresoras de recibos de OPDV también admiten controladores de Windows. Si usa un controlador de Windows, puede tener acceso a las últimas fuentes y conectar en red una impresora para varios registros. Sin embargo, existen desventajas al utilizar los conductores de Windows. Algunos ejemplos estas desventajas son:

-   Cuando se usan los controladores de Windows, las imágenes se generan antes de la impresión. Por lo tanto, la impresión tiende a ser más lenta que en impresoras que usan controles de OPDV.
-   Los dispositivos conectados a través de la impresora ("cadena margarita") pueden no funcionar correctamente cuando se usan los controladores de Windows. Por ejemplo, la caja registradora puede que no se abra o la impresora de recibos puede que no funcione como espera.
-   OPDV también admite un conjunto más amplio de variables que son específicas de las impresoras de recibos, como papel para cortar o impresión de resguardos.
-   Las impresoras de Windows no se admiten a través de la estación de hardware de IIS. 

Si los controles de OPDV están disponibles para la impresora de Windows que usa, la impresora debe aún así funcionar correctamente con Commerce.

### <a name="plug-and-play-devices"></a>Dispositivos plug and play

Cuando un dispositivo Plug and Play se conecta con una versión del SO de Windows que admita ese tipo de dispositivo, no se requerirá ningún controlador para que el dispositivo se use como previsto. Por ejemplo, si Windows detecta un dispositivo altavoz de Bluetooth, el SO sabe que tiene el dispositivo es del tipo de clase "Altavoz" y trata ese dispositivo como altavoz. No es necesaria configuración adicional. 

En el caso de los dispositivos periféricos de PDV, muchos dispositivos USB se pueden enchufar y el SO Windows los reconocerá como Dispositivos de interfaz de usuario (HID). Sin embargo, es posible que Windows no pueda determinar las capacidades que proporciona el dispositivo, ya que el dispositivo no especifica la clase o el tipo de dispositivo. En Windows 10, se han agregado clases de dispositivo para los escáneres de código de barras y los MSR. Por lo tanto, si un dispositivo se declara a Windows 10 como dispositivo de una de estas clases, Windows estará al tanto de los eventos del dispositivo en los momentos adecuados.

Modern POS admite UWP, MSR y escáneres. Por lo tanto, cuando Modern POS está listo para recibir datos desde uno de estos dispositivos y un dispositivo que pertenezca a una de estas clases de dispositivo se conecta, ese dispositivo se podrá utilizar. Por ejemplo, si un escáner de códigos de barras de plug and play se conecta a un equipo de Windows 10 y un inicio de sesión de código de barras se configura para Modern POS, el escáner de códigos de barras estará activo en la página de inicio de sesión. No es necesaria configuración adicional.

Se están agregando clases adicionales de periféricos POS a Windows, como clases para cajas registradoras e impresoras de recibos. La compatibilidad para estas nuevas clases de dispositivo en Modern POS está pendiente.

> [!NOTE] 
> Ciertos dispositivos USB pueden dejar de responder o no ser fiables cuando se administran mediante una función de administración de energía de Windows 10 llamada [Suspensión selectiva USB](/windows-hardware/drivers/usbcon/usb-selective-suspend). Si un periférico USB deja de responder, puede ser necesario desactivar la función de suspensión selectiva para ese dispositivo. Para obtener más información, consulte [Habilitar suspensión selectiva](/windows-hardware/drivers/usbcon/usb-selective-suspend#enabling-selective-suspend). 

### <a name="keyboard-wedge"></a>Cuña de teclado

Los dispositivos de cuña de teclado envían datos al equipo como si los datos se escribieran en un teclado. Por lo tanto, de forma predeterminada, el campo que está activo en PDV recibirá los datos que se escanean o pasan por la banda. En algunos casos, este comportamiento puede producir el tipo incorrecto de datos que se digitalizarán en el campo incorrecto. Por ejemplo, un código de barras se puede escanear en un campo que se ha creado para la entrada de los datos de la tarjeta de crédito. En muchos casos, hay lógica en los PDV que determina si los datos que se escanean o se pasan por la banda es un una tarjeta de código de barras o una tarjeta que se ha pasado por la banda. De esta forma, los datos se gestionan correctamente. Sin embargo, cuando los dispositivos se configuran como OPDV en lugar de dispositivos de cuña de teclado, hay más control sobre cómo los datos de esos dispositivos se pueden utilizar, porque se tiene más información sobre el dispositivo que origina estos datos. Por ejemplo, los datos de un escáner de códigos de barras se reconoce automáticamente como código de barras y el registro asociado en la base de datos se encuentra más fácilmente y más rápidamente que si se usara una búsqueda de cadenas genérica, como en el caso de los dispositivos de cuña de teclado.

> [!NOTE]
> Cuando se utilizan escáneres de cuña de teclado en el POS, deben programarse para enviar un retorno de carro o evento **Entrar**, después del último carácter escaneado. Si no se realiza esta configuración, los escáneres de cuña de teclado no funcionarán correctamente. Consulte la documentación proporcionada por el fabricante de su dispositivo para obtener detalles sobre cómo agregar el evento de devolución de carro.  

### <a name="device-printers"></a>Impresoras de dispositivos

Las impresoras de tipo "Dispositivo" se pueden configurar para que pregunten al usuario que seleccione una impresora que está configurada para el equipo. Cuando una impresora del tipo "Dispositivo" se configura, si Modern POS detecta un comando de impresión, se pedirá al usuario que seleccione una impresora en una lista. Este comportamiento se diferencia del comportamiento de los controladores de "Windows", porque el tipo de impresora de Windows en el perfil de hardware no muestra al usuario una lista de impresoras. En su lugar, requiere que se proporcione una impresora con nombre en el campo **Nombre del dispositivo**.

### <a name="network"></a>Red

Las cajas registradoras, las impresoras de recibos y los terminales de pago gestionables a través de la red se pueden usar en una red, ya sea directamente a través de la estación de hardware de las comunicaciones entre procesos (IPC) que se genera en Modern POS para la aplicación de Windows o a través de la estación de hardware de IIS para otros clientes de Modern POS.

## <a name="hardware-station-deployment-options"></a>Opciones de implementación de la estación de hardware

### <a name="dedicated"></a>Dedicada

Los clientes de Modern POS para Windows y Android incluyen estaciones de hardware **dedicadas** o integradas. Esos clientes pueden comunicarse directamente con los periféricos utilizando la lógica de negocios que está integrada en las aplicaciones. La aplicación Android solo admite dispositivos de red. Para más información sobre soporte periférico para Android, visite el artículo [Configurar la aplicación POS hybrid en Android e iOS](./dev-itpro/hybridapp.md).

Para usar la estación de hardware dedicada, siga estos pasos.

1. Asigne un perfil de hardware a un registro que usará Modern POS para la aplicación de Windows o Android.
1. Cree una estación de hardware de tipo "Dedicado" para la tienda donde se usará el registro. 
1. Abra Modern POS en modo sin cajón y use la operación **Administrar estaciones de hardware** para activar las capacidades de la estación de hardware. La estación de hardware dedicada estará activa de forma predeterminada. 
1. Salga de Modern POS. Luego vuelva a iniciar sesión y abra un turno. Los periféricos que están configurados en el perfil de hardware ahora serán utilizables. 

### <a name="shared"></a>Compartido

También denominada a veces estación de hardware "IIS", "IIS" implica que la aplicación PDV se conecta a la estación de hardware a través de Microsoft Internet Information Services. La aplicación de PDV se conecta a la estación de hardware de IIS a través de los servicios web que se ejecutan en un equipo donde los dispositivos se conectan. Cuando se usa la estación de hardware compartida, los periféricos asociados a una estación de hardware se pueden usar por cualquier registro de PDV que esté en la misma red que la estación de hardware de IIS. Dado que solo Modern POS para Windows y Android incluyen compatibilidad integrada para periféricos, el resto de aplicaciones de Modern POS deben usar la estación de hardware de IIS para comunicarse con los periféricos de PDV que se configuran en el perfil de hardware. Por lo tanto, cada instancia de la estación de hardware de IIS requiere un equipo que ejecute el servicio web y la aplicación que se comunica con los dispositivos. 

La estación de hardware compartida se puede usar para permitir que varios clientes de punto de venta compartan periféricos o se puede usar para administrar un conjunto comprometido de periféricos para un único punto de venta. 

Cuando se usa una estación de hardware para admitir el intercambio de periféricos entre varios clientes de PDV, solo se deben usar cajas registradoras, impresoras de recibos y terminales de pago. No puede conectar directamente los escáneres de código de barras independientes, los MSR, pantallas las de línea, las balanzas u otros dispositivos. Si no, aparecerán conflictos cuando varios dispositivos PDV intentan demandar esos periféricos al mismo tiempo. Aquí se explica cómo se gestionan los conflictos de los dispositivos admitidos:

-   **La caja registradora** la caja registradora se abre mediante un evento que se envía al dispositivo. Pueden darse problemas si se llama a una caja registradora cuando el cajón ya esté abierto. Una caja registradora usada en una configuración de hardware de estación compartida debe establecerse en **Compartida** en el perfil de hardware. Este valor impide que los PDV comprueben si la caja registradora ya está abierta cuando envían comandos para abrirla.
-   **Impresora de recibos**: si se envían dos comandos de impresión de recibos a la estación de hardware al mismo tiempo, uno de los siguientes comandos se puede perder, en función del dispositivo. Algunos dispositivos tienen memoria interna o agrupaciones que pueden evitar este problema. Si un comando de impresión no se realiza correctamente, el cajero recibe un mensaje de error y puede reintentar el comando de impresión desde el PDV.
-   **Termina de pago**: si un cajero intenta realizar una transacción en un terminal de pago que ya se está usando, un mensaje notifica al cajero que se está utilizando el terminal y se solicita al cajero que lo intente de nuevo más adelante. Normalmente, los cajeros pueden ver que un terminal ya se está usando y esperarán hasta que se complete la otra transacción antes de intentarlo de nuevo.

La validación está prevista para que una versión futura detecte si los dispositivos no admitidos se configuran para un perfil de hardware que está asignado a una estación de hardware compartida. Si se detectan dispositivos no admitidos, el usuario recibirá un mensaje que indica que los dispositivos no son compatibles para estaciones de hardware compartidas. En el caso de las estaciones compartidas de hardware, la opción **Seleccionar en pago** está establecida en **Sí** a nivel del registro. A continuación se pide que el usuario del PDV seleccione una emisora de hardware cuando se selecciona una forma e pago para una transacción en el PDV. Cuando la estación de hardware solo se selecciona en el momento de la forma de pago, la selección de estación de hardware se agrega directamente al flujo de trabajo de PDV para los escenarios móviles. Como prestación adicional, no se utilizará la pantalla de línea en la terminal de pago para los escenarios compartidos. Si la terminal de pago se usa como pantalla de línea, se podría bloquear a otros usuarios a la hora de usar la terminal hasta que la transacción se complete. En escenarios para aplicaciones móviles, se pueden agregar líneas a transacciones durante un período más largo. Por lo tanto, se requiera la opción **Seleccionar en pago** para garantizar la disponibilidad óptima del dispositivo.

### <a name="network-peripherals"></a>Periféricos de red

La designación de la red para los dispositivos en el perfil de hardware habilita las cajas registradoras, las impresoras de recibos y los terminales de pago para que se conecten mediante una conexión de red.

#### <a name="modern-pos-for-windows"></a>Modern POS para Windows

Puede especificar direcciones IP para periféricos de red en dos ubicaciones. Si el cliente de Modern POS para Windows utiliza un único conjunto de periféricos de red, debe establecer el conjunto de direcciones IP para dichos dispositivos mediante la opción **Configuración de IP** en el Panel de acciones para el propio registro. En el caso de los dispositivos de red que se van a compartir entre registros de PDV, se puede asignar directamente un perfil de hardware que tenga dispositivos de red asignados, a una estación de hardware compartida. Para asignar direcciones IP, seleccione la estación de hardware en la página **Tiendas** y, a continuación utilice la opción **Configuración de IP** en **Estaciones de hardware** para especificar los dispositivos de red asignados a esa estación de hardware. Para las estaciones de hardware que solo tienen dispositivos de red, no es necesario implementar la propia estación de hardware. En este caso, la estación de hardware se requiere solo para agrupar los dispositivos que se pueden gestionar en red de forma conceptual según su ubicación en la tienda.

#### <a name="cloud-pos-and-modern-pos-for-ios"></a>Cloud POS y Modern POS para iOS

La lógica que controla los periféricos físicamente conectados y que se pueden gestionar en red se encuentran en la estación de hardware. Por lo tanto, para todos los clientes de PDV excepto para Modern POS para Windows y Android, una estación de hardware de IIS debe implementarse y estar activa para permitir al PDV comunicarse con los periféricos, independientemente de si los periféricos están físicamente conectados con una estación de hardware o se gestionan a través de la red.

## <a name="setup-and-configuration"></a>Establecimiento y configuración
### <a name="hardware-station-installation"></a>Instalación de la estación de hardware

Para obtener más información sobre cómo instalar una estación de hardware IIS, consulte [Configurar e instalar la estación de hardware](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Establecimiento y configuración de Modern POS para Windows

Para obtener información, consulte [Configurar, instalar y activar Modern POS (MPOS)](retail-modern-pos-device-activation.md).

### <a name="modern-pos-for-android-and-ios-setup-and-configuration"></a>Establecimiento y configuración de Modern POS para Android e iOS

Para obtener más información, consulte [Configurar una aplicación de POS Hybrid en Android e iOS](./dev-itpro/hybridapp.md).

### <a name="opos-device-setup-and-configuration"></a>Establecimiento y configuración del dispositivo de OPDV

Para obtener más información sobre los componentes de OPDV, consulte la sección "Interfaces admitidas" de este documento. Normalmente, los controladores de OPDV los suministra el fabricante del dispositivo. Cuando un controlador de dispositivo de OPDV está instalado, agrega una clave al Registro de Windows en una de las siguientes ubicaciones:

-   **Sistema de 32 bits:** HKEY\_LOCAL\_MACHINE\SOFTWARE\OLEforRetail\ServiceOPOS
-   **Sistema de 64 bits:** HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\OLEforRetail\ServiceOPOS

Dentro de la ubicación del registro de ServiceOPOS, los dispositivos configurados se organizan según la clase de dispositivo de OPDV. Se guardan controladores de múltiples dispositivos.

## <a name="supported-scenarios-by-hardware-station-type"></a>Escenarios compatibles según el tipo de estación de hardware
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Soporte del cliente: estación de hardware de IPC frente a estación de hardware de IIS

En la tabla siguiente se muestran las topologías y los escenarios de implementación que se admiten.

| Cliente      | Estación de hardware de IPC | Estación de hardware de IIS |
|-------------|----------------------|----------------------|
| Aplicación de Windows | Sí                  | Sí                  |
| PDV en la nube   | No                   | Sí                  |
| Android     | Sí                  | Sí                  |
| iOS         | No                   | Sí                  |

### <a name="network-peripherals"></a>Periféricos de red

Los periféricos de red se admiten directamente a través de la estación de hardware que se integra en las aplicaciones Modern POS para Windows y Android. Para todos los demás clientes, debe implementar una estación de hardware de IIS.

| Cliente      | Estación de hardware de IPC | Estación de hardware de IIS |
|-------------|----------------------|----------------------|
| Aplicación de Windows | Sí                  | Sí                  |
| PDV en la nube   | No                   | Sí                  |
| Android     | Sí                  | Sí                  |
| iOS         | No                   | Sí                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Tipos de dispositivo compatibles según el tipo de estación de hardware
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS para Windows con una estación de hardware de IPC (integrado)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase de dispositivo admitido</th>
<th>Interfaces admitidas</th>
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
<li>UWP (No se requiere configuración).</li>
<li>Cuña de teclado (no se requiere ninguna configuración).</li>
</ul></td>
</tr>
<tr class="even">
<td>Cajón</td>
<td><ul>
<li>OPDV</li>
<li>Red </br><strong>Nota:</strong> solo se puede configurar una caja registradora si <strong>Uso de turno compartido</strong> se configura en la caja registradora.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Cajón 2</td>
<td><ul>
<li>OPDV</li>
<li>Red </br><strong>Nota:</strong> solo se puede configurar una caja registradora si <strong>Uso de turno compartido</strong> se configura en la caja registradora.</li>
</ul></td>
</tr>
<tr class="even">
<td>Escáner</td>
<td><ul>
<li>OPDV</li>
<li>UWP (No se requiere configuración).</li>
<li>Cuña de teclado (no se requiere ninguna configuración).</li>
</ul></td>
</tr>
<tr class="odd">
<td>Escáner 2</td>
<td><ul>
<li>OPDV</li>
<li>UWP (No se requiere configuración).</li>
<li>Cuña de teclado (no se requiere ninguna configuración).</li>
</ul></td>
</tr>
<tr class="even">
<td>Escala</td>
<td>OPDV</td>
</tr>
<tr class="odd">
<td>Terminal para introducción de PIN</td>
<td>OPDV (el soporte se proporciona con personalización del conector de pago.)</td>
</tr>
<tr class="even">
<td>Captura de firma</td>
<td>OPDV</td>
</tr>
<tr class="odd">
<td>Terminal de pago </td>
<td><ul>
<li>Compatibilidad con el dispositivo personalizado</li>
<li>Red (para obtener más información, consulte la documentación sobre el conector de pago).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Todos los clientes de Modern POS que tienen una estación de hardware de IIS "compartida" comprometida

> [!NOTE]
> Cuando la emisora de hardware de IIS es "comprometida", hay una relación unívoca entre el cliente de PDV y la estación de hardware.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase de dispositivo admitido</th>
<th>Interfaces admitidas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impresora</td>
<td><ul>
<li>OPDV</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="even">
<td>Impresora 2</td>
<td><ul>
<li>OPDV</li>
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
<td>Cajón</td>
<td><ul>
<li>OPDV</li>
<li>Red </br><strong>Nota:</strong> solo se puede configurar una caja registradora por perfil de hardware si <strong>Uso de turno compartido</strong> se configura en la caja registradora.</li>
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
<td>Terminal para introducción de PIN</td>
<td>OPDV (el soporte se proporciona con personalización del conector de pago.)</td>
</tr>
<tr class="odd">
<td>Sig. capturar</td>
<td>OPDV</td>
</tr>
<tr class="even">
<td>Terminal de pago </td>
<td><ul>
<li>Compatibilidad con el dispositivo personalizado</li>
<li>Red (para obtener más información, consulte la documentación sobre el conector de pago).</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-share-an-iis-hardware-station"></a>Todos los clientes de Modern POS que comparten una estación de hardware de IIS

> [!NOTE]
> Cuando la estación de hardware de IIS es "compartida”, varios dispositivos pueden usar la estación de hardware al mismo tiempo. Para este escenario, debe usar solamente los dispositivos que se muestran en la tabla siguiente. Si intenta compartir los dispositivos que no se enumeran aquí, como los escáneres de código de barras y los MSR, aparecerán errores cuando varios dispositivos intenten demandar el mismo periférico. En el futuro, tal configuración se impedirá explícitamente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase de dispositivo admitido</th>
<th>Interfaces admitidas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impresora</td>
<td><ul>
<li>OPDV</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="even">
<td>Impresora 2</td>
<td><ul>
<li>OPDV</li>
<li>Red</li>
</ul></td>
</tr>
<tr class="odd">
<td>Cajón</td>
<td><ul>
<li>OPDV</li>
<li>Red </br><strong>Nota:</strong> solo se puede configurar una caja registradora por perfil de hardware si <strong>Uso de turno compartido</strong> se configura en la caja registradora.</li>
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
<li>Compatibilidad con el dispositivo personalizado</li>
<li>Red (para obtener más información, consulte la documentación sobre el conector de pago).</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configuración para los escenarios admitidos
Para obtener más información sobre cómo crear perfiles de hardware, consulte [Conectar periféricos en el punto de venta (POS)](define-maintain-channel-clients-registers-hw-stations.md). 

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS para Windows con una estación de hardware de IPC (integrado)

Esta configuración es la más típica para los registros tradicionales y fijos de PDV. Para este escenario, la información del perfil de hardware se asigna directamente al mismo registro. El número de terminal de EFT se debe establecer en el registro propiamente dicho. Para establecer esta configuración, siga estos pasos.

1.  Cree un perfil de hardware donde se configuren todos los periféricos necesarios.
2.  Asigne el perfil de hardware a un registro de PDV.
3.  Cree una estación de hardware de tipo **Dedicado** para la tienda donde se usará el registro PDV. La descripción es opcional. 

    > [!NOTE]
    > No es necesario establecer ninguna otra propiedad en la estación de hardware. El resto de la información requerida, como el perfil de hardware, vendrá del mismo registro.

4.  Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
5.  Seleccione la programación de la distribución **1090** para sincronizar el nuevo perfil de hardware en la tienda. Seleccione **Ejecutar ahora** para sincronizar los cambios en el PDV.
6.  Seleccione la programación de la distribución **1040** para sincronizar la nueva estación de hardware en la tienda. Seleccione **Ejecutar ahora** para sincronizar los cambios en el PDV.
7.  Instalar y activar Modern POS para Windows.
8.  Iniciar Modern POS para Windows y comience a utilizar los dispositivos periféricos conectados.

### <a name="modern-pos-for-android-with-an-ipc-built-in-hardware-station"></a>Modern POS para Android con una estación de hardware de IPC (integrado)

**Novedad para 10.0.8**: las impresoras de red Epson y las cajas registradoras conectadas a esas impresoras a través del puerto DK ahora son compatibles con la aplicación Modern POS para Android. Para obtener más información, visite el artículo [Configurar una aplicación de POS Hybrid en Android e iOS](./dev-itpro/hybridapp.md).

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Todos los clientes de Modern POS que tienen una estación de hardware de IIS compartida comprometida

Esta configuración se puede utilizar para todos los clientes de Modern POS que tengan una emisora de hardware que se usará exclusivamente por un registro de PDV. Para establecer esta configuración, siga estos pasos.

1.  Cree un perfil de hardware donde se configuren todos los periféricos necesarios.
2.  Cree una estación de hardware de tipo **Dedicado** para la tienda donde se usará el registro PDV.
3.  En la estación dedicada de hardware, establezca las siguientes propiedades:
    -   **Nombre del host:** el nombre del equipo host donde la estación de hardware se ejecutará. 
    
        > [!NOTE]
        > Cloud POS puede resolver **localhost** para determinar el equipo local donde se ejecuta Cloud POS. Sin embargo, el certificado necesario para emparejar Cloud POS con la estación de hardware también debe tener “Localhost” como nombre del equipo. Para evitar problemas, se recomienda que anote una instancia de cada estación dedicada de hardware para la tienda, según convenga. Para cada estación de hardware, el nombre de host debe ser el nombre de equipo específico donde la estación de hardware será implementada.
    
    -   **Puerto**: el puerto que se va a utilizar para que la estación de hardware se comunique con el cliente de Modern POS.
    -   **Perfil de hardware**: si el perfil de hardware no se proporciona en la propia emisora de hardware, el perfil de hardware asignado al registro se usará.
    -   **Número de PDV de EFT:** El identificador de la terminal de EFT para usar cuando se envían autorizaciones de EFT. Este identificador lo proporciona el procesador de tarjetas de crédito.
    -   **Nombre del paquete**: el paquete de la estación de hardware para utilizar cuando se implementa la estación de hardware.

4.  Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
5.  Seleccione la programación de la distribución **1090** para sincronizar el nuevo perfil de hardware en la tienda. Seleccione **Ejecutar ahora** para sincronizar los cambios en el PDV.
6.  Seleccione la programación de la distribución **1040** para sincronizar la nueva estación de hardware en la tienda. Seleccione **Ejecutar ahora** para sincronizar los cambios en el PDV.
7.  Instale la estación de hardware. Para obtener más información sobre cómo instalar la estación de hardware, consulte [Configurar e instalar la estación de hardware de Retail](retail-hardware-station-configuration-installation.md).
8.  Instalar y activar Modern POS. Para obtener más información sobre cómo instalar Modern POS, consulte [Configurar, instalar y activar Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md).
9.  Inicie sesión en Modern POS y seleccione **Realizar operaciones no relacionadas con la caja registradora**.
10. Inicie la operación **Administrar estaciones de hardware**.
11. Seleccione **Administrar**.
12. En la página de gestión de la estación de hardware, defina la opción para activar la estación de hardware.
13. Seleccione la estación de hardware para utilizar y luego **Emparejar**.
14. Después de emparejar la emisora de hardware, seleccione **Cerrar**.
15. En la página de selección de estación de hardware, seleccione la estación de hardware recientemente seleccionada para activarla.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Todos los clientes de Modern POS que tienen una estación de hardware de IIS compartida

Esta configuración se puede utilizar para todos los clientes de Modern POS que comparten las estaciones de hardware con otros dispositivos. Para establecer esta configuración, siga estos pasos.

1.  Cree un perfil de hardware donde se configuren los periféricos necesarios.
2.  Cree una estación de hardware de tipo **Compartido** para la tienda donde se usará el registro PDV.
3.  En la estación compartida de hardware, establezca las siguientes propiedades:
    -   **Nombre del host:** el nombre del equipo host donde la estación de hardware se ejecutará.
    -   **Descripción**: el texto que va a ayudar a identificar la estación de hardware, por ejemplo o **Devoluciones** o **Parte delantera de tienda**.
    -   **Puerto**: el puerto que se va a utilizar para que la estación de hardware se comunique con el cliente de Modern POS.
    -   **Perfil de hardware**: para las estaciones compartidas de hardware, cada estación de hardware debe tener un perfil de hardware. Los perfiles de hardware se pueden compartir entre varias estaciones de hardware, pero se deben asignar a cada estación de hardware. Además, se recomienda que use turnos compartidos cuando varios dispositivos usen la misma estación de hardware compartida. Para establecer un turno compartido, vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware**. Para cada perfil de hardware compartido, seleccione la caja registradora y establezca la opción **Caja registradora de turno compartido** en **Sí**.
    -   **Número de PDV de EFT:** El identificador de la terminal de EFT para usar cuando se envían autorizaciones de EFT. Este identificador lo proporciona el procesador de tarjetas de crédito.
    -   **Nombre del paquete**: el paquete de la estación de hardware para utilizar cuando se implementa la estación de hardware.

4.  Repita los pasos 2 y 3 para cada estación de hardware adicional que sea necesaria en la tienda.
5.  Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
6.  Seleccione la programación de la distribución **1090** para sincronizar el nuevo perfil de hardware en la tienda. Seleccione **Ejecutar ahora** para sincronizar los cambios en el PDV.
7.  Seleccione la programación de la distribución **1040** para sincronizar la nueva estación de hardware en la tienda. Seleccione **Ejecutar ahora** para sincronizar los cambios en el PDV.
8.  Instale la estación de hardware en cada equipo del host que haya configurado en los pasos 2 y 3. Para obtener más información sobre cómo instalar la estación de hardware, consulte [Configurar e instalar la estación de hardware de Retail](retail-hardware-station-configuration-installation.md).
9.  Instalar y activar Modern POS. Para obtener más información sobre cómo instalar Modern POS, consulte [Configurar, instalar y activar Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md).
10. Inicie sesión en Modern POS y seleccione **Realizar operaciones no relacionadas con la caja registradora**.
11. Inicie la operación **Administrar estaciones de hardware**.

12. Seleccione **Administrar**.
13. En la página de gestión de la estación de hardware, defina la opción para activar la estación de hardware.
14. Seleccione la estación de hardware para utilizar y luego **Emparejar**.
15. Repita el paso 14 para cada estación de hardware que utilizará Modern POS.
16. Después emparejar todas las estaciones de hardware necesarias, seleccione **Cerrar**.
17. En la página de selección de estación de hardware, seleccione la estación de hardware recientemente seleccionada para activarla. 

> [!NOTE]
> Si los dispositivos utilizan a menudo distintas estaciones de hardware, recomendamos que configure Modern POS para solicitar a los cajeros que seleccionen una estación de hardware al iniciar el proceso de forma de pago. Vaya a **Venta minorista y comercio \> Configuración de canal \> Configuración de PDV \> Registros**. Seleccione el registro y, después, establezca la opción **Seleccionar en pago** en **Sí**. Use la programación de distribución **1090** para sincronizar los cambios con la base de datos de canal.

## <a name="extensibility"></a>Extensibilidad
Para obtener información sobre escenarios de extensibilidad para la estación de hardware, consulte [Integrar el POS con un nuevo dispositivo de hardware y generar el instalador de extensiones](dev-itpro/hardware-device-extension.md).

## <a name="security"></a>Seguridad
Según las normas actuales de seguridad, los valores siguientes se deben usar en un entorno de producción: 

### <a name="hardware-station-installer"></a>Instalador de la estación de hardware
El instalador de la estación de hardware automáticamente hará estas ediciones de registro como parte de la instalación a través de autoservicio.

-   La capa de sockets seguros (SSL) debería deshabilitarse.
-   Únicamente la versión 1.2 de la seguridad de la capa de transporte (TLS) (o la versión más reciente) debe estar habilitada y en uso. 

### <a name="ssl-and-tls"></a>SSL y TLS
De forma predeterminada, SSL y todas las versiones de TLS, excepto TLS 1.2, están deshabilitadas. Para editar o habilitar estos valores, siga estos pasos:
    1.  Presione la tecla del logotipo de Windows +R para abrir una ventana **Ejecutar**.
    2.  En el campo **Abrir**, escriba **Regedit** y a continuación, seleccione **Aceptar**.
    3.  Si aparece un cuadro de mensaje de **Control de cuentas de usuario**, seleccione **Sí**.
    4.  En la ventana del **Editor de Registro**, vaya a **HKEY\_LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Se han especificado las teclas siguientes automáticamente para permitir solo TLS 1.2:
        -   TLS 1.2Server:Enabled=1
        -   TLS 1.2Server:DisabledByDefault=0
        -   TLS 1.2Client:Enabled=1
        -   TLS 1.2Client:DisabledByDefault=0
        -   TLS 1.1Server:Enabled=0
        -   TLS 1.1Client:Enabled=0
        -   TLS 1.0Server:Enabled=0
        -   TLS 1.0Client:Enabled=0
        -   SSL 3.0Server:Enabled=0
        -   SSL 3.0Client:Enabled=0
        -   SSL 2.0Server:Enabled=0
        -   SSL 2.0Client:Enabled=0
-   No deben abrirse otros puertos de red adicionales, a menos que se necesiten por motivos conocidos y especificados.
-   El uso compartido de recursos entre orígenes se debe deshabilitar y especificar los orígenes permitidos que se aceptan.
-   Solo se deben usar entidades emisoras de certificados de confianza para recopilar los certificados que se usarán en los equipos que ejecutan la estación de hardware.

> [!NOTE]
> Es muy importante que consulte las instrucciones de seguridad de IIS y los requisitos del sector para tarjetas (PCI).

## <a name="peripheral-simulator"></a>Simulador periférico
Para obtener más información, consulte [Simulador de periféricos para Commerce](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsoft-tested-peripheral-devices"></a>Dispositivos periféricos probados por Microsoft
### <a name="ipc-built-in-hardware-station"></a>Estación de hardware de IPC (integrada)

Los siguientes periféricos se probaron mediante la estación de hardware de IPC que se integra en Modern POS para Windows.

#### <a name="printer"></a>Impresora

| Fabricante | Modelo    | Interfaz | Comentarios                |
| ------------ | -------- | --------- | ----------------------- |
| Epson        | TM-T88V  | OPDV      |                         |
| Epson        | TM-T88IV | OPDV      |                         |
| HP           | H300     | OPDV      | Con tecnología USB             |
| Star         | TSP650II | Personalizar    | Conectado a través de la red   |
| Star         | mPOP     | OPDV      | Conectado mediante Bluetooth |
| Toshiba      | HSP100   | OPDV      |                         |
| Toshiba      | HSP150   | OPDV      |                         |

> [!NOTE]
> La impresora Star TSP 100 no es compatible con la estación de hardware incorporada. La estación de hardware incorporada utiliza un proceso de 64 bits, que no es compatible con los controladores de Star TP 100 existentes. 

#### <a name="bar-code-scanner"></a>Escáner de códigos de barras

| Fabricante  | Modelo         | Interfaz | Comentarios |
| ------------- | ------------- | --------- | -------- |
| Datalogic     | Magellan 8400 | OPDV      |          |
| Honeywell     | 1900          | UWP       |          |
| HP integrado | E1L07AA       | OPDV      |          |
| Símbolo        | LS2208        | OPDV      |          |

#### <a name="payment-terminals-and-pin-pads"></a>Terminales de pago y teclados de PIN

Dynamics 365 Commerce proporciona una solución lista para usar para la integración con Adyen para servicios de pago. EL [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md) utiliza la [Interfaz de programación de aplicaciones (API) de Adyen Payment Terminal](https://www.adyen.com/blog/introducing-the-terminal-api) que no depende de dispositivos y puede interactuar con todos los terminales de pago que admiten esta API. Para obtener una lista completa de los terminales de pago admitidos, consulte [Terminales PDV Adyen](https://www.adyen.com/pos-payments/terminals).

También puede utilizar otros proveedores de pago con Dynamics 365 Commerce creando un conector personalizado. Cualquier terminal de pago que sea compatible con el proveedor de pago se puede utilizar con Dynamics 365 Commerce. De forma similar, Dynamics 365 Commerce permite cualquier modelo de integración de dispositivo de pago que sea compatible con el proveedor de pago, como IP local, API en la nube o conexión directa (por ejemplo, a través de USB) al POS. Para más información, consulte [Crear integración de pago de un extremo a otro para un terminal de pago](dev-itpro/end-to-end-payment-extension.md).

#### <a name="cash-drawer"></a>Caja registradora

| Fabricante | Modelo     | Interfaz | Comentarios                |
|--------------|-----------|-----------|-------------------------|
| Star         | mPOP      | OPDV      | Conectado mediante Bluetooth |
| APG          | Atwood    | Personalizado    | Conectado a través de la red   |
| Star         | SMD2-1317 | OPDV      |                         |
| HP           | QT457AA   | OPDV      |                         |
| Epson        |           | Personalizado    | Conectado a la impresora Epson de red a través del puerto DK |

#### <a name="line-display"></a>Visualización de líneas

| Fabricante | Modelo    | Interfaz | Comentarios |
| ------------ | -------- | --------- | -------- |
| Epson        | DM-D110  | OPDV      |          |
| HP           | T-series | OPDV      |          |

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

### <a name="dedicated-iis-hardware-station"></a>Estación de hardware IIS conectada

Los siguientes se periféricos se probaron mediante una estación de hardware IIS dedicada (no compartida) junto con Modern POS para Windows y Cloud POS.

#### <a name="printer"></a>Impresora

| Fabricante | Modelo    | Interfaz | Comentarios                |
| ------------ | -------- | --------- | ----------------------- |
| Epson        | TM-T88V  | OPDV      |                         |
| Epson        | TM-T88IV | OPDV      |                         |
| HP           | H300     | OPDV      | Con tecnología USB             |
| Star         | TSP650II | Personalizar    | Conectado a través de la red   |
| Star         | mPOP     | OPDV      | Conectado mediante Bluetooth |
| Toshiba      | HSP100   | OPDV      |                         |
| Toshiba      | HSP150   | OPDV      |                         |

#### <a name="bar-code-scanner"></a>Escáner de códigos de barras

| Fabricante  | Modelo         | Interfaz | Comentarios |
| ------------- | ------------- | --------- | -------- |
| Datalogic     | Magellan 8400 | OPDV      |          |
| HP integrado | E1L07AA       | OPDV      |          |
| Símbolo        | LS2208        | OPDV      |          |

#### <a name="payment-terminals-and-pin-pads"></a>Terminales de pago y teclados de PIN

Dynamics 365 Commerce proporciona una solución lista para usar para la integración con Adyen para servicios de pago. EL [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md) utiliza la [API Adyen Payment Terminal](https://www.adyen.com/blog/introducing-the-terminal-api) que no depende de dispositivos y puede interactuar con todos los terminales de pago que admiten esta API. Para obtener una lista completa de los terminales de pago admitidos, consulte [Terminales PDV Adyen](https://www.adyen.com/pos-payments/terminals).

También puede utilizar otros proveedores de pago con Dynamics 365 Commerce creando un conector personalizado. Cualquier terminal de pago que sea compatible con el proveedor de pago se puede utilizar con Dynamics 365 Commerce. De forma similar, Dynamics 365 Commerce permite cualquier modelo de integración de dispositivo de pago que sea compatible con el proveedor de pago, como IP local, API en la nube o conexión directa (por ejemplo, a través de USB) al POS. Para más información, consulte [Crear integración de pago de un extremo a otro para un terminal de pago](dev-itpro/end-to-end-payment-extension.md).

#### <a name="cash-drawer"></a>Caja registradora

| Fabricante | Modelo     | Interfaz | Comentarios              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizado    | Conectado a través de la red |
| Star         | SMD2-1317 | OPDV      |                       |
| HP           | QT457AA   | OPDV      |                       |
| Epson        |           | Personalizado    | Conectado a la impresora Epson de red a través del puerto DK |

#### <a name="line-display"></a>Visualización de líneas

| Fabricante  | Modelo   | Interfaz | Comentarios |
|---------------|---------|-----------|----------|
| HP integrado | G6U79AA | OPDV      |          |
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

### <a name="shared-iis-hardware-station"></a>Estación de hardware IIS compartida

Los siguientes se periféricos se probaron mediante una estación de hardware IIS compartida junto con Modern POS para Windows y Cloud POS. 

> [!NOTE]
> Únicamente se admite una impresora, un terminal de pago y una caja registradora.

#### <a name="printer"></a>Impresora

| Fabricante | Modelo    | Interfaz | Comentarios                |
| ------------ | -------- | --------- | ----------------------- |
| Epson        | TM-T88V  | OPDV      |                         |
| Epson        | TM-T88IV | OPDV      |                         |
| HP           | H300     | OPDV      | Con tecnología USB             |
| Star         | mPOP     | OPDV      | Conectado mediante Bluetooth |
| Toshiba      | HSP100   | OPDV      |                         |
| Toshiba      | HSP150   | OPDV      |                         |

#### <a name="payment-terminal"></a>Terminal de pago 

Dynamics 365 Commerce proporciona una solución lista para usar para la integración con Adyen para servicios de pago. EL [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md) utiliza la [API Adyen Payment Terminal](https://www.adyen.com/blog/introducing-the-terminal-api) que no depende de dispositivos y puede interactuar con todos los terminales de pago que admiten esta API. Para obtener una lista completa de los terminales de pago admitidos, consulte [Terminales PDV Adyen](https://www.adyen.com/pos-payments/terminals).

También puede utilizar otros proveedores de pago con Dynamics 365 Commerce creando un conector personalizado. Cualquier terminal de pago que sea compatible con el proveedor de pago se puede utilizar con Dynamics 365 Commerce. De forma similar, Dynamics 365 Commerce permite cualquier modelo de integración de dispositivo de pago que sea compatible con el proveedor de pago, como IP local, API en la nube o conexión directa (por ejemplo, a través de USB) al POS. Para más información, consulte [Crear integración de pago de un extremo a otro para un terminal de pago](dev-itpro/end-to-end-payment-extension.md).

#### <a name="cash-drawer"></a>Caja registradora

| Fabricante | Modelo     | Interfaz | Comentarios              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personalizado    | Conectado a través de la red |
| Star         | SMD2-1317 | OPDV      |                       |
| HP           | QT457AA   | OPDV      |                       |
| Epson        |           | Personalizado    | Conectado a la impresora Epson de red a través del puerto DK |


## <a name="troubleshooting"></a>Solución de problemas
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Modern POS puede detectar la estación de hardware en su lista para su selección, pero no puede completar el emparejamiento

**Solución:** compruebe la siguiente lista de posibles fallos:

-   El equipo que está ejecutando Modern POS confía en el certificado que se usa en el equipo que ejecute la estación de hardware.
    -   Para comprobar esta configuración, en un explorador web, vaya a la dirección URL siguiente: https://&lt;Nombre del equipo&gt;:&lt;Número de puerto&gt;/HardwareStation/ping.
    -   Esta dirección URL utiliza un ping para comprobar que se puede acceder al equipo y el explorador indica si el certificado es de confianza. (Por ejemplo, en Internet Explorer, un símbolo de bloqueo aparece en la barra de direcciones. Al seleccionar este símbolo, Internet Explorer comprueba si se confía en el certificado actualmente. Es posible instalar el certificado en el equipo local viendo los detalles del certificado que se aparece.)
-   En el equipo que ejecute la estación de hardware, el puerto que usará en la estación de hardware se abre en el firewall.
-   La estación de hardware ha instalado correctamente la información de la cuenta de comerciante a través de la herramienta para instalar la información de comerciante que se ejecuta cuanto termina el instalador de la estación de hardware.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Modern POS no puede detectar la estación de hardware en su lista de selección

**Solución:** cualquiera de los factores siguientes puede producir este problema:

-   La estación de hardware no se ha configurado correctamente en la sede central. Para más información, consulte [Configurar e instalar la estación de hardware para Retail](retail-hardware-station-configuration-installation.md#troubleshooting). 
-   Los trabajos no se han ejecutado para actualizar la configuración del canal. En este caso, ejecute el trabajo 1070 para la configuración del canal.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Modern POS no refleja nuevos parámetros de la caja registradora

**Solución**: cierre el lote actual. Los cambios en la caja registradora no se actualizan para Modern POS hasta que el lote actual esté cerrado.

### <a name="modern-pos-is-reporting-an-issue-with-a-peripheral"></a>Modern POS está notificando un problema con un periférico

**Solución:** aquí se exponen algunas causas típica para este problema:

-   Asegúrese de que están cerradas otras utilidades de configuración del controlador del dispositivo. Si estas utilidades están abiertas, puede que eviten que Modern POS o la estación de hardware demanden el dispositivo.
-   Si el periférico se comparte con varios dispositivos de PDV, asegúrese de que pertenezca a una de las categorías siguientes:
    -   Caja registradora
    -   Impresora de recibos
    -   Terminal de pago 

    Si el periférico no pertenece a una de estas categorías, la estación de hardware no está diseñada para habilitar que el periférico se comparta entre varios dispositivos de PDV.
-   A veces, los controladores de dispositivos pueden hacer que Common Control Objects (CCO) dejen de funcionar correctamente. Si un dispositivo se ha instalado recientemente, pero no funciona correctamente u observa otros problemas, muchas veces se puede resolver el problema reinstalando los CCO. Para descargar los CCO, visite <http://monroecs.com/oposccos_current.htm>.
-   Si realiza cambios de periféricos frecuentes durante las pruebas o la solución de problemas, puede que tenga que restablecer IIS en lugar de esperar a que la memoria caché se actualice. Para resetear IIS, siga estos pasos:
    1.  En el menú **Inicio**, escriba **CMD**.
    2.  En los resultados de la búsqueda, haga clic con el botón secundario en el **Símbolo del sistema** y seleccione **Ejecutar como administrador**.
    3.  En la ventana del **Símbolo del sistema**, escriba **iisreset /Restart** y presione Entrar.
    4.  Una vez que haya reiniciado IIS, reinicie Modern POS.
-   Cuando realiza cambios frecuentes en los dispositivos periféricos, si además también inicia y sale con frecuencia del cliente de PDV, el proceso de dllhost de una sesión anterior de PDV puede interferir con la sesión actual. En este caso, puede que no se pueda usar un dispositivo hasta que se cierre que el host de la biblioteca de vínculos dinámicos (DLL) que administra la sesión anterior. Para cerrar el host de DLL, siga estos pasos:
    1.  En el menú **Inicio**, escriba **Administrador de tareas**.
    2.  En los resultados de la búsqueda, seleccione **Administrador de tareas**.
    3.  En Administrador de tareas, en la ficha **Detalles**, seleccione el encabezado de columna que indica **Nombre** para ordenar la tabla alfabéticamente por nombre.
    4.  Baje hasta encontrar dllhost.exe.
    5.  Seleccione cada host DLL y luego **Finalizar tarea**.
    6.  Una vez que se haya cerrado los host de DLL, reinicie Modern POS.


## <a name="additional-resources"></a>Recursos adicionales

[Simulador periférico de Commerce](dev-itpro/retail-peripheral-simulator.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
