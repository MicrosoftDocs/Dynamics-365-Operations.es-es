---
title: Seguimiento de actualización para ubicación
description: Este tema describe cómo configurar y ejecutar el seguimiento de actualizaciones para la tarea periódica de colocación.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d8e2a42d8e12a5a9cf18e876b6f9e45ecb877881
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500032"
---
# <a name="update-tracking-for-put-away"></a>Seguimiento de actualización para ubicación

[!include [banner](../includes/banner.md)]

La tarea periódica *Actualizar seguimiento de colocación* está diseñada para ejecutarse como un lote recurrente nocturno. Identifica qué viajes han recibido todas las transacciones de inventario y qué viajes no tienen un valor para la fecha de finalización real. A continuación, establece la fecha de finalización real en la fecha actual según sea necesario.

*Actividades de contenedores* se crean para cada *tramo* de un viaje para cada *contenedor de envío*. Estos valores están definidos por la plantilla de viaje que se selecciona cuando se crea un viaje. Para cada registro de actividades de contenedor, se pueden establecer valores para los campos **Fecha de inicio**, **Fecha de finalización estimada** y **Fecha de finalización real**. Estos campos se pueden actualizar cuando se recibe la confirmación de que un tramo ha comenzado o se ha completado.

Por lo general, la información relacionada con las fechas confirmadas la proporciona un tercero, como un transitario, porque estas acciones se mantienen fuera de Microsoft Dynamics 365 Supply Chain Management. Sin embargo, no se requiere información de un tercero para rastrear la llegada de mercancías desde un tramo de viaje al almacén (como lo marca la colocación de mercancías). Por lo tanto, el seguimiento se puede determinar en función de la información en Dynamics 365 Supply Chain Management.

Para configurar y ejecutar la tarea periódica *Actualizar seguimiento de colocación*, siga estos pasos:

1. Vaya a **Coste en destino\> Tareas periódicas\> Actualizar seguimiento de colocación**.
1. En el cuadro de diálogo **Actualizar seguimiento de colocación**, en la sección **Parámetros**, configure los siguientes campos:

    - **Tramo** - Seleccione el nombre/número de identificación único para la parte de un viaje para la que desea actualizar el seguimiento. El valor seleccionado debe representar la llegada del viaje al almacén.
    - **Actividad** - Seleccione la actividad que se llevó a cabo durante el tramo seleccionado. Estos valores se asignan por línea de plantilla de viaje en el centro de control de seguimiento.

1. Para limitar el conjunto de registros que deben incluirse en la actualización, en la ficha desplegable **Registros a incluir** seleccione el botón **Filtrar**. Aparece un cuadro de diálogo de consulta estándar, donde puede definir criterios de selección, criterios de clasificación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Supply Chain Management. Los campos aquí son de solo lectura y muestran valores relacionados con su consulta.
1. En la ficha desplegable **Ejecutar en segundo plano**, configure las opciones de programación y por lotes según lo requiera, tal como lo haría para otros trabajos por lotes en Supply Chain Management.
1. Seleccione **Aceptar** para aplicar su configuración y para ejecutar o programar la actualización.
