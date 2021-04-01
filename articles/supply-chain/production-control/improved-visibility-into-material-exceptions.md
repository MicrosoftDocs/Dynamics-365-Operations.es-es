---
title: Visibilidad sobre excepciones de material
description: Este tema describe cómo puede obtener una mejor visibilidad en las excepciones para las materias primas para los pedidos de producción y los pedidos por lote.
author: johanhoffmann
manager: tfehr
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, WHSProdWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 87f82733388501f2f902e7ebba8b547d9ae5ed16
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246174"
---
# <a name="visibility-into-material-exceptions"></a>Visibilidad sobre excepciones de material

[!include [banner](../includes/banner.md)]

En el espacio de trabajo **Gestión de planta de producción**, tres mosaicos proporcionan una mejor visibilidad en las excepciones para las materias primas para los pedidos de producción y los pedidos por lote:

- Líneas de material sin liberar que requieren atención
- Oleadas sin procesar que requieren atención
- Abrir trabajo de almacén que requiere atención

Para los tres mosaicos, la fecha de materias primas de las líneas de la lista de materiales (LM) y las líneas de fórmula se compara con la fecha del espacio de trabajo y también con los filtros para **Unidad de producción**, **Grupo de recursos** y **Recurso**, que se establecen en el menú **Configurar el espacio de trabajo**. De forma predeterminada, la fecha del espacio de trabajo está establecida en la fecha actual, pero se puede ajustar.

Una línea inédita de LM o una línea de fórmula requiere atención si la fecha de las materias primas de la línea es igual o anterior a la fecha del área de trabajo y si cumple con los criterios definidos por los filtros en el área de trabajo.

En la siguiente ilustración, la barra azul representa un trabajo de producción que está programado en un recurso. El trabajo está programado para iniciarse el 1 de mayo de 2017 (01/05/2017). Esta fecha es la fecha de materia prima. Es decir el material que se asigna al trabajo en la lista de materiales y las líneas de fórmula deben estar listos en esta fecha. La otra fecha en la ilustración, el 6 de mayo de 2017 (06/05/2017), representa la fecha del espacio de trabajo. En este ejemplo, la fecha de la materia prima es anterior a la fecha del área de trabajo. Por lo tanto, la fecha en la que el consumo de materias primas debería iniciar ha pasado, y la LM y las líneas de fórmula cumplen los criterios para requerir asistencia.

![Ejemplo de un trabajo de producción en el que la fecha de la materia prima es anterior a la fecha del área de trabajo](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Líneas de material sin liberar que requieren atención

Una LM o una línea de fórmula se puede liberar al almacén de estas tres maneras:

- Como parte de un pedido de producción o una liberación pedido de lote
- Como una liberación manual
- Automáticamente con un trabajo por lotes

Para obtener más información, consulte [Liberar LM y líneas de fórmula al almacén](releasing-bom-and-formula-lines-to-warehouse.md). 

Si una lista de materiales o una línea de fórmula no se ha liberado o se ha liberado sólo parcialmente, y si la fecha y los criterios de filtro del espacio de trabajo se cumplen, la línea se incluye en el cálculo del número que aparece en el mosaico **Líneas inéditas de materiales que necesiten asistencia**.

Al seleccionar el mosaico, se abre la página **Liberar a almacenar**. Esta página muestra el número de LM inédito y líneas de fórmula que se indica con el número del mosaico. Las líneas inéditas aparecen en la cuadrícula superior. Esta cuadrícula muestra la cantidad que estaba originalmente estimada para la línea, la cantidad que se ha liberado y la cantidad restante que se debe liberar. Puede agregar líneas de la cuadrícula superior a la cuadrícula inferior. Desde la cuadrícula inferior, puede liberar las líneas seleccionadas al almacén. Desde la cuadrícula inferior, también puede ajustar la cantidad para liberar para solo liberar una cantidad parcial.

## <a name="unprocessed-waves-needing-attention"></a>Oleadas sin procesar que requieren atención

Cuando se libere una LM o una línea de fórmula, se agrega a una nueva oleada de la producción o a una oleada abierta existente, en función de la configuración de la plantilla de la oleada de la producción. Mediante la configuración de la plantilla de la oleada también puede configurar una oleada para procesarla automáticamente cuando se libera una LM o una línea de fórmula. Cuando se procesa la oleada, el trabajo del almacén para el picking de materia prima se genera. Si la plantilla de la oleada se configura para que las oleadas no estén procesadas en el momento de liberación, la oleada se queda en un estado sin procesar. El mosaico **Oleadas sin procesar que necesiten asistencia** muestra el número de LM y las líneas de fórmula que se han liberado al almacén en oleadas sin procesar y que tienen una fecha de la materia prima que es anterior o igual a la fecha del espacio de trabajo. Las líneas también se deben consumir por un recurso de operaciones que aplique al filtro del espacio de trabajo.

Cuando se selecciona el mosaico, se abre la página **Todas las oleadas de la producción**. Esta página se filtra en función del número de oleadas abiertas que contengan las líneas de la oleada de la LM liberada y las líneas de fórmula que cumplan los criterios para el mosaico. En la página **Todas las oleadas de la producción**, puede procesar manualmente la oleada.

## <a name="open-warehouse-work-needing-attention"></a>Abrir trabajo de almacén que requiere atención

El mosaico **Trabajo de almacén abierto que necesiten asistencia** muestra el número de LM y las líneas de fórmula que se han liberado al almacén, que tienen oleadas sin procesar y que tienen una fecha de la materia prima que es anterior o igual a la fecha del espacio de trabajo. Las líneas también se deben consumir por un recurso de operaciones que aplique al filtro del espacio de trabajo.

Cuando se selecciona el mosaico, se abre la página **Todos los trabajos**. Esta página se filtra en función del número de encabezados de trabajo abiertos que contengan las líneas de la LM liberada y las líneas de fórmula que cumplan los criterios para el mosaico. En la página **Todos los trabajos**, puede procesar manualmente el trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]