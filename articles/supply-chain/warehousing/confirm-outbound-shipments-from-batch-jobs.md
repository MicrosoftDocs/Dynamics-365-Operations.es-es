---
title: Confirmar envíos salientes de trabajos por lotes
description: Este tema describe cómo configurar un trabajo por lotes que confirma automáticamente los envíos de pedidos de transferencia salientes para cargas listas para enviar.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: d47b88fcc5e25fc85377b52fa9832916a4bb2217
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572394"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Confirmar envíos salientes de trabajos por lotes

[!include [banner](../includes/banner.md)]

Este tema describe cómo configurar un trabajo por lotes que confirma automáticamente los envíos de pedidos de transferencia salientes para cargas listas para enviar. El trabajo por lotes descrito aquí solo se aplica a los envíos de pedidos de transferencia, no a los pedidos de ventas.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Habilitar la característica Confirmar envíos salientes desde trabajos por lotes

Antes de poder usar esta característica, debe estar habilitada en su sistema. Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario. La característica aparece como:

- **Módulo** - *Gestión de almacén*
- **Nombre de la característica** - *Confirmar envíos salientes desde trabajos por lotes*

## <a name="process-outbound-shipments"></a>Procesar envíos salientes

Para configurar un trabajo por lotes programado para ejecutar la confirmación de envío saliente para las cargas que están listas para enviar:

1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar envíos salientes**.
1. El cuadro de diálogo **Confirmar envío** se abre. En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.
1. El cuadro de diálogo del editor de consultas se abre. En la pestaña **Intervalo**, agregue una fila con los siguientes valores:
    - **Tabla** - *Cargas*
    - **Tabla derivada** - *Cargas*
    - **Campo** - *Estado de carga*
    - **Criterios** - *Cargado*
1. Seleccione **Aceptar** para volver al cuadro de diálogo **Confirmar envío**.
1. En la ficha desplegable **Ejecutar en segundo plano**, establezca **Procesamiento por lotes** en **Sí**.
1. En la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.
1. Se abre el cuadro de diálogo **Definir recurrencia**. Establezca el programa de ejecución según sea necesario para su empresa.
1. Seleccione **Aceptar** para volver al cuadro de diálogo **Confirmar envío**.
1. Seleccione **Aceptar** en el cuadro de diálogo **Confirmar envío** para agregar el trabajo por lotes a la cola de trabajos por lotes.

Para obtener más información, vea [Descripción general del procesamiento por lotes](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]