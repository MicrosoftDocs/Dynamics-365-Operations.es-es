---
title: Parámetros de almacén para el procesamiento de oleadas
description: Este tema describe cómo configurar los parámetros del almacén para el procesamiento por oleadas. Puede usar el procesamiento para agrupar trabajo de picking para varios pedidos de trabajo en una sola oleada.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b120c24ad3289f5f46119d70c8cb7124546e41b1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019187"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Parámetros de almacén para el procesamiento de oleadas

[!include [banner](../includes/banner.md)]

Este tema describe cómo configurar los parámetros del almacén para el procesamiento por oleadas. Puede usar el procesamiento para agrupar trabajo de picking para varios pedidos de trabajo en una sola oleada.

Para utilizar el procesamiento de oleadas, especifique lo siguiente en la página **Parámetros de gestión de almacén**:

- Si puede el procesar oleadas mediante un trabajo por lotes.
- Si se recopila información en un archivo de registro cuando se procesan las oleadas.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Configurar parámetros de gestión de almacén para el procesamiento de oleadas

Para configurar los parámetros de almacén para el procesamiento de oleadas, siga estos pasos:

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Parámetros de gestión de almacenes**.

1. En la ficha desplegable **Procesamiento de oleadas**, realice la siguiente configuración:

    - **Grupo de proceso de oleada por lotes**: seleccione el grupo de lotes que se debe usar al procesar oleadas mediante trabajos por lotes. El grupo de lotes especifica el servidor en el que se ejecutan los trabajos por lotes.
    - **Procesar oleadas en lote**: elija si desea permitir que las oleadas se procesen automáticamente mediante un trabajo por lotes. Debe configurar esto en *Sí* para utilizar procesamiento paralelo. Puede configurar el trabajo por lotes en la página **Procesar oleadas**. (Consulte también la nota al final de esta lista).
    - **Crear registro de progreso de oleadas**: elija si el sistema debe generar un registro cada vez que comienza y termina la asignación de un artículo y sus dimensiones. Solo debe habilitar este registro cuando lo necesite, por ejemplo, durante la prueba inicial o para la resolución de problemas. Para obtener más información, consulte [Asignación de oleadas](wave-allocation-method.md).
    - **Crear un registro del historial de procesamiento de oleadas**: elija si desea guardar automáticamente la información sobre una oleada en un archivo de registro después de que se procese la oleada, incluso durante el procesamiento paralelo de las asignaciones pendientes. Por lo general, solo debe habilitar esto durante la resolución de problemas porque agrega una sobrecarga adicional. Para ver el registro, vaya a **Gestión de almacenes \> Oleadas salientes \> Registro de historial de procesamiento de oleadas**. Para obtener más información, consulte [Creación y procesamiento de oleadas](wave-processing.md).
    - **Crear registro de historial de creación de contenedor** - Elija si desea guardar automáticamente la información sobre la creación de contenedores para una oleada en un archivo de registro después de que se procese la oleada. Para ver el registro, vaya a **Gestión de almacenes \> Embalaje y creación de contenedores \> Historial de creación de contenedores**.
    - **Esperar al bloqueo (ms)**: especifique el tiempo, en milisegundos, que un paso de asignación esperará a un recurso del sistema bloqueado por otro paso de la asignación. Cuando se supere este tiempo, la oleada no se procesará y se mostrará un mensaje de error.

1. En la ficha desplegable **Liberar al almacén**, realice la siguiente configuración:

    - **Error en la falla del lote**: elija si desea generar un error cuando falla un trabajo por lotes de liberación al almacén. Si está habilitado, los trabajos fallidos terminarán con un estado de *Error*. Si está deshabilitado, los trabajos fallidos terminarán con un estado de *Finalizado*.

> [!NOTE]
> En la plantilla de la oleada que se usa para procesar la oleada, puede especificar parámetros que automatizan el proceso de la oleada. Si configura una programación del trabajo por lotes, debe coordinar la sincronización con la configuración de automatización en la plantilla de la oleada. Para obtener más información, consulte [Crear una plantilla de oleada](wave-templates.md).
>
> Si está usando *Administración de transporte* y *Administración avanzada de almacenes*, puede especificar si consolidar cargas al procesar una oleada. Por ejemplo, esto es útil cuando varias pequeñas cargas se pueden enviar al mismo tiempo. Para consolidar cargas cuando procesa una ola, en la pestaña **Cargas**, seleccione la casilla de verificación **Consolidar cargas durante el procesamiento de oleadas**.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Configurar la reserva parcial o completa para las oleadas de producción

Para los pedidos de ventas y las órdenes de kanban, el inventario se debe reservar antes de que el pedido se libere al almacén. Si no, los artículos o las líneas de asignación no se pueden procesar en una oleada. Sin embargo, los pedidos de producción son ligeramente más flexibles. Para los pedidos de producción, puede especificar lo siguiente:

- Permitir que los pedidos de producción se liberen al almacén aunque no todos los materiales se puedan reservar. Si selecciona esta opción, debe repetir manualmente el proceso de liberación al almacén cuando los materiales adicionales estén disponibles. Por ejemplo, esto resulta útil si tiene los materiales que necesita para iniciar una producción y puede esperar hasta que los materiales adicionales estén disponibles.
- Requerir que todos los materiales se reserven antes de poder liberar el pedido al almacén.

Para requerir la reserva completa o permitir la reserva parcial, siga estos pasos:

1. Vaya a **Control de producción** \> **Configurar** \> **Parámetros de control de producción**.
1. En la pestaña **General**, en el campo **Liberar al almacén**, seleccione la configuración predeterminada.
