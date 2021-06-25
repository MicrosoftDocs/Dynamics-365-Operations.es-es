---
title: Asignar tiempo a trabajos en una agrupación de trabajos
description: En la ejecución de fabricación se pueden agrupar trabajos. A continuación puede iniciar varios trabajos a la vez en la página Lista de trabajos.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86fbc81de8ba59f0782bd9af5b50bfcf45d5621a
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193054"
---
# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Asignar tiempo a trabajos en una agrupación de trabajos

[!include [banner](../includes/banner.md)]

En la ejecución de fabricación se pueden agrupar trabajos. A continuación puede iniciar varios trabajos a la vez en la página Lista de trabajos.

Si agrupa trabajos, debe definir cómo se asigna para cada trabajo el tiempo registrado total de todos los trabajos. Puede definir la asignación seleccionando una de las siguientes opciones en el campo **Agrupación de trabajos** de la página **Claves de asignación**:

-   **Estimación**: el tiempo se divide entre los trabajos en función del tiempo estimado para ellos.
-   **Trabajos**: el tiempo se divide en función de los trabajos agrupados y del tiempo empleado en finalizar los trabajos.
-   **Tiempo neto**: el tiempo se divide equitativamente entre los trabajos que se encuentran en el grupo en cualquier momento.
-   **Tiempo real**: se asigna el tiempo real del trabajo. El coste se puede calcular en función del coste real de nóminas. **Nota**: la clave de asignación de **Tiempo real** está disponible solo si su empresa usa la funcionalidad de nóminas en tiempo y asistencia.

Los ejemplos siguientes muestran los resultados de las distintas claves de asignación.

## <a name="example-scenario"></a>Supuesto de ejemplo
Se deben completar tres trabajos de la cola de trabajo. Inicia el primer trabajo y, a continuación, mientras este está en curso, empieza el segundo y el tercero. Por lo tanto, hay una agrupación de tres trabajos. La siguiente tabla muestra el tiempo estimada de producción para cada trabajo.

| Trabajo   | Tiempo de producción |
|-------|-----------------|
| Trabajo 1 | 1 hora          |
| Trabajo 2 | 3 horas         |
| Trabajo 3 | 4 horas         |
| Total | 8 horas         |

En la tabla siguiente se muestra las horas de trabajo reales que se emplean en cada trabajo.

| Trabajo    | Fecha inicial | Hora final | Hora de la agrupación |
|--------|------------|----------|-------------|
| Trabajo 1  | 09:00      | 11:00    | 2 horas     |
| Trabajo 2  | 10:00      | 13:00    | 3 horas     |
| Trabajo 3  | 10:00      | 15:00    | 5 horas     |
| Agrupación | 09:00      | 15:00    | 6 horas     |

Las siguientes secciones describen los resultados del tiempo calculado para cada clave de asignación.

## <a name="estimation-allocation-key"></a>Clave de asignación de estimación
La siguiente tabla muestra la fórmula para calcular el tiempo asignado. Esta es la fórmula: Tiempo por trabajo = Tiempo de agrupación total x (Tiempo de trabajo estimado ÷ Tiempo total estimado)

| Trabajo   | Fórmula           | Tiempo asignado |
|-------|-------------------|----------------|
| Trabajo 1 | 6 × (1 ÷ 8) horas | 0,75 horas      |
| Trabajo 2 | 6 × (3 ÷ 8) horas | 2,25 horas     |
| Trabajo 3 | 6 × (4 ÷ 8) horas | 3 horas     |

## <a name="jobs-allocation-key"></a>Clave de asignación de trabajos
La siguiente tabla muestra la fórmula para calcular el tiempo asignado. Esta es la fórmula: Tiempo por trabajo = Tiempo de agrupación total ÷ Número de trabajos

| Trabajo   | Fórmula | Tiempo asignado |
|-------|---------|----------------|
| Trabajo 1 | 6 ÷ 3   | 2 horas        |
| Trabajo 2 | 6 ÷ 3   | 2 horas        |
| Trabajo 3 | 6 ÷ 3   | 2 horas        |

## <a name="net-time-allocation-key"></a>Clave de asignación del tiempo neto
La siguiente tabla muestra la fórmula para calcular el tiempo asignado. Esta es la fórmula: Tiempo calculado para notificación = Tiempo de agrupación ÷ Número de trabajos

| Ejemplo                       | 09:00–10:00 (1 hora) | 10:00–11:00 (1 hora) | 11:00–13:00 (2 horas) | 13:00–15:00 (2 horas) | Tiempo asignado |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| Número de trabajos en la agrupación | 1                    | 3                    | 2                     | 1                     | No aplicable |
| Trabajo 1                        | 1 ÷ 1 = 1 hora       | 1 ÷ 3 = 0,33 horas    | No aplicable        | No aplicable        | 1,33 horas     |
| Trabajo 2                        | No aplicable       | 1 ÷ 3 = 0,33 horas    | 2 ÷ 2 = 1 hora        | No aplicable        | 1,33 horas     |
| Trabajo 3                        | No aplicable       | 1 ÷ 3 = 0,33 horas    | 2 ÷ 2 = 1 hora        | 2 ÷ 1 = 2 horas       | 3,33 horas     |

## <a name="real-time-allocation-key"></a>Clave de asignación de tiempo real
Si desea calcular los costes de producción según los costes reales, debe desactivar la opción **Categoría de coste** en la página **Valores predeterminados de pedido de producción**. La siguiente tabla muestra la fórmula para calcular el tiempo asignado. Esta es la fórmula: Tiempo real por trabajo = Tiempo real en agrupación

| Trabajo   | Hora real |
|-------|-------------|
| Trabajo 1 | 2 horas     |
| Trabajo 2 | 3 horas     |
| Trabajo 3 | 5 horas     |

Imaginemos los tres trabajos realizados por un trabajador con un salario por horas de 12 dólares USD. No se obtiene ninguna bonificación por horas extra en el tiempo empleado en los trabajos. El trabajador ha trabajado en estos tres trabajos agrupados durante un total de seis horas. Por lo tanto, el coste del salario será 6 x 12,00 USD = 72,00 USD. Al usar la asignación en tiempo real, el coste por hora se vuelve a calcular mediante el factor de la fórmula de tiempo neto. El tiempo real empleado en cada trabajo se transfiere a continuación junto con el precio de coste corregido por hora. En el ejemplo, se emplean seis horas, aunque se han asignado diez. La siguiente tabla muestra la fórmula para calcular el coste. Esta es la fórmula: Coste por hora = (Tiempo total de agrupación por trabajo (tiempo neto) ÷ Tiempo real por trabajo) x Precio de coste estándar por hora

| Trabajo   | Cálculo del coste corregido por hora | Coste corregido por hora | Tiempo asignado | Coste total del trabajo |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| Trabajo 1 | (1,33 ÷ 2) × 12,00 USD                 | 8,00 USD                | 2 horas        | 16,00 USD         |
| Trabajo 2 | (1,33 ÷ 3) × 12,00 USD                 | 5,33 USD                | 3 horas        | 16,00 USD         |
| Trabajo 3 | (3,33 ÷ 5) × 12,00 USD                 | 8,00 USD                | 5 horas        | 40,00 USD         |

El coste corregido por hora y el tiempo de trabajo se registran en un diario de producción. **Nota:** si selecciona la opción **Categoría de coste** en la ficha **General** de la página **Valores predeterminados de pedido de producción**, la hora real para cada trabajo se transfiere a un diario de producción, donde el coste se aplica a la categoría de coste del trabajo específico.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]