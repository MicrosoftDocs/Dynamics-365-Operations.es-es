---
title: Configuración de un viaje de varios tramos
description: Este tema describe cómo configurar viajes de varios tramos para el módulo de costo de entrega.
author: Weijiesa
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c65a3d3971593ccf832a6af3c8c27d56a68b46c8
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689730"
---
# <a name="multi-leg-journey-setup"></a>Configuración de un viaje de varios tramos

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar viajes de varios tramos para el módulo **Costo descargado**.

## <a name="legs"></a>Escalas

Los tramos se utilizan para identificar partes separadas de un viaje. Cada tramo se construye seleccionando los puertos de envío "hacia" y "desde" y el método de transporte que se utiliza para ese tramo. Los plazos de entrega se pueden asociar a cada tramo. Los plazos de entrega pueden ayudar a rastrear un envío y también se pueden utilizar para calcular la fecha estimada de entrega de las mercancías en un viaje. Además, cuando se completa un tramo de un viaje, el estado del viaje, el contenedor de envío y las líneas de orden de compra asociadas se pueden actualizar a través de la configuración del control de seguimiento. Los tramos se pueden utilizar con una sola plantilla de viaje o se pueden reutilizar con varias plantillas de viaje. La carga de contenedores, la aduana y el transporte local generalmente se configuran como tramos, y para ellos se utiliza un puerto de envío no específico.

Para trabajar con tramos, vaya a **Coste de aterrizaje \> Configuración de viaje de varios tramos \> Tramos**. Allí, puede ver, abrir, crear y eliminar registros para tramos. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Escala | Escriba un nombre/número de identificador único para el tramo del viaje. |
| Descripción | Proporcione una descripción del tramo del viaje. Normalmente, esta descripción identifica los puertos "hacia" y "desde", o el paso del viaje. |
| Puerto de origen | Introduzca el punto de origen de la mercancía en el tramo. |
| Puerto de destino | Introduzca el punto de destino de la mercancía en el tramo. |
| Método de envío | Ingrese el método de transporte para el tramo. |

## <a name="journey-templates"></a>Plantillas de recorrido

Una plantilla de viaje define el viaje de varios tramos entre dos puertos por los que viajan las mercancías durante un viaje. Los tramos del viaje se combinan para identificar la cantidad de tiempo que se necesitará para que las mercancías viajen desde el punto de origen del proveedor hasta el destino final del almacén. Cuando los tramos se colocan en la plantilla de viaje en un orden específico, los plazos de entrega identificarán la fecha de cada tramo y el estado del viaje, el contenedor y las líneas de compra para el viaje. Usa el [Centro de control de seguimiento](delivery-information-setup.md) para configurar los plazos de entrega asociados con cada tramo que forma la plantilla de viaje. La plantilla de viaje también se utiliza cuando se configuran los costos automáticos de un viaje. Cuando se define un viaje, el costo asociado con el transporte de las mercancías se puede definir en la página de costos del automóvil.

Para trabajar con plantillas de viaje, vaya a **Coste de aterrizaje \> Configuración de viaje de varios tramos \> Plantillas de viaje**. Allí, puede ver, abrir, crear y eliminar plantillas de viaje.

Para cada plantilla de viaje, configure los siguientes campos en el encabezado.

| Campo | Descripción |
|---|---|
| Plantilla de recorrido | Escriba un nombre/número de identificador único para la plantilla de viaje. La plantilla de viaje generalmente describe el punto de origen y el punto de destino del viaje. |
| Descripción | Especificar una descripción de la plantilla de viaje. La descripción generalmente indica los puertos "hacia" y "desde", y el tipo de viaje. |

En la sección **Líneas**, agregue una línea para cada tramo del viaje y ordene las líneas. Utilice las flechas **Arriba** y **Abajo** en la barra de herramientas para cambiar el orden de las líneas. En la tabla siguiente se describen los campos disponibles para cada línea.

| Campo | Descripción |
|---|---|
| Escala | Seleccione un tramo para agregar al viaje. |
| Descripción | Descripción del tramo. |
| Puerto de origen | El puerto que es el punto de origen de la mercancía en el tramo. Este puerto es el puerto "a" que se utiliza para determinar los costos de automóvil para un viaje. |
| Puerto de destino | El puerto de destino final de la mercancía en el tramo. |
| Modo de entrega | El modo de entrga que se usa para el tramo. |
| Puerto de origen del recorrido | Si el puerto que se especifica para el tramo se utiliza para determinar los costos del automóvil, seleccione esta casilla de verificación para identificarlo como el puerto "viaje desde". Este puerto se mostrará en el encabezado del viaje. |
| Puerto de destino del recorrido | Si el puerto que se especifica para el tramo se utiliza para determinar los costos del automóvil, seleccione esta casilla de verificación para identificarlo como el puerto "viaje a". Este puerto se mostrará en el encabezado del viaje. |
| Empresa de transporte | Seleccione la empresa de envío que se utiliza para el tramo. |

## <a name="activities"></a>Actividades

Los ajustes de la página **Actividades** establecen los tipos de actividades que pueden ocurrir en el puerto de destino de un tramo. Los usuarios que trabajan en la página **Todos los contenedores de envío** pueden seleccionar entre estos valores cuando estiman la duración de cada actividad y registran la duración real para fines de comparación.

Para configurar sus actividades, vaya a **Coste de aterrizaje \> Configuración de viajes de varios tramos \> Actividades**. Allí puede agregareliminar y editar actividades usando los botones del panel de acciones.

En la tabla siguiente se describen los campos disponibles para cada actividad en la cuadrícula.

| Campo | Descripción |
|---|---|
| Actividad | El nombre de la actividad. |
| Descripción | Una descripción de la actividad. |
| Empresa de transporte | La cuenta de proveedor de la empresa de envío asociada a la actividad. |
