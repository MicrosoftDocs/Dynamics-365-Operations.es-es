---
title: "Fechas límite del pedido"
description: "En este artículo se proporciona información acerca de los plazos de la entrada de pedidos. Una fecha límite de entrada de pedido es una hora límite que determina si se trata un pedido de cliente (y se completa) como si se hubiera recibido en el día actual o al día siguiente."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e9d1912abf9a356542ce2c317fa717bc991dbf9
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="order-entry-deadlines"></a>Fechas límite del pedido

[!include[banner](../includes/banner.md)]


En este artículo se proporciona información acerca de los plazos de la entrada de pedidos. Una fecha límite de entrada de pedido es una hora límite que determina si se trata un pedido de cliente (y se completa) como si se hubiera recibido en el día actual o al día siguiente.

En muchas empresas, solo los pedidos de ventas que se reciben antes de una hora determinada del día se tratan como si se recibieran ese día. Los pedidos recibidos después de esa hora se tratan como si se hubieran recibido el siguiente día laboral. Esta hora límite para los pedidos se conoce como fecha límite de entrada de pedidos.  

Las fechas límite de entrada de pedidos se usan como entrada para los compromisos de entrega. Por lo tanto, le ayudan a gestionar las expectativas del cliente sobre las entregas del pedido. Por ejemplo, los clientes pueden ver que, si realizan un pedido antes de una hora específica, usted se compromete a enviar las mercancías en el mismo día. Sin embargo, si no cumplen ese plazo, puede contar con el envío solo en el siguiente día laboral. Las fechas límite de entrada de pedidos se establecen en función de las capacidades de almacén y las programaciones del transportista del envío.  

En la página **Fechas límite del pedido**, puede configurar las horas de la fecha límite de entrada de pedidos para todos los días de la semana. Si se reciben pedidos después de la hora especificada, se tratan como si se hubieran recibido el día siguiente. De forma predeterminada, estas horas se establecen a las 23:59 (es decir, un minuto antes de la media noche del final del día pertinente). Puede cambiar las horas predeterminadas para que coincidan con las horas de la fecha límite de envío o recepción reales.  

Puede definir fechas límite de entrada de pedidos para un grupo de clientes específico. Por ejemplo, quizás desee que un grupo de clientes específico tenga fechas límite de entrada de pedidos posteriores a las de otros clientes. En este caso, defina primero los grupos para fechas límite de entrada de pedidos en la página **Grupos de fechas límite de pedido**. A continuación, asigne los grupos a clientes en la página **Clientes**.  

Si su empresa consta de varios sitios, puede configurar fechas de entrada de pedidos para cada sitio. Si los sitios se encuentran en zonas horarias diferentes, las fechas límite de entrada de pedidos se configuran en cada zona horaria del sitio. Sin embargo, al trabajar con pedidos de ventas y presupuestos de ventas, la fecha límite de entrada de pedidos se convierte a su zona horaria en la página **Fechas de envío y recepción disponibles**.  

En la página **Activar combinaciones de fechas límite de pedido**, puede definir las combinaciones de sitios y grupos de fechas límite de entrada de pedidos que se permiten.

## <a name="example-order-entry-deadline"></a>Ejemplo: fecha límite de entrada de pedido
La fecha límite de pedido de los martes se ha establecido a las 16:00. Un martes concreto, a las 17:00, intenta establecer la fecha actual como fecha de envío. (Observe que no hay plazo para este ejemplo). Si está activada la casilla **Control de fecha de entrega**, recibirá una advertencia que indica que la fecha no es válida. Esta advertencia aparece en la página **Fechas de envío y recepción disponibles**, donde puede seleccionar fechas alternativas.

## <a name="example-different-order-entry-deadlines-per-site"></a>Ejemplo: diferentes fechas límite de entrada de pedidos en cada sitio
Su empresa consta de dos sitios. Los sitios se encuentran en diferentes zonas horarias, tal y como se muestra en la siguiente tabla.

| Sitio A                      | Sitio B                      |
|-----------------------------|-----------------------------|
| California                  | Florida                     |
| PST (Hora estándar del Pacífico) | EST (Hora estándar del Este) |

Los sitios A y B han definido las siguientes fechas límite de entrada de pedidos.

| Día de la semana             | A: Fechas límite del pedido (PST) | B: Fechas límite del pedido (EST) |
|-----------------------------|--------------------------------|--------------------------------|
| Lunes                      | 13:00                          | 14:00                          |
| Martes                     | 13:00                          | 14:00                          |
| Miércoles                   | 13:00                          | 14:00                          |
| Jueves                    | 13:00                          | 14:00                          |
| Viernes                      | 13:00                          | 14:00                          |

Usted es el procesador de pedidos y se encuentra en Utah, cuya zona horaria es MST (Hora estándar de las Montañas). Por lo tanto, siempre que realice pedidos con el sitio A antes de las 14:00 MST y realice pedidos con el sitio B antes de las 12:00 MST, cumplirá las fechas límite de entrada de pedidos para ambos sitios.  

En la siguiente tabla, se muestra cómo se convierten a hora MST las fechas límite de entrada de pedidos para los sitios A y B.

| Sitio A: PST         | Sitio A: MST        | Sitio B: EST           | Sitio B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00               | 14:00              | 14:00                 | 12:00              |

**Nota**: si el ajuste de horario de verano está en vigor, las fechas límite de entrada de pedidos se ajustan como corresponda.

## <a name="example-same-order-entry-deadline-per-site"></a>Ejemplo: la misma fecha límite de entrada de pedidos en cada sitio
Su empresa consta de dos sitios. Los sitios se encuentran en diferentes zonas horarias, tal y como se muestra en la siguiente tabla.

| Sitio A                      | Sitio B                      |
|-----------------------------|-----------------------------|
| California                  | Florida                     |
| PST (Hora estándar del Pacífico) | EST (Hora estándar del Este) |

Los sitios A y B han definido las siguientes fechas límite de entrada de pedidos.

| Día de la semana | PST y EST |
|-----------------|-------------|
| Lunes          | 13:00       |
| Martes         | 13:00       |
| Miércoles       | 13:00       |
| Jueves        | 13:00       |
| Viernes          | 13:00       |

Usted es el procesador de pedidos y se encuentra en Utah, cuya zona horaria es MST (Hora estándar de las Montañas). Por lo tanto, siempre que realice pedidos con el sitio A antes de las 14:00 MST y realice pedidos con el sitio B antes de las 11:00 MST, cumplirá las fechas límite de entrada de pedidos para ambos sitios. 

En la siguiente tabla, se muestra cómo se convierten a hora MST las fechas límite de entrada de pedidos para los sitios A y B.

| Sitio A: PST         | Sitio A: MST        | Sitio B: EST           | Sitio B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00               | 14:00              | 13:00                 | 11:00              |

**Nota**: si el ajuste de horario de verano está en vigor, las fechas límite de entrada de pedidos se ajustan como corresponda.

<a name="see-also"></a>Consulte también
--------

[Programaciones de entrega](delivery-schedules.md)




