---
title: Actualización manual de los contadores de activos
description: En este tema se describe la actualización manual de contadores de activos en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875884"
---
# <a name="manual-update-of-asset-counters"></a>Actualización manual de los contadores de activos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Los contadores se utilizan para crear registros en un activo acerca de, por ejemplo, el número de horas en funcionamiento o el número de cantidades producidas.

Si el tipo de contador seleccionado para un contador se establece para heredar valores de contador (Ficha desplegable **Administración de activos** > **Configuración** > **Tipos de activos** > **Contadores** > **General** > botón de alternancia **Heredar valores de contador de activos** establecido en "Sí"), entonces cuando cree una nueva línea de contador de ese tipo, cada activo secundario que utiliza el mismo tipo de contador se actualiza automáticamente.

En **Todos los activos**, cree registros de contador de horas o cantidad en un activo, según sus lecturas en el activo.

1. Haga clic en **Administración de activos** > **Común** > **Activos** > **Todos los activos**.

2. Seleccione el activo en la lista y haga clic en **Contadores**. En el formulario **Contadores de activos**, verá una lista de todos los registros de contador previos en el activo seleccionado.

3. Haga clic en **Nuevo** para crear un nuevo registro. El id. de activo se inserta automáticamente.

4. En el campo **Contador**, seleccione el contador pertinente. Solo están disponibles los contadores relacionados con el tipo de activo seleccionado en el activo. La unidad relacionada se inserta automáticamente en el campo **Unidad**.

5. Seleccione la fecha y la hora para el registro del contador.

6. En el campo **Valor**, inserte el número desde el último registro del contador, o en el campo **Valor agregado**, inserte el número total de contadores.

- Si instala físicamente un nuevo contador en un activo, debe registrar el cambio en el activo en **Contadores de activos**. A continuación, debe crear dos líneas de registro con horas de registro idénticas y seleccionar la casilla **Restablecimiento del contador** en la línea relativa al nuevo contador. Cuando cree las dos líneas de registro, la primera línea debe ser para el contador que va a sustituir. En el campo **Totales**, el número total de recuentos es la suma de contadores totales de todos los valores registrados en ese tipo de contador.  
- Si se selecciona la casilla **Restablecimiento del contador** en un activo mediante un plan de mantenimiento con un tipo de intervalo "Una vez de..." o "Una vez alcanzado…", el contador sigue activo en la nueva línea del contador porque crea una línea de contador independiente y empieza de nuevo con un nuevo contador.

![Figura 1](media/11-work-orders.png)


Si tiene que realizar registros de contadores en varios activos, esto se puede hacer en **Administración de activos** > **Consultas** > **Activos** > **Contadores de activos**.

>[!NOTE]
>Puede configurar un intervalo para definir desviaciones en los registros de contadores manuales, así como el tipo de mensaje que se debe mostrar si los registros están fuera del intervalo definido. Consulte el tema [Contadores](../setup-for-objects/counters.md) en los que respecta a la configuración de los contadores.
