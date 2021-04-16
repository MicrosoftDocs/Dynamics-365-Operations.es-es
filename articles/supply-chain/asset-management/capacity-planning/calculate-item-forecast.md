---
title: Calcular previsión de artículo
description: En este tema se explica cómo calcular la previsión de artículo Administración de activos.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9392245abe5858b03b8324dcb471f5652aed7cd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813902"
---
# <a name="calculate-item-forecast"></a>Calcular previsión de artículo

[!include [banner](../../includes/banner.md)]

 

Al igual que puede crear los cálculos de la carga de capacidad, que se describe en la sección anterior, también puede crear cálculos de previsión de artículos en:

- líneas del programa de mantenimiento  
- órdenes de trabajo que aún no se han programado  
- órdenes de trabajo programadas

Esto resulta útil si desea obtener una visión general del consumo de artículos esperado (piezas de repuesto así como otros elementos requeridos para completar los pedidos de trabajo) para un período específico. El cálculo de la previsión de artículo se puede realizar en todos los activos o los activos seleccionados. También puede crear un cálculo en una actividad del tiempo de inactividad por mantenimiento (**Todas las actividades del tiempo de inactividad por mantenimiento** o **Actividades de tiempo de inactividad por mantenimiento activas**) o bien respecto a un conjunto de pedidos de trabajo (**Todos los grupos de órdenes de trabajo** o **Grupos de órdenes de trabajo activas**).

1. Haga clic en **Administración de activos** > **Consultas** > **Previsión de artículo** o **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** / **Grupos de órdenes de trabajo activas** > seleccionar el grupo de órdenes de trabajo en la lista > botón **Previsión de artículo** o **Administración de activos** > **Común**  > **Actividades de tiempo de inactividad por mantenimiento** > **Todas las actividades de tiempo de inactividad por mantenimiento** / **Actividades de tiempo de inactividad por mantenimiento activas** > seleccione actividad de tiempo e inactividad por mantenimiento en la lista > botón **Previsión de artículo**.

2. En el diálogo **Calcular la previsión de artículo**, seleccione un período para el cálculo en los campos **Fecha y hora de inicio** y los campos **Fecha y hora final**.

3. Seleccione "Sí" en el botón de alternar **Incluir programación de mantenimiento** si desea incluir líneas de mantenimiento en el cálculo de la previsión.

4. Seleccione "Sí" en el botón de alternar **Incluir orden de trabajo** si desea incluir trabajos de orden de trabajo en el cálculo de la previsión.

5. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de previsión de artículo con respecto a las ubicaciones técnicas. 

      Por ejemplo, si especifica el número "1" en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas líneas del programa de mantenimiento y órdenes de trabajo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. 
  
      Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas del programa de mantenimiento y todas las órdenes de trabajo en todos los niveles de la ubicación técnica con el que están relacionadas.

6. Haga clic en **Aceptar** para iniciar el cálculo.

7. En los grupos **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo. En la captura de pantalla siguiente, los botones **Agrupar por** seleccionados se destacan en color azul. Haga clic en un botón para activarlo o desactivarlo.

8. Haga clic en el botón **Mostrar dimensiones** si desea ver el producto, el almacenamiento o las dimensiones de seguimiento relacionadas con los artículos. Seleccione las casillas de verificación relevantes y haga clic en **Aceptar**.

![Figura 1](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]