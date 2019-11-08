---
title: Coste del programa de mantenimiento
description: En este tema se explica el coste del programa de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b30fa3c142057b43202a8f5a323c0b425865e971
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571332"
---
# <a name="maintenance-schedule-cost"></a>Coste del programa de mantenimiento

[!include [banner](../../includes/banner.md)]

 

En Administración de activos, puede calcular los costes presupuestarios en las líneas del programa de mantenimiento. Esto resulta útil si desea obtener una visión general de los costes previstos, por ejemplo, costes relacionados con trabajos de mantenimiento preventivo planificados para el año próximo. Los cálculos se basan en líneas existentes del programa de mantenimiento de tipo "Planes de mantenimiento" y "Rondas de mantenimiento" y "Solicitudes de mantenimiento".

1. Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Coste del programa de mantenimiento**.

2. En el diálogo **Coste del programa de mantenimiento**, puede seleccionar un **Conjunto de dimensiones financieras** si desea ver costes agrupados en dimensiones financieras.

>[!NOTE]
>Los conjuntos de dimensiones financieras se configuran en **Contabilidad general** > **Plan de cuentas** > **Dimensiones** > **Conjuntos de dimensiones financieras**.

3. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas del programa de mantenimiento con respecto a las ubicaciones técnicas. Por ejemplo, si especifica el número "1" en el campo y tiene una estructura de ubicación técnica de varios niveles, todas líneas del programa de mantenimiento para una ubicación técnica se mostrarán en el nivel superior. De este modo, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas del programa de mantenimiento en todos los niveles de la ubicación técnica con los que están relacionados.

4. Si desea hacer un cálculo para determinados activos, haga clic en **Filtro** en la ficha desplegable **Registros que incluir** y seleccione los activos relevantes. Si es necesario, también puede especificar una fecha **Inicial prevista** para el cálculo de coste o seleccionar un **Estado** diferente para el cálculo de costes

5. Haga clic en **Aceptar** para iniciar el cálculo de costes.

6. En la pestaña **Coste del programa de mantenimiento** > en los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo de costes. Se resaltarán los botones del grupo de paneles de acciones seleccionado. Haga clic en un botón para activarlo o desactivarlo.

7. Haga clic en el botón **Calcular coste** si desea crear un nuevo cálculo de costes.

La ilustración siguiente muestra los resultados del cálculo de costes del programa de mantenimiento.

![Figura 1](media/17-preventive-maintenance.png)

