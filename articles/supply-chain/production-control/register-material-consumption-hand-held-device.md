---
title: Registrar el material de consumo mediante un dispositivo móvil
description: Este tema describe un flujo de trabajo que habilita el registro de consumo de materias primas en la producción mediante un dispositivo de mano.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5b9c73cf9b23eb8ad9ed872b76b92b395609e9a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "336138"
---
# <a name="register-material-consumption-using-a-mobile-device"></a>Registrar el material de consumo mediante un dispositivo móvil

[!include [banner](../includes/banner.md)]

Este tema describe un flujo de trabajo que habilita el registro de consumo de materias primas en la producción mediante un dispositivo de mano.

<a name="introduction"></a>Introducción
------------

Este flujo de trabajo es relevante si hay un requisito estricto para la trazabilidad del material. En tales casos, para mantener la trazabilidad de los materiales, la hora y la cantidad exactas se deben notificar para el consumo. Este proceso se puede ver en comparación con operaciones de autoconsumo o flujo invertido, donde hay una demora entre la hora de registro y la hora en la que tiene lugar el consumo real. Esto explica por qué una estrategia de consumo automático no se puede usar para algunos materiales con requisitos de la trazabilidad. Miremos una situación de ejemplo sencilla que explica cómo configurar un flujo de trabajo para habilitar el registro de consumo de materias primas en la producción mediante un dispositivo de mano. [![configurar un flujo de trabajo para habilitar el registro de consumo de materias primas mediante un dispositivo de mano](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Detalles del escenario

Un proceso continuo de producción (5) consume la materia prima RM-100 controlada por lotes. El material está disponible en la ubicación Bulk-001 (1), en la matrícula PL -1 con dos lotes, B1 y B2, ambos con una cantidad de 100 lbs. El trabajo de almacén (2) se libera y se procesa para RM-100, y se recoge el material de Bulk-001 a la ubicación de entrada de producción PIL-01 (3), que se define como sin control de matrículas. El operador de maquinaria pesa el material de la ubicación de entrada de producción (3) y registra el peso y el número de lote como consumido (4). Desde la ubicación de entrada de producción, se agrega una parte del material manualmente al proceso de producción a intervalos de tiempo definidos. Cuando el operador de maquinaria agrega el material, se pesa en una báscula y se registra el número de lote.

## <a name="set-up-theworkflow-to-register-consumption-using-a-handheld-device"></a>Configuración del flujo de trabajo para registrar el consumo mediante un dispositivo de mano
Cree un producto de bien terminado, FG-100, con una lista de materiales con la materia prima controlada por lotes RM-100. Agregue dos lotes, B1 y B2, de RM-100 en una cantidad de 100 a la ubicación: Bulk-001 en la matrícula: PL-1. El principio de vaciado de la línea de lista de materiales para RM-100 se establece en **Manual**. Configure la ubicación de entrada de producción como PIL-01. Puede hacerlo seleccionando esta ubicación como ubicación de entrada de producción predeterminada en el almacén 51.

1.  Cree un nuevo elemento de menú del dispositivo móvil: 

-    **Nombre de elemento de menú**: Registrar el consumo de material. 
-    **Título**: Registrar el consumo de material. 
-    **Modo**: Indirecto. 
-    **Código de actividad**: Registrar el consumo de material.

2.  Añada el elemento de menú al menú de dispositivo **Móvil de producción**.
3.  Cree un pedido de producción para el producto acabado: 

-    **Número de artículo**: FG-100 
-    **Sitio**: 5 
-    **Almacén**: 51 
-    **Cantidad**: 150

El pedido de producción es **Estimado** y **Liberado** y se crea el trabajo de almacén.

4.  Complete el trabajo mediante el flujo de trabajo para la selección de materias primas para el dispositivo de mano.

Esto traerá el material de la ubicación de almacenaje a la ubicación de entrada de producción PIL-01. Una vez que haya terminado el trabajo, el material tiene el estado **Seleccionado en la ubicación de entrada de producción**. El estado después de que se haya procesado el trabajo puede ser **Seleccionado** o **Reservado físicamente**. Esto se configura con el parámetro **Estado de emisión después de puesto el formulario Almacén**.

5.  Iniciar el pedido de producción desde el cliente o desde el dispositivo de mano mediante el elemento de menú **Iniciar producción** .

Una vez iniciado el pedido de producción, puede registrar el consumo de materiales mediante el flujo de trabajo del dispositivo de mano. Comencemos por registrar el consumo de 25 libras del lote B1.

6.  Seleccione el elemento de menú **Registrar el**  **consumo de material** en el menú del dispositivo de mano, especifique los detalles siguientes: 

-    El número de pedido de producción. 
-    La ubicación en la que el material se va a consumir, en este caso PIL-01. 
-    Número de artículo RM-100. 
-    Número de lote B1. 
-    Cantidad de 25.

7.  Seleccionar **Aceptar**.

Tenga en cuenta que el mensaje “Se creó la línea de diario” aparece en la pantalla. En el pedido de producción existe un diario abierto del tipo **Lista de selección de producción** para el número de artículo RM-100 y el número de lote B1. 

Ahora puede optar por continuar su registro, por ejemplo en el número de lote B2, y cada vez que se seleccione **Aceptar,** una nueva línea de diario se agrega al diario abierto. 

Una vez que haya terminado su registro, seleccione **Hecho** para registrar el diario y finalizar el flujo de trabajo.

### <a name="additional-comments"></a>Comentarios adicionales 

-   Si un usuario cancela el flujo de trabajo después de que se cree una línea de diario, el diario se encuentra en estado sin registrar, pero si el usuario en un momento posterior utiliza el flujo de trabajo para el mismo pedido de producción, las líneas se agregarán al diario abierto en lugar de un nuevo diario.
-   El nuevo flujo de trabajo también admite el registro de números de serie.
-   Es posible registrar sólo un número de artículo definido en la lista de materiales o en la fórmula del pedido de producción seleccionado o del pedido de lote.
-   El material puede sobreconsumirse. Por ejemplo, si se estima que el material se consumirá con la cantidad de 100 libras, después puede sobreconsumirse con una cantidad de, por ejemplo, 105 lbs.


