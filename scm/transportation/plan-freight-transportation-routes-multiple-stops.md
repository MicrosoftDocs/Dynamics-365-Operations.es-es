---
title: Planificar rutas de transporte de flete con varias paradas
description: "Este artículo describe los distintos elementos que utiliza para planificar rutas de transporte en Dynamics 365 for Finance and Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: e7965c094f91bcbcad21ecfa599f133a6e84f4f7
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Planificar rutas de transporte de flete con varias paradas
<a id="plan-freight-transportation-routes-with-multiple-stops" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este artículo describe los distintos elementos que utiliza para planificar rutas de transporte en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

Puede utilizar planes y guías de ruta para rutas de transporte complejas con varias paradas. Si se va a utilizar la misma ruta con regularidad, puede configurar una ruta programada.

## Planes de ruta
<a id="route-plans" class="xliff"></a>
Un plan de ruta contiene segmentos de ruta que proporcionan información sobre los paradas que se visitan en la ruta y los transportistas que se utilizan para cada segmento. Debe definir las paradas en la ruta como concentradores. Un concentrador puede ser un proveedor, un almacén, un cliente o incluso simplemente un lugar para volver cargar donde cambiar el transportista. Para cada segmento, puede definir " tasas al contado" para gastos varios. A continuación se incluyen algunos ejemplos:

-   Gastos de viaje a los segmentos dados
-   Cargos por recoger las mercancías
-   Gastos por entrega de las mercancías

Cada plan de ruta debe asociarse a una guía de ruta.

## Guías de ruta
<a id="route-guides" class="xliff"></a>
Una guía de ruta define los criterios para la conciliación de una carga con un plan de ruta específico. Por ejemplo, puede especificar un concentrador de origen y un concentrador de destino, los límites para el volumen o el peso del contenedor, y un transportista de envío, el servicio o el grupo. Las guías de ruta están disponibles en la página **Área de trabajo de la ruta de la tasa**, donde las cargas pueden asociarse a las rutas de manera manual o automática. Si la guía de ruta es una ruta programada, también está disponible en la página **Área de trabajo de planificación de la carga**.

## Rutas programadas
<a id="scheduled-routes" class="xliff"></a>
Una ruta programada es un plan de ruta predefinido que tiene una programación para las fechas de envío. Las rutas programadas y no programadas difieren en la forma en que se les asignan las cargas. Si asigna una ruta no programada mediante el área de trabajo de la ruta de la tasa, solo se validan la carga y la guía de ruta. Si asigna una ruta programada, también se tienen en cuenta las fechas y las direcciones de los pedidos y los concentradores y la fecha del plan de ruta. No tiene que utilizar la página Área de trabajo de la ruta de la tasa para asignar cargas manualmente a una ruta programada. En su lugar, puede utilizar el Área de trabajo de planificación de la carga para sugerir que las cargas se creen basándose en las direcciones de los clientes y las fechas de entrega de los pedidos de ventas para una ruta programada determinada. Para las rutas programadas, el plan de ruta tendrá concentradores de origen y de destino fijos. Normalmente, el servicio y el transportista del envío serán el mismo para todos los segmentos, pero pueden diferir. Los concentradores de destino se crean utilizando los códigos postales de los clientes que se visitan en la ruta. Pueden definirse varias programaciones de ruta para un plan de ruta. El plan de ruta debe asociarse a una guía de ruta. Sin embargo, para las rutas programadas, el plan puede asociarse a una única guía de ruta. La programación de ruta solo se utiliza para crear las rutas reales en la página **Programación de ruta**. Puede utilizar la plantilla de carga predeterminada al proponer cargas en el Área de trabajo de planificación de la carga.

## Área de trabajo de planificación de la carga
<a id="load-building-workbench" class="xliff"></a>
El Área de trabajo de planificación de la carga utiliza direcciones y fechas de entrega desde pedidos de ventas y las rutas programadas que están disponibles para proponer una carga. De forma predeterminada, los valores de la ruta se especifican en el área de trabajo. Sin embargo, puede seleccionar una fecha de inicio que sea anterior a la fecha de inicio en la ruta. Cuando se propone una carga, se comprueban la dirección de entrega y la fecha de entrega de pedidos de ventas abiertos. Si el código postal de la dirección de entrega coincide con el código postal de un concentrador en el plan de viaje, y la fecha de entrega se encuentra dentro del intervalo seleccionado en los criterios, se propone la orden de venta para la carga. También se considera la capacidad de la plantilla de carga. Solo se propone una carga cada vez. Si tiene un pedido de ventas que no se incluye, es posible que tenga que utilizar una plantilla de carga diferente (por ejemplo, una plantilla de carga para un camión o un contenedor más grandes) o planificar una entrega adicional.




