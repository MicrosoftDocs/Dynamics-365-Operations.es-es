---
title: Escenarios de fecha de alineación
description: Este artículo proporciona ejemplos que muestran cómo funcionan las fechas de alineación en la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 102e3a104be5be287f914172160e95aff65d0b18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872626"
---
# <a name="alignment-date-scenarios"></a>Escenarios de fecha de alineación

Este artículo proporciona ejemplos que muestran cómo funcionan las fechas de alineación en la facturación de suscripción.

Para estos ejemplos, un detalle de facturación para una programación de facturación tiene una fecha de alineación del 31 de octubre de 2019. El primer detalle de facturación de la línea finaliza el 31 de octubre de 2019 y se prorratea en consecuencia. La línea se renueva automáticamente usando una fecha de inicio de renovación del 11 de noviembre.

> [!NOTE]
> El año es relevante porque puede hacer que la fecha de alineación sea mayor o menor a un año. Para estos ejemplos, el método de prorrateo se establece en **Mensual** en la página **Parámetros de facturación de contratos periódicos**. Si está configurado como **Diario** variarán algunos importes parciales.

## <a name="scenario-1-no-alignment"></a>Escenario 1: Sin alineación

El calendario de facturación se configura con los siguientes datos:

- **Fecha de inicio**: 1 de mayo de 2019
- **Fecha de finalización:** 31 de diciembre de 2024
- **Importe:** 1000 $

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 30/4/2020 | | | 1.00 | | 1.00 | 1.000,00 |
| 5/1/2020 | 4/30/2021 | | | 1.00 | | 1.00 | 1.000,00 |
| 5/1/2021 | 4/30/2022 | | | 1.00 | | 1.00 | 1.000,00 |
| 5/1/2022 | 4/30/2023 | | | 1.00 | | 1.00 | 1.000,00 |
| 5/1/2023 | 4/30/2024 | | | 1.00 | | 1.00 | 1.000,00 |
| 5/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>Escenario 2: alineación acortada

El calendario de facturación se configura con los siguientes datos:

- **Fecha de inicio**: 1 de mayo de 2019
- **Fecha de finalización:** 31 de diciembre de 2024
- **Importe:** 1000 $
- **Fecha de alineación:** 31 de diciembre de 2019

El importe de la primera renovación es por menos de un año.

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2021 | 12/31/2021 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2022 | 12/31/2022 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 1.000,00 |

## <a name="scenario-3-extended-alignment"></a>Escenario 3: alineación ampliada

El calendario de facturación se configura con los siguientes datos:

- **Fecha de inicio**: 1 de mayo de 2019
- **Fecha de finalización:** 31 de diciembre de 2024
- **Importe:** 1000 $
- **Fecha de alineación:** 31 de diciembre de 2020

El importe de la primera renovación es por más de un año.

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 31/12/2020 | | | 1.00 | | 1.00 | 1,666.67 |
| 1/1/2021 | 12/31/2021 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2022 | 12/31/2022 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 1.000,00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>Escenario 4: alineación con un mes de finalización diferente

El calendario de facturación se configura con los siguientes datos:

- **Fecha de inicio**: 1 de mayo de 2019
- **Fecha final:** 31 de octubre de 2024
- **Importe:** 1000 $
- **Fecha de alineación:** 31 de diciembre de 2019

> [!NOTE]
> Este escenario no es común.

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2021 | 12/31/2021 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2022 | 12/31/2022 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 1.000,00 |
| 1/1/2024 | 10/31/2024 | | | 1.00 | | 1.00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>Escenario 5: año parcial único

El calendario de facturación se configura con los siguientes datos:

- **Fecha de inicio**: 1 de mayo de 2019
- **Fecha de finalización:** 31 de diciembre de 2019
- **Importe:** 1000 $
- **Fecha de alineación**: 31 de diciembre de 2019

En este escenario, la fecha de alineación no es necesaria. Este escenario es común para renovaciones automáticas.

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 5/1/2019 | 12/31/2019 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>Escenario 6: fechas calculadas

El soporte y la renovación se configuran con los siguientes datos:

- **Fecha de inicio de anulación:** No
- **Fechas de inicio de soporte y renovación:** Principios del mes siguiente
- **Fecha de registro de la factura:** 22 de junio de 2019
- **Fecha de alineación:** 31 de diciembre de 2020

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 7/1/2019 | 7/31/2019 | | | 1.00 | | 1.00 | 297.60 |
| 8/1/2019 | 31/12/2020 | | | 1.00 | | 1.00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>Escenario 7: fechas calculadas y registro futuro

El soporte y la renovación se configuran con los siguientes datos:

- **Fecha de inicio de anulación:** No
- **Fechas de inicio de soporte y renovación:** Principios del mes siguiente
- **Fecha de registro de la factura:** 22 de junio de 2019
- **Fecha de alineación:** 31 de diciembre de 2020

Para este escenario, la fecha de alineación se cambia al 31 de diciembre de 2021.

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1.00 | | 1.00 | 0,00 |
| 8/1/2019 | 31/12/2020 | | | 1.00 | | 1.00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>Escenario 8: fechas manuales y varios años

El soporte y la renovación se configuran con los siguientes datos:

- **Fecha de inicio de anulación:** Sí
- **Fecha inicial de renovación:** 1 de julio de 2020
- **Fecha de finalización de renovación**: 31 de diciembre de 2024
- **Fecha de alineación:** 31 de diciembre de 2021

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1.00 | | 1.00 | 0,00 |
| 7/1/2020 | 12/31/2021 | | | 1.00 | | 1.00 | 375.00 |
| 1/1/2022 | 12/31/2022 | | | 1.00 | | 1.00 | 250,00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 250,00 |
| 1/1/2024 | 12/31/2024 | | | 1.00 | | 1.00 | 250,00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>Escenario 9: fechas manuales, varios años y un mes de finalización diferente

El soporte y la renovación se configuran con los siguientes datos:

- **Fecha de inicio de anulación:** Sí
- **Fecha inicial de renovación:** 1 de julio de 2020
- **Fecha de finalización de renovación**: 31 de octubre de 2024
- **Fecha de alineación:** 31 de diciembre de 2021

| Fecha de inicio de facturación | Fecha de finalización de facturación | Lectura anterior | Lectura actual | Cantidad entrada | Cantidad libre | Cantidad facturable | Precio unitario |
|---|---|---|---|---|---|---|---|
| 6/22/2019 | 6/22/2019 | | | 1.00 | | 1.00 | 0,00 |
| 7/1/2020 | 12/31/2021 | | | 1.00 | | 1.00 | 375.00 |
| 1/1/2022 | 12/31/2022 | | | 1.00 | | 1.00 | 250,00 |
| 1/1/2023 | 12/31/2023 | | | 1.00 | | 1.00 | 250,00 |
| 1/1/2024 | 10/31/2024 | | | 1.00 | | 1.00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>Escenario 10: alineación sin prorrateo

El soporte y la renovación se configuran con los siguientes datos:

- **Fecha de inicio de anulación:** No
- **Fecha de registro de la factura:** 22 de junio de 2019
- **Fecha de alineación:** 31 de diciembre de 2019

La fecha de inicio de renovación y las fechas de alineación se ajustan para que ambas fechas de inicio sean posteriores a la fecha de registro.

- **Fecha de inicio de renovación:** 1 de enero de 2020
- **Fecha de finalización de renovación**: 31 de diciembre de 2020
