---
title: Parámetros no utilizados por Optimización de planificación
description: Este tema enumera los parámetros que Planning Optimization no considera actualmente durante su funcionamiento.
author: crytt
ms.date: 6/29/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4d459f4de67f26f36aabcbde015988132e957601
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361358"
---
# <a name="parameters-not-used-by-planning-optimization"></a>Parámetros no utilizados por Optimización de planificación

[!include [banner](../../includes/banner.md)]

Este tema enumera los parámetros que Planning Optimization no considera actualmente durante su funcionamiento. El servicio de planificación puede omitir un parámetro porque, por ejemplo, la funcionalidad relacionada aún no es compatible. Alternativamente, el parámetro podría haberse vuelto obsoleto debido a cambios funcionales.

Las siguientes secciones enumeran los parámetros que Planning Optimization no usa en páginas específicas. También explican por qué no se utiliza cada parámetro.

## <a name="master-planning-parameters-page"></a>Página de parámetros de planificación maestra

Planning Optimization no utiliza los siguientes parámetros u opciones en la página **Parámetros de planificación maestra**:

- Pestaña **General**:

    - **Plan de previsión actual**: compatibilidad de *Pronóstico* pendiente.
    - **Plan maestro estático actual** - Compatibilidad pendiente con *Copiar plan estático en dinámico*.
    - **Plan maestro dinámico actual** - Compatibilidad pendiente con *Copiar plan estático en dinámico*.
    - **Copie el plan maestro estático completo y actualizado al plan maestro dinámico** - Pendiente compatibilidad con *Copiar plan estático en dinámico*.
    - **Hora de inicio para retrasos calculados** - Pendiente compatibilidad con *Retrasos calculados*.
    - **Utilice días negativos dinámicos** - Planning Optimization siempre utiliza el enfoque *Días negativos dinámicos*.
    - **Calendario de fechas de hoy** - Pendiente compatibilidad con *Planificación*.
    - **Uso de caché** - La configuración de la suscripción a Microsoft Azure maneja los puntos de rendimiento.
    - **Número de tareas en el paquete de tareas de ayuda** - La configuración de la suscripción de Azure maneja los puntos de rendimiento.
    - **Preprocesamiento: filtra automáticamente por artículos con demanda directa** - La configuración de la suscripción de Azure maneja los puntos de rendimiento.
    - **Posprocesamiento: filtra automáticamente por artículos con demanda directa** - La configuración de la suscripción de Azure maneja los puntos de rendimiento.
    - **Número de pedidos en el paquete de puesta en firme** - La configuración de la suscripción de Azure maneja los puntos de rendimiento.
    - **Número de subprocesos** - La configuración de la suscripción de Azure maneja los puntos de rendimiento.
    - **Tiempo de espera del proceso de planificación, en minutos** - La configuración de la suscripción de Azure maneja los puntos de rendimiento.
    - **Programación de la hora de inicio** - Pendiente compatibilidad con *Planificación*.

- Pestaña **Pedidos planificados**:

    - **Hora de recepción** - Pendiente compatibilidad con *Planificación*.
    - **Producción** - Pendiente compatibilidad con *Planificación*.
    - Campos en la sección **Proyecto** - Pendiente compatibilidad con *Planificación*.

- Pestaña **Actualización estándar**:

    - **Actualizar marcado** - Pendiente compatibilidad con *Reafirmante*.
    - **Deje de reafirmar si ocurre un error** - Pendiente compatibilidad con *Reafirmante*.
    - **Agrupar por proveedor** - Pendiente compatibilidad con *Reafirmante*.
    - **Agrupar por grupo de compradores** - Pendiente compatibilidad con *Reafirmante*.
    - **Agrupar por acuerdo de compra** - Pendiente compatibilidad con *Reafirmante*.
    - **Agrupar por período** - Pendiente compatibilidad con *Reafirmante*.
    - **Buscar acuerdo de compra** - Pendiente compatibilidad con *Reafirmante*.
    - **Agrupar por prioridad de planificación** - Pendiente compatibilidad con *Reafirmante*.
    - **Agrupar por período** - Pendiente compatibilidad con *Reafirmante*.

## <a name="coverage-groups-page"></a>Página Grupos de cobertura

Optimización de planificación no utiliza los siguientes parámetros u opciones en la página **Grupos de cobertura**:

- Ficha desplegable **General**:

    - **Días positivos** - Pendiente compatibilidad con *Días positivos*.
    - **Consumir inventario disponible** - Pendiente compatibilidad con *Consumo de inventario disponible*.
    - **Utilice la lista de materiales o la versión de fórmula especificada** - Pendiente compatibilidad con *Versiones de fórmula con Co / Por producto*.
    - **Utilice la versión de ruta especificada** - Pendiente compatibilidad con *Demanda con requisitos de ruta o lista de materiales específicos definidos*.

- Ficha desplegable **Acción**:

    - **Mensaje de acción** - Pendiente compatibilidad con *Comportamiento*.
    - **Límite de tiempo de acción** - Pendiente compatibilidad con *Comportamiento*.
    - **Posponer margen** - Pendiente compatibilidad con *Comportamiento*.
    - **Avanzar margen** - Pendiente compatibilidad con *Comportamiento*.
    - **Fecha base** - Pendiente compatibilidad con *Comportamiento*.
    - **Avanzar** - Pendiente compatibilidad con *Comportamiento*.
    - **Posponer** - Pendiente compatibilidad con *Comportamiento*.
    - **Reducir** - Pendiente compatibilidad con *Comportamiento*.
    - **Aumentar** - Pendiente compatibilidad con *Comportamiento*.
    - **Acciones derivadas** - Pendiente compatibilidad con *Comportamiento*.

- Ficha desplegable **Otro**:

    - **Valla de tiempo de congelación (días)** - La compatibilidad con *Congelar la valla del tiempo* no está planeado en Optimización de planificación.
    - **Valla de tiempo de explosión de la lista de materiales (días)** - Pendiente compatibilidad con *Planificación*.
    - **Valla de tiempo de programación de capacidad (días)** - Pendiente compatibilidad con *Planificación*.
    - **Límite de tiempo de solicitud aprobado (días)** - Pendiente compatibilidad con *Requisar*.
    - **Límite de tiempo de plan de previsión**: compatibilidad con *Pronóstico* pendiente.

- Ficha desplegable **Retrasos**:

    - **Retrasos calculados** - Pendiente compatibilidad con *Retrasos calculados*.
    - **Límite de tiempo para retrasos calculados (días)** - Pendiente compatibilidad con *Retrasos calculados*.

## <a name="item-coverage-page"></a>Página Cobertura de artículos

Optimización de planificación no utiliza los siguientes parámetros u opciones en la página **Cobertura de artículos**:

- Pestaña **General**:

    - **Tipo de orden planificada** - Optimización de planificación no es compatible con la opción *Kanban*, pendiente compatibilidad con *Kanban*.
    - **Valla de tiempo de congelación (días)** - La compatibilidad con *Congelar la valla del tiempo* no está planeado en Optimización de planificación.
    - **Valla de tiempo de explosión de la lista de materiales (días)** - Pendiente compatibilidad con *Planificación*.
    - **Valla de tiempo de programación de capacidad (días)** - Pendiente compatibilidad con *Planificación*.
    - **Límite de tiempo de solicitud aprobado (días)** - Pendiente compatibilidad con *Requisar*.
    - **Cumplir con el mínimo** - Optimización de planificación no es compatible con *Fecha*, *Primer problema* y *Límite de tiempo de cobertura*. Siempre utiliza la opción *Fecha de hoy + tiempo de adquisición*.
    - **Periodos mínimos** - Pendiente la compatibilidad con *Nivel mínimo de inventario*.
    - **Fórmula de planificación** - Pendiente la compatibilidad con *Versiones de fórmulas con Co / subproductos*.
    - **Prioridad predeterminada** - Pendiente la compatibilidad con *Versiones de fórmulas con Co / subproductos*.
    - **Prioridad actual** - Pendiente la compatibilidad con *Versiones de fórmulas con Co / subproductos*.
    - **Fecha cambiada** - Pendiente la compatibilidad con *Versiones de fórmulas con Co / subproductos*.
    - **Consumir inventario disponible** - Pendiente compatibilidad con *Consumo de inventario disponible*.

## <a name="master-plans-page"></a>Página Planes maestros

Planning Optimization no utiliza los siguientes parámetros u opciones en la página **Planes maestros**:

- Ficha desplegable **General**:

    - **Incluir inventario disponible** - Pendiente compatibilidad con *Consumo de inventario disponible*.
    - **Reemplazar inventario disponible** - Pendiente compatibilidad con *Consumo de inventario disponible*.
    - **Consumir inventario disponible** - Pendiente compatibilidad con *Consumo de inventario disponible*.
    - **Incluir transacciones de inventario** - Pendiente compatibilidad con *Consumo de inventario disponible*.
    - **Incluir cotizaciones de ventas** - Pendiente la compatibilidad con *Cotizaciones de venta*.
    - **Incluir solicitud de cotizaciones** - Pendiente la compatibilidad con *Solicitud de cotizaciones*.
    - **Utilice fechas de caducidad** - Pendiente la compatibilidad con *Duración*.
    - **Incluir plan de continuidad** - Pendiente la compatibilidad con *Programación de continuidad*.
    - **Método de programación** - Pendiente compatibilidad con *Planificación*.
    - **Propiedad finita** - Pendiente la compatibilidad con *Planificación*.
    - **Límite de tiempo de capacidad de programación regresiva** - Pendiente compatibilidad con *Planificación*.
    - **Capacidad finita** - Pendiente la compatibilidad con *Planificación*.
    - **Límite de tiempo de capacidad finita** - Pendiente la compatibilidad con *Planificación*.
    - **Capacidad finita para recursos de cuello de botella** - Pendiente la compatibilidad con *Planificación*.
    - **Límite de tiempo de capacidad para recursos de cuello de botella** - Pendiente la compatibilidad con *Planificación*.
    - **Órdenes planificadas** - Optimización de la planificación utiliza secuencias numéricas fijas.
    - **Sesión** - Optimización de la planificación utiliza secuencias numéricas fijas.
    - **Plan de continuidad** - Optimización de la planificación utiliza secuencias numéricas fijas.

- Ficha desplegable **Límites de tiempo en días**:

    - **Congelación** - La compatibilidad con *Congelar la valla del tiempo* no está planeado en Optimización de planificación.
    - **Explosión** - Pendiente compatibilidad con *Planificación*.
    - **Plan de previsión**: más compatibilidad con *Pronóstico* pendiente.
    - **Capacidad** - Pendiente la compatibilidad con *Planificación*.
    - **Plan de continuidad** - Pendiente la compatibilidad con *Programación de continuidad*.
    - **Mensaje de acción** - Pendiente compatibilidad con *Comportamiento*.
    - **Retrasos calculados** - Pendiente más compatibilidad con *Retrasos calculados*.
    - **Secuenciación** - Pendiente compatibilidad con *Producción*.

- Ficha desplegable **Retrasos calculados**:

    - **Asegúrese de que las órdenes previsionales no se creen antes de la fecha de ejecución de la planificación maestra** - Pendiente la compatibilidad con *Retrasos calculados*.
    - **Agregue el retraso calculado a la fecha de requisito** (en la sección **Órdenes de compra planificadas**) - Pendiente la compatibilidad con *Retrasos calculados*.
    - **Agregue el retraso calculado a la fecha de requisito** (en la sección **Órdenes de producción planificadas**) - Pendiente la compatibilidad con *Retrasos calculados*.
    - **Agregue el retraso calculado a la fecha de requisito** (en la sección **Transferencia planificada**) - Pendiente la compatibilidad con *Retrasos calculados*.
    - **Agregue el retraso calculado a la fecha de requisito** (en la sección **Kanban planificada**) - Pendiente la compatibilidad con *Retrasos calculados*.

- Ficha desplegable **Secuenciación**:

    - **Secuenciar órdenes previsionales después de la planificación maestra** - Pendiente la compatibilidad con *Secuenciación*.
    - **Tipo de cucharón** - Pendiente la compatibilidad con *Secuenciación*.
    - **Tipo de período** - Pendiente la compatibilidad con *Secuenciación*.
    - **Número de depósitos en el ciclo de la campaña** - Pendiente la compatibilidad con *Secuenciación*.

## <a name="released-product-details-page"></a>Página de detalles de productos emitidos

Optimización de planificación no utiliza la siguiente opción de parámetro en la página **Detalles de productos lanzados**:

- Ficha desplegable **Ingeniero**:

    - **Tipo de produccion** - Planning Optimization no es compatible con la opción *Elemento de planificación*, pendiente la compatibilidad con *Elementos de planificación*.

## <a name="default-order-settings-page"></a>Página Configuración predeterminada de pedido

Optimización de planificación no utiliza la siguiente opción de parámetro en la página **Configuración de pedido predeterminada**:

- Ficha desplegable **Inventario**:

    - **Control de fecha de entrega** - Planning Optimization no es compatible con la opción *CTP*, pendiente la compatibilidad con *CTP*.

## <a name="working-time-calendars-page"></a>Página Calendarios de horarios de trabajo

Planning Optimization no utiliza el siguiente parámetro en la página **Calendarios de horas laborables**:

- **Calendario base** - Pendiente la compatibilidad con *Calendarios base*.

## <a name="batch-disposition-master-page"></a>Página Disposición maestra de lote

Optimización de planificación no utiliza el siguiente parámetro en la página **Maestro de disposición por lotes**:

- Ficha desplegable **Configuración**:

    - **Incluido como inventario** - Pendiente la compatibilidad con *Códigos de disposición de lotes*.