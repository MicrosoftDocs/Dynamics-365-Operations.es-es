---
title: Seguimiento de viajes entrantes y viajes de contenedores de envío
description: Este tema explica cómo puede utilizar la página de seguimiento de entrada para realizar un seguimiento del progreso de sus viajes y viajes de contenedores de envío.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 678f2b6cda0592e0393bb15f372cb4be84778932
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501255"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Seguimiento de viajes entrantes y viajes de contenedores de envío

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La página **Seguimiento de entrada** permite realizar un seguimiento del progreso de sus viajes y viajes de contenedores de envío. Cada viaje y viaje se desglosa por *actividades*, cada uno de los cuales tiene su propia fila en la página. Puede usar la página para ver e ingresar fechas estimadas y fechas reales por actividad.

Normalmente, dependiendo de la configuración en el [Centro de control de seguimiento](delivery-information-setup.md#tracking-control-center), estas actividades muestran automáticamente la fecha estimada de aterrizaje en el destino final. Además, dependiendo de la configuración, la fecha final generalmente actualiza la fecha de entrega o la fecha confirmada en las líneas de la orden de compra. Para las líneas de orden de transferencia, puede configurar el sistema para actualizar la fecha de recepción.

Para abrir la página **Seguimiento entrante**, ir a **Coste de aterrizaje \> Seguimiento \> Seguimiento entrante**.

## <a name="filter-the-activities-list"></a>Filtrar la lista de actividades

Puedes usar los campos **Viaje** y **Contenedor de envío** en la parte superior de la página **Seguimiento entrante** para filtrar la página de modo que muestre solo las actividades que están asociadas con el viaje y / o contenedor de envío seleccionado.

## <a name="update-tracking-information"></a>Actualizar la información de seguimiento

Para actualizar el cronograma de un viaje o viaje, ingrese la fecha de inicio de la primera actividad. A continuación, se actualiza la fecha de finalización estimada de la última actividad. La configuración de cada tramo y plantilla de viaje en el [Centro de control de seguimiento](delivery-information-setup.md#tracking-control-center) determina los plazos de entrega estimados. Las fechas de finalización estimadas utilizan el tiempo de espera desde la fecha de inicio de la actividad. Luego, cuando se registra la fecha de finalización real, la fecha de inicio de la siguiente actividad se actualiza a la misma fecha que la fecha de finalización real de la actividad anterior. El tiempo de entrega real se actualiza para que se puedan realizar comparaciones y análisis. Se pueden introducir notas adicionales en el campo **Nota**.

El orden de las actividades en la cuadrícula está determinado por el orden de los tramos en la plantilla de viaje correspondiente. Si cambia el orden de los tramos en el viaje adjunto, también cambia el control de seguimiento.

Puede actualizar las fechas de todos los contenedores seleccionando **Actualizar fecha de inicio** o **Actualizar la fecha de finalización real** en el Panel de acciones. Alternativamente, puede ingresar las fechas por contenedor en el envío. Este enfoque permite una mayor flexibilidad, porque los contenedores se pueden dividir en un entorno de viajes múltiples.

## <a name="buttons-on-the-action-pane"></a>Botones en el panel de acciones

Puede utilizar los botones del panel de acciones de la página **Seguimiento de entrada** para trabajar con viajes y recorridos de entrada. En la tabla siguiente se describen los botones disponibles.

| Botón | Descripción |
|---|---|
| Editar | Edite un viaje o el viaje de un contenedor de envío. |
| Crear nuevo | Cree un viaje o el viaje de un contenedor de envío. |
| Borrar | Elimine un viaje o recorrido de contenedor de envío seleccionado. |
| Actualizar fecha de inicio | Actualice la fecha de inicio de una actividad para todos los contenedores de un viaje. Cuando se actualiza la fecha de inicio de una actividad específica o tramo de un viaje, las fechas de inicio estimadas subsiguientes se actualizan en función del tiempo de espera especificado. |
| Actualizar fecha de finalización real | Actualice la fecha de final de una actividad para todos los contenedores de un viaje. Cuando se actualiza la fecha de final de una actividad específica o tramo de un viaje, las actividades subsiguientes se actualizan en función del tiempo de espera especificado. |
| Agregar actividades | Agregue manualmente una actividad a un viaje. Por ejemplo, puede agregar una actividad de fumigación. La adición puede hacer que cambie la fecha de entrega confirmada de las mercancías en el barco o en el viaje. Cuando se agrega una actividad al viaje, los días estimados no se ingresan hasta que se actualiza la fecha de inicio de un tramo del viaje. |

## <a name="information-and-settings-on-the-overview-tab"></a>Información y configuración en la pestaña Descripción general

La pestaña **Visión general** muestra una lista de todas las actividades que pertenecen al viaje y / o contenedor de envío que se selecciona en la parte superior de la página. En la tabla siguiente se describen los campos disponibles para cada actividad.

| Campo | Descripción |
|---|---|
| Escala | El ID de tramo de la actividad, tal como se define en la plantilla de viaje. |
| Modo de entrega | El método de entrega esperado para la actividad. |
| Actividad | Este campo generalmente identifica el trabajo o la tarea que está asociada con la actividad. Los ejemplos típicos incluyen *Navegación* y *Autorización*. |
| Descripción | Una descripción más larga de la actividad. |
| Fecha inicial | Este campo muestra inicialmente la fecha estimada de inicio de la actividad. Sin embargo, después de ingresar la fecha de finalización real de la actividad anterior, se muestra la fecha de inicio real. Este campo se utiliza para determinar la fecha de finalización estimada, en función del plazo de entrega. |
| Fecha final estimada | El valor de este campo se calcula en función de la fecha de inicio y el plazo de entrega. Por lo general, no editará el valor directamente. |
| Fecha final real | Un usuario debe actualizar este campo lo antes posible después de que se haya producido la actividad. A continuación, se actualiza el tiempo de entrega real. |
| Días estimados | La duración estimada en días necesaria para completar la actividad. |
| Días reales | La duración real en días necesaria para completar la actividad. |
| Billete | Utilice este campo para agregar notas y detalles diversos sobre la actividad. |

## <a name="information-and-settings-on-the-general-tab"></a>Información y configuración en la pestaña General

La ficha **General** muestra información sobre el tramo seleccionado en la fihca **Visión general**. Aunque repite parte de la información que aparece en la ficha **Visión general**, también incluye información adicional sobre el tramo seleccionado.
