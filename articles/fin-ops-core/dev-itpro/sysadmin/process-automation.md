---
title: Automatización de procesos
description: En este artículo se ofrece información sobre cómo la automatización de procesos permite una programación sencilla de los procesos que ejecutará el servidor de lotes.
author: RyanCCarlson2
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: c0015b65f1ff00cfce19139cb8aaa248512d070b
ms.sourcegitcommit: 3d2c0a39c4f987e9ac71df2f2fa6df0f64f10b2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "9114947"
---
# <a name="process-automation"></a>Automatización de procesos

[!include[banner](../includes/banner.md)]

La automatización de procesos permite una programación sencilla de los procesos que ejecutará el servidor de lotes. La vista actualizada del calendario del trabajo programado permite a los usuarios finales ver y realizar acciones sobre el trabajo programado y completado.

## <a name="administration"></a>Administración

La página de administración central para todas las automatizaciones de procesos se encuentra en el módulo de Gestión del sistema en el menú **Configuración**. En esta página se mostrarán todos los procesos automatizados (serie) que se configuran en el sistema. También le permitirá agregar nuevas automatizaciones de procesos directamente desde esta página. Después de configurar una serie, puede administrar cada serie de esta lista. Puede optar por editar la serie completa, eliminarla, ver todas las repeticiones en una vista de lista o deshabilitar la serie si desea pausar el trabajo programado durante un período de tiempo. 

Cualquier proceso que esté deshabilitado en la administración de características no se mostrará cuando la característica esté deshabilitada. Además, el motor de programación de automatización de procesos no programará ninguna instancia ni procesos en segundo plano para una característica deshabilitada. Si se vuelve a habilitar la característica, las instancias programadas o los procesos en segundo plano del pasado se ejecutarán de inmediato. El motor de programación de automatización de procesos se basa en la ejecución del trabajo por lotes del sistema **Trabajo del sistema de sondeo de automatización de procesos**. El trabajo no debe modificarse ni manipularse en ningún momento. Si este trabajo por lotes no se está ejecutando o se encuentra en un estado de error, seleccione **Inicializar automatizaciones de procesos** para restablecer el trabajo por lotes. Este restablecimiento garantiza que se inicialicen todas las automatizaciones nuevas lanzadas en una versión más reciente de la aplicación. 

## <a name="calendar-view"></a>Vista de calendario

Uno de las principales ventajas de la automatización de procesos es la capacidad de ver el trabajo programado en una vista de calendario sencilla.  Esta vista le permite ver de una vez el trabajo para una semana. Verá esta vista en el lado derecho de la página **Automatización de procesos**. Se rellenará con el trabajo programado para la serie seleccionada. 

[![Calendario de automatización de procesos.](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Cambios de repetición

Cada repetición puede modificarse sin afectar otras repeticiones definidas por la serie que las originó. Las repeticiones de trabajo programado se pueden editar desde la vista de calendario seleccionando el botón **Ver o editar** y seleccionando **Repetición**. Esta página le permite acceder a todas las configuraciones que se muestran originalmente en el asistente para la configuración de la serie y le brinda la posibilidad de realizar un cambio único para la repetición seleccionada. Una repetición de trabajo programado también se puede desactivar seleccionando el botón **Deshabilitar** de la vista de calendario.

## <a name="developer-documentation"></a>Documentación del desarrollador

El marco de automatización de procesos permite a los desarrolladores ampliar el marco de automatización de procesos. La documentación del [Marco de automatización de procesos](../process-automation/process-automation-framework.md) proporciona información sobre cómo puede crear procesos personalizados que deben ser ejecutados por el servidor por lotes programado con el asistente de automatización de procesos y que aparecen automáticamente en la vista de calendario.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
