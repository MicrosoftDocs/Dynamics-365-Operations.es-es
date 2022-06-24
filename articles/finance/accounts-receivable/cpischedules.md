---
title: Programación de índices de precios al consumidor
description: Este artículo explica cómo crear la lista de programaciones del índice de precios al consumidor (CPI) que obtiene de Internet para ayudar a determinar el cargo de escalación en la facturación de Suscripción.
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
ms.openlocfilehash: f08b79ee00baab3713d9ccc24a7595b1de7a7768
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904884"
---
# <a name="consumer-price-index-schedule"></a>Programación de índices de precios al consumidor

[!include [banner](../includes/banner.md)]

Este artículo explica cómo crear, eliminar, revisar y procesar programaciones del índice de precios al consumidor (IPC). Se puede usar una programación de IPC para determinar los precios de los bienes y servicios de consumidor que agrega como líneas de programación de facturación. La programación de CPI se puede usar con escalamiento y precios de descuento en las programaciones de facturación, o se puede procesar manualmente para actualizar los importes de facturación en las programaciones de facturación. Puede introducir programaciones de CPI manualmente o puede importarlas mediante la entidad compuesta de programación de CPI.

Para añadir una programación de CPI, siga estos pasos.

1. En la página **Programación de índice de precios al consumidor**, seleccione **Nuevo**.
2. En el campo **Programación de índice de precios al consumidor**, introduzca un nombre único.
3. En el campo **Descripción**, escriba una descripción.
4. En la pestaña **Programación de índice de precios al consumidor**, seleccione **Agregar**.
5. En el campo **Fecha del índice de precios al consumidor**, especifique la fecha en que se activa la nueva programacióna de CPI.
6. En el campo **Programación del índice de precios al consumidor**, introduzca el nombre que introdujo en el paso 2.
7. Seleccione **Guardar**.

Para eliminar una fecha de programación de CPI, siga estos pasos.

1. En la página **Programación del índice de precios al consumidor**, seleccione una o más líneas que desee eliminar y, a continuación, seleccione **Eliminar**.
2. Para eliminar toda la programación de CPI, en el panel de acciones, seleccione **Eliminar**. No puede eliminar la programación de CPI seleccionada si está asociada con cualquier programación de facturación.
3. En el panel de acciones, seleccione **Procesar** para actualizar las programaciones de facturación que utilizan la programación de CPI seleccionada. Las fechas de CPI más recientes y los importes de la programación se utilizarán para actualizar los precios de la programación de facturación.
4. En la ficha desplegable **Proceso del índice de precios al consumidor**, revise los campos **Número de programación de facturación**, **Número de artículo**, **Fecha de inicio de facturación**, **Fecha de finalización de facturación**, **Fecha de escalamiento** y **Frecuencia de escalamiento** actualizados.

Una vez que se configuran las programaciones de CPI, se pueden usar para escalar y cambiar los precios de descuento en las programaciones de facturación.

## <a name="cpi-calculation"></a>Cálculo del CPI

Para estos ejemplos, el período es desde el 1 de enero de 2020 hasta el 31 de diciembre de 2022. La tasa de CPI base (el valor del CPI cuando comienza el contrato) es 105,65. El 1 de enero de 2021, el CPI actual es 110,5. El 1 de enero de 2022, el CPI actual es 114,25. El importe inicial es de 1,000 $.

**Ejemplo 1**

En la página **Parámetros de facturación de contratos periódicos**, configure el campo **Cálculo del índice de precios al consumidor** en **Índice de precios al consumidor base**.

Para el período del 1 de enero de 2021, el importe del primer escalamiento se calcula de la siguiente manera, según el importe inicial:

1000 + (110,5 – 105,65) &divide; 105,65 &times; 1000 = 1045,91

Para el período del 1 de enero de 2022, el importe del escalamiento se calcula de la siguiente manera:

1000 + (114,25 – 105,65) &divide; 105,65 &times; 1000 = 1081,40

**Ejemplo 2**

En la página **Parámetros de facturación de contratos periódicos**, configure el campo **Cálculo del índice de precios al consumidor** en **Índice de precios al consumidor anterior**.

Para el período del 1 de enero de 2021, el importe del primer escalamiento se calcula de la siguiente manera, según el importe inicial:

1000 + (110,5 – 105,65) &divide; 105,65 &times; 1000 = 1045,91

Para el período del 1 de enero de 2022, el importe del escalamiento se calcula de la siguiente manera, según el importe de la primera escalación:

1045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1045,91 = 1081,40

> [!NOTE]
> El proceso de escalamiento siempre usa el último valor del CPI, independientemente de la fecha del índice. Por ejemplo, si la escalación es en septiembre, pero el último valor del CPI es para julio, se utiliza el índice de julio. No se realizan ajustes después de introducir el índice de septiembre.

## <a name="prorated-escalation"></a>Escalación prorrateada

Si la escalación ocurre en medio de un período de facturación, la cantidad se prorrateará. Por ejemplo, el período de facturación es del 1 de agosto de 2020 al 31 de julio de 2021. En la fecha del CPI del 1 de septiembre de 2019, el valor del CPI es 244. En la fecha del CPI del 1 de septiembre de 2020, este valor del CPI es 250. Si la tarifa anterior es 1000, se utilizan las siguientes fórmulas para calcular el importe de facturación del periodo:

* *Cambios de CPI* = (250 – 244) &divide; 244 = 2,459 %
* *Fecha actual* = 1000 &times; 2,459 % = 1024,59
* *Número de días a la tarifa actual* = 31 de julio de 2021 – 1 de septiembre de 2020 = 334
* *Tarifa anterior* = 1000
* *Número de días a la tarifa anterior* = 31 de agosto de 2020 – 1 de agosto de 2020 = 31
* *Número total de días en el período de facturación* = 31 de julio de 2021 – 1 de agosto de 2020 + 1 = 365
* *Importe de facturación para este período* = (1000 &times; 31 &divide; 365) + (1024,59 &times; 334 &divide; 365) = 1022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Escalamiento que utiliza el CPI y porcentaje

Las escalaciones se pueden hacer usando el CPI. El CPI más un 3 por ciento de escalación comienza el 1 de enero de 2020 y tiene una frecuencia anual.

- El importe que se factura desde el 1 de enero de 2019 hasta el 31 de diciembre de 2020 es de 4000.
- El período de facturación que se escalará es del 1 de enero de 2020 al 31 de diciembre de 2020.
- En la fecha del CPI del 1 de diciembre de 2018, el valor del CPI es 205,3. En la fecha del CPI del 1 de diciembre de 2019, el valor del CPI es 219,6.

Si la tarifa anterior es 4000, el importe de facturación de este periodo se cacula de esta forma:

- *Cambios de CPI* = (219,6 – 205,3) &divide; 205,3 = 6,965 %
- *Fecha actual* = (4000 &times; 6,965 %) – 4000 = 278,60
- *Cambios porcentuales* = (4000 &times; 1,03) – 4000 = 120
- *Importe de facturación* = 4000 + 278,6 + 120 = 4398,6
