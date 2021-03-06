---
title: Descripción general de instantáneas (Vista previa)
description: Este tema describe la característica de instantáneas, que le permite guardar un pronóstico de flujo de efectivo para analizarlo o compararlo con los datos reales más adelante. Cuando genera un pronóstico de flujo de efectivo, puede guardar ese pronóstico como una "instantánea". Luego, puede usar esas instantáneas para editar las cuentas que se incluyeron en el pronóstico o comparar el pronóstico en la instantánea con los datos reales.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 593d6fa8efdecf1b64ef802e6861783d6f85489c
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186599"
---
# <a name="snapshots-overview-preview"></a>Descripción general de instantáneas (Vista previa)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Las instantáneas permiten a las organizaciones editar y guardar información sobre su posición de efectivo y pronósticos de efectivo en un momento determinado. Puede comparar la instantánea con las finanzas reales, examinar la desviación y usar esa información para mejorar los pronósticos de flujo de efectivo a lo largo del tiempo. Más específicamente, las instantáneas se pueden utilizar de las siguientes maneras:

- Realice un seguimiento de la posición de efectivo y las previsiones de efectivo a lo largo del tiempo.
- Filtre los datos para mostrar un subconjunto de entidades legales para las que se creó la instantánea.
- Edite la posición de efectivo y la previsión de efectivo que generó el sistema.
- Realice un análisis hipotético para considerar puntos de vista optimistas, pesimistas y más probables del flujo de efectivo.
- Compare el rendimiento financiero real con el pronóstico que se guarda en la instantánea.

Puede crear una instantánea seleccionando **Nueva instantánea** en cualquiera de las pestañas **Posición de efectivo** o **Previsión de efectivo** en el espacio de trabajo **Previsiones de flujo de efectivo**. Después de crear una instantánea, las entradas y salidas en ella se pueden editar y guardar. Todas las instantáneas guardadas están disponibles en la pestaña **Instantáneas**. Para abrir una instantánea, seleccione su nombre.

Las entradas y salidas de efectivo en instantáneas se pueden editar en cualquier momento. Cuando se edita un importe de entrada o un importe de salida, el importe actualizado se prorratea a las cuentas de liquidez que formaron el saldo original. Cuando haya terminado de editar una instantánea, seleccione **Guardar** para guardar los cambios.

Para comparar varias instantáneas, seleccione **Comparar instantáneas**. Puede comparar dos instantáneas a la vez. Seleccione las dos instantáneas a comparar y luego seleccione **Aceptar**. La página **Comparar instantánea** le mostrará una comparación de las instantáneas seleccionadas. El gráfico de la sección superior de la página muestra una comparación de las entradas de efectivo, las salidas de efectivo y los saldos bancarios en los períodos superpuestos entre las dos instantáneas. La cuadrícula de la sección inferior muestra una comparación detallada de los dos pronósticos para cada importe de liquidez. La columna **Desviación** de la cuadrícula muestra la diferencia entre los saldos de un período.

Para comparar los resultados financieros reales con un pronóstico que se guardó como instantánea, seleccione **Comparar con datos reales**. La página **Comparar instantánea** mostrará una comparación de los importes reales y el pronóstico. El gráfico de la sección superior de la página muestra una comparación de las entradas de efectivo, las salidas de efectivo y los saldos bancarios en los períodos superpuestos entre las dos instantáneas. La cuadrícula de la sección inferior muestra una comparación detallada de los saldos actuales para cada periodo y el saldo previsto para cada importe de liquidez. La columna **Desviación** de la cuadrícula muestra la diferencia entre el saldo actual de un período y el saldo previsto.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
