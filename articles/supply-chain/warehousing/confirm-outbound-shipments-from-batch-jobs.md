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
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103924"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Confirmar envíos salientes de trabajos por lotes

[!include [banner](../includes/banner.md)]

Este tema describe cómo configurar un trabajo por lotes que confirma automáticamente los envíos de pedidos de transferencia salientes para cargas listas para enviar. El trabajo por lotes descrito aquí solo se aplica a los envíos de pedidos de transferencia, no a los pedidos de ventas.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>Activar o desactivar la característica Confirmar envíos salientes desde trabajos por lotes

Para utilizar la funcionalidad descrita en este tema, debe activarse la característica *Confirmar envíos salientes desde trabajos por lotes* en su sistema. A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Confirmar envíos salientes desde trabajos por lotes* en el espacio de trabamo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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