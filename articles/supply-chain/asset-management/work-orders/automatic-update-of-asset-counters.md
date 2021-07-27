---
title: Actualización automática de los contadores de activos
description: Este tema describe la actualización automática de contadores de activos en la Administración de activos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d1e8a3b34cb359b7ea7f7181d2308f8e021f3c95
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359134"
---
# <a name="automatic-update-of-asset-counters"></a>Actualización automática de los contadores de activos

[!include [banner](../../includes/banner.md)]

Para obtener información acerca del registro manual de contadores de activos, consulte [Actualización manual de contadores de activos](../work-orders/manual-update-of-asset-counters.md). Para obtener más información sobre cómo configurar contadores de activos, consulte [Contadores](../setup-for-objects/counters.md).

Los valores de un contador también se pueden actualizar automáticamente a partir de los registros de producción, en función de las horas de producción o la cantidad de producción (es decir, la cantidad que se produce). Esta actualización se realiza en la página **Actualizar contadores de activos**. Puede actualizar uno o varios activos configurando un parámetro, **Desde fecha**. Este parámetro especifica la fecha de inicio para los registros de producción (horas de producción o cantidades de producción). Es decir, especifica la fecha desde la que deben actualizarse los valores del contador.

Todos los activos que están relacionados con un recurso *y* que tienen contadores de activos que están configurados para actualizarse según las horas de producción o la cantidad de producción, se incluirán en una actualización automática. Se crearán nuevos valores del contador.

Para los contadores que se basan en la cantidad de producción, el recuento incluye la cantidad sin errores y la cantidad con errores que se registran. Si la unidad que se utiliza para el registro de cantidad de producción difiere de la unidad que se utiliza para el contador, la cantidad se convierte para que se corresponda con la unidad del contador.

Como se mencionó anteriormente, los contadores automáticos se pueden actualizar a partir de los registros de producción. Por tanto, el activo para el que desea para actualizar automáticamente los contadores debe estar relacionado con un recurso (máquina). Cuando se hayan registrado las cantidades o las horas de producción en el recurso, puede actualizar los contadores de activos relacionados.

1. Seleccione **Administración de activos** > **Periódico** > **Activos** > **Actualizar contadores de activos**.

2. En el campo **Desde fecha**, seleccione la fecha de inicio de la actualización automática.

    >[!NOTE]
    >La fecha de este campo es la fecha de "trabajo en curso" **Transacciones de ruta** (campo **Control de producción** > **Consultas e informes** > **Producción** > **Transacciones e rutas** > **Fecha física**).

3. En la ficha desplegable **Registros que incluir**, puede seleccionar activos específicos, tipos de activos o recursos para la actualización automática. Seleccione **Filtrar** y haga las selecciones relevantes.

4. En la pestaña desplegable **Ejecutar en segundo plano**, puede configurar la actualización automática como un trabajo por lotes según sea necesario.

    La ilustración siguiente muestra un ejemplo del cuadro de diálogo **Actualizar contadores de activos**.

    ![Figura 1.](media/12-work-orders.png)

5. Seleccione **Aceptar**. 

Una vez realizada la actualización automática del contador de activos, puede ver los registros del contador que están relacionados con el activo en la página **Contadores de activos**. Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**, seleccione el activo y, a continuación, en el panel de acciones, en la pestaña **Activo**, en el grupo **Preventivo**, seleccione **Contadores**.

En la página **Valor agregado de activo**, puede obtener una visión general del último registro que se ha hecho en todos los tipos de contador en todos los activos. Seleccione **Administración de activos** > **Consultas** > **Activos** > **Valor agregado de activos**. Esta página es similar a la página **Contadores de activos**, pero no puede agregar o editar registros. Es solo para la visión general.

La ilustración siguiente muestra un ejemplo de la página **Valor agregado de activos**.

![Figura 2.](media/13-work-orders.png)

Tenga en cuenta los aspectos siguientes:

- Aún puede crear registros manuales de valor del contador para los tipos de contador que se actualizan. Para obtener más información, consulte [Actualización manual de contadores de activos](../work-orders/manual-update-of-asset-counters.md).

- Puede configurar los contadores que están relacionados con otro contador. En este caso, cuando se actualiza un contador, los contadores relacionados se actualizan automáticamente al mismo tiempo. Para obtener más información sobre la configuración de los contadores relacionados, consulte [Contadores](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]