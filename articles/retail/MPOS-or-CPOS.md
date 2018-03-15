---
title: Elegir entre Modern POS y Cloud POS
description: "Este tema explica las diferencias entre Retail Modern POS y Cloud POS. También se describen los distintos factores que los minoristas que están implementando Microsoft Dynamics 365 for Retail deben considerar para ayudar a tomar las mejores decisiones para sus requisitos."
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 7eb15f9f73f4773d98160e1b0ec5ce74c159cdea
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---

# <a name="choose-between-modern-pos-and-cloud-pos"></a>Elegir entre Modern POS y Cloud POS

[!include[banner](includes/banner.md)]

Este tema proporciona a los implementadores antecedentes, sugerencias, y directrices adicionales para los factores que deben tener en cuenta al implementar Microsoft Dynamics 365 for Retail. Revisando y siguiendo esta orientación como parte del proceso de implementación, los implementadores podrán evitar problemas que podrían afectar a la satisfacción del usuario o al rendimiento.

## <a name="insights"></a>Información
Retail proporciona una gran variedad de opciones de implementación y topología. Por lo tanto, los minoristas pueden elegir los componentes y la configuración que mejor cumplan sus requisitos empresariales y de tecnología. Un aspecto de la implementación que requiere una consideración cuidadosa es la elección de una plataforma y un factor de forma para el componente de punto de venta (PDV).

### <a name="pos-platform-and-form-factor-considerations"></a>Consideraciones de la plataforma y el factor de forma de PDV
Retail admite las siguientes opciones de PDV:

- Retail Modern POS (MPOS) para Microsoft Windows
- MPOS para Microsoft Windows Phone
- MPOS para el Apple iPad o tableta de Google Android
- Cloud POS (CPOS), que admite los exploradores Microsoft Edge, Internet Explorer, y Google Chrome

En todos los casos, el sistema POS (MPOS y CPOS) comparte el mismo código de aplicación básica. Este punto es importante por los siguientes motivos:

- La interfaz de usuario (IU) es coherente, independientemente de la plataforma o factor de forma.
- La mayoría de las capacidades funcionales son iguales, independientemente de la plataforma o factor de forma. Sin embargo, existen algunas diferencias importantes. Estas diferencias se indican en este tema.
- En un almacén determinado, las variaciones de POS se pueden combinar y se pueden ejecutar simultáneamente. Por ejemplo, para sus registros principales, un minorista puede usar MPOS en equipos que ejecutan Windows. Sin embargo, el minorista puede complementar dichos registros con terminales basados en el explorador o dispositivos móviles.
- Las personalizaciones y extensiones se pueden utilizar con facilidad a través de varias plataformas y factores de forma. Dado que el código de aplicación básica se comparte, la mayoría de las personalizaciones se pueden implementar una vez en lugar de varias veces.

### <a name="mpos-vs-cpos"></a>MPOS y CPOS
Aunque los MPOS y los CPOS son prácticamente iguales, existen algunas diferencias importantes que debe comprender.

#### <a name="mpos"></a>MPOS

MPOS en un dispositivo Windows, iOS, o Android es una aplicación que se empaqueta, se instala y se mantiene en dicho dispositivo.

- **Windows** – El MPOS para la aplicación de Windows contiene todo el código de aplicación y el tiempo de ejecución de comercio incrustado (CRT). 
- **iOS/Android** En estas plataformas, la aplicación actúa como host para el código de aplicación de los CPOS. Es decir, el código de aplicación procede del servidor de los CPOS en Microsoft Azure o la unidad de escala de tienda de Retail (RSSU). Para obtener más información, consulte [Visión general de la unidad de escala de Retail Store Connect](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>CPOS

Dado que los CPOS se ejecutan en un explorador, la aplicación no se instala en el dispositivo. En su lugar, el explorador tiene acceso al código de aplicación desde el servidor de los CPOS. Por lo tanto, los CPOS no pueden tener acceso directamente al hardware ni trabajar sin conexión.

### <a name="store-deployment-considerations"></a>Consideraciones sobre la implementación de la tienda
Además de una plataforma y un factor de forma, los minoristas deben elegir también una opción de implementación en la tienda. En la siguiente tabla, se muestran las configuraciones que están disponibles para opción de POS.

| Solicitud de POS         | Retail Server | Disponible sin conexión |
|-------------------------|---------------|-------------------|
| MPOS para Windows        | Nube o RSSU | Sí               |
| MPOS para Android o iOS | Nube o RSSU | N.º                |
| PDV en la nube               | Nube o RSSU | N.º                |

#### <a name="retail-server"></a>Retail Server

Retail server es un componente que aloja el CRT. CRT contiene toda la lógica de negocios que utiliza PDV, y proporciona acceso a la base de datos del canal. Mientras están en línea, todos los clientes de PDV del almacén utilizan Retail server. Retail server se puede implementar en la nube o en la tienda (RSSU).

#### <a name="offline-mode"></a>Modo sin conexión

MPOS para Windows admite el modo sin conexión. En el modo desconectado, POS puede seguir procesando ventas incluso si se ha desconectado de Retail server. Se puede sincronizar con la base de datos del canal al restablecer la conectividad. MPOS utiliza su propia instancia incrustada de CRT y utiliza temporalmente su propio origen de datos locales (base de datos de SQL Server sin conexión). Para obtener más información sobre la funcionalidad sin conexión, consulte [Funcionalidad sin conexión de PDV](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>Consideraciones sobre los periféricos/hardware del PDV
Los minoristas deben también considerar cómo los PDV tendrán acceso a los dispositivos y periféricos como impresoras, cajas registradoras, y terminales de pago. Solo MPOS para Windows admite la comunicación directa con estos dispositivos. MPOS para Windows Phone, iOS, o Android, y Cloud POS requieren una estación de hardware para obtener acceso a estos dispositivos. Las estaciones de hardware se pueden dedicar a un registro de POS o compartir entre los registros de una tienda. Para obtener más información sobre estaciones de hardware, consulte [Instalar y configurar una estación de hardware de Retail](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Consideraciones sobre la implementación
Tenga en cuenta la siguiente información cuando planee su implementación de PDV en sus tiendas al por menor:

- **Requisitos funcionales** – Los procesos y las capacidades de negocio principales son iguales, independientemente de la plataforma, factor de forma, o topología de implementación. Por lo tanto, la mayoría de los minoristas no tienen que tener en cuenta los requisitos funcionales cuando planifican su implementación.
- **Conectividad** - La disponibilidad de la red (red de área extendida \[WAN\] y red de área local \[LAN\]) es un factor principal que requiere una consideración cuidadosa. Todos los beneficios que aporta una solución alojada en la nube de espacio cero en términos de coste y sencillez se pierden si el sistema no está disponible para los procesos de negocio indispensables.

    A menos que la conectividad para un dispositivo dado sea muy de confianza y resistente, o a menos que una determinada cantidad de tiempo de inactividad sea aceptable para el minorista, se recomienda una de las siguientes opciones:

    - Usar MPOS en Windows y habilitar el modo sin conexión.
    - Implementar una RSSU local.

    Estas dos opciones no se excluyen mutuamente. En la topología más fiable, los minoristas pueden implementar una RSSU local para reducir la dependencia de conectividad de Internet o la disponibilidad de Azure y también pueden implementar registros de PDV donde el modo sin conexión está habilitado si hay un problema con el servidor local o la red.

- **Dispositivos de hardware/periféricos** – Un aspecto importante de un sistema Retail POS es su capacidad para usar periféricos de PDV como impresoras, cajas registradoras, y terminales de pago. Aunque todas las opciones disponibles de POS puedan usar dispositivos periféricos, solo los MPOS para Windows los admiten directamente. Para el resto de solicitudes, se requieren una o más estaciones de hardware. Aunque este planteamiento añade flexibilidad, deben implementarse, configurarse y mantener componentes adicionales.
- **Requisitos del sistema** – Los requisitos del sistema para la aplicación de PDV varían. Asegúrese de verificar la información más reciente antes de tomar una decisión. Por ejemplo, ya que los CPOS se ejecutan en un explorador, admiten una gama más amplia de sistemas operativos. Para obtener más información acerca de los requisitos del sistema, consulte los [Requisitos del sistema para implementaciones en la nube](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Implementación y mantenimiento** La complejidad de los requisitos de implementación y mantenimiento puede variar, en función de las opciones de la aplicación y la implementación. Por ejemplo, para una implementación de CPOS hospedada en la nube, no es necesario instalar y actualizar en cada dispositivo. Por lo tanto, este planteamiento reduce significativamente la complejidad y el coste. Sin embargo, si se implementan MPOS en cada registro y habilita el modo desconectado, y también implementa las estaciones compartidas de hardware, aumenta significativamente el número de extremos que deben administrarse.

