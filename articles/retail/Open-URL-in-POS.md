---
title: Abrir URL en POS
description: En este tema se proporciona una visión general de las mejoras que se han realizado en la funcionalidad de búsqueda de productos y clientes en Microsoft Dynamics 365 for Retail.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 729caf9fad9097a3ecbf7d546c8f8a96f67aec92
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845698"
---
# <a name="open-url-in-pos"></a>Abrir dirección URL en el punto de venta

[!include [banner](includes/banner.md)]

Este tema describe cómo puede configurar un botón en Retail POS (PDV) para abrir una dirección URL. Esta función no requiere una personalización de código, y se puede configurar por una persona con un rol que no es un desarrollador. Esta función está disponible como parte de liberación de la versión 8.1.3 Dynamics 365 for Finance and Operations (generación 8.1.227.10014) y posterior. 

Esta característica permite la configuración de un botón en PDV, mediante el Diseñador de la cuadrícula de botones para abrir una dirección URL. Actualmente, esto se admite en las siguientes configuraciones:

- Abrir en ventana nueva.
- Abrir dentro de PDV.
- Abrir una aplicación nativa.

## <a name="open-in-new-window"></a>Abrir en ventana nueva

Esta configuración define si abrir la dirección URL en una ventana nueva o dentro de la aplicación. Cuando está configurado para abrir una dirección URL web dentro de la aplicación, el panel lateral de navegación y la barra de PDV superior están visibles y disponibles para la interacción del usuario. Cuando está configurada para abrirse en una ventana nueva, la dirección URL se abrirá en Modern POS para Windows y en una nueva ficha del explorador en todos los demás clientes de PDV. Para habilitarla, debe configurar la URL con la opción **Abrir en ventana nueva** seleccionada.

## <a name="open-within-pos"></a>Abrir dentro de PDV

El abrir una dirección URL web dentro de PDV se admite actualmente solo para Modern POS en Windows. En otros clientes, esta capacidad se encuentra en desarrollo y planificada para su lanzamiento en actualizaciones futuras. Para habilitarlo, debe configurar la URL con la opción **Abrir en ventana nueva** sin seleccionar.

## <a name="open-a-native-app"></a>Abrir una aplicación nativa

Esta función también le permite especificar URL que no son de Web para abrir una aplicación nativa. Por ejemplo, puede especificar protocolos de URL como Mailto, SIP, IM o MSTEAMS, que se pueden administrar mediante aplicaciones nativas respectivas en el dispositivo del host. Para habilitarla, debe configurar la URL con la opción **Abrir en ventana nueva** seleccionada.

- Para los equipos de Windows, consulte [Exportar o importar asociaciones de aplicaciones predeterminadas](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) para establecer las asociaciones predeterminadas de protocolos si configura su equipo utilizando la Administración y mantenimiento de imágenes de implementación (DISM).
- Si utiliza MDM, como Intune para administrar los equipos de Windows, consulte [Directiva CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).
- Si es desarrollador de software que crea una página Web personalizada, consulte [Iniciar la aplicación predeterminada para URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).

## <a name="open-a-native-app-seamlessly"></a>Abrir una aplicación nativa fácilmente

Windows, IOS y, Android también permiten abrir aplicaciones más fácilmente, en función de la asociación del protocolo de la aplicación. Si su aplicación no está ya configurada para gestionar la apertura desde un explorador web, puede necesitar que un programador la configure.

- Para Windows, consulte [Habilitar aplicaciones de páginas Web mediante controladores de URI de la aplicación](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).
- Para IOS, consulte [Vínculos universales para los desarrolladores](https://developer.apple.com/ios/universal-links/).
- Para Android, consulte [Administrar vínculos de la aplicación de Android](https://developer.android.com/training/app-links/).

| Cliente                | Abrir en ventana nueva | Abrir una aplicación nativa | Abrir dentro de PDV | Detalles                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Modern POS en Windows | ✓\*                | ✓               | ✓              | \* Se abre en una nueva ventana de Modern POS |
| PDV en la nube             | ✓\*                | ✓               | X              | \* Se abre en una nueva pestaña del explorador        |
| Modern POS en iOS     | ✓\*                | ✓               | X              | \* Se abre en una nueva pestaña del explorador        |
| Modern POS en Android | ✓\*                | ✓               | X              | \* Se abre en una nueva pestaña del explorador        |

## <a name="before-you-begin"></a>Antes de comenzar

Antes de empezar, revise cómo configurar [Diseños para Pantalla del punto de venta (PDV)](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>Abrir URL en POS

Para configurar una dirección URL para ser abierta en PDV, realice los pasos siguientes.

1. En la oficina central vaya a **Venta minorista \> Configuración de canal \> Configuración de PDV \> PDV \> Diseños de pantalla**.
2. Seleccione **Cuadrículas de botones \> diseñador**.
3. Cree un botón nuevo.
4. Seleccione las propiedades de **botón**.
5. Seleccione **Abrir URL** como la acción.
6. Especifique la dirección URL que desee usar.
7. Configurar si abrir la dirección URL en una ventana nueva.
