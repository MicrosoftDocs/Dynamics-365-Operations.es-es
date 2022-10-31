---
title: Mejora del rendimiento de la activación de la estructura contable
description: En este artículo se explica la nueva mejora introducida en el rendimiento del proceso de activación de la estructura contable.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2022
ms.locfileid: "9714011"
---
# <a name="account-structure-activation-performance-enhancement"></a>Mejora del rendimiento de la activación de la estructura contable

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Esta mejora de rendimiento le permite activar más rápidamente las estructuras contables al ejecutar varias actualizaciones de transacciones a la vez. Además, después de validar la estructura, esta se marca como activa y el procesamiento de las transacciones puede proseguir mientras se actualizan las transacciones no registradas en la nueva estructura. Como las actualizaciones de las transacciones pueden tardar cierto tiempo en ejecutarse, puede seguir el estado de la activación seleccionando **Ver estado de activación** encima de la cuadrícula que hay en la página **Estructuras contables**. También puede ver el estado de la activación seleccionando **Ver** en el Panel de acciones y luego seleccionando **Estado de activación** en el menú desplegable.

[![Página de estructuras contables](./media/AccountStructure1.png)](./media/AccountStructure1.png)

Después de seleccionar **Ver estado de activación**, se visualizará un cuadro de diálogo donde se muestran las tareas individuales que se ejecutan en el proceso de activación. Puede ver el estado de cada tarea y, cuando esta se haya completado, la fecha y hora de finalización.

[![Escala de tiempo de activación de la estructura contable](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Consejos de activación de la estructura contable

El cuadro de diálogo de activación de la estructura contable que aparece cuando se selecciona **Activar** para el borrador de una estructura contable contiene una sección de pestaña denominada **Actualizar transacciones sin registrar**. En esta sección, se incluye una opción denominada **Forzar actualización**. Puede seleccionarla para actualizar todas las transacciones sin registrar en la estructura actual. Sin embargo, solo debe usar esta opción cuando se haya producido un error o cuando el soporte técnico de Microsoft así se lo indique.

A continuación, indicamos algunos factores que pueden influir en el rendimiento del proceso de activación:

- Un gran número de registros de diario sin registrar.
- Una gran número de registros de documentos de código abierto, como facturas de servicios, facturas de proveedores y documentos relacionados que usan el marco de documento de origen y tienen distribuciones contables abiertas.
- La cantidad de datos de TaxUncommitted.
- La cantidad de datos de presupuesto abiertos.
- La importación de datos de diario mientras las tareas de activación se están ejecutando todavía.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
