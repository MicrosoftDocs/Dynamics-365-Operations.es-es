---
title: Crear presupuestos de mantenimiento
description: En este artículo se explica cómo crear un presupuesto de mantenimiento en Administración de activos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1fa5e4c76621634930206c1d89fd8e8f4f541fd5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858051"
---
# <a name="create-maintenance-budgets"></a>Crear presupuestos de mantenimiento

[!include [banner](../../includes/banner.md)]

 



Los presupuestos de mantenimiento que se usan para proporcionar una visión general de los costes previstos para el mantenimiento preventivo. Las líneas de presupuesto se calculan basándose en las líneas de la programación de mantenimiento con una fecha de inicio prevista durante el período presupuestario.

Los presupuestos de mantenimiento se basan en los tipos de coste que se usan en Administración de activos: **Preventivo**, **Correctivo** e **Inversión**. Los costes presupuestarios para el mantenimiento de la inversión se incluyen para los activos que estén activos y que tengan una fecha de sustitución durante el período presupuestario y un valor de sustitución relacionado. Los costes presupuestarios para el mantenimiento correctivo se incluyen si se incluye una fecha correctiva pasada en el cálculo del presupuesto. En ese caso, los costes correctivos de un período anterior se calculan para el mismo período futuro para el que se calcula el presupuesto de mantenimiento.

## <a name="create-a-maintenance-budget"></a>Crear un presupuesto de mantenimiento

1. Seleccione **Administración de activos** \> **Consultas** \> **Presupuesto de mantenimiento** \> **Presupuesto**.
2. Seleccione **Crear presupuesto**.
3. En el campo **Presupuesto de mantenimiento**, especifique un Id. de presupuesto.
4. En el campo **Descripción**, escriba una descripción.
4. En la ficha desplegable **Período**, en los campos **Fecha inicial** y **Fecha final**, especifique las fechas de inicio y fin del período presupuestario.
5. Para incluir los costes de presupuesto correctivo que se calculan a partir de los costes reales de un período anterior, en el campo **Correctivo desde fecha**, especifique la fecha inicial del período desde el cual se deben incluir esos costes.
6. En función del nivel de detalle necesario en el presupuesto, establezca las opciones relevantes en las cinco pestañas desplegables **Agrupar por**.
7. Seleccione **Aceptar**.
8. Seleccione **Líneas de presupuesto** para abrir la página **Líneas de presupuesto de mantenimiento**, donde podrá ver todas las líneas de presupuesto que se han creado para el período.
9. Para aprobar el presupuesto, selecciónelo en la página **Presupuestos de mantenimiento** y, a continuación, seleccione **Aprobar**. A continuación, en el cuadro **Aprobar el presupuesto**, seleccione **Aceptar**. Su nombre se especifica en el campo **Aprobado por** en la página **Presupuestos de mantenimiento**.

    > [!NOTE]
    > Una vez que haya aprobado un presupuesto de mantenimiento, no puede volver a calcular o ajustar las líneas relacionadas en la página **Líneas de presupuesto de mantenimiento**, a menos que primero quite la aprobación. Para quitar la aprobación de un presupuesto de mantenimiento, selecciónelo en la página **Presupuestos de mantenimiento** y, a continuación, seleccione **Aprobar**. A continuación, en el cuadro **Aprobar el presupuesto**, seleccione **Aceptar**.

![Presupuestos de mantenimiento.](media/01-maintenance-budgets.png)

También puede crear un nuevo presupuesto de mantenimiento copiando un presupuesto existente. En la página **Presupuestos de mantenimiento**, seleccione el presupuesto que quiere copiar y, a continuación, seleccione **Copiar**. Este es enfoque es práctico si, por ejemplo, ha creado un presupuesto para un mes y desea copiarlo a otros meses.

> [!NOTE]
> El presupuesto de mantenimiento calcula solo los costes del presupuesto según las líneas de la programación de mantenimiento. Para calcular los costes reales para el mismo período, puede realizar dicho cálculo en la página **Control de costes de activos**. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]