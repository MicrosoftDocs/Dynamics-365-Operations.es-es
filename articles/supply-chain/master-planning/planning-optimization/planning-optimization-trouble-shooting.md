---
title: Solución de problemas de optimización de planificación
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con Optimización de planiicación.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2100235fadabe6af87849aab7d9ec55d85ea66fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812892"
---
# <a name="troubleshoot-planning-optimization"></a>Solución de problemas de optimización de planificación 

[!include [banner](../../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con Optimización de planiicación.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>La instalación del complemento Optimización de planiicación no se completa

Optimización de planificación requiere un entorno de alta disponibilidad de Lifecycle Services (LCS) habilitado, nivel 2 o superior (no un entorno OneBox), con Dynamics 365 Supply Chain Management, versión 10.0.7 o posterior. Si intenta instalar el complemento en un entorno OneBox, la instalación no se completará.

**Reparar**: cancele la instalación y use un entorno de alta disponibilidad, nivel 2 o superior (no un entorno OneBox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>La planificación de trabajos por lotes falla cuando está habilitada Optimización de planificación

Cuando se habilita Optimización de planificación, el motor de planificación maestro incorporado se desactiva automáticamente. Los trabajos por lotes de planificación maestros creados para el motor de planificación de Supply Chain Management tendrán errores si se activan mientras está habilitada Optimización de planificación. Puede recibir un mensaje de error como *Esta operación activó la planificación maestra que no es compatible cuando la Optimización de planificación está habilitada*.

**Reparar**: cancele todos los trabajos por lotes de planificación maestra que se crearon para el motor de planificación de Supply Chain Management.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>Los resultados de Optimización de planificación son diferentes de los resultados anteriores

Optimización de planificación difiere del diseño de planificación maestra incorporado en algunas áreas. Esto también pueden provocarlo funciones pendientes.

**Reparar**: ejecute el análisis de ajuste de Optimización de planificación y luego analice los resultados mientras consulta la documentación relacionada para comprender la incidencia. Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>No es posible habilitar Optimización de planificación

El **Estado de conexión** debe ser **Conectado** antes de poder establecer **Usar Optimización de planificación** en **Sí**. Para obtener más información, consulte [Empezar a utilizar la optimización de la planificación](get-started.md).

**Reparar**: asegúrese de que el complemento Optimización de planificación se haya instalado correctamente.

## <a name="error-message-is-shown-during-ctp"></a>Se muestra un mensaje de error durante CTP

Si intenta ejecutar Capaz de comprometer (CTP) desde un pedido de ventas cuando la Optimización de planificación está habilitada, recibirá el siguiente mensaje de error: *Esta operación activó la planificación maestra que no es compatible cuando Optimización de planificación está habilitada*.

Esto está relacionado con una función pendiente que está planificada como parte del soporte para pedidos de producción.

**Reparar:** Evite los cálculos de CTP cuando la Optimización de planificación esté habilitada hasta que esté disponible el soporte de CTP.

## <a name="additional-resources"></a>Recursos adicionales

[Introducción a la optimización de la planificación](get-started.md)

[Análisis de idoneidad de optimización de la planificación](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]