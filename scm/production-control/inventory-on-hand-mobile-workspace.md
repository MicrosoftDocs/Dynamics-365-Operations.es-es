---
title: "Espacio de trabajo móvil de inventario disponible para la aplicación Microsoft Dynamics 365 for Operations"
description: "El espacio de trabajo móvil de inventario disponible le ayuda a obtener información en el inventario reservado y disponible en cualquier momento y en cualquier lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espacio de trabajo móvil de inventario disponible para la aplicación Microsoft Dynamics 365 for Operations

El espacio de trabajo móvil de inventario disponible le ayuda a obtener información en el inventario reservado y disponible en cualquier momento y en cualquier lugar. 

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                         | Descripción                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Obtenga información sobre la plataforma móvil de Microsoft Dynamics 365 for Operations | [Plataforma móvil de Microsoft Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | Un entorno que tiene la versión 1611 de Microsoft Dynamics 365 for Operations y la actualización 3 de la plataforma de Microsoft Dynamics for Operations (noviembre de 2016). |
| Revisión 3215650 KB                                                    | Instale la revisión para habilitar los espacios de trabajo provistos en Microsoft Dynamics 365 for Operations.                                       |
| Dispositivo móvil que tiene instalada la aplicación Dynamics 365 for Operations | Descargue la aplicación Dynamics 365 for Operations desde su tienda de aplicaciones móviles.                                                                           |

## <a name="introduction"></a>Introducción
Por lo general, las empresas tienen múltiples envíos y múltiples recepciones de inventario cada día. Estos movimientos cambian constantemente el estado del inventario disponible. El espacio de trabajo móvil de inventario disponible le permite ver el estado de inventario disponible entre empresas, de modo que puede obtener la información más reciente sobre los datos de inventario en el dispositivo móvil que elija. Independientemente de si trabaja en el almacén, compras, ventas, fabricación o administración, o tiene otras funciones, puede tener acceso a los datos de inventario disponible en cualquier momento y en cualquier lugar. El espacio de trabajo móvil proporciona una vista inmediata del estado disponible entre instalaciones y le permite ver el inventario disponible entre instalaciones, las reservas actuales de material y el inventario disponible no reservado. También puede introducir los números de artículo para consultar el inventario disponible y realizar una búsqueda filtrada para los productos o variantes disponibles. El espacio de trabajo móvil proporciona específicamente estas características:

-   Puede buscar por número de producto o por nombre de producto para encontrar productos para ver el estado de inventario disponible.
-   Para los productos seleccionados, puede ver la información siguiente:
    -   Inventario disponible por sitio
    -   Inventario disponible por almacén
    -   Inventario disponible por ubicación
    -   Inventario disponible por lote (para productos controlados por lote)
    -   Inventario disponible por estado de inventario

<!-- -->

-   El inventario disponible del producto se muestra de las siguientes formas:
    -   Por inventario físico (Esta vista representa la cantidad total).
    -   Por inventario reservado (Esta vista representa la cantidad reservada).
    -   Por inventario físico disponible (Esta vista representa la cantidad disponible que no tiene reservas.)

## <a name="get-started"></a>Introducción
Para comenzar en su dispositivo móvil:

1.  Desde su tienda de aplicaciones móviles, descargue e instale la aplicación Microsoft Dynamics 365 for Operations.
2.  Inicie la aplicación en su dispositivo.
3.  Escriba la URL de Dynamics 365.
4.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
5.  La primera vez que inicia sesión, se le pedirá el nombre de usuario y la contraseña de su cuenta Microsoft Dynamics 365 for Operations. Escriba sus credenciales. Tras iniciar sesión, verá los espacios de trabajo disponibles para su empresa.

Para ver los espacios de trabajo en su aplicación móvil, primero debe publicar los espacios de trabajo deseados para la aplicación Dynamics 365 for Operations.

1.  Inicie Dynamics 365 for Operations.
2.  Vaya a **Administración del sistema** &gt; **Configurar** &gt; **parámetros del sistema**.
3.  Seleccionar **Administrar aplicación móvil**.
4.  Seleccione el espacio de trabajo que desea publicar en la plataforma móvil.
5.  Seleccione **Publicar espacio de trabajo**.
6.  Actualice su dispositivo para ver los espacios de trabajo publicados.

## <a name="view-the-onhand-inventory-for-a-product"></a>Visualice el inventario disponible para un producto
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Inventario disponible**.
2.  Seleccione **Comprobar el inventario disponible de un artículo**. Verá una lista de los productos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero puede cambiar este número. Para obtener más información, consulte el manual previamente leído.
3.  Si el artículo no está en la lista, seleccione **Buscar más** para realizar una búsqueda en línea en Dynamics 365 for Operations. Busque por número de producto o cambie a una búsqueda por nombre de producto.
4.  Seleccione un producto. Si el artículo tiene una imagen, esta se muestra.
5.  Seleccione una de las siguientes opciones para visualizar el estado de inventario disponible:
    -   Ver el inventario disponible por sitio
    -   Ver el inventario disponible por almacén
    -   Ver inventario disponible por ubicación
    -   Ver inventario disponible por lote (para productos controlados por lote)
    -   Ver inventario disponible por estado de inventario

    El inventario disponible del producto se muestra de las siguientes formas:
    -   Por inventario físico (Esta vista representa la cantidad total).
    -   Por inventario reservado (Esta vista representa la cantidad reservada).
    -   Por inventario físico disponible (Esta vista representa la cantidad disponible que no tiene reservas.)




