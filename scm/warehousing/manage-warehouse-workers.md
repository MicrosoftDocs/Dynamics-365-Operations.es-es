---
title: "Gestionar trabajadores de almacén"
description: "Este artículo describe cómo puede usar Dynamics 365 for Finance and Operations para ayudar a controlar y a supervisar el trabajo que han realizado los empleados en los almacenes."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 52753c21862a2955e15140bb1cdb5ef6f6efe31a
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Gestionar trabajadores de almacén
<a id="manage-warehouse-workers" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este artículo describe cómo puede usar Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para ayudar a controlar y a supervisar el trabajo que han realizado los empleados en los almacenes.

Si usa la funcionalidad de gestión de almacenes, todas las operaciones de trabajador de almacén se conocen como *trabajo*. Trabajo como seleccionar, mover y recuento de inventario disponible se registra con los dispositivos móviles. Antes de que un trabajador de almacén pueda realizar el trabajo, debe estar asociado a un trabajador en recursos humanos. Cada cuenta de **Trabajador** puede tener varios usuarios de trabajo de almacén asociados. Dichos usuarios de trabajo pueden trabajar en varios almacenes y pueden tener distintos niveles de acceso a los distintos menús del dispositivo móvil. Puede pensar en los usuarios de trabajo de almacén como varios inicios de sesión para el trabajador seleccionado. Cada usuario de trabajo tiene un almacén predeterminado y los flujos de trabajo específicos son expuestos por los elementos de menú que están disponibles para dicho usuario de trabajo. 

Para crear un usuario de trabajo nuevo, en la página **Trabajadores**, en la pestaña **General**, en la sección **Almacenes**, haga clic en **Trabajador**. Debe especificar un id. de usuario, un nombre de usuario, un almacén predeterminado y un nombre de menú. Este menú se carga cuando el usuario inicia sesión en el portal del dispositivo móvil del almacén, y le permite definir los elementos de menú a los que el usuario tendrá acceso. 

Como parte de la configuración para cada usuario de trabajo, también puede definir flujos de trabajo específicos del proceso. Por ejemplo, puede usar el campo **Es un supervisor del recuento cíclico** para especificar si el usuario puede realizar ajustes en el proceso a las discrepancias del recuento cíclico durante una operación de recuento, o si esta configuración debe ser revisada primero por otra persona.

## Definición de estándares de mano de obra
<a id="defining-labor-standards" class="xliff"></a>
La página **Estándares de mano de obra** permite definir los métodos de cálculo que el sistema usa para calcular el tiempo estimado que un tipo concreto de trabajo debe requerir. Esta definición se puede establecer a nivel genérico o a nivel específico. Por ejemplo, puede definir el tiempo que debe ser necesario para procesar una selección de un pedido de ventas por peso para una definición específica de la unidad cuando se usa un proceso de selección específico. Al mismo tiempo, puede registrar la hora, en función de otro método de cálculo, para la operación de colocación del inventario disponible que se ha seleccionado. 

Para habilitar los estándares de mano de obra que ha definido, debe seleccionar la opción **Permitir estándares de mano de obra** para cada almacén donde los estándares de mano de obra se usarán.

## Supervisión del trabajo del almacén
<a id="monitoring-and-controlling-warehouse-work" class="xliff"></a>
La página **Todos los trabajos** le permite supervisar y mantener todo el trabajo planificado, en proceso y completado. Desde esta página, puede actualizar varios procesos, como asignaciones de usuario de trabajo de almacén y prioridad de trabajo. También puede explorar en profundidad detalles relacionados con el encabezado de trabajo y líneas de trabajo para obtener un entendimiento de los procesos previstos o completados de trabajo. 

Si activa la opción **Estándares de mano de obra**, puede ver la hora estimada calculada para el trabajo. Posteriormente, cuando se procesa el trabajo, el tiempo real también se mostrará para cada operación de trabajo. De esta manera, puede comparar los cálculos de tiempo estimado con el tiempo real. 

Además, puede usar el tiempo estimado en las reglas para dividir el trabajo automáticamente durante la creación de trabajo. De esta manera, puede cargar el trabajo de saldos, en función del tiempo previsto para completar las tareas. 

El análisis del tiempo que se usa para procesar los elementos de trabajo puede ayudar a impulsar mejoras en la eficacia de los trabajadores de almacén. Los informes siguientes están disponibles para ayudar con este análisis:

-   **Mano de obra por usuario** este informe muestra la productividad del trabajador, en función del tiempo real comparado con el tiempo previsto.
-   **Mano de obra por tipo de transacción de trabajo** puede usar este informe para investigar ineficacias en procesos específicos del almacén. Por ejemplo, puede observar que las selecciones para los pedidos de transferencia tardan más esta semana que en semanas anteriores Puede usar esta información para investigar más.





