---
title: Asignación de datos de la planificación presupuestaria
description: Este tema describe los métodos de asignación que están disponibles en Microsoft Dynamics 365 Finance y cómo se pueden usar.
author: ShylaThompson
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18afd1cd59932269086736cb5e350af84b5aa3a34de3f8084462489c18fb9347
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778347"
---
# <a name="budget-planning-data-allocation"></a>Asignación de datos de la planificación presupuestaria

[!include [banner](../includes/banner.md)]

Este tema describe los métodos de asignación que están disponibles en Microsoft Dynamics 365 Finance y cómo se pueden usar.  

Puede distribuir los datos en un plan de presupuesto de varias formas de retratar exactamente los importes proyectados.

## <a name="allocation-methods"></a>Métodos de asignación
Tres métodos de asignación (Asignar en períodos, Asignar a dimensiones y Usar reglas de asignación contable) pueden crear las líneas del plan presupuestario que se basan en las líneas del mismo plan presupuestario. Otros tres métodos (Agregado, Distribuir y Copiar del plan presupuestario) pueden crear líneas de plan presupuestario en otros planes de presupuesto. Para los seis métodos de asignación, especifica la situación de destino. El escenario de destino puede ser el mismo que el escenario de origen o puede ser diferente. Además, puede especificar si las nuevas líneas se agregan al plan presupuestario o reemplazan las líneas actuales en el plan presupuestario.

> [!NOTE] 
> Se debe usar un escenario único para la agregación que sea diferente del escenario que se usó para la distribución u otras modificaciones que se realizaron previamente en el plan principal.  

[![Método de asignación de asignar en períodos.](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Asignar en períodos**: use una clave de asignación de período para asignar las líneas del plan presupuestario desde el escenario del plan presupuestario de origen en los períodos del escenario de destino. El importe de origen se asigna a varias líneas en la situación de destino, en función del porcentaje y la fecha que se definen en la categoría de asignación de períodos.         

[![Método de asignación de asignar a dimensiones.](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Asignar a dimensiones**: las líneas del plan presupuestario se asignan de la situación de planificación presupuestaria de origen a una o varias líneas en la situación de destino, en función de los porcentajes y las dimensiones financieras que se definen en una condición de asignación del presupuesto seleccionada.           

![Gráfico de agregado.](./media/aggregatechart-300x230.png)
**Agregado**: las líneas del plan presupuestario se agregan desde el escenario del plan presupuestario de origen de los planes presupuestarios (secundarios) asociados al escenario de destino del plan presupuestario principal. Este método permite consolidar en un nivel superior los importes presupuestarios que están preparados en un nivel inferior de la organización.          

[![Gráfico de distribución.](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribuir**: las líneas del plan presupuestario se distribuyen de la situación de planificación presupuestaria de origen en el plan presupuestario principal a la situación de destino de los planes presupuestarios (secundario) asociados, en función de las dimensiones financieras de las unidades de la organización de los planes asociados. Este método permite extender los importes presupuestarios que están preparados en un nivel superior de la organización para una revisión más localizada.           

[![Reglas de asignación de libro mayor.](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Usar reglas de asignación contable**: las líneas del plan presupuestario se distribuyen del escenario de planificación presupuestaria de origen al escenario de destino, basándose en la regla de asignación contable seleccionada. 

[![Copiar del plan presupuestario.](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copiar del plan presupuestario**: como en el método de asignación de distribución, las líneas del plan presupuestario se crean en el destino, en función de las líneas de un plan presupuestario relacionado. Sin embargo, para este método, el plan presupuestario de origen no tiene que ser el principal, pero puede estar en un nivel superior de la jerarquía del plan presupuestario. Este método de asignación es útil si los importes consolidados se presupuestaron originalmente en un nivel muy superior y se debe transferir a un nivel inferior de la organización para la revisión y el ajuste detallados antes de que puedan recibir la aprobación de nivel superior.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Mediante métodos de asignación en un plan presupuestario
Para realizar asignaciones en la página del plan presupuestario, seleccione las líneas para asignar y haga clic en **Asignar presupuesto**.

[![Botón Asignar presupuesto.](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

A continuación, seleccione un método de asignación. Los campos restantes se establecen a continuación, según el método seleccionado. Estos campos incluyen el origen y destino de los datos del plan presupuestario y una opción que le permite multiplicar el origen por un factor especificado cuando se crean los importes de destino para simplificar el ajuste masivo. También puede establecer la opción **Anexar al plan**. Seleccione **No** para reemplazar las líneas existentes del plan presupuestario o seleccione **Sí** para conservar las líneas existentes del plan presupuestario y agregar nuevas líneas para los importes asignados.

## <a name="automating-allocations-during-a-workflow"></a>Automatización de asignaciones durante un flujo de trabajo
Una característica potente permite llevar a cabo asignaciones automáticamente como parte de un flujo de trabajo de planificación presupuestaria. Mientras que un plan presupuestario pasa por su flujo de trabajo, las tareas automatizadas pueden invocar una asignación en una etapa de planificación presupuestaria especificada. 

Para configurar la asignación automatizada, primero debe crear una programación de asignación en la página **Configuración de planificación presupuestaria**. La programación de la asignación define el método de asignación que se usará cuando se ejecute la asignación automática y los valores de las diferentes opciones de asignación (consulte la sección anterior para ver las descripciones). 

A continuación, cree una asignación de etapa en la página **Configuración de planificación presupuestaria**. La asignación de etapa asocia una programación de asignación al flujo de trabajo de planificación presupuestaria y fase. 

Finalmente, agregue una tarea automatizada para la asignación de la etapa de planificación presupuestaria en la etapa deseada del flujo de trabajo. En el siguiente ejemplo, dos asignaciones de etapa de planificación presupuestaria (destacadas en rojo) se han insertado en el flujo de trabajo.

[![Asignaciones de etapa de planificación presupuestaria.](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]