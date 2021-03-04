---
title: Distribuir orden de trabajo
description: En este tema se explica cómo distribuir órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d46beb04923d06aa8ccec05355731aa1b3f27c5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436677"
---
# <a name="dispatch-work-order"></a>Distribuir orden de trabajo

[!include [banner](../../includes/banner.md)]

 

Puede programar una orden de trabajo o varias para un trabajador mediante la funcionalidad **Distribuir** .

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo en la lista.

3. En la ficha **General**, haga clic en **Distribuir**.

4. En el cuadro de diálogo **Programar orden de trabajo**, seleccione el trabajador en el campo **Trabajador**.

5. En el campo **Horas de la programación**, puede insertar las horas de trabajo esperadas en el caso de que las horas de trabajo esperadas difieran de las horas previstas.

6. En el campo **Inicio programado**, puede editar la fecha y hora de inicio, si procede.

7. Si el proceso de programación debe respetar las limitaciones de capacidad respecto a los recursos ya programados en otros trabajos, asegúrese de que los botones de alternar **Activo**, **Herramienta** y **Trabajador** están configurados en **Sí**. Si desea ver información detallada sobre los procesos de programación, seleccione **Sí** en el botón de alternar **Detallado**. Esto significa que la información detallada sobre las puntuaciones calculadas en la orden de trabajo se mostrará en el registro de información.

8. Seleccione **Sí** en el botón de alternar **Omitir programación** para omitir días cerrados en el calendario (se aplica a activo, trabajador y herramientas). Seleccione **Sí** en el botón de alternar **Ignorar ejecución programada** para ignorar las limitaciones que puedan haberse seleccionado en la orden de trabajo en conexión con la programación. 

    Para obtener información acerca de la configuración de la ejecución programada, consulte la sección [Ejecución programada](../setup-for-work-orders/scheduled-execution.md).

9. Haga clic en **Aceptar**. El estado de ciclo de vida de la orden de trabajo se actualiza automáticamente según el estado de ciclo de vida **Programado** especificado en **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Modelos del ciclo de vida**.

La ilustración siguiente muestra un ejemplo de las selecciones de distribución en el cuadro de diálogo **Programar orden de trabajo**.

![Figura 1](media/04-work-order-scheduling.png)

[!NOTE]
Si desea eliminar la programación en una orden de trabajo, seleccione la orden de trabajo en **Todas las órdenes de trabajo** y haga clic en **Eliminar programación** en la pestaña **General**. Recuerde actualizar manualmente el estado de ciclo de vida de la orden de trabajo si elimina la programación.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]