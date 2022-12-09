---
title: Programar la impresión de etiquetas de oleada durante la oleada
description: Este artículo describe cómo configurar y utilizar la funcionalidad para la impresión de etiquetas wave basada en tareas.
author: perlynne
ms.date: 12/02/2022
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e788e5a9206e46ada6490d4a0196c7ea8ca6af15
ms.sourcegitcommit: 04e42c495d018e457fb3b038cadc4fe75ecbba12
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2022
ms.locfileid: "9822372"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Programar la impresión de etiquetas de oleada durante la oleada

[!include [banner](../../includes/banner.md)]

Utilizar *Impresión de etiquetas de ondas basada en tareas* como parte de su proceso de ondulación para ayudar a mejorar la eficiencia y para que el sistema cree etiquetas de ondas y trabaje en tareas separadas.

El proceso de configuración de la impresión de etiquetas de ondas es complejo y se basa en una configuración precisa y datos maestros. No es raro que falle la generación de registros de etiquetas de ondas y, cuando lo hace, se revierte todo el procesamiento de ondas. La función *Impresión de etiquetas de ondas basada en tareas* le ayuda a evitar tener que volver a crear el trabajo y las líneas de trabajo cada vez que una etiqueta de onda se imprime incorrectamente.

Cuando usa la función *Impresión de etiquetas de ondas basada en tareas*, el sistema primero crea trabajo y líneas de trabajo. Luego crea e imprime etiquetas de ondas. Finalmente, si las etiquetas de oleada se crean correctamente, libera el trabajo y la oleada para picking.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>Active la función de impresión de etiquetas de ondas basada en tareas en la gestión de funciones

Para utilizar las funciones descritas en este artículo, deben estar activadas en su sistema. Use el espacio de trabajo [Administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), para activar las siguientes funciones en este orden:

1. *Bloqueo de trabajo en toda la organización*: esta característica es requerida para la configuración manual y automática de la creación de trabajos programados. (A partir de la versión 10.0.21 de Supply Chain Management, esta función es obligatoria, por lo que está activada de forma predeterminada y no se puede volver a desactivar).
1. *Impresión de etiquetas de ondas basada en tareas* - Esta función es necesaria para dividir la impresión de etiquetas de onda en un ámbito de transacción independiente.

## <a name="manually-enable-the-new-wave-step-method"></a>Habilite manualmente el método de paso de nueva ola

Primero debe crear el nuevo método de paso de oleada y habilitarlo para el procesamiento de tareas asincrónicas en paralelo.

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.
1. En el panel acciones, seleccione **Regenerar método**. Darse cuenta de que *waveLabelPrinting* se agrega a la lista de métodos de proceso de oleada que puede utilizar en sus plantillas de oleada de envío.
1. Seleccione el registro donde el campo **Nombre del método** está configurado en *waveLabelPrinting* y, a continuación, en el panel de acciones, seleccione **Configuración de tareas**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Almacén**: seleccione el almacén que utilizará para programar el procesamiento de creación de trabajo. (Si está utilizando datos de demostración con fines de prueba, puede seleccionar almacén *24*.)
    - **Número máximo de tareas por lotes**: especifique un número máximo de tareas por lotes. En la mayoría de los casos, el valor debe ser de *8* a *dieciséis*. Sin embargo, le recomendamos que experimente para encontrar la configuración óptima para sus escenarios.
    - **Grupo de lotes de procesamiento de oleadas**: seleccione un grupo de lotes de procesamiento de oleadas dedicado para optimizar el procesamiento de la cola de lotes.

Ahora puede actualizar una plantilla de oleada existente para que utilice el método de procesamiento *Impresión de etiquetas onduladas* de ondas. Alternativamente, puede crear una nueva plantilla de oleada que la utilice.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el panel Acciones, seleccione **Editar**.
1. En el panel de lista, seleccione la plantilla de oleada para actualizar. (Si está utilizando datos de demostración con fines de prueba, puede seleccionar el *envío predeterminado 24*).
1. En la ficha desplegable **Métodos**, en la columna **Métodos restantes**, seleccione la fila donde el campo **Nombre** está establecido en *waveLabelPrinting*.
1. Seleccione **agregar** (botón flecha derecha) para mover la fila seleccionada a al columna **Métodos seleccionados**.
1. En el campo **Código de paso de onda**, introduzca un código de paso de onda que se utilizará para conectar la plantilla de onda con una plantilla de etiqueta de onda.

## <a name="set-wave-task-processing-threshold-data"></a>Establecer datos de umbral de procesamiento de tareas de oleadas

La primera vez que se ejecuta un proceso de oleada utilizando cualquier procesamiento basado en tareas, el sistema crea datos de umbral de procesamiento de tareas de oleada predeterminados. Estos datos se utilizan para controlar si el procesamiento de oleadas se ejecutará de forma asincrónica y se basará en tareas, lo que le permite procesar y crear etiquetas de oleada en paralelo.

Los datos predeterminados utilizarán inicialmente un valor de umbral de *1* para el número mínimo de id. de trabajo (`MinimumWorkThresholdForLabelPrinting`). Por lo tanto, cuando el sistema procesa una ola que tiene más de un ID de trabajo, utilizará el procesamiento basado en tareas de las etiquetas de la ola en una transacción separada. Puede insertar o actualizar manualmente estos datos en la tabla `WHSWaveTaskProcessingThresholdParameters` en sus entornos de prueba. Para cambiar la configuración en un entorno de producción, debe contactar con el Soporte de Microsoft para solicitar la actualización.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>Cambios en la lógica de procesamiento de ondas cuando se utiliza la impresión de etiquetas de ondas basada en tareas

Si el procesamiento de etiquetas de oleadas excede el umbral de procesamiento de tareas de oleadas, se inicia el procesamiento basado en tareas. En el siguiente procesamiento de oleada que se ajuste a la plantilla de oleada, la impresión de etiquetas de oleada se ejecutará de forma independiente la transacción *ttsbegin*/*ttscommit* inmediatamente después de la creación del trabajo. Si la liberación de trabajo (desbloqueo) está configurada en la plantilla de oleada para que se ejecute automáticamente, solo se produce después de que el proceso de impresión de la etiqueta de oleada se haya completado con éxito.

Si la generación de etiquetas de oleadas falla (por ejemplo, si la conversión de la cantidad de trabajo a la cantidad de etiquetas de oleadas falla y arroja un error), solo falla la transacción apropiada. El trabajo que se creó anteriormente permanece congelado. Para corregir errores e imprimir las etiquetas de ondas, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione la oleada correspondiente en la cuadrícula.
1. En el panel de acciones, en la pestaña **Oleada**, en el grupo **Imprimir**, seleccione **Etiquetas de oleada**.
1. Siga las instrucciones en pantalla para enviar las etiquetas a imprimir.
1. En el panel de acciones, en la pestaña **Onda**, en el grupo **Onda**, seleccione **Lanzamiento** para liberar manualmente el trabajo de la oleada seleccionada.

## <a name="additional-resources"></a>Recursos adicionales

- [Impresión de etiquetas de oleadas](configure-wave-label-printing.md)
- [Programar creación de trabajo durante lanzamiento](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
