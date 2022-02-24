---
title: Descripción general de instantáneas (Vista previa)
description: Este tema describe la característica de instantáneas, que le permite guardar un pronóstico de flujo de efectivo para analizarlo o compararlo con los datos reales más adelante. Cuando genera un pronóstico de flujo de efectivo, puede guardar ese pronóstico como una "instantánea". Luego, puede usar esas instantáneas para editar las cuentas que se incluyeron en el pronóstico o comparar el pronóstico en la instantánea con los datos reales.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f0d0bdde8b69148c72b8c645e040f0e596ecba92
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645634"
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

#### <a name="privacy-notice"></a>Aviso de privacidad
Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.
