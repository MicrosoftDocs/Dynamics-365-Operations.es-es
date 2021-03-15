---
title: Creación de órdenes de trabajo
description: En este tema se explica cómo crear órdenes de trabajo en Administración de activos.
author: johanhoffmann
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 876aef9f3f470490bb385e1861c837dcfa82db69
ms.sourcegitcommit: 1e615288db245f83c5d5e0cd45315400f8946beb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "5131802"
---
# <a name="creating-work-orders"></a>Creación de órdenes de trabajo

[!include [banner](../../includes/banner.md)]

Después de programar trabajos de mantenimiento preventivo, el paso siguiente es crear las órdenes de trabajo para los trabajos. Puede completar este paso utilizando uno de los programas de mantenimiento. Los trabajos programados en un programa de mantenimiento pueden tener distintos tipos de referencia, como se describe en la siguiente tabla.

| Tipo de referencia | Descripción |
|---|---|
| Planes de mantenimiento | Trabajos de mantenimiento preventivo basados en los tipos de programas de mantenimiento *Hora* o *Contador*. |
| Rondas de mantenimiento | Trabajos de mantenimiento preventivo que contienen varios activos que requieren un tipo de mantenimiento similar. |
| Solicitud de mantenimiento | Una solicitud creada manualmente para el mantenimiento o reparación de un activo. Esta solicitud se puede convertir en una orden de trabajo. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Crear órdenes de trabajo basadas en su programa de mantenimiento

Para crear órdenes de trabajo basadas en su programa de mantenimiento, siga estos pasos.

1. Abra una de las siguientes páginas, según cómo desee seleccionar los artículos del programa para sus órdenes de trabajo:

    - Todo el programa de mantenimiento (**Administración de activos \> Programa de administración \> Todo el programa de mantenimiento**)
    - Abra las líneas del programa de mantenimiento (**Administración de activos \> Programa de administración \> Abrir líneas del programa de mantenimiento**)
    - Abra los grupos del programa de mantenimiento (**Administración de activos \> Programa de administración \> Abrir grupos del programa de mantenimiento**)

1. En la cuadrícula, seleccione la casilla de verificación para cada trabajo de mantenimiento programado para el que desee crear una orden de trabajo. Después, en el panel Acciones, seleccione **Orden de trabajo**.

    Aparecerá el cuadro de diálogo **Crear órdenes de trabajo**. El campo **Horas de previsión de mantenimiento** muestra el número total de horas previstas para las líneas seleccionadas.

    ![Cuadro de diálogo Crear órdenes de trabajo](media/18-preventive-maintenance.png)

1. En la sección **Parámetros**, especifique el número de órdenes de trabajo que se deben crear. Seleccione una de las siguientes opciones:

    - **Una orden de trabajo por línea**: cree una orden de trabajo por línea de programación de mantenimiento.
    - **Una orden de trabajo por**: cree órdenes de trabajo que se agrupan de acuerdo con la configuración de las otras opciones que están disponibles cuando selecciona esta opción.

1. En el campo **Tipo de orden de trabajo**, seleccione el tipo de orden de trabajo que se utilizará para todas las órdenes de trabajo que cree.
1. Seleccione **Aceptar** para crear las órdenes de trabajo según su configuración.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>Líneas de orden de trabajo grupales que se crean automáticamente mientras se ejecuta un plan de mantenimiento

> [!IMPORTANT]
> La funcionalidad que se describe en esta sección está disponible como parte de una versión preliminar. El contenido y la funcionalidad están sujetos a cambios. Para obtener más información acerca las versiones preliminares, consulte [Preguntas frecuentes sobre actualizaciones del servicio de una versión](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

Esta función le permite definir reglas para agrupar líneas de órdenes de trabajo bajo una sola orden de trabajo cuando el sistema está configurado para generar órdenes de trabajo automáticamente, en base a un plan de mantenimiento. Anteriormente, las órdenes de trabajo generadas automáticamente podían contener solo una línea. Sin embargo, ahora puede agrupar las órdenes de trabajo por, por ejemplo, activo, tipo de activo o ubicación técnica. (Las órdenes de trabajo generadas manualmente ya se podían agrupar de esta manera, como se describe en la sección anterior de este tema).

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Habilitar la agrupación para órdenes de trabajo generadas automáticamente

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Administración de activos*
- **Nombre de la característica:** *(versión preliminar) aplicar reglas para agrupar órdenes de trabajo mientras ejecuta un plan de mantenimiento*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Configurar la agrupación para órdenes de trabajo generadas automáticamente

Para configurar la agrupación para órdenes de trabajo generadas automáticamente, siga los siguientes pasos.

1. Vaya a **Administración de activos \> Configuración \> Mantenimiento preventivo \> Planes de mantenimiento**.
1. Para cada plan en el que desee generar órdenes de trabajo agrupadas, siga estos pasos:

    1. Seleccione el plan en el panel de la lista.
    1. En la ficha desplegable **Líneas**, asegúrese de que la casilla **Crear automáticamente** está seleccionada en cada línea.

1. Vaya a **Administración de activos \> Periódico \> Mantenimiento preventivo \> Programar planes de mantenimiento**.
1. En el cuadro de diálogo **Programar planes de mantenimiento**, en la sección **Período**, especifique el horizonte de tiempo para el plan (lo lejos que desea anticipar a la hora de encontrar trabajos de mantenimiento programado para los que generar trabajo).
1. Establezca la opción **Crear automáticamente una orden de trabajo a partir del programa** a *Sí*.
1. En la sección **Orden de trabajo**, seleccione una de las siguientes opciones:

    - **Una orden de trabajo por línea**: cree una orden de trabajo por línea de programación de mantenimiento. (Esta opción proporciona la misma funcionalidad que está disponible cuando la característica *aplicar reglas para agrupar órdenes de trabajo mientras ejecuta un plan de mantenimiento* está desactivada).
    - **Una orden de trabajo por**: cree órdenes de trabajo que se agrupan de acuerdo con la configuración de las otras opciones que están disponibles cuando selecciona esta opción.

1. Si desea que las opciones se apliquen cuando ejecuta solo algunos de sus planes de mantenimiento, en la ficha desplegable **Registros que incluir**, agregue los filtros que necesite, tal como lo haría con otros trabajos por lotes en Microsoft Dynamics 365 Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, configure las opciones de programación y por lotes según lo requiera, tal como lo haría para otros trabajos por lotes en Supply Chain Management.
1. Seleccione **Aceptar** para ejecutar o programar los planes de mantenimiento seleccionados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]