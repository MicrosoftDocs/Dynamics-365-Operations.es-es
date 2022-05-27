---
title: Habilitar el cálculo de impuestos retrasado en diarios
description: Este tema explica cómo activar la función de Cálculo de impuestos retrasados para ayudar a mejorar el rendimiento del cálculo de impuestos cuando el número de las líneas de diario es muy grande.
author: EricWang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: fddb6d3a9850b8f2f88f813f9591006637c7e535
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713145"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Habilitar el cálculo de impuestos retrasado en diarios
[!include [banner](../includes/banner.md)]


Este tema explica cómo puede retrasar el cálculo de impuestos en los diarios. Esta capacidad ayuda a mejorar el rendimiento de los cálculos de impuestos cuando existen muchas líneas de diario.

De forma predeterminada, los importes de impuestos en las líneas de diario se calculan siempre que se actualicen los campos relacionados con impuestos. Estos campos incluyen los campos para los grupos de impuestos y los grupos de impuestos de artículos. Cualquier actualización a una línea de diario hace que las cantidades de impuestos se recalculen para todas las líneas de diario. Aunque este comportamiento ayude al usuario a tener en cuenta los importes de impuestos calculados en tiempo real, también puede afectar al rendimiento si el número de líneas de diario es muy grande.

La característica retrasa del cálculo de impuestos le permite retrasar el cálculo del impuesto sobre los diarios y por tanto ayuda a corregir problemas de rendimiento. Cuando esta función está activada, las cantidades de impuestos sólo se calcularán cuando el usuario seleccione **Impuestos** o registre el diario.

Se puede retrasar el cálculo de impuestos en tres niveles:

- Entidad jurídica
- Nombre del diario
- Cabecera de diario

El sistema da prioridad al valor de la cabecera de diario. De forma predeterminada, este valor se toma del nombre del diario. De forma predeterminada, el valor del nombre del diario se toma del valor de la página **Parámetros de contabilidad general** cuando se crea el nombre del diario. En las secciones siguientes se explica cómo activar el cálculo en retraso de impuestos para las entidades jurídicas, los nombres de diario y las cabeceras de diario.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>Active el cálculo retrasado de impuestos en el nivel de entidad jurídica

1. Vaya a **Contabilidad general \> Configuración de contabilidad \> Parámetros de Contabilidad general**.
2. En la pestaña **Impuestos**, en la ficha desplegable **General**, establezca la opción **Cálculo de impuestos retrasado** en **Sí**.

![Imagen de los parámetros de contabilidad general.](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>Active el cálculo retrasado de impuestos en el nivel de nombre de diario

1. Vaya a **Contabilidad general \> Configuración de diario \> Nombres de diarios**.
2. En la ficha desplegable **General**, en la sección **Impuestos**, establezca la opción **Cálculo de impuestos retrasado** en **Sí**.

![Imagen de los nombres de diario.](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>Active el cálculo retrasado de impuestos en el nivel de encabezado de diario

1. Vaya a **Contabilidad general \> Movimientos de diario \> Diarios generales**.
2. Seleccione **Nuevo**.
3. Seleccione un nombre de diario.
4. En la pestaña **Configuración** , establezca la opción **Cálculo Retrasado de impuestos** en **Sí**.

![Imagen general de la página del diario.](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
