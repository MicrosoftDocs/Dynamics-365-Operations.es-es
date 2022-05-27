---
title: Visión general de las tareas de servicio
description: Utilice tareas de servicios para describir la tarea que hay que realizar durante un pedido de servicio. Tanto técnicos como clientes pueden ver esta información.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76eba18fb9228c3b9c2accf17cb938e7f2a12dbe
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671713"
---
# <a name="service-tasks-overview"></a>Visión general de las tareas de servicio

[!include [banner](../includes/banner.md)]

Utilice tareas de servicios para describir la tarea que hay que realizar durante un pedido de servicio.
Tanto técnicos como clientes pueden ver esta información.

Crea tareas de servicio en la página **Tareas de servicio** y asocia tareas de servicio a un contrato de servicio o pedido de servicio específico creando relaciones de tareas de servicio. Cada vez que crea una relación de tarea de servicio, puede crear:

-  Notas internas para la tarea, como solicitudes técnicas detalladas para la tarea que es importante que conozca el técnico.

-  Notas externas que puede ver el cliente. Pueden proporcionar una explicación menos técnica de la tarea que se está realizando, de contrato con el contrato entre el cliente y la empresa de servicios.

Una vez que haya configurado una relación de tarea de servicio entre una tarea de servicio y un pedido de servicio o un acuerdo de servicio, puede especificar esta tarea de servicio al crear líneas de pedido de servicio o líneas de acuerdo de servicio para el pedido de servicio o el acuerdo de servicio actual.

Al generar pedidos de servicio a partir de un acuerdo de servicio, puede usar las tareas de servicio asignadas a cada línea de acuerdo de servicio para agrupar las líneas de pedido de servicio en pedidos de servicio.

## <a name="create-a-service-task"></a>Crear a tarea de servicio

1. Haga clic en **Gestión de servicio** \> **Configuración** \> **Tareas de servicio**.
2. Cree una línea nueva.
3. Especifique el id. del servicio y su descripción.

## <a name="example"></a>Ejemplo

Un técnico debe realizar dos trabajos en una caja de cambios (objeto de servicio GB-1234) en un sitio de cliente. Se crea un acuerdo de servicio para el cliente y varias transacciones se asocian a los trabajos. A continuación se muestra el acuerdo de servicio y las líneas de acuerdo de servicio para los dos trabajos:

### <a name="service-agreement"></a>Acuerdo de servicio

| Project | Acuerdo de servicio | Descripción                                  | Grupo   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Inspección y sustitución de rutina – GB-1234 | Bonificación |

### <a name="service-agreement-lines"></a>Líneas de acuerdo de servicio

| Descripción             | Tipo de transacción | Objeto de servicio | Tarea de servicio |
|-------------------------|------------------|----------------|--------------|
| Inspección y limpieza | Hora             | GB-1234        | I/C - GB1234 |
| Viajes                  | Expense          | GB-1234        | I/C - GB1234 |
| Materiales               | Artículo             | GB-1234        | I/C - GB1234 |
| Sustitución de rutina     | Hora             | GB-1234        | RR - GB1234  |
| GR-1                    | Artículo             | GB-1234        | RR - GB1234  |
| GR-5                    | Artículo             | GB-1234        | RR - GB1234  |

Las líneas de acuerdo de servicio para los dos trabajos tienen dos tareas de servicio vinculadas. Las tareas de servicio determinan las transacciones que pertenecen a cada trabajo. En el primer caso, la tarea de servicio I/C - GB1234 identifica todas las líneas de acuerdo de servicio implicadas en la inspección y limpieza del objeto GB-1234. En el segundo caso, la tarea de servicio RR - GB1234 identifica todas las líneas de acuerdo de servicio implicadas en la finalización de un trabajo de sustitución de rutina.

Las relaciones de tareas de servicio que conectan las tareas de servicio con el contrato específico son como se indica a continuación:

### <a name="service-tasks"></a>Tareas de servicio

| Tarea de servicio | Descripción                             | Nota interna                                                                                                                 | Nota externa                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | Inspección de la caja de cambios GB-1234           | Inspección visual y mecánica y limpieza de la caja de cambios GB-1234                                                              | Inspección de rutina de la caja de cambios |
| RR - GB1234  | Sustitución de rutina de piezas en GB-1234 | Sustitución de servicio de rutina de componentes de GR-1 y GR-5 (para cajas de cambio fabricadas antes de 2002, sustituir también el componente GR-2) | Sustitución de piezas de rutina  |

## <a name="group-service-orders"></a>Agrupar pedidos de servicio

Al crear pedidos de servicio automáticamente, puede usar las tareas de servicio como criterio de agrupación. Para agrupar pedidos de servicios por tareas de servicio, defina el acuerdo de servicio que los pedidos de servicio basados en el acuerdo de servicio deben agruparse por identificador de tarea de servicio como criterio de agrupación inicial.

**Agrupar por tarea de servicio**

1. Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.
2. En la pestaña **Configuración**, seleccione **Por tarea de servicio** en el campo **Combinar pedidos de servicio** .




[!INCLUDE[footer-include](../../includes/footer-banner.md)]