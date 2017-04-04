---
title: "Recepción del inventario el área de trabajo disponible para móvil Microsoft Dynamics 365 para la aplicación de operaciones"
description: "Las ayudas disponible móviles del espacio de trabajo de inventario que tiene penetraciones móviles en el inventario disponible y reservado en cualquier momento y cualquier lugar."
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

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Recepción del inventario el área de trabajo disponible para móvil Microsoft Dynamics 365 para la aplicación de operaciones

Las ayudas disponible móviles del espacio de trabajo de inventario que tiene penetraciones móviles en el inventario disponible y reservado en cualquier momento y cualquier lugar. 

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                         | Descripción                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Lea sobre el Microsoft Dynamics 365 para la plataforma de móvil de las operaciones | [365 Dinámica para la plataforma] móvil de las operaciones (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dinámica 365 para las operaciones                                          | Un entorno con Microsoft Dynamics 365 para la versión 1611 de las operaciones y Microsoft Dynamics para la plataforma de las operaciones actualiza 3 (noviembre de 2016) |
| Sustitución 3215650 KB                                                    | Instale el reemplazo para habilitar las áreas de trabajo que se proporcionan en su Microsoft Dynamics 365 para las operaciones.                                       |
| Dispositivo móvil que tiene Dynamics 365 para la aplicación de las operaciones instalada | Descargue Dynamics 365 para la aplicación de las operaciones de la tienda móvil de la aplicación.                                                                           |

## <a name="introduction"></a>Introducción
Normalmente, las empresas tienen varios envíos y recepciones de inventario varios cada día. Estos movimientos cambian constantemente el estado disponible de inventario. El área de trabajo disponible móvil del inventario permite ver el estado de inventario entre empresas disponible, de modo que pueda ganar las últimas penetraciones en los datos de inventario en el dispositivo móvil de su elección. Independientemente de si trabaja en el almacén, la compra, las ventas, la fabricación, o la administración, o tener otras funciones, puede tener acceso a los datos de inventario en cualquier momento y cualquier lugar. El área de trabajo móvil proporciona una vista inmediata el estado disponible a través de instalaciones, y permite ver el inventario disponible a través de instalaciones, las reservas actuales, materiales y del inventario disponible no reservada. También puede especificar números de artículo para ver el inventario disponible, y realice una búsqueda filtrada disponible para los productos o las variantes. Específicamente, el área de trabajo proporciona móvil estas características:

-   Puede buscar el número de producto o el nombre del producto para buscar productos para ver el estado disponible de inventario para.
-   Para los productos seleccionados, puede ver la información siguiente:
    -   Inventario disponible por sitio
    -   Inventario disponible por almacén
    -   Inventario disponible por ubicación
    -   Inventario disponible por lotes (para los productos controlados por lote)
    -   Inventario disponible por el estado de inventario

<!-- -->

-   El inventario del producto disponible se muestra de las siguientes formas:
    -   Por el inventario físico (esta vista representa el importe total).
    -   Por la reservados físicamente (esta vista representa el importe reservado).
    -   Por la cantidad Física disponible (esta vista representa el importe disponible que no tiene ninguna reserva.)

## <a name="get-started"></a>Introducción
Para obtener iniciado en su dispositivo móvil:

1.  De su tienda móvil de la aplicación, y descarga el instalar Microsoft Dynamics 365 para la aplicación de las operaciones.
2.  Iniciar la aplicación del dispositivo.
3.  Especifique la dirección URL de Dynamics 365.
4.  Especifique la empresa para iniciar sesión en. Por ejemplo, escriba USMF ** **.
5.  La primera vez que se iniciar sesión, se le solicitará el nombre de usuario y la contraseña para su Microsoft Dynamics 365 para la cuenta de operaciones. Especifique sus. Tras en firme, verá las áreas de trabajo disponibles para su empresa.

Para ver Áreas de trabajo en su aplicación móvil, primero debe publicar las áreas de trabajo deseadas a Dynamics 365 para la aplicación de las operaciones.

1.  Dinámica 365 de inicio de las operaciones.
2.  Retroceda ** Administración del sistema ** &gt; ** la configuración ** &gt; ** los parámetros del sistema **.
3.  Seleccione ** gestionar la aplicación móvil **.
4.  Seleccione el área de trabajo para publicar en esta plataforma móvil.
5.  Seleccione ** publique el área de trabajo **.
6.  Actualización del dispositivo para ver las áreas de trabajo publicadas.

## <a name="view-the-onhand-inventory-for-a-product"></a>Vea el inventario total disponible para un producto
1.  En el dispositivo móvil, seleccione ** inventario disponible ** el área de trabajo.
2.  Seleccione ** compruebe disponible para un artículo **. Ve una lista de los productos que se cargan en su aplicación para la usarla sin conexión. De forma predeterminada, 50 artículos están cargados, pero puede cambiar este número. Para obtener más información, consulte el manual previos leído.
3.  Si el artículo no está en la lista, seleccione ** busque más ** para realizar una búsqueda en línea en Dynamics 365 para las operaciones. Busque el número derivado, o el cambio a un nombre derivado de la búsqueda.
4.  Seleccione un producto. Si el artículo tiene una imagen, se muestra la imagen.
5.  Seleccione una de las opciones siguientes para ver el estado disponible de inventario:
    -   Visión disponible por sitio
    -   Visión disponible por almacén
    -   Visión disponible por la ubicación
    -   Visión disponible por lote (para los productos controlados por lote)
    -   Visión disponible por el estado de inventario

    El inventario del producto disponible se muestra de las siguientes formas:
    -   Por el inventario físico (esta vista representa el importe total).
    -   Por la reservados físicamente (esta vista representa el importe reservado).
    -   Por la cantidad Física disponible (esta vista representa el importe disponible que no tiene ninguna reserva.)




