---
title: Calcular la carga de capacidad en órdenes de trabajo programadas
description: En este tema se explica cómo calcular la carga de capacidad en órdenes de pedido programadas en Administración de activos.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 164ae10eef8ef3692cd3a8b5232de64ec3d83b1b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354189"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Calcular la carga de capacidad en órdenes de trabajo programadas

[!include [banner](../../includes/banner.md)]

 

Puede calcular la carga de capacidad en órdenes de trabajo programadas para obtener una visión general de la carga de trabajo en los recursos durante un período específico. Los cálculos se pueden realizar para los siguientes recursos: trabajadores de mantenimiento, grupos de trabajadores, herramientas y activos.

1. Haga clic en **Administración de activos** > **Consultas** > **Programación** > **Carga de capacidad**.

2. En el cuadro de diálogo **Calcular carga de capacidad** > campo **Mostrar**, seleccione el tipo de carga desea calcular: **Capacidad**, **Reservada** o **Restante**.

3. Seleccione **Sí** en el botón de alternar **Omitir cero** si no desea mostrar los resultados que contengan el valor cero.

4. Seleccione los tipos de recurso para los que desea calcular la carga de capacidad seleccionando **Sí** en los botones de alternar relevantes: **Trabajador**, **Grupo del trabajador de mantenimiento**, **Herramienta** y **Activo**.

5. Seleccione la fecha de inicio para el cálculo en el campo **Desde fecha**.

6. En el campo **Tipo de intervalo**, seleccione el intervalo para el cálculo: **Día**, **Semana**, **Mes** o **Trimestre**.

7. En el campo **Frecuencia de períodos**, inserte el número de intervalos que desee calcular. Por ejemplo, si se ha seleccionado **Día** como el tipo de intervalo e introduzca el número "5 "en este campo, se realizará un cálculo de cinco días desde la fecha de inicio.

8. Haga clic en **Aceptar** para iniciar el cálculo.

La ilustración siguiente muestra el resultado de un cálculo que cubre tres semanas para el tipo de carga **Reservada**.

![Figura 1.](media/08-work-order-scheduling.png)

[!NOTE]
Si selecciona los tipos de carga **Capacidad** o **Restante** para el cálculo, aparecerá el mismo resultado si no se han realizado reservas para los recursos en el período seleccionado.

Para obtener información sobre cómo calcular la carga de capacidad en las líneas de la programación de mantenimiento y las órdenes de trabajo no programadas, consulte [Calcular la carga de capacidad](../capacity-planning/calculate-capacity-load.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]