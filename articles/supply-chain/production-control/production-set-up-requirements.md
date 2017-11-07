---
title: "Requisitos de configuración de producción"
description: "Este artículo proporciona información acerca de los requisitos de configuración para poder trabajar con el Control de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b5df3c6c776a8dafdcfb3be7e2f273e01d70bcae
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="production-setup-requirements"></a>Requisitos de configuración de producción

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de los requisitos de configuración para poder trabajar con el Control de producción. 

Control de producción se integra con funciones de otros módulos. Esta interconectividad le permite modificar las órdenes de producción y garantizar que se actualizan automáticamente en los demás procesos y cálculos del sistema. Los siguientes procesos de configuración se enumeran en el orden en que se deben realizar.

## <a name="required-baseline-setup-in-other-modules"></a>Configuración de línea base requerida en los demás módulos
Para poder trabajar con Control de producción, debe configurarse previamente información en los demás módulos. Esta configuración incluye las tareas siguientes:

-   La configuración de la información general de la empresa.
-   La configuración de la contabilidad general.
-   La definición de grupos de artículos.
-   La configuración de cuentas contables para grupos de artículos.
-   La configuración de la tabla de artículos de inventario en Gestión del inventario.
-   La creación de listas de materiales (L. MAT.) y versiones de L. MAT. en Gestión del inventario.

## <a name="required-calendar-and-resource-setup"></a>Configuración necesaria del calendario y del recurso
Antes de utilizar Control de producción, abra Administración de la organización y cree y defina el calendario y los recursos de operaciones en el orden siguiente:

1.  **Plantillas de horarios de trabajo**: configure las plantillas de horarios de trabajo para definir los tiempos que están disponibles para la programación de producción.
2.  **Calendarios**: configure los calendarios de horarios de trabajo para definir los días de año que están disponibles para la programación de producción.
3.  **Grupos de recursos**: configure los grupos de recursos para agrupar los recursos de operaciones y, así, obtener una visión general de las capacidades libres cuando se ejecuta la programación. No tiene que configurar grupos de recursos antes de configurar recursos de operaciones. Sin embargo, recomendamos que entienda cómo se agrupan recursos cuando configura Control de producción.
4.  **Recursos**: configure los recursos de operaciones para definir los recursos utilizados para completar el proceso de producción y planificar la capacidad.

## <a name="required-production-parameters-setup"></a>Configuración de parámetros de producción
**Parámetros de control de producción**: configure los parámetros de producción básicos para definir cómo debe el sistema gestionar y procesar los pedidos de producción. Defina cómo se crean, estiman, programan y consumen los pedidos de producción. También puede escoger qué clase de realimentación desea y cómo se realiza la contabilidad de costes.

## <a name="required-journal-name-identification"></a>Identificación del nombre del diario
**Nombres de diario de producción**: especifique los nombres de diario de producción que se usan para registrar y contabilizar transacciones.

## <a name="setup-if-you-use-operations"></a>Configuración en caso de utilizar operaciones
Las operaciones representan las actividades específicas para obtener el producto final. **Nota:** debe conocer a los tipos de actividades necesarias para producir el artículo, y el orden y las prioridades de dichas actividades. También debe conocer qué recursos están involucrados y cuántos.

1.  **Operaciones**: configure las operaciones para representar las tareas que se deben realizar para producir el artículo finalizado.
2.  **Relaciones**: configure las relaciones de operaciones para establecer propiedades detalladas. Para definir relaciones de operaciones, haga clic en **Relaciones** en la página **Operaciones**.

## <a name="setup-if-you-use-routes"></a>Configuración en caso de utilizar rutas
Si trabaja con rutas, deben definirse operaciones para cada ruta de producción configurada. La ruta representa la ruta que sigue el artículo de una operación a otra desde el inicio hasta el final del proceso.

1.  **Categorías de coste**: configure categorías de costes para definir el coste por hora de los procesos y las horas de configuración especificadas.
2.  **Grupos de coste**: configure grupos de costes para crear y mantener diferentes tipos de versiones de costes.
3.  **Grupos de rutas**: configure grupos de rutas para definir parámetros relacionados con los grupos de rutas. Debe configurar los grupos de rutas antes de poder crear rutas de producción.
4.  **Rutas**: configure rutas de producción y defina los parámetros predeterminados para el control de programación, las operaciones de coste y el precio de rutas y controlar los informes de progreso.
5.  **Rutas**: configure versiones de ruta para habilitar variaciones del artículo en la producción.

## <a name="optional-advanced-settings"></a>Parámetros avanzados opcionales
1.  **Grupos de producción**: configure grupos de producción para establecer relaciones entre la orden de producción y las cuentas contables. Las cuentas contables se usan para registrar o agrupar pedidos que están listos para informe.
2.  **Conjuntos de producción**: cree grupos de producción para agrupar órdenes de producción para el procesamiento de órdenes de producción urgentes o para la eliminación y el registro de grupos de pedidos.
3.  **Propiedades**: defina propiedades para crear atributos especiales que puede asignar a sus recursos para controlar el orden de las producciones. Estos atributos x la plantilla de horario de trabajo.





