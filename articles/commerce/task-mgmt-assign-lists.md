---
title: Asignar listas de tareas a tiendas o empleados
description: Este tema describe cómo asignar listas de tareas a tiendas o empleados en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3d249809f15b50c59620d69a901a427dc3ecb2f0
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477593"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Asignar listas de tareas a tiendas o empleados

[!include [banner](includes/banner.md)]

Este tema describe cómo asignar listas de tareas a tiendas o empleados en Microsoft Dynamics 365 Commerce.

La gestión de tareas en Dynamics 365 Commerce le permite asignar una lista de tareas a múltiples tiendas o empleados, o a una combinación de tiendas y empleados. Por ejemplo, un gerente regional de 20 tiendas podría querer asignar la lista de tareas **Preparación de la temporada de vacaciones** a las 20 tiendas.

## <a name="start-the-task-list-assignment-process"></a>Comience el proceso de asignación de la lista de tareas

Para comenzar el proceso de asignación de una lista de tareas, siga estos pasos.

1. Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.
1. Seleccione la lista de tareas para asignar.
1. Seleccione **Iniciar proceso**.
1. En el cuadro de diálogo **Iniciar proceso**, en la pestaña **General**, en el campo **Nombre del proceso**, introduzca un nombre (por ejemplo, **Tiendas de la región este**).
1. En el campo **Fecha objetivo**, especifique una fecha.
1. Para asignar la lista de tareas a las tiendas, en la pestaña **Tiendas**, use el filtro **Jerarquía organizativa** para buscar y seleccionar las tiendas.

    Para asignar la lista de tareas a los empleados, en la pestaña **Trabajadores**, busque y seleccione a los empleados.

1. Seleccione **Aceptar** para iniciar el proceso. La lista de tareas se asigna a las tiendas o empleados seleccionados.

La siguiente ilustración muestra un ejemplo de cómo encontrar y seleccionar tiendas en el cuadro de diálogo **Iniciar proceso**.

![Encontrar y seleccionar tiendas en el cuadro de diálogo Iniciar proceso](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Asigna listas de tareas de forma periódica

El minorista a veces tiene tareas recurrentes, como "Lista de verificación de cierre del jueves" o "Lista de verificación del primer día del mes". Por lo tanto, es posible que desee asignar la lista de tareas de forma periódica.

1. Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.
1. Seleccione la lista de tareas para asignar.
1. Seleccione **Iniciar proceso**.
1. En el cuadro de diálogo **Iniciar proceso**, en la pestaña **General**, en el campo **Nombre del proceso**, introduzca un nombre.
1. Establezca la opción **Periodicidad** en **Sí**.
1. En el campo **Fecha objetivo de periodicidad compensada en días**, introduzca una cantidad de días. Por ejemplo, si introduce **4**, la fecha objetivo es la fecha de periodicidad más cuatro días.
1. En la pestaña **Ejecutar en segundo plano** seleccione **Periodicidad**.
1. En el cuadro de diálogo **Definir periodicidad**, introduzca los criterios de frecuencia y luego seleccione **Aceptar**.

La siguiente ilustración muestra un ejemplo de cómo ingresar criterios de frecuencia en el cuadro de diálogo **Definir periodicidad**.

![Introducir el criterio de frecuencia en el cuadro de diálogo Definir periodicidad](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>Seguimiento del estado de la lista de tareas

Si es un gerente regional o gerente de tienda, es posible que desee realizar un seguimiento del estado de las listas de tareas que se han asignado a varias tiendas o empleados. Luego puede hacer un seguimiento de las tiendas o los trabajadores que no completaron sus tareas asignadas a tiempo. El back office de Commerce le permite ver el estado de las listas de tareas, reasignar tareas o cambiar el estado de una tarea.

Para realizar un seguimiento del estado de la lista de tareas para todas las tareas, siga estos pasos.

1. Vaya a **Retail y Commerce \> Administración de tareas \> Administración de procesos de tareas**.
1. Seleccione la pestaña **Todas las listas de tareas** para ver el estado de todas las listas de tareas asignadas a varias tiendas.

Para realizar un seguimiento de la lista de estado de tareas de todas las tareas que tiene asignadas, siga estos pasos.

1. Vaya a **Retail y Commerce \> Administración de tareas \> Administración de procesos de tareas**.
1. Seleccione la pestaña **Mis tareas** o **Todas las tareas** para ver o actualizar el estado de las tareas que se le asignan.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la administración de tareas](task-mgmt-overview.md)

[Configurar la administración de tareas](task-mgmt-configure.md)

[Crear listas de tareas y agregar tareas](task-mgmt-create-lists.md)

[Administración de tareas en PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
