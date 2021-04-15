---
title: Liberar pedidos de producción
description: Un pedido de producción liberado es una orden que se ha autorizado para producción. El término Liberado se usa para describir un estado en el ciclo de vida del pedido de producción, donde el pedido de producción está disponible para la ejecución en la planta de producción y para procesos de almacén.
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 118b0d6300647135b22e42cc84a79f07e48d7ef4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811711"
---
# <a name="release-production-orders"></a>Liberar pedidos de producción

[!include [banner](../includes/banner.md)]

Un pedido de producción liberado es una orden que se ha autorizado para producción. El término Liberado se usa para describir un estado en el ciclo de vida del pedido de producción, donde el pedido de producción está disponible para la ejecución en la planta de producción y para procesos de almacén.

## <a name="characteristics-of-the-released-state"></a>Características de estado Liberado

El estado **Liberado** es un estado en el ciclo de vida del pedido de producción. Los pedidos de producción que tengan estado **Liberado** están disponibles para su ejecución en la planta de producción y para los procesos de almacén. El estado **Liberado** tiene las siguientes características:

- Un pedido de producción se puede cambiar al estado **Liberado** desde el pedido de producción o mediante un proceso por lotes. El pedido de producción también se puede actualizar automáticamente desde los pedidos de producción planificados en firme mediante el campo **Límite de tiempo de puesta en firme** de la página **Plan maestro**.
- El estado **Liberado** es la señal para que los operadores de planta (operadores) comiencen a ejecutar los trabajos de producción en planta.
- Los papeles de producción, como las tarjetas de ruta, los trabajos de ruta y las tarjetas de trabajo proporcionan información acerca de los trabajos de producción y se pueden emitir.
- Para los materiales físicamente reservados, el trabajo de almacén se genera para seleccionar materiales para el pedido de producción.

## <a name="releasing-jobs-to-the-shop-floor"></a>Liberación de trabajos a la planta

Después de liberar un pedido de producción, los trabajos de producción relacionados con el pedido quedan visibles y listos para su registro. Los operadores pueden realizar tareas de registro de trabajos, como inicio, detención y finalización, en la página **Terminal de tarjeta de trabajo** o en la página **Dispositivo de tarjeta de trabajo**. El tiempo y la cantidad registrados se transfieren automáticamente desde las páginas de registro a los diarios de producción para hacer un seguimiento del tiempo y la cantidad consumidos.

## <a name="route-cards"></a>Tarjetas de ruta

Las tarjetas de ruta proporcionan una visión general de la información proveniente de las configuraciones de ruta y operaciones y de los métodos de programación de trabajos y operaciones.

## <a name="route-jobs"></a>Trabajos de ruta

Los trabajos de ruta enumeran todos los trabajos de una operación detalladamente e incluyen los tiempos de configuración, procesamiento, cola y transporte. Por ejemplo, una operación tal como la pintura puede requerir trabajos individuales como, por ejemplo, el momento de configuración, el tiempo de ejecución para el proceso de pintura y el tiempo en cola para el secado.

## <a name="job-cards"></a>Tarjetas de trabajo

En las tarjetas de trabajo se enumeran los números de trabajo individuales de una operación en particular. Aparece un trabajo en cada página. Los trabajos incluidos en las tarjetas de trabajo y sus tiempos estimados provienen de la información de configuración de la ruta y la operación. Desde una tarjeta de trabajo puede abrir la página **Líneas de diario de producción**, **tarjeta de trabajo**. Las personas que ejecutan recursos de operaciones pueden proporcionar comentarios sobre el proceso de producción. Existen cambios en los que se especifican las estadísticas y la información de consumo como, por ejemplo, la cantidad de error.

## <a name="warehouse-work-for-raw-material-picking"></a>Trabajo de almacén para selección de materiales

El trabajo para seleccionar de materia prima se genera durante el proceso de liberación. El trabajo solo se genera para la cantidad de materiales que se ha reservado físicamente para el pedido de producción antes de que el pedido se liberara. Se requiere la configuración siguiente para generar el trabajo de almacén para seleccionar materias primas:

- Un directorio de ubicación para seleccionar materias primas que determine en qué ubicación de almacén seleccionar los materiales.
- Una plantilla de oleada para materias primas, donde se hayan configurado directivas de ejecución del trabajo de almacén.
- Una ubicación de entrada de producción que determine dónde se colocan los materiales.

Al utilizar ubicaciones controladas por matrículas, puede elegir si la cantidad pedida o la cantidad total disponible para el artículo se debe recoger mientras se procesa el trabajo de preparación de la materia prima. Para configurar esta opción:

1. Vaya a **Panel de navegación \> Productos \> Productos despachados** y abra el artículo pertinente.
1. Expanda la ficha desplegable **Almacén**.
1. Seleccione una de las siguientes opciones para el campo **Recogida de material en ubicaciones de matrículas**:
    - *Selección de pedido*: sólo la cantidad pedida debe ser seleccionada.
    - *Etapas*: siempre que sea posible, debe seleccionarse la cantidad completa disponible en la matrícula. Para que un trabajador pueda recoger la cantidad completa de matrículas, la matrícula no debe contener elementos mezclados y no debe tener dimensiones mixtas. Si la matrícula contiene elementos o dimensiones mixtas, la selección procederá como si estuviera configurada en *Preparación de pedidos*.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]