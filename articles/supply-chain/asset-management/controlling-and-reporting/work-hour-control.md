---
title: Control de horas de trabajo
description: Este tema explica el control de las horas de trabajo en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: 1a59b4bbf1a4612cea1ba3bd536ba4b018fc621f
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652342"
---
# <a name="work-hour-control"></a>Control de horas de trabajo

[!include [banner](../../includes/banner.md)]

 

En Administración de activos, puede calcular las horas para obtener una visión general de las horas reales comparadas con las horas del presupuesto sobre los activos, ubicaciones técnicas y órdenes de trabajo. Las horas reales se basan en las transacciones registradas.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Control de horas de trabajo para los activos, las ubicaciones técnicas y las órdenes de trabajo

Los cálculos realizados para los activos, las ubicaciones técnicas y las órdenes de trabajo son idénticos casi. Únicamente la diferencia es que en los activos y las ubicaciones técnicas, también puede incluir subactivos y sububicaciones en el cálculo. La fecha es la fecha de la transacción en la que el registro se ha registrado.

1. Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Control de horas de activos** o **Control de horas de ubicación técnica** o **Administración de activos** > **Consultas** > **Órdenes de trabajo** > **Control de horas de órdenes de trabajo**.

2. En el cuadro de diálogo **Control de horas de activos**.

3. En el diálogo **Control de horas de activos** / **Control de horas de ubicación técnica** / **Control de horas de órdenes de trabajo**, seleccione un período que se calculará en los campos **Desde fecha** y **Hasta fecha**.

4. Si es necesario, seleccione un **conjunto de dimensiones financieras** que se incluirá en el cálculo.

5. Seleccione "Sí" en el botón de alternar **Omitir cero** si no desea mostrar los resultados que contengan el valor cero horas.

6. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de control de horas con respecto a las ubicaciones técnicas. 

    Por ejemplo, si especifica el número "1 "en el campo, y tiene una jerarquía de ubicación técnica de varios niveles, todas las líneas de control de horas de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. 
    
    Si especifica el número "0 "en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de control de horas en todo el nivel de la ubicación técnica con el que están relacionadas.

7. Seleccione "Sí" en el botón de alternar **Incluir subactivos** para mostrar costes relacionados con los activos secundaria como líneas independientes.

8. Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de ubicaciones técnicas y órdenes de trabajo en la ficha desplegable **Registros a incluir**.

9. Haga clic en **Aceptar** para iniciar el cálculo.

10. En la página **Control de horas de activos**, haga clic en los botones **Agrupar por** para mostrar el nivel de detalle necesario del cálculo. Se resaltarán los botones **Agrupar por** seleccionados. Haga clic en un botón para activarlo o desactivarlo.

## <a name="example"></a>Ejemplo

La captura de pantalla siguiente muestra un ejemplo de un cálculo de **Control de horas de activos**.

- El campo **Presupuesto original** muestra las horas del presupuesto según la previsión de órdenes de trabajo. 
- El campo **Horas reales** muestra las horas registradas en órdenes de trabajo. 
- El campo **Horas comprometidas** muestra el total de horas a las que se comprometió la empresa con respecto a las órdenes de trabajo.

![Ejemplo de cálculo de Control de horas de activos](media/04-controlling-and-reporting.png)

Otra forma de realizar un cálculo de horas es seleccionar múltiples activos en **Todos los activos** o **Activos activos**. A continuación, haga clic en el botón **Control de horas** de la ficha desplegable **General**. Los activos seleccionados se insertan automáticamente en el campo **Activo** en la ficha desplegable **Registros que incluir**. Haga clic en **Aceptar** en el diálogo **Control de horas de activos**, y el cálculo de los activos seleccionados se mostrará. El mismo procedimiento se puede realizar para las ubicaciones técnicas en **Todas las ubicaciones técnicas** o **Ubicaciones técnicas activas**, y para las órdenes de trabajo en **Todas las órdenes de trabajo** o **Órdenes de trabajo activas**.


