---
title: "Área de trabajo móvil de los pedidos de ventas para Microsoft Dynamics 365 para la aplicación de operaciones"
description: "Con los pedidos de ventas área de trabajo móvil, puede permanecer actualizado a los pedidos de ventas y cualquier lugar en cualquier momento."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Área de trabajo móvil de los pedidos de ventas para Microsoft Dynamics 365 para la aplicación de operaciones

Con los pedidos de ventas área de trabajo móvil, puede permanecer actualizado a los pedidos de ventas y cualquier lugar en cualquier momento. 

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                         | Descripción                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lea sobre el Microsoft Dynamics 365 para la plataforma de móvil de las operaciones | [365 Dinámica para la plataforma] móvil de las operaciones (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dinámica 365 para las operaciones                                          | Asegúrese de que utiliza un entorno con Microsoft Dynamics 365 para la versión 1611 de las operaciones y Microsoft Dynamics para la plataforma de las operaciones actualiza 3 (noviembre de 2016). |
| Sustitución 3215650 KB                                                    | Instale el reemplazo para habilitar las áreas de trabajo que se proporcionan en Microsoft Dynamics 365 para las operaciones.                                                                       |
| Dispositivo móvil que tiene Dynamics 365 para la aplicación de las operaciones instalada | Descargue Dynamics 365 para la aplicación de las operaciones de la tienda móvil de la aplicación.                                                                                                      |

## <a name="overview"></a>Visión general
Esta Área de trabajo de móvil tiene acceso a Dynamics 365 para la aplicación de las operaciones y le permiten ver información detallada sobre cada pedido de ventas, por ejemplo, el estado del pedido, la información de contacto del cliente, y la información de contacto de tomador del pedido. El área de trabajo móvil proporciona una vista inmediata de los pedidos de ventas. Puede ver pedidos de ventas del cliente, o ver todos los pedidos de ventas, o ver información sobre un pedido de ventas específico. El área de trabajo móvil proporciona dos vistas para ayudarle a analizar los pedidos de venta detallados.

### <a name="view-all-sales-orders"></a>Permite ver todos los pedidos de ventas

Esta vista muestra todos los pedidos de ventas.

-   Use uno de los filtros siguientes para seleccionar los pedidos de ventas que desea ver.
    -   Buscar por pedido de ventas
    -   Buscar por cuenta de cliente
    -   Buscar por nombre de cliente
    -   Búsqueda de estado
    -   Búsqueda de estado de liberación
    -   Buscar por fecha y hora creada

<!-- -->

-   Tras seleccionar los pedidos de ventas, puede ver los detalles de pedidos específicos. Específicamente, puede ver:
    -   Información del nombre y la dirección del cliente
    -   Las distintas fechas del pedido de ventas, como la fecha de envío solicitada y fecha de envío confirmada
    -   Información de contacto de tomador del pedido
    -   Información de contacto del cliente
    -   Líneas de pedido
    -   Envíos que muestran cómo y cuándo se ha registrado un pedido de ventas

### <a name="view-orders-for-a-customer-"></a>Pedidos de la información del cliente ** **

Esta vista muestra pedidos de ventas por cliente.

-   Use uno de los filtros siguientes para ver los pedidos para un cliente.
    -   Buscar por nombre
    -   Buscar por cuenta

<!-- -->

-   Tras seleccionar un cliente, puede ver:
    -   Nombre y grupo de cliente
    -   Información de contacto del cliente
    -   Pedidos de ventas y detalles de cliente sobre los pedidos de ventas:
        -   Información del nombre y la dirección del cliente
        -   Las distintas fechas del pedido de ventas
        -   Información de contacto de tomador del pedido
        -   Información de contacto del cliente
        -   Líneas de pedido
        -   Envíos que muestran cómo y cuándo se han registrado los pedidos de ventas

## <a name="get-started"></a>Introducción
Siga estos pasos para iniciarse mediante el área de trabajo móvil de los pedidos de ventas en su dispositivo móvil.

1.  En su tienda móvil de la aplicación, y descarga el instalar Microsoft Dynamics 365 para la aplicación de las operaciones.
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

## <a name="view-information-about-sales-orders-for-a-customer"></a>Permite ver información acerca de los pedidos de ventas para un cliente
1.  En el dispositivo móvil, seleccione ** los pedidos de ventas ** el área de trabajo.
2.  Seleccione ** pedidos de la información del cliente **.
3.  Uso ** ** cuenta o ** nombre de cliente ** información de encontrar el cliente deseado.
4.  Seleccione el cliente.
5.  Seleccione ** información de contacto o ** ** pedidos de ventas **.
6.  Si ** pedidos de ventas ** se selecciona, la lista de pedidos de ventas para el cliente se mostrará.
7.  Seleccione ** pedido de ventas **.
8.  Aquí puede ver información sobre las líneas de pedido de ventas, los envíos, la información de contacto de cliente, y la información de contacto de tomador del pedido.




