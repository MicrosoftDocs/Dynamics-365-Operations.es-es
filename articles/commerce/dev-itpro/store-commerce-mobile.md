---
title: Aplicación Store Commerce para plataformas móviles
description: Este artículo describe cómo comenzar a usar la aplicación Microsoft Dynamics 365 Commerce Store Commerce para Android e iOS.
author: stuharg
ms.date: 10/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: 1f07a130629863ebd9d036378436cf360e90ac26
ms.sourcegitcommit: 98231ff810f41f9fcdc6b536d87e453028aa6db8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2022
ms.locfileid: "9642346"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>Aplicación Store Commerce para plataformas móviles

[!include [banner](../includes/banner.md)]

Este artículo describe cómo comenzar a usar las aplicaciones Microsoft Dynamics 365 Commerce Store Commerce para Android e iOS.

Las aplicaciones móviles de Dynamics 365 Commerce para Android e iOS hacen que el proceso de implementación de dispositivos de punto de venta (PDV) móviles con funciones completas para su entorno minorista sea directo y simple. Las aplicaciones móviles de Store Commerce ofrecen todas las capacidades y ventajas de la [Aplicación Store Commerce para Windows](store-commerce.md) en factores de forma de teléfono y tableta. Las aplicaciones móviles de Store Commerce se pueden instalar directamente desde las tiendas de aplicaciones de Apple y Google Play, y no requieren que un desarrollador cree un nuevo paquete de aplicaciones para implementarlas o actualizarlas. 

Las aplicaciones móviles de Store Commerce conservan la paridad funcional total con las aplicaciones híbridas minoristas actuales. Además, Store Commerce para iOS incluye soporte para una estación de hardware dedicada, de modo que los dispositivos iOS puedan comunicarse con terminales de pago en red, impresoras de recibos y cajas registradoras sin necesidad de implementar una estación de hardware compartida. 

> [!IMPORTANT]
> Las aplicaciones Store Commerce para Windows, Android e iOS son la próxima generación de aplicaciones de PDV para Dynamics 365 Commerce. La aplicación Modern POS (MPOS) actual y las [Aplicaciones híbridas minoristas](hybridapp.md) para dispositivos móviles quedarán obsoletas en octubre de 2023. Microsoft recomienda que use Store Commerce o Cloud POS (CPOS) para todas las nuevas implementaciones de PDV. Los clientes existentes deben planear migrar de la aplicación híbrida Retail a Store Commerce. Para obtener más información sobre la programación de obsolescencia de MPOS y las aplicaciones híbridas de Retail, consulte [Modernizando la pila de tecnología de Dynamics 365 Commerce en tienda](https://www.microsoft.com/download/details.aspx?id=103896). 

## <a name="app-architecture"></a>Arquitectura de la aplicación

Las aplicaciones móviles Store Commerce usan la misma topología que la aplicación Store Commerce para Windows cuando se implementa en modo híbrido. Las aplicaciones móviles de Store Commerce son aplicaciones de shell que representan CPOS directamente desde la Commerce Scale Unit (CSU) y se conectan a Commerce sin periféricos y Commerce headquarters a través de la CSU. El modelo de aplicación shell permite que las aplicaciones Store Commerce admitan una estación de hardware dedicada para la integración directa con una terminal de pago, una impresora, una caja registradora y otros periféricos. No tiene que configurar una estación de hardware compartida para usar dispositivos de hardware. 

Para actualizar una aplicación móvil de Store Commerce, simplemente actualice la CSU. La aplicación seleccionará automáticamente todas las nuevas funciones y características de PDV. Para obtener más información acerca de cómo actualizar la CSU, consulte [Aplicar actualizaciones y extensiones a Commerce Scale Unit (nube)](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

Las aplicaciones de shell reciben servicio a través de actualizaciones de la tienda de aplicaciones. Cuando una versión secundaria alcance la disponibilidad general (GA), Microsoft la publicará en las tiendas de aplicaciones. Microsoft también podría publicar parches entre actualizaciones de versiones menores para publicar correcciones de errores de alta prioridad.

## <a name="prerequisites"></a>Requisitos previos

Las aplicaciones móviles de Store Commerce requieren Dynamics 365 Commerce, específicamente Commerce headquarters y los componentes de CSU. La siguiente tabla enumera las versiones mínimas del sistema operativo (SO) y CSU que requieren las aplicaciones móviles para Android e iOS. 

| Requisito previo | Android      | iOS  |
| ------------ | ------------ | ---- |
| Versión de SO   | 7.0          | 15.0 |
| Versión CSU  | 9.38.22266.8 | Por determinar  |

## <a name="install-the-app"></a>Instalar la aplicación

Puede instalar las aplicaciones móviles de Store Commerce directamente desde Google Play Store o Apple App Store. 

- [Aplicación Store Commerce para Android](https://aka.ms/storecommerceandroid)
- Aplicación Store Commerce para iOS (disponible pronto)

Los paquetes de aplicaciones de Android (.apk) y de Apple (.ipa) también se pueden descargar desde la biblioteca de activos compartidos en Microsoft Dynamics Lifecycle Services. 

## <a name="device-and-register-setup"></a>Configuración de dispositivo y registro

Antes de que se pueda activar un registro en las aplicaciones móviles de Store Commerce, debe configurar un dispositivo y un registro en Commerce headquarters. Para obtener más información, vea [Dispositivos y registros](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Configuración del dispositivo

Para crear y configurar un nuevo dispositivo, siga estos pasos.

1. En Commerce headquarters, vaya a **Retail y Commerce \> Configuración del canal \> Configuración del PDV \> Dispositivos**. 
1. Cree un nuevo dispositivo y seleccione **Modern POS - Android** o **Moder POS - iOS** como el tipo de aplicación, según la aplicación móvil que esté implementando. 

    > [!NOTE] 
    > Los tipos de aplicación **Modern POS - Android** y **Modern POS - iOS** también se utilizan para implementar las aplicaciones híbridas actuales para Android e iOS. Después que MPOS quede en desuso, las etiquetas para estos tipos de aplicaciones se actualizarán a **Store Commerce - Android** y **Modern POS - iOS**. 

### <a name="register-setup"></a>Registrar configuración

Puede crear un nuevo registro y asociarlo con el dispositivo que creó, o puede asociar un registro existente con su nuevo dispositivo. Para obtener más información acerca de los registros, consulte [Crear y asociar registros](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Configuración de diseño de pantalla

Si está reutilizando un diseño de pantalla que se incluye en los datos de demostración que se proporcionan con su licencia de Dynamics 365 Commerce, la aplicación Store Commerce seleccionará automáticamente el diseño compacto incluido si la resolución de pantalla de su dispositivo es inferior a 480 &times; 853 píxeles en orientación vertical. Sin embargo, si crea un diseño de pantalla desde cero, o si su dispositivo móvil usa una resolución mayor que la que admite el diseño compacto, asegúrese de crear una resolución y cuadrículas de botones asociadas que sean apropiadas para el teléfono o la tableta que a la que planea implementar. Para obtener más información sobre las configuraciones de diseño de pantalla, consulte [Configuraciones visuales de la interfaz de usuario de PDV](../pos-screen-layouts.md). 

Después de configurar los dispositivos y registros, en Commerce headquarters, vaya a **Retail y Commerce \> Id. de Retail y Commerce \> Programaciones de distribución** y ejecute el trabajo de registros.

## <a name="activate-a-device"></a>Activar un dispositivo

Para activar un dispositivo en una aplicación móvil Store Commerce, siga estos pasos.

1. Abra la aplicación en el dispositivo móvil.
1. Introduzca la URL de CPOS, que puede encontrar en la página de detalles del entorno en Lifecycle Services, o en la página **Perfiles de canales** en Commerce headquarters (**Retail y Commerce \> Configuración de canales \> Perfiles de canales**).
1. Inicie sesión con las credenciales de un trabajador que tenga permiso para administrar dispositivos.
1. Seleccione la tienda que está asociada con el registro que creó o reutilizó en Commerce headquarters.
1. Seleccione el registro que asoció con el dispositivo que creó en Commerce headquarters.
1. Su dispositivo ahora debería estar activado. Puede iniciar sesión en el registro utilizando el id. de operador y la contraseña de un trabajador asociado con la tienda que seleccionó. 

Para obtener más información sobre la activación del dispositivo, consulte [Activación de dispositivos de punto de venta (PDV)](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>Paridad de características con Store Commerce para Windows

La siguiente tabla compara las capacidades de la aplicación Store Commerce en las plataformas Windows, Android e iOS.

| Característica                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Estación de hardware dedicada                                                            | Sí     | Sí     | Sí |
| Estación de hardware compartida                                                               | Sí     | Sí     | Sí |
| Comunicación con periféricos en red (terminal de pago, impresora y caja registradora) | Sí     | Sí     | Sí |
| OLE para periféricos de punto de venta (OPDV) a través de una estación de hardware local             | Sí     | N.º      | N.º  |
| Modo sin conexión                                                                          | Sí     | N.º      | N.º  |

## <a name="additional-resources"></a>Recursos adicionales

[Aplicación Store Commerce](store-commerce.md)

[Elija entre Store Commerce y Cloud POS](../mpos-or-cpos.md)

[Solucionar problemas de configuración e instalación de Store Commerce](../troubleshoot/store-commerce-setup-installation.md)
