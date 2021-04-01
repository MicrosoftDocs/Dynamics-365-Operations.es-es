---
title: Actualizar presupuestos de mantenimiento
description: En este tema se explica cómo actualizar un presupuesto de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 21aba6224bba98eb9bbb423847e123616003b5d9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253479"
---
# <a name="update-maintenance-budgets"></a>Actualizar presupuestos de mantenimiento

[!include [banner](../../includes/banner.md)]

 

La página **Líneas de presupuesto de mantenimiento** muestra todas las líneas de presupuesto que se han creado para el presupuesto seleccionado en la página **Presupuestos de mantenimiento**. (Para obtener más información, consulte [Crear presupuestos de mantenimiento](create-maintenance-budget.md).) Puede volver a calcular y ajustar las líneas de presupuesto de mantenimiento hasta que se apruebe el presupuesto de mantenimiento. Una vez que haya pasado el periodo del presupuesto y se hayan registrado los costes en Administración de activos, también puede actualizar las líneas de presupuesto con los costes reales.

## <a name="recalculate-a-maintenance-budget"></a>Volver a calcular un presupuesto de mantenimiento

Puede volver a calcular un presupuesto de mantenimiento en la página **Líneas de presupuesto de mantenimiento**. Cuando vuelva a calcular un presupuesto de mantenimiento, se eliminan las líneas de presupuesto existentes y se hace un nuevo cálculo.

1. En la página **Líneas de presupuesto de mantenimiento**, seleccione **Volver a calcular**.
2. En el cuadro de diálogo **Volver a calcular el presupuesto**, realice los cambios necesarios para el nuevo cálculo y seleccione **Aceptar**.

Se crean nuevas líneas de presupuesto en función de los valores que establezca.

## <a name="adjust-budget-lines"></a>Ajustar líneas de presupuesto

En lugar de volver a calcular todo el presupuesto de mantenimiento, puede ajustar las líneas seleccionadas que están relacionadas con los costes presupuestarios.

1. En la página **Líneas de presupuesto de mantenimiento**, seleccione las líneas para actualizar el coste presupuestario.
2. Seleccione **Ajustar**.
3. Para agregar un importe a las líneas seleccionadas, seleccione la casilla **Agregar coste** e introduzca el valor en el campo **Agregar valor**.
4. Para multiplicar el coste presupuestario en las líneas de presupuesto seleccionadas por un factor, seleccione la casilla **Multiplicar coste** e introduzca el factor en el campo **Multiplicar valor**.

    Por ejemplo, si introduce **1,2** en el campo **Multiplicar valor**, aumentará el coste presupuestario en las líneas seleccionadas en un 20 por ciento. Si introduce **0,7**, reducirá el coste presupuestario en las líneas seleccionadas en un 30 por ciento.

5. Seleccione **Aceptar**.

Las líneas de presupuesto seleccionadas se actualizan en función de los valores definidos en el paso 3 o 4.

## <a name="update-actual-costs"></a>Actualizar costes reales

Una vez que hayan pasado las fechas en las líneas de presupuesto y se hayan registrado los costes reales en Administración de activos, puede actualizar los costes reales en el presupuesto de mantenimiento.

1. En la página **Líneas de presupuesto de mantenimiento**, seleccione **Actualizar coste**.
2. En el cuadro de diálogo **Calcular coste real**, seleccione **Aceptar**.

Los campos **Coste real** en las líneas de presupuesto se actualizan si se han registrado los costes reales. Se podrán generar nuevas líneas de presupuesto si se han creado nuevos tipos de activos desde que creó el presupuesto, y si esos tipos de activos se han utilizado en los activos para los que se han creado órdenes de trabajo y para los que se han registrado costes relacionados. Las nuevas líneas de presupuesto muestran solo los costes reales, ya que no se calculó ningún coste presupuestario para ellas.

> [!NOTE]
> Para obtener una visión general de los costes reales divididos en costes preventivos, correctivos y de inversión, puede hacer un cálculo para el mismo período en la página **Control de costes del activo**. 

## <a name="manually-add-budget-lines"></a>Agregar líneas de presupuesto manualmente

En la página **Líneas de presupuesto de mantenimiento**, puede agregar manualmente una nueva línea de presupuesto seleccionando **Nueva** y haciendo selecciones en la línea. A continuación se muestran algunos ejemplos de situaciones en las que este enfoque podría ser de utilidad:

- Sabe que la restauración de algunos activos se encuentra actualmente en la fase de planificación, pero los trabajos relacionados aún no se han creado en Administración de activos. Sin embargo, desea que se incluyan los costes presupuestarios para esos trabajos en el presupuesto de mantenimiento.
- Se han creado nuevos activos o tipos de activos desde que hizo el presupuesto de mantenimiento, pero los planes de mantenimiento aún no se han configurado en esos activos o tipos de activos. Sin embargo, desea que se incluyan los costes presupuestarios para esos tipos de activos en el presupuesto de mantenimiento.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]