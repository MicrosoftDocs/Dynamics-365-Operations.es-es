---
title: El lanzamiento no es idónea para limpieza
description: El lanzamiento no es idónea para limpieza
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924336"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>El lanzamiento no es idónea para limpieza

Código de error: WaveNotEligibleForCleanup

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> No es posible elegir el lanzamiento %1 para limpieza.

Los datos del lanzamiento no se pueden limpiar.  

## <a name="cause"></a>Causa

El lanzamiento se está procesando actualmente, como lo indica una de las siguientes condiciones:

- El campo **Estado de lanzamiento** está establecido en *Ejecución*.
- Cuando selecciona **Trabajo por lotes** en el grupo **Lanzamiento** de la pestaña **Lanzamiento** del panel de acciones, el campo **Estado** no está configurado en *Terminado*, *Error* ni *Cancelado*. Por lo tanto, se está ejecutando un trabajo por lotes.

## <a name="resolution"></a>Resolución

En el panel de acciones, en la pestaña **Lanzamiento**, en el grupo **Lanzamiento**, seleccione **Trabajo por lotes** y luego siga uno de estos pasos:

- Si el campo **Estado** está configurado en *Ejecución*: en el panel de acciones, en la pestaña **Trabajo por lotes**, en el grupo **Trabajo por lotes**, seleccione **Ver tareas**. Puede seguir el progreso actualizando la página **Tareas por lotes**.
- Si el campo **Estado** no está configurado en *Ejecución*: en el panel de acciones, en la pestaña **Trabajo por lotes**, en el grupo **Funciones**, seleccione **Cambiar estado**. En el campo **Seleccionar nuevo estado**, seleccione *Espera*. A continuación seleccione **Aceptar**.
