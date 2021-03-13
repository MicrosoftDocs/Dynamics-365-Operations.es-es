---
title: Solucionar problemas de planificación maestra
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con planificación maestra.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 44291f5bcd9ffedf717150f8efe32e9eeda02f2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011365"
---
# <a name="troubleshoot-master-planning"></a>Solucionar problemas de planificación maestra

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con planificación maestra.

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a>La explosión de la lista de materiales se comporta de manera diferente para las órdenes de producción firmes y para las órdenes de producción estimadas para el trabajo creado manualmente.

### <a name="issue-description"></a>Descripción del problema

Cuando se confirma una orden de producción, los artículos no se desglosan cuando se desglosa la lista de materiales (BOM). Sin embargo, cuando crea manualmente una orden de trabajo y luego estima la orden de producción, los artículos se desglosan.

### <a name="issue-resolution"></a>Solución del problema

El sistema funciona como se esperaba. La explosión que se produce cuando se confirma la orden de producción apuntará a la orden planificada, pero no parece que la orden planificada esté actualmente firme en este caso. Sin embargo, si se ha estimado la orden de producción, la explosión se desencadena desde la orden de producción liberada donde no existe una orden previsional.

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a>El valor de Retraso no se actualiza cuando reprogramo un pedido planificado.

Para actualizar el retraso de los pedidos planificados, abra el cuadro de diálogo **Reprogramación** de la orden previsional. En la ficha desplegable **Explosión**, asegúrese de que la opción **Realizar explosión después de reprogramación** está establecida en *Sí*.

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a>La programación de la producción no considera los márgenes de seguridad que se establecen en la cobertura del artículo para el suministro vinculado.

### <a name="issue-description"></a>Descripción del problema

La planificación maestra considera los márgenes de seguridad. Sin embargo, los márgenes de seguridad se ignoran cuando se programan órdenes de producción planificadas.

### <a name="issue-resolution"></a>Solución del problema

Los márgenes se consideran solo durante la planificación maestra, no durante la programación manual. Los márgenes están diseñados para actuar como un amortiguador durante la fase de planificación, para dar algún "margen" para el proceso real.

Para obtener el resultado deseado, puede eliminar el margen. Luego, la ruta debe actualizarse para que incluya el tiempo deseado (por ejemplo, como tiempo de espera). Tanto la planificación maestra como la programación manual deberían producir el mismo resultado.

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a>Los pedidos planificados se generan aunque tengamos artículos en stock y ya existan pedidos de producción para ellos.

Es posible que pueda solucionar este problema aumentando el valor **Días positivos** para los grupos relevantes en la página **Grupo de cobertura**. Este cambio hará que el sistema determine si el inventario disponible se puede utilizar para la demanda. Entonces, no se generará un nuevo pedido planificado para los artículos que están en stock.

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a>La planificación maestra no parece respetar las limitaciones de capacidad y está programando más que la capacidad disponible.

### <a name="issue-description"></a>Descripción del problema

Cuando usa la programación de operaciones donde hay una capacidad finita, y donde la ruta especifica una combinación de requisitos para un grupo de recursos y recursos individuales, existe una pequeña posibilidad de overbooking debido a la forma en que el algoritmo valida los conflictos de capacidad. Esta sobreventa puede ocurrir cuando utiliza ayudantes para ejecutar la planificación maestra. Es más probable que ocurra si hay muchos trabajos que tienen un tiempo de ejecución relativamente corto.

### <a name="issue-resolution"></a>Solución del problema

Si es esencial que no se produzca una sobreventa para la programación de operaciones, puede hacer que la programación sea parte de la planificación maestra de un solo subproceso activando la opción **Capacidad finita precisa para la programación de operaciones** en la página **Parámetros de planificación maestra**. Esta opción no está disponible de forma predeterminada. Debe agregarlo manualmente a la página mediante funciones de personalización. Cuando usa esta opción, la programación se ejecutará más lentamente debido a la falta de procesamiento paralelo.

## <a name="planned-orders-take-a-long-time-to-update"></a>Los pedidos planificados tardan mucho en actualizarse.

### <a name="issue-description"></a>Descripción del problema

Al actualizar la cantidad requerida y / o la fecha de entrega en un pedido planificado, generalmente se necesitan al menos 30 segundos por pedido para guardar la actualización.

### <a name="issue-resolution"></a>Solución del problema

Este es un problema conocido con el motor de planificación maestro integrado. Se debe a la explosión automática subyacente a través de la estructura de la lista de materiales durante las ediciones. Este problema se aborda en la Optimización de la planificación, donde un planificador puede actualizar y aprobar los pedidos relevantes y, cuando lo desee, activar una ejecución de planificación para actualizar los pedidos planificados para la estructura BOM subyacente.

Una forma de mejorar el rendimiento con el motor de planificación maestro integrado es hacer lo siguiente:

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un tipo de plan.
1. Expanda la ficha desplegable **Límites de tiempo en días**.
1. Establezca **Explosión** en *Sí* y establezca el campo debajo de esta configuración en 0 (cero).

> [!NOTE]
> Esto limitará el período de explosiones realizadas para este plan maestro a un solo día.
