---
title: Modificar manualmente una previsión de demanda
description: Este tema describe cómo modificar la previsión de un artículo
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889033"
---
# <a name="modify-a-demand-forecast-manually"></a>Modificar manualmente una previsión de demanda

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo modificar la previsión de un artículo. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento se va a utilizar para el planificador de producción.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modificación de la previsión para un artículo seleccionado

Para modificar la previsión para un artículo seleccionado:

1. Vaya a **Módulos \> Gestión de información de productos \> Productos \> Productos despachados**.
1. En la lista, busque y seleccione el registro deseado. Seleccione el artículo para el que desee modificar la previsión.
1. En el panel de acciones, abra la pestaña **Plan** y seleccione **Previsión de demanda**.
1. En la lista, seleccione una fila. Si no hay líneas de previsión, cree una nueva seleccionando **Nuevo** en el panel de acciones.  
1. En el campo **Cantidad de ventas**, introduzca un número positivo. Este número representa la cantidad prevista para el artículo. Se mostrará un error si ingresa un número negativo.
1. Rellene los demás campos según sea necesario.
1. Seleccione **Guardar** en el panel Acciones.

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a>Modificar la previsión de uno o más elementos en Microsoft Excel

Para modificar la previsión de uno o más elementos en Microsoft Excel:

1. Realice una de las acciones siguientes:
    - Abra la página **Previsión de demanda** para cualquier elemento (no importa cuál) como se describe en la sección anterior.
    - Vaya a **Planificación maestra \> Previsión \> Previsión de demanda \> Previsión de la demanda ajustada**.
1. En el panel de acciones, seleccione **Abrir en Microsoft Office \> Entradas de previsión de demanda**.
1. Seleccione una ubicación de descarga, guarde y luego abra el archivo descargado en Excel.
1. Si ve una advertencia, elija **Permitir la edición**.
1. En Excel, inicie sesión en Supply Chain Management utilizando el panel de tareas de Microsoft Dynamics. Debes iniciar sesión con la opción **Mantenme conectado** habilitada y debe confiar en la aplicación de conexión de datos.
1. La hoja de cálculo de Excel ahora muestra todas las líneas de pronóstico de demanda actuales para su empresa.  Puede agregar, eliminar y editar líneas de previsión de demanda según sea necesario.
1. Seleccione **Publicar** en el panel de tareas de Microsoft Dynamics para volver a cargar los cambios en Supply Chain Management.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
