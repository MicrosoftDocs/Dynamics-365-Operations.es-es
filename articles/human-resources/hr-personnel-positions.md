---
title: Puestos
description: Este tema describe los elementos conceptuales que puede incluir un puesto. También proporciona ejemplos que muestran cómo puede utilizar esos elementos en su organización.
author: twheeloc
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bb7582165f49c40d294acd3cf804fe89782936c4
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689449"
---
# <a name="positions"></a>Puestos


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe los elementos conceptuales que puede incluir un puesto. También proporciona ejemplos que muestran cómo puede utilizar esos elementos en su organización.

Antes de poder crear un puesto, se debe configurar un trabajo. Algunos detalles del puesto, como la región de compensación, la asignación del trabajador, la duración del puesto y la relación de informes, tienen vigencia desde la fecha.

## <a name="general-information"></a>Información general

Cuando crea un puesto, debe seleccionar un trabajo. La siguiente información se completará automáticamente a partir del trabajo que seleccione:

- Descripción
- Cargo
- Equivalente de jornada completa
- Familia de trabajos

El título del puesto se utiliza para hacer referencia al título de un empleado. (No se usa el título que figura en el empleado). Por lo tanto, los títulos de los puestos deben estandarizarse tanto como sea posible.

> [!NOTE]
> No se puede asignar a un trabajador a un puesto en una fecha anterior a la fecha de disponibilidad para asignación.
>
> Un parámetro en la pestaña **Posiciones** de la página **Parámetros compartidos de recursos humanos** controla el comportamiento de la asignación del trabajador. Seleccione uno de los siguientes valores:
>
> - **Siempre:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Cuando se crean los puestos, la fecha y la hora **Disponibles para la asignación** en la pestaña **General** de la página **Puesto** se cambian automáticamente a la fecha y hora de la creación.
> - **Nunca:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos. Si selecciona esta opción, debe abrir la página **Posición** para cada nueva posición a medida que esté disponible. Entonces, en la pestaña **General**, ingrese la fecha **Disponible para asignación** para habilitar la asignación de trabajadores. Si selecciona esta opción, la fecha de asignación del trabajador se establecerá en **Nunca** de forma predeterminada cuando intenta asignar el trabajador.

## <a name="position-duration"></a>Duración del puesto

Cada puesto es efectivo durante un período de tiempo específico que se denomina duración. Por ejemplo, los puestos de verano podrían tener una duración del 1 de mayo de 2021, hasta el 31 de agosto de 2021. La fecha de activación es la fecha en que el puesto está activo en el sistema. La fecha de retirada es la fecha en que el puesto ya no está activo en el sistema.

Tenga en cuenta que ni la fecha de disponibilidad para asignación ni la fecha de asignación del trabajador pueden ser anteriores a la fecha de activación. Un puesto no se considera activo hasta que se alcanza la fecha de activación. Además, la asignación de un trabajador no puede extenderse más allá de la fecha de jubilación del puesto.

## <a name="reports-to-position"></a>Notifica al puesto

Los puestos son elementos importantes en el nivel inferior de una jerarquía organizativa. En la página **Puesto**, puede especificar el puesto de mayor jerarquía para un puesto subordinado. Al asignar un trabajador a un puesto que es subordinado de otro puesto, crea una relación jerárquica entre los trabajadores asignados a esos dos puestos. Por ejemplo, la posición 000220 informa a la posición 000300. Kim Akers se asigna al puesto 000220 y Sanjay Patel se asigna al puesto 000300. Por lo tanto, Kim Akers informa a Sanjay Patel.

> [!TIP]
> La posición de informes a se utiliza en todo el sistema para determinar quién es el gerente de un empleado. En el ejemplo anterior, si el rol de gerente se asigna a Sanjay Patel en el sistema, verá a Kim Akers como un subordinado directo en el autoservicio del gerente. La relación de informes también se puede utilizar al crear reglas de enrutamiento de flujo de trabajo y tareas de lista de verificación.

## <a name="relationships"></a>Relaciones

Si su organización utiliza una jerarquía matricial u otra jerarquía personalizada, puede configurar tipos de jerarquía de puestos. A continuación, puede agregar relaciones de informes a los puestos para cada tipo de jerarquía que configure. Por ejemplo, Lorri Penor es directora general de Adventure Works y está asignada al puesto **Director general**. Lorri gestiona el desarrollo de un producto que se usa para limpiar widgets. Ella necesita un contador que la ayude con las finanzas. Por lo tanto, reclutó a Kim Akers para ser su contable. Kim es subordinado directo de Sanjay Patel, pero también trabaja con Lorri Penor en su trabajo relacionado con las finanzas para el desarrollo del limpiador widgets.

Para el ejemplo anterior, debe completar las tareas siguientes para configurar la relación de trabajo entre Kim Akers y Lorri Penor:

1. Cree un tipo de jerarquía de puestos personalizado denominado **Widget** para crear una jerarquía que incluya los puestos que son responsables de trabajar en el producto limpiador de widgets.
2. Especifique el puesto **Director general** como puesto del que será subordinado el puesto Kim en la jerarquía de **Widget**.
3. Use la jerarquía de puestos para ver la estructura de la jerarquía de puestos subordinados. Si tiene varias jerarquías de puestos, puede ver la jerarquía para cada tipo de jerarquía en la jerarquía de puestos. También puede buscar un puesto por el identificador de puesto o mediante el nombre del trabajador asignado al puesto. La jerarquía de puestos es una jerarquía organizativa.

## <a name="labor-union"></a>Sindicato

Puede registrar si se requiere un acuerdo sindical para el puesto y qué sindicato se utiliza. También puede asociar el acuerdo con una entidad jurídica.

## <a name="financial-dimensions"></a>Dimensiones financieras

Cuando crea la dimensión financiera para un puesto, debe especificar una entidad legal. Puede seleccionar las dimensiones predeterminadas para cada dimensión individualmente. Alternativamente, puede seleccionar una plantilla de distribución para completar automáticamente las dimensiones predeterminadas. Una plantilla de distribución también ofrece la opción de asignar cantidades a varios valores de dimensión.
