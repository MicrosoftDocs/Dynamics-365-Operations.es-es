---
title: Rondas de mantenimiento
description: En este artículo se explican las rondas de mantenimiento en Administración de activos.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRoundTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 519431d84652e45dcd45aefbbaaa2a0e2afe6349
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016518"
---
# <a name="maintenance-rounds"></a>Rondas de mantenimiento

[!include [banner](../../includes/banner.md)]

 

En **Administración de activos**, puede crear rondas de mantenimiento para varios activos en los que tiene que realizar una tarea similar a intervalos periódicos. Por ejemplo, los trabajos de lubricación o de inspección de seguridad que tengan que llevarse a cabo en una serie de máquinas dentro de los mismos intervalos. El primer paso consiste en crear una ronda de mantenimiento, incluidos los activos que requieren el mismo formulario de trabajo de mantenimiento. A continuación, programe las rondas de mantenimiento. Cuando haya completado la programación de rondas de mantenimiento, puede ver todos los registros de trabajo relacionados con la ronda en **Todo el programa de mantenimiento** y en **Líneas del programa de mantenimiento abiertas**.

>[!NOTE]
>Las rondas de mantenimiento también se pueden configurar en las ubicaciones técnicas que se completarán en los activos instalados en la ubicación técnica en el momento de la creación de la orden de trabajo basada en rondas. Consulte [Crear ubicaciones técnicas](../functional-locations/create-functional-locations.md) para obtener más información sobre la configuración de rondas de mantenimiento en ubicaciones técnicas.

## <a name="set-up-a-maintenance-round"></a>Configurar una ronda de mantenimiento

1. Haga clic en **Administración de activos** > **Configuración** > **Mantenimiento preventivo** > **Rondas de mantenimiento**.

2. Haga clic en **Nueva** para crear una nueva ronda de mantenimiento.

3. Inserte un id. en el campo **Ronda de mantenimiento** y un nombre para la ronda de mantenimiento en el campo **Nombre**.

4. Seleccione una fecha de inicio para la ronda en el campo **Fecha de inicio**.

5. En los campos **Finalizar en días** y **Finalizar en horas**, puede insertar la fecha de finalización prevista en días u horas. La fecha de finalización prevista se calcula en relación con la fecha de inicio, que se calcula cuando se crean las líneas del programa de mantenimiento. Por ejemplo, puede insertar "7" en el campo **Finalizar en días** para indicar que el trabajo relacionado debe completarse en una semana desde la fecha de inicio.

6. Seleccione "Sí" en el botón de alternancia **Crear automáticamente** si deben crearse órdenes de trabajo automáticamente a partir de líneas del programa de mantenimiento que se crean desde esta ronda de mantenimiento.

7. En el campo **Tipo de orden de trabajo**, seleccione el tipo de orden de trabajo que se va a usar en las órdenes de trabajo creadas desde esta ronda de mantenimiento.

8. En el campo **Nivel de servicio**, seleccione el nivel de servicio de la orden de trabajo que se va a usar en las órdenes de trabajo creadas desde esta ronda de mantenimiento.

9. En la ficha desplegable **Líneas de activos**, haga clic en **Agregar** para agregar un activo a la ronda de mantenimiento.

10. Un número de línea se inserta automáticamente en el campo **Número de línea** para indicar la secuencia de los activos en la ronda de mantenimiento.

11. Seleccione el activo en el campo **Activo**.

12. Seleccione el tipo de trabajo de mantenimiento para el activo en el campo **Tipo de trabajo de mantenimiento**.

13. Si es necesario, seleccione la **Variante de tipo de trabajo de mantenimiento** y el **Comercio** relacionados con el tipo de trabajo de mantenimiento.

14. Seleccione la periodicidad (día, semana, etc) en el campo **Tipo de período**.

15. En el campo **Frecuencia de períodos**, inserte el número de periodicidades para la ronda de mantenimiento. Ejemplo: si ha seleccionado "Día" en el campo **Tipo de periodo** e inserta el número "7" en este campo, se crean nuevas líneas de la ronda de mantenimiento durante la programación de mantenimiento preventivo una vez a la semana.

16. Seleccione una fecha de inicio para el activo que se va a incluir en la ronda de mantenimiento en el campo **Fecha de inicio**. Esta fecha puede diferir de la fecha de inicio establecida en la ronda de mantenimiento.

17. Repita los pasos 9 a 16 para agregar más activos a la ronda de mantenimiento.

18. En la ficha desplegable **Líneas de ubicación técnica**, haga clic en **Agregar** para agregar una ubicación técnica a la ronda de mantenimiento. Consulte a continuación la descripción de los campos relacionados. Están disponibles los mismos campos que para la creación de una línea del activo, pero también puede seleccionar **Fabricante** y **Modelo** para una ubicación técnica, si es necesario. Si selecciona solo una ubicación técnica en una línea, pero no hace ninguna selección en **Tipo de activo**, **Fabricante**, **Modelo**, **Tipo de trabajo de mantenimiento**, **Variante de tipo de trabajo de mantenimiento** y **Comercio**, todos los activos relacionados con esa ubicación técnica en el momento de la programación de mantenimiento se incluirán en la ronda de mantenimiento.

19. En la ficha desplegable **Grupos**, haga clic en **Agregar** para seleccionar un grupo de órdenes de trabajo que se van a incluir en la ronda de mantenimiento. Se pueden conectar varios grupos de órdenes de trabajo a una ronda de mantenimiento.

20. Guarde su configuración.

>[!NOTE]
>Los campos **Activos** y **Líneas** que se encuentran en el grupo **Detalles** en la ficha desplegable **Encabezado** muestran el número total de activos y líneas relacionados con la ronda de mantenimiento seleccionada.

La ilustración siguiente muestra un ejemplo de una ronda de mantenimiento con tres activos.

![Figura 1.](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Programar rondas de mantenimiento

Cuando haya configurado una ronda de mantenimiento, ejecute un trabajo de programación para programar todos los trabajos relacionados con la ronda de mantenimiento.

1. Haga clic en **Administración de activos** > **Periódico** > **Mantenimiento preventivo** > **Programar rondas de mantenimiento**; o **Administración de activos** > **Programa de mantenimiento** > **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas** o **Grupos del programa de mantenimiento abiertos** > seleccione una línea del programa de mantenimiento en la lista > botón **Rondas de mantenimiento**.

2. En el campo **Período**, seleccione el tipo de período que se va a utilizar para el trabajo de programación.

3. En el campo **Frecuencia de períodos**, inserte el número de períodos que se van a incluir en el trabajo de programación. El inicio de la programación es la fecha actual.

4. Seleccione "Sí" en el botón de alternancia **Crear automáticamente** si una orden de trabajo debe crearse automáticamente en función una ronda de mantenimiento.

>[!NOTE]
>Si tanto este botón de alternancia como el de **Crear automáticamente** se establecen en "Sí" en la ronda de mantenimiento del formulario **Rondas de mantenimiento**, se crean órdenes de trabajo en función de las líneas de la ronda de mantenimiento, así como líneas del programa de mantenimiento con el estado "Orden de trabajo creada". Si se establece en "Sí" solo uno de los botones de alternancia **Crear automáticamente**, en este desplegable o en **Rondas de mantenimiento**, solo se crean las líneas del programa de mantenimiento con el estado "Creada". En ese caso, no se crean órdenes de trabajo.

5. Si es necesario, puede seleccionar rondas concretas u otra fecha de inicio para el trabajo de programación. Haga clic en **Filtrar** y agregue las rondas que se van a incluir.

6. Haga clic en **Aceptar**.

7. Ahora puede ver los trabajos de las rondas de mantenimiento en **Administración de activos** > **Programa de mantenimiento** > **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas**. Si las rondas programadas están conectadas a un grupo de órdenes de trabajo, verá las líneas del programa de mantenimiento en **Grupos del programa de mantenimiento abiertos**. Las líneas del programa de mantenimiento creada desde una ronda tienen el tipo de referencia "Rondas de mantenimiento".

Las dos siguientes ilustraciones siguientes muestran un trabajo de programación en el cuadro de diálogo **Rondas de mantenimiento de programación** y las líneas del programa de mantenimiento creadas en **Todo el programa de mantenimiento** basándose en ese trabajo de programación.

![Figura 2.](media/14-preventive-maintenance.png)

![Figura 3.](media/15-preventive-maintenance.png)

- Cuando se crean órdenes de trabajo manualmente en activos que son cubiertos por la garantía de un proveedor, se muestra un cuadro de diálogo para que el usuario reconozca la garantía. La creación de la orden de trabajo se puede cancelar. La comprobación de una relación de garantía se omite para órdenes de trabajo que se crean automáticamente.  
- Puede configurar un trabajo por lotes en la ficha desplegable **Ejecutar en segundo plano** para programar rondas a intervalos periódicos.  
- Si una ronda se incluye en varios grupos de órdenes de trabajo (consulte [Grupos de órdenes de trabajo](../work-orders/work-order-pools.md)), se muestra un registro para cada grupo en **Grupos del programa de mantenimiento abiertos**. Esto se hace para optimizar las opciones de filtrado para grupos de órdenes de trabajo.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]