---
title: Agregar error a orden de trabajo
description: Este tema describe cómo agregar registros de error órdenes de trabajo en Administración de activos.
author: johanhoffmann
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 30cd077402928bc33949b821b9b114fbf8a632f2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359158"
---
# <a name="add-fault-to-work-order"></a>Agregar error a orden de trabajo

[!include [banner](../../includes/banner.md)]



Puede agregar los errores que se configuraron en el diseñador de errores para una orden de trabajo. Deben conectarse uno o más registros de error a los tipos de activos que se usan para el activo que está seleccionado en la orden de trabajo. Para obtener más información sobre la configuración, consulte [Gestión de errores](../setup-for-work-orders/fault-management.md).

1. Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo para realizar un registro de errores y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Activo**, seleccione **Error de activo**.

3. En la ficha desplegable **Síntomas**, seleccione **Agregar línea**. Un número secuencial de error se introduce automáticamente en el campo **Error**.

4. En el campo **Síntoma del error**, seleccione el síntoma relevante.

5. En los campos **Área del error** y **Tipo de error**, seleccione los valores adecuados.

6. El campo **Fecha del error**, se inserta automáticamente la fecha actual. Puede seleccionar una fecha diferente cuando sea necesario.

7. En la ficha desplegable **Causas para el síntoma seleccionado**, agregue una línea para describir el motivo del problema.

8. En la ficha desplegable **Remedios para el síntoma seleccionado**, agregue una línea para describir una posible solución para el problema.

9. Seleccione **Guardar**.

En la ilustración siguiente se muestra un ejemplo de un registro de errores.

![Figura 1.](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Ver errores de activos

En la lista **Errores de activo**, puede obtener una visión general de todos los errores registrados en los activos.

En la página de lista **Errores de activo**, puede obtener una visión general de todos los errores que se han registrado en los activos. Para abrir la página, seleccione **Administración de activos** > **Consultas** > **Error de activo** > **Errores de activos**.


## <a name="print-asset-fault-report"></a>Imprimir informe de errores de activo

En la página de la lista **Todos los activos**, puede imprimir un informe de errores de activos que muestra todos los registros de error y una visión general gráfica de las estadísticas del error.

1. Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**.

2. Seleccione los activos para los que se imprimirá un informe de errores.

3. En el panel de acciones, en la pestaña **General**, en el grupo **Informes**, seleccione **Error de activo**.

4. Introduzca un período específico o seleccione un tipo de error.

5. Seleccione **Aceptar** para imprimir el informe.

>[!NOTE]
>Para imprimir un informe de error para varios activos o tipos de activo, seleccione **Administración de activos** > **Informes** > **Activos** > **Error de activo**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]