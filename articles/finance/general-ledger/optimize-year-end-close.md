---
title: Optimizar cierre de fin de año
description: En este artículo se describe el complemento de servicio de cierre de fin de año de Optimize que está disponible para el proceso de cierre de fin de año del libro mayor.
author: moaamer
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 41d0c2975341cf3d612cc36be348326e24e94f1b
ms.sourcegitcommit: 707957bb7bcd98faf2600eff1c98067901a0fb73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750016"
---
# <a name="optimize-year-end-close"></a>Optimizar cierre de fin de año

El complemento de servicio de cierre de fin de año de Optimize para Microsoft Dynamics 365 Finance permite que el procesamiento de cierre de fin de año se ejecute fuera de la instancia de Application Object Server (AOS) para los recursos de Dynamics 365 Finance. Utiliza tecnología de microservicios. Los beneficios que están asociados con la funcionalidad de cierre de año de Optimize incluyen un rendimiento mejorado y un impacto reducido en la base de datos SQL durante el proceso de cierre de fin de año.

Para usar la funcionalidad de cierre de fin de año de Optimize, debe completar las siguientes tareas:

1. Instale el complemento de servicio de cierre de fin de año de Optimize desde su proyecto en Microsoft Dynamics Lifecycle Service.
2. Habilitar la característica **Optimizar el cierre de fin de año** en Gestión de funciones.

> [!NOTE]
> Todavía puede usar la funcionalidad de cierre de fin de año actual para los recursos de Finance al deshabilitar la función **Optimizar el cierre de fin de año** en Gestión de funciones.

## <a name="improved-performance"></a>rendimiento mejorado

La característica **Optimizar el cierre de fin de año** está diseñada para acelerar el procesamiento de cierre de fin de año, especialmente para clientes que tienen grandes volúmenes de datos. Cuando el cierre de fin de año se ejecuta en un servicio, el procesamiento pesado se descarga de los recursos de Finance para ayudar a reducir el tiempo de procesamiento y liberar los recursos que podrían afectar las operaciones diarias de otros usuarios.

La característica **Optimizar el cierre de fin de año** puede ayudarlo a lograr los siguientes objetivos:

- Mejore el rendimiento del cierre de fin de año al reducir el tiempo de ejecución.
- Reducir el impacto en otros procesos durante la ejecución del cierre de fin de año.
- Mejore los informes y los ajustes para los resultados de fin de año, porque la ejecución de cierre de fin de año lleva menos tiempo.

## <a name="new-options-and-visibility"></a>Nuevas opciones y visibilidad

Cuando la característica **Optimizar el cierre de fin de año** está habilitada, dos nuevas columnas, **Resultados** y **Estado**, se añaden en los siguientes lugares:

- En la página del **Cierre de fin de año**
- En el cuadro de diálogo **Resultados del cierre de fin de año**
- En las opciones **Transferencia de la dimensión financiera del balance** opciones en la página **Plantilla de cierre de fin de año**

La siguiente ilustración muestra un ejemplo de las columnas **Resultados** y **Estado** en la página **Cierre de fin de año**. Puede seleccionar el enlace **Ver resultados** en la columna **Resultados** para abrir los resultados del cierre del ejercicio. La columna **Estado** muestra el estado actual del proceso de cierre de fin de año. Por lo tanto, las nuevas columnas brindan visibilidad sobre el progreso del proceso de cierre de fin de año.

[![Columnas de resultados y estado en la página de cierre de fin de año.](./media/Yearendclose.jpg)](./media/Yearendclose.jpg)

Además, cuando la característica **Optimizar el cierre de fin de año** está habilitada, una ficha desplegable **Dimensiones financieras del balance de situación** está disponible en la página **Plantilla de cierre de fin de año**. Puede utilizar esta ficha desplegable para especificar las dimensiones financieras del balance de situación en detalle al cerrar un año. Esta capacidad es paralela a la capacidad que ya está disponible para las cuentas de pérdidas y ganancias.

## <a name="architecture-and-data-flow"></a>Arquitectura y flujo de datos

Para usar **Optimizar el cierre de fin de año** y ejecutar el cierre de fin de año en un microservicio, debe instalar el complemento de servicio de cierre de fin de año de Optimize desde Lifecycle Services y luego habilitar la característica **Optimizar el cierre de fin de año** en Gestión de funciones.

Como muestra la siguiente ilustración, el procesamiento de cierre de fin de año verifica que el complemento esté instalado y que la característica esté habilitada. Si se cumplen ambos requisitos previos, el cierre de fin de año se ejecuta en el microservicio.

[![Diagrama de flujo de datos.](./media/Lifecycle-services.jpg)](./media/Lifecycle-services.jpg)

## <a name="high-level-flow-for-year-end-close-processing"></a>Flujo de alto nivel para el procesamiento de cierre de fin de año

1. El proceso de cierre de año comienza en Finance , en **Contabilidad general \> Cierre de periodo \> Cierre de fin de año**. El proceso crea tareas y trabajos por lotes de cierre para las entidades jurídicas que se están cerrando.
2. El cierre de fin de año determina si el cierre de fin de año debe ejecutarse en el microservicio o en la lógica de cierre actual.

    - Si el complemento de servicio de cierre de fin de año está instalado en Lifecycle Services y la característica **Optimizar cierre de fin de año** está habilitada en la administración de características, el cierre de fin de año se ejecutará en el microservicio.

        1. La funcionalidad de cierre de fin de año de Optimize crea un trabajo de servicio de cierre de fin de año para cada entidad jurídica que se está cerrando y luego ejecuta la lógica de cierre de fin de año. El microservicio realiza el cierre de fin de año.
        2. Finance escucha el cierre de fin de año en el microservicio para determinar cuándo finalizó el microservicio. Los resultados de cierre de fin de año se actualizan después en la página **Cierre de fin de año** en Finance.

    - De lo contrario, el cierre de fin de año se ejecutará en la lógica de cierre actual.
