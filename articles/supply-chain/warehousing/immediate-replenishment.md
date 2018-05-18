---
title: Reabastecimiento inmediato
description: "Este tema describe cómo puede usar el reabastecimiento inmediato para reabastecer el inventario cuando una directiva de la ubicación no puede asignar el inventario."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a11a26df85647aa36cd30c42f81be4ec2af4409b
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="immediate-replenishment"></a>Reabastecimiento inmediato

[!include [banner](../includes/banner.md)]

El reabastecimiento inmediato le permite reabastecer el inventario de forma inmediata cuando una línea de directiva de la ubicación no puede asignar el inventario. El reabastecimiento se basa en una única línea en la configuración de la directiva de la ubicación. Si el inventario no está disponible en la unidad de medida que se especifica por dicha línea, el reabastecimiento de esa unidad de medida aparece inmediatamente.

El reabastecimiento inmediato proporciona una alternativa al método en el que la asignación del inventario se basa en más líneas en la directiva de la ubicación y dónde la demanda se suma al final de la asignación y se reabastece en la unidad de medida especificada en la última línea en la directiva de la ubicación.

Los beneficios del uso del reabastecimiento inmediato son que el reabastecimiento se puede limitar por las unidades específicas y la cantidad se puede dirigir a ubicaciones específicas.

## <a name="business-scenario"></a>Escenario empresarial

Por ejemplo, tiene un almacén que tiene áreas de picking individuales para las unidades de medida "caja" y "unidad". Desea optimizar el proceso de picking recogiendo tantas cajas como sea posible y después recoger cualquier cantidad restante que sea inferior a una caja del área "unidad".

En este caso, puede usar el reabastecimiento inmediato. En la directiva de la ubicación, puede configurar el reabastecimiento inmediato para las cajas para usar el reabastecimiento de la demanda tan pronto como haya escasez de cajas que se pueden recoger para la cantidad de demanda. De esta manera, se optimiza el proceso de picking de modo que la distribución incluya tantas cajas como sea posible. El reabastecimiento inmediato generará el reabastecimiento de las cajas y la demanda no se transferirá para seleccionar las cantidades de la unidad de medida "unidad". Es decir, sólo las cantidades que se supone que deben de ser seleccionadas en la unidad de medida "unidad" (es decir, las cantidades inferiores a una caja) se seleccionarán del área "unidad". Si hay escasez en el área "caja", puede seleccionar tantas cajas como sea posible de la demanda total. Las cantidades restantes se seleccionarán del área "unidad".

## <a name="where-it-applies"></a>Dónde se aplica

El reabastecimiento inmediato se usa durante la ejecución de una oleada si falla la asignación de una línea de directiva de ubicación que tenga una plantilla de reabastecimiento.

## <a name="set-up-immediate-replenishment"></a>Configure el reabastecimiento inmediato

- Vaya a **Administración de almacenes** \> **Configuración** \> **Directivas de la ubicación**y, a continuación, en la pestaña **Líneas** , en la lista **Plantilla de reabastecimiento inmediato**, seleccione una plantilla de reabastecimiento para la demanda de la oleada.

Se aplica la plantilla de reabastecimiento si la línea de directiva de la ubicación no puede asignar una unidad de medida dedicada.

## <a name="troubleshooting"></a>Solución de problemas

Si el reabastecimiento inmediato está activado para una línea directiva de la ubicación, pero no se generará ningún trabajo de reabastecimiento al utilizar plantillas de reabastecimiento de demanda para dicha línea de directiva de la ubicación, dos causas principales deben ser investigadas:

- Asegúrese de que la plantilla de reabastecimiento de la demanda que se aplica esté configurada para usar plantillas correctas de la ubicación y plantillas de trabajo del tipo **reabastecimiento**.
- Asegúrese de que haya suficiente inventario disponible en las ubicaciones en las que la plantilla de reabastecimiento de la demanda busca inventario disponible para reabastecimiento.

