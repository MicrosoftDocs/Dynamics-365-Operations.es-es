---
title: Comprobación de estado de periféricos y servicios de PDV
description: Este tema proporciona una visión general de la operación de comprobación de estado en el punto de venta (PDV).
author: BrianShook
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: cd4e97b8dbfc4faf336d4ea927342fd4fa3cc7cd
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779881"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Comprobación de estado de periféricos y servicios de PDV

[!include [banner](includes/banner.md)]

En este tema se describe la operación de comprobación de estado en el punto de venta (PDV).

## <a name="overview"></a>Información general

Las tiendas minoristas pueden ser entornos complejos en los que se usan muchas aplicaciones y dispositivos. A medida que crecen las operaciones, puede resultar difícil garantizar que funcionen de forma fluida a causa de sus dependencias de, por ejemplo, periféricos que pueden averiarse o desconectarse accidentalmente a lo largo del día. La solución de problemas relacionados con los dispositivos y servicios puede ser costosa para comercios grandes e igualmente frustrantes para las operaciones más pequeñas.

Microsoft Dynamics 365 Commerce, versión 10.0.10 y posteriores, incluye una operación de comprobación de estado que puede ayudar a evitar parte de este coste y frustración. Esta operación proporciona un método para comprobar dispositivos directamente desde el PDV fuera de las operaciones normales. Así, puede ayudar a los minoristas a detectar problemas antes de que ocurran.

## <a name="key-terms"></a>Términos clave

| Condición | Descripción |
|---|---|
| Periféricos | Cualquier dispositivo que la aplicación de PDV utilice para facilitar las transacciones y otras operaciones en la tienda. Algunos ejemplos son cajas registradoras, lectores de códigos de barras y terminales de pago. |
| Servicio | En este tema, un servicio es una aplicación auxiliar de la que depende la aplicación PDV para realizar transacciones y operaciones diarias. Los ejemplos incluyen aplicaciones que ayudan a calcular impuestos o envíos. |

## <a name="health-check-operation"></a>Operación de comprobación de estado

La operación de comprobación de estado es la operación 717 en la página **Operaciones de PDV** de la sede de Commerce. Se puede usar mientras el PDV esté en modo de operaciones no relacionadas con la caja registradora. Sin embargo, debe haber una estación de hardware activa.

De forma predeterminada, la comprobación de estado solo prueba los dispositivos que están configurados en el perfil de hardware para la estación de hardware que está actualmente activa para un registro. Si un registro utiliza varias estaciones de hardware en el transcurso del día, para realizar comprobaciones de estado de todas ellas debe conectarse a una estación de hardware a la vez. No hay comprobación de estado a nivel de tienda. Sin embargo, es posible que este tipo de comprobación se pueda realizar a través de la extensibilidad de Commerce Server.

### <a name="out-of-box-health-checks"></a>Comprobaciones de estado listas para usar

| Tipo | Conexión | Detalles |
|---|---|---|
| Impresora | OPDV | Esta comprobación prueba las operaciones básicas de vinculación e incrustación de objetos para funciones de PDV (OPOS). A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Visualización de líneas | OPDV | Esta comprobación prueba las funciones básicas de OPOS. A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Dos visualizaciones | Windows | Esta comprobación garantiza que el sistema operativo detecta una segunda pantalla de Windows. | 
| MSR | OPDV | Esta comprobación prueba las funciones básicas de OPOS. A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Librador | OPDV | Esta comprobación prueba las funciones básicas de OPOS. A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> | 
| Escáner | OPDV | Esta comprobación prueba las funciones básicas de OPOS. A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> | 
| Balanza | OPDV | Esta comprobación prueba las funciones básicas de OPOS. A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Terminal para ingreso de PIN | OPDV | Esta comprobación prueba las funciones básicas de OPOS. A continuación, encontrará algunos ejemplos:<ul><li>Abrir: **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Cerrar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Terminal de pago | SDK de pagos | Esta comprobación prueba las funciones básicas del terminal de pago proporcionadas por el SDK de pagos. <ul><li>Bloquear</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Cerrar</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Usar la operación de comprobación de estado en el PDV

Cuando se inicia la operación de comprobación de estado en el PDV, un panel a la derecha muestra los dispositivos configurados, así como el estado de cada dispositivo. Para realizar una comprobación de estado de un solo dispositivo, seleccione el dispositivo y, a continuación, seleccione **Probar seleccionados**. Para realizar una comprobación de estado de todos los dispositivos, seleccione **Probar todos**. La función **Probar todos** prueba todos los dispositivos, uno cada vez, y actualiza el estado de cada dispositivo en la columna **Estado**.

La columna **Última comprobación** muestra cuándo se realizó la última comprobación de estado para cada dispositivo.

Si un dispositivo supera la comprobación de estado (es decir, si no se encuentran errores), el estado del dispositivo será **Correcto**. Si no se supera la comprobación de estado, el estado indicará que se produjo un error. En este caso, el panel de la derecha proporciona detalles relacionados con el error o le indica al usuario que se ponga en contacto con el administrador del sistema.

Algunos dispositivos, como el bloqueo de teclado de OPOS, no tienen pruebas de comprobación de estado listas para usar. Si no se detecta una prueba de comprobación de estado para algún dispositivo utilizado, el estado será **No admitido**.

### <a name="extending-health-checks"></a>Ampliar las comprobaciones de estado

Las pruebas de comprobación de estado listas para usar están configuradas para proporcionar algunos mensajes descriptivos de los errores típicos. Sin embargo, no cubren todos los escenarios. Mediante la extensibilidad, los comerciantes pueden asignar mensajes descriptivos a errores que pueden ser específicos de su entorno.

También se pueden crear comprobaciones de estado personalizadas para probar dispositivos que no son compatibles inicialmente, o para probar cualquier servicio del que el PDV dependa.

## <a name="related-articles"></a>Artículos relacionados

[Desencadenadores e impresión de Modern POV (MPOS)](dev-itpro/pos-trigger-printing.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]