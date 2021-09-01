---
title: Estrategias de reabastecimiento
description: Este tema proporciona información sobre las estrategias de reabastecimiento y explica cómo puede utilizar el campo Estrategia de reabastecimiento en las líneas de la plantilla de reabastecimiento de demanda de oleada para seleccionar cómo se realiza el reabastecimiento.
author: mirzaab
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: d6baffd6ea6107c7f8f81a553f518e4298406899a1cbf35f5d6cdb74063bd1f9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734052"
---
# <a name="replenishment-strategies"></a>Estrategias de reabastecimiento

[!include [banner](../includes/banner.md)]

Las plantillas que se definen en la página **Plantillas de reabastecimiento** incluyen líneas de plantilla de reabastecimiento de demanda de oleada que le permiten seleccionar cómo se realiza el reabastecimiento. Cada línea ahora incluye un campo **Estrategia de reposición**.

La estrategia *Cantidad de demanda de olas* es la estrategia predeterminada. Es la estrategia de reabastecimiento que se utilizó antes de la introducción del campo **Estrategia de reposición**. Utiliza las directivas de ubicación de reabastecimiento para encontrar ubicaciones que se pueden reabastecer. Luego, reabastece esas ubicaciones hasta que se cubre la demanda.

La estrategia *Capacidad máxima de ubicación* introduce algunas funciones nuevas. Como *Cantidad de demanda de olas*, esta estrategia utiliza las directivas de ubicación de reabastecimiento para encontrar ubicaciones que se pueden reabastecer y luego reabastece esas ubicaciones hasta que se cubre la demanda. Se diferencia de la estrategia *Cantidad de demanda de olas* en que todas las ubicaciones reabastecidas se reabastecen a su capacidad máxima, según lo definido por los límites de almacenamiento de la ubicación. La estrategia *Capacidad máxima de ubicación* intenta crear trabajo para traer la cantidad solicitada, más alguna cantidad extra, para llenar las ubicaciones que se están reponiendo. Sin embargo, en algunos casos, ese intento puede fallar. Por ejemplo, es posible que las ubicaciones a granel no tengan suficiente inventario para cubrir la cantidad adicional. En estos casos, el sistema detecta la falla e intenta recuperarse.

La temporada alta es un ejemplo de una situación en la que la estrategia *Capacidad máxima de ubicación* es preferible a la estrategia *Cantidad de demanda de olas*. Durante la temporada alta, algunos artículos pueden venderse a un gran volumen. Por lo tanto, es posible que desee reabastecer de manera proactiva las ubicaciones de picking relevantes tanto como sea posible, para reducir la cantidad de ID de trabajo que se crean para reabastecimiento.

> [!IMPORTANT]
> Para aprovechar al máximo la estrategia *Capacidad máxima de ubicación*, debe redefinir los límites de existencias para las ubicaciones relevantes. De lo contrario, esta estrategia funciona igual que la estrategia *Cantidad de demanda de olas*.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>Active la función Reposición al máximo según la función de límites de existencias

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado esta función y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de caracetrística:** *Reposición al máximo según la función de límites de existencias*

## <a name="set-up-replenishment-strategies"></a>Configurar estrategias de reabastecimiento

Para acceder a las plantillas, vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento**. En la sección **Visión de conjunto**, seleccione o cree una plantilla de reabastecimiento de demanda de oleada donde el campo **Tipo de reposición** esté configurado en *Demanda de olas*. Luego configure las líneas de la plantilla de reabastecimiento en la sección **Detalles de la plantilla de reabastecimiento**. Para cada línea, en el campo **Estrategia de reposición**, seleccione la estrategia de reabastecimiento que desea utilizar.

![Página Plantillas de reabastecimiento.](media/ReplenTempWaveDmdMaxLocCap.png "Página Plantillas de reabastecimiento")

Si la columna **Estrategia de reposición** no aparece en la cuadrícula en la sección **Detalles de la plantilla de reabastecimiento**, asegúrese de que la función esté activada y de que la plantilla de reabastecimiento seleccionada tenga un tipo de reabastecimiento de *Demanda de olas*.

> [!NOTE]
> La estrategia *Cantidad de demanda de olas* es la estrategia predeterminada. Por lo tanto, solo tiene que actualizar las líneas de la plantilla de reabastecimiento donde desea usar la estrategia *Capacidad máxima de ubicación* en su lugar.

## <a name="example-scenarios"></a>Escenarios de ejemplo

### <a name="example-1"></a>Ejemplo 1

Para este ejemplo, solo hay una plantilla de reabastecimiento que tiene solo una línea de plantilla de reabastecimiento.

Cree un pedido de cliente para 130 piezas (pcs) del artículo A0001. Antes de enviar el pedido al almacén, el almacén se configura de la siguiente manera:

- Solo hay una ubicación a granel y tiene 500 unidades de inventario disponible.
- Hay tres ubicaciones de selección, cada una de las cuales tiene un límite de existencias de 100 unidades. (Recuerde que se requieren límites de almacenamiento para la estrategia *Capacidad máxima de ubicación*).
- Las ubicaciones de colocación de reabastecimiento son las mismas que las ubicaciones de selección de ventas.
- La unidad de reposición es una caja (1 caja = 20 piezas).

En el momento del pedido, el siguiente inventario está disponible en las ubicaciones de selección de ventas:

- **Pick-001:** 20 piezas (1 caja)
- **Pick-002:** 0 piezas
- **Pick-003:** 0 piezas

Inicialmente, la estrategia de reabastecimiento se establece en *Cantidad de demanda de olas*.

Una vez que libera el pedido de cliente al almacén y se ejecuta el procesamiento de oleadas para la oleada, obtiene el siguiente trabajo de reabastecimiento:

- **Trabajo de reposición 1:** Elija 4 cajas de la ubicación a granel y colóquelas en la ubicación pick-001.
- **Trabajo de reposición 2:** Elija 2 cajas de la ubicación a granel y colóquelas en la ubicación pick-002.

Obtiene dos ID de trabajo de reabastecimiento porque debe reabastecer dos ubicaciones, y no se admiten las ubicaciones múltiples.

Si establece la estrategia de reabastecimiento en *Capacidad máxima de ubicación* en su lugar, obtiene el siguiente trabajo de reposición:

- **Trabajo de reposición 1:** Elija 4 cajas de la ubicación a granel y colóquelas en la ubicación pick-001.
- **Trabajo de reposición 2:** Elija 5 cajas de la ubicación a granel y colóquelas en la ubicación pick-002.

[![Ejemplo 1.](media/ReplenTemp_example_1.png "Ejemplo 1")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>Ejemplo 2

Este ejemplo muestra lo que sucede cuando la ubicación a granel no tiene suficiente inventario para cubrir la cantidad adicional. Utiliza el mismo escenario que el ejemplo 1, pero la ubicación a granel tiene 160 unidades (8 cajas).

La estrategia *Cantidad de demanda de olas* crea el mismo trabajo que hizo en el ejemplo 1.

Sin embargo, debido a que la estrategia *Capacidad máxima de ubicación* intenta crear los ID de trabajo como lo hizo en el ejemplo 1, podría fallar. En ese momento, el sistema intenta recuperarse.

Dependiendo del ajuste de la opción **Permitir dividir** en las directivas de ubicación para el picking de reabastecimiento, son posibles dos resultados:

- Si la opción **Permitir dividir** está configurada en *Sí*, se crea el siguiente trabajo de reposición:

    - **Trabajo de reposición 1:** Elija 4 cajas de la ubicación a granel y colóquelas en la ubicación pick-001.
    - **Trabajo de reposición 2:** Elija 4 cajas de la ubicación a granel y colóquelas en la ubicación pick-002.

- Si la opción **Permitir dividir** está configurada en *No*, se crea el siguiente trabajo de reposición:

    - **Trabajo de reposición 1:** Elija 4 cajas de la ubicación a granel y colóquelas en la ubicación pick-001.
    - **Trabajo de reposición 2:** Elija 2 cajas de la ubicación a granel y colóquelas en la ubicación pick-002.

Los resultados difieren debido a la información que está disponible cuando crea el trabajo. Cuando **Permitir dividir** se establece en *Sí* en las directivas de ubicación para el picking de reabastecimiento, sabe que logró encontrar 160 unidades. Por lo tanto, puede crear trabajo para esa cantidad. Sin embargo, cuando la opción **Permitir dividir** está configurada en *No*, no conoces la existencia de las 160 uds. Debido a que la cantidad extra que decidió reponer era de 3 cajas, suelte esa cantidad extra y vuelva a intentar la cantidad original.

[![Ejemplo 2.](media/ReplenTemp_example_2.png "Ejemplo 2")](media/ReplenTemp_example_2_large.png)

Por lo tanto, para obtener la cantidad máxima en las ubicaciones reabastecidas, debe establecer la opción **Permitir dividir** en *Sí* en las directivas de ubicación para el picking de reabastecimiento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]