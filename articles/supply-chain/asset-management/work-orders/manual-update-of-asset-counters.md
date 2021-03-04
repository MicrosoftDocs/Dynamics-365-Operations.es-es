---
title: Actualización manual de los contadores de activos
description: En este tema se describe la actualización manual de contadores de activos en la Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23a94415a662059ddbd41cc6a0ba9dab24aae44e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436671"
---
# <a name="manual-update-of-asset-counters"></a>Actualización manual de los contadores de activos

[!include [banner](../../includes/banner.md)]



Los contadores se utilizan para crear registros de un activo, como registros sobre el número de horas que el activo ha estado en funcionamiento o la cantidad que se ha producido.

Se puede definir el tipo de contador para un contador de manera que herede los valores del contador. Es decir la opción **Heredar valores de contador de activo** se establece en **Sí** en la ficha desplegable **General** de la página **Contadores** (**Administración de activos** > **Configuración** > **Tipos del activo** > **Contadores**). En este caso, al crear una línea de contador nueva de ese tipo, cada activo secundario que utiliza el mismo tipo de contador se actualiza automáticamente.

En la página **Todos los activos**, cree registros de contador de horas o cantidad en un activo, según sus lecturas en el activo.

1. Seleccione **Administración de activos** > **Común** > **Activos** > **Todos los activos**.

2. Seleccione el activo y, a continuación, en el panel de acciones, en la pestaña **Activo**, en el grupo **Preventivo**, seleccione **Contadores**. La página **Contadores de activos** muestra una lista de todos los registros de contador previos realizados en el activo seleccionado.

3. Seleccionar **Nuevo** para crear un registro. El ID de activo se inserta automáticamente en el campo **Activo**.

4. En el campo **Contador**, seleccione el contador pertinente. Solo están disponibles para la selección los contadores relacionados con el tipo de activo seleccionado en el activo. La unidad relacionada se inserta automáticamente en el campo **Unidad**.

5. En el campo **Registrado**, seleccione la fecha y hora del registro contrario.

6. En el campo **Valor**, especifique el número ya que el registro de contador. Como alternativa, en el campo **Valor agregado**, especifique el número de contadores total.

Tenga en cuenta los aspectos siguientes:

- Si instala físicamente un nuevo contador en un activo, debe registrar el cambio en el activo en la página **Contadores de activos**. A continuación, debe crear dos líneas de registro con horas de registro idénticas. La primera línea debe ser para el contador que va a sustituir. En la línea relacionada con el nuevo contador, seleccione la casilla de verificación **Reinicio del contador**. En el campo **Totales**, el número total de recuentos es la suma de contadores totales de todos los valores registrados en ese tipo de contador.

- Si se selecciona la casilla **Restablecimiento del contador** en un activo mediante un plan de mantenimiento con un tipo de intervalo "Una vez de..." o "Una vez alcanzado…", el contador sigue activo en la nueva línea del contador porque crea una línea de contador independiente y empieza de nuevo con un nuevo contador.

La ilustración siguiente muestra un ejemplo de la página de lista **Contadores de activos**.

![Figura 1](media/11-work-orders.png)

En la página **Contadores de activos** (**Administración de activos** > **Consultas** > **Activos** > **Contadores de activos**), puede crear registros de contador en varios activos simultáneamente, como sea necesario.

>[!NOTE]
>Puede configurar un intervalo para definir desviaciones en los registros de contadores manuales. También puede especificar el tipo de mensaje que se muestra si los registros están fuera del intervalo definido. Para obtener más información sobre la configuración de los contadores, consulte [Contadores](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]