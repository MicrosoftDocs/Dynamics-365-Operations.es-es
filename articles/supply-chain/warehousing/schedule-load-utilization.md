---
title: Programar utilización de carga
description: En este tema se explica cómo configurar y programar la carga para un almacén.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac4dcba153b8da3d62261326c3c4e169325c2210
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977397"
---
# <a name="schedule-load-utilization"></a>Programar utilización de carga

[!include[banner](../includes/banner.md)]

Puede programar la utilización de carga para los tipos de ubicación seleccionados, y además proyectar la utilización de carga actual y futura. Puede proyectar la carga para uno o varios sitios, para las unidades de carga (zona o almacén), o para una combinación de una zona y un almacén.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Programación y ver la carga de un almacén o un sitio

Para programar la carga para sitios, almacenes o zonas, crea una configuración de utilización de espacio y la asocia con un plan maestro.

En la configuración de la utilización de espacio se usan tipos de ubicación, como **Ubicación de almacenaje** y **Ubicación de picking**, para especificar cómo se debe proyectar la utilización del espacio. También especifica un modo de carga de almacenamiento, como **Zona**.

La proyección de la utilización de espacio futura se basa en la información que se calcula en el plan maestro asociado. Los planes maestros prevén la planificación de recursos para pedidos entrantes y salientes para producción y operaciones. La proyección del espacio disponible se basa en la relación entre la configuración de la utilización del espacio y el plan maestro seleccionado.

Mediante el modo de carga de almacenamiento que ha seleccionado en la configuración de utilización del espacio, puede especificar si la carga se debe proyectar para cada almacén o zona, o si las proyecciones deben incluir información sobre almacenes y zonas. También especifica si las ubicaciones bloqueadas se excluyen del cálculo de la utilización de carga.

Puede proyectar la utilización del espacio generando el informe **Utilización de carga de almacén** . Cuando genera este informe, puede especificar si la utilización de carga se debe proyectar para cada sitio, entre sitios o para la unidad de carga seleccionada, como zona o almacén.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Crear una configuración de utilización de espacio para un almacén

1. Seleccione **Gestión del inventario** \> **Configuración** \> **Supervisión de almacén** \> **Uso del espacio**.
2. Seleccione **Nuevo** para crear una configuración de uso del espacio. Especificar un id. y un nombre para la nueva configuración
3. En el campo **Modo de carga de almacenamiento**, seleccione si la visión general de la utilización del espacio debe mostrar información por almacén, zona, o almacén y zona.
4. Establezca la opción **Excluir ubicaciones bloqueadas** en **Sí** para excluir las ubicaciones de inventario bloqueadas del cálculo de espacio disponible. Puede bloquear una ubicación de inventario para entrada y salida especificando la causa del bloqueo de la ubicación en el campo **Entrada bloqueada** o **Salida bloqueada** en la ficha desplegable **Otros** de la página **Ubicaciones del inventario**.
5. En la ficha desplegable **Tipo de ubicación**, seleccione los tipos de ubicación que desea incluir en el cálculo de utilización del espacio. Debe seleccionar al menos un tipo de ubicación de la proyección.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Asociar una configuración de utilización de espacio con un plan maestro

1. Seleccione **Gestión del inventario** \> **Tareas periódicas** \> **Programar utilización de carga**.
2. En el campo **Plan maestro**, seleccione un plan maestro.
3. En el campo **Número de días**, especifique el número de días que desea incluir en la proyección de las cargas de trabajo actuales y futuras.
4. En el campo **Uso del espacio**, seleccione la configuración de la utilización de espacio que desea usar para la proyección de las cargas de trabajo actuales y futuras.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>Especificar la proyección de utilización de carga y ver la información

1. Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Informes de inventario físico** \> **Utilización de carga de almacén**.
2. En el campo **Mostrar por**, seleccione el nivel de proyección de utilización del espacio:

    - **Sitio**: proyectar la utilización del espacio para cada sitio. Esta proyección resulta útil si, por ejemplo, desea ver todos los almacenes para un sitio de manera que pueda equilibrar la utilización de espacio entre los almacenes.
    - **Unidad de carga**: proyectar la utilización del espacio para zonas o almacenes. El espacio disponible se proyecta en conformidad con el valor seleccionado en el campo **Modo de carga de almacenamiento** de la página **Uso del espacio** al crear la configuración de la utilización de espacio.

3. Siga uno de estos pasos, según el valor seleccionado en el paso anterior:

    - Si seleccionó **Sitio** en el campo **Mostrar por**, el campo **Sitio** está disponible. Seleccione uno o varios sitios para incluirlos en la proyección.
    - Si seleccionó **Unidad de carga** en el campo **Mostrar por**, el campo **Unidad de carga** está disponible. Seleccione la unidad de carga.

4. En el campo **Tipo de carga**, seleccione **Volumen** o **Peso** para especificar la unidad operativa de almacén para la que desea proyectar espacio.
5. En el campo **Configuración de utilización del espacio**, seleccione la configuración de la utilización del espacio en la que se basará la proyección.
