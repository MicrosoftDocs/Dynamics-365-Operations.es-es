---
title: Planes de compensación
description: Los directores de compensación y de prestaciones pueden usar la Administración de compensaciones para mantener y procesar los planes de compensación variable y fija para los empleados de la organización.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b6dd163b0e956624eb57fa031b918a94609f9cfa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420374"
---
# <a name="compensation-plans"></a>Planes de compensación

Los directores de compensación y de prestaciones pueden usar la Administración de compensaciones para mantener y procesar los planes de compensación variable y fija para los empleados de la organización.

### <a name="introduction"></a>Introducción

La gestión de compensaciones se usa para controlar la entrega de salarios base y primas. El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos. El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable. 

Los empleados pueden estar inscritos a uno o más planes de ambos tipos. Un empleado debe cumplir los requisitos siguientes para que se pueda aplicar para la inscripción a un plan de compensación:
-   El empleado debe tener una asignación de puesto activa.
-   El empleado debe cumplir los criterios definidos por las reglas de elegibilidad para un plan de compensación.

## <a name="compensation-setup"></a>Configuración de la compensación
En la tabla siguiente se muestran los componentes del proceso de compensación que pueden integrar la configuración de los planes de compensación de la empresa.

<table>
<thead>
<tr class="header">
<th>Componente</th>
<th>Más información...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Acciones de compensación fija</td>
<td>Las acciones de compensación fija cumplen dos propósitos:
<ul>
<li>Las acciones pueden especificar el tipo de información que se debe registrar cuando la compensación del empleado cambia. Por ejemplo, se puede requerir que el motivo de un cambio, como una promoción o un descenso, se registre.</li>
<li>Las acciones garantizan que un cálculo se aplique a un proceso de evento cuando se calculan los planes de compensación fija.  Por ejemplo, las acciones del tipo Recursos propios compararán el sueldo de los empleados con el punto de referencia mínimo para el nivel en el empleado y garantiza que el empleado reciba al menos el sueldo mínimo.</li>
</ul></td>
</tr>
<tr class="even">
<td>Niveles</td>
<td>Los niveles están asociados con trabajos y con los puestos relacionados con esos trabajos. Puede crear niveles diferenciados para los tres tipos de planes de compensación: Categoría, Grupo y Paso.</td>
</tr>
<tr class="odd">
<td>Matriz del intervalo de aprovechamiento</td>
<td>Una matriz de uso de intervalos le ayudará en la transición de los empleados al punto de control de sus trabajos. También se puede aplicar el uso de intervalos al control de la equidad del índice salarial en la empresa, sin tener en cuenta el rendimiento individual de un empleado o el rendimiento general de la empresa. Por ejemplo, los empleados con menores pagas en un intervalo obtienen porcentajes de aumento más altos que los empleados que perciben mejores pagas en el intervalo. De esta manera, quedan sistemáticamente anuladas las diferencias entre recursos propios. El uso de intervalos se calcula como sigue: (Índice salarial fijo - mínimo del intervalo) (÷ máximo del intervalo - mínimo del intervalo).</td>
</tr>
<tr class="even">
<td>Parámetros de configuración de puntos de referencia</td>
<td>Una configuración de un punto de referencia incluye un conjunto de puntos de referencia que representan los intervalos de una matriz. Cada intervalo puede estar asociado con un índice salarial. Por ejemplo, los planes de clasificación tendrán a menudo puntos de referencia Mínimo, Punto medio y Máximo.</td>
</tr>
<tr class="odd">
<td>Matriz de compensación</td>
<td>Una matriz de compensación es el conjunto de puntos de referencia y por los niveles que se usan para crear una estructura de compensaciones.</td>
</tr>
<tr class="even">
<td>Estructura de compensación</td>
<td>Una estructura de compensaciones es una matriz de compensaciones que incluye índices salariales asociados con puntos de referencia en cada nivel.</td>
</tr>
<tr class="odd">
<td>Regla de idoneidad</td>
<td>Se usan las reglas de elegibilidad para identificar a los empleados en trabajos específicos, funciones de trabajo, tipos de trabajo, departamentos, sindicatos o regiones de compensación que quedan cubiertos por planes de compensación específicos. Debe crear reglas de idoneidad para los planes de compensación fija y variables para inscribir a empleados en el plan. Después de especificar las reglas de idoneidad para un plan de compensación, puede definir los niveles que se deben aplicar a los trabajos que éste va a cubrir.</td>
</tr>
<tr class="even">
<td>Frecuencias de pago</td>
<td>Las frecuencias de pago se usan para definir el período de tiempo para el cual se especifica la compensación.  Por ejemplo, la frecuencia de pago ayuda a entender si el importe de compensación se especifica como sueldo anual frente a tasa de pago por hora. Las frecuencias de pago se usan también para configurar factores de conversión para convertir importes de compensación de frecuencia mensual, semanal, quincenal y por hora a una frecuencia de pago anual.</td>
</tr>
<tr class="odd">
<td>Regiones de compensación</td>
<td>Las regiones de compensación sirven para especificar la compensación del empleado en función de la ubicación de su área de trabajo.</td>
</tr>
<tr class="even">
<td>Punto de control</td>
<td>El punto de control define qué considerar el índice salarial ideal para todos los empleados de un nivel de compensación. Para estructuras de plan medio, los puntos de control suelen ser el punto medio de los intervalos. Las estructuras de la ficha desplegable raramente usan puntos de control. Puede especificar el punto de control de un plan de compensación fija en el formulario Planes de compensación fija.</td>
</tr>
<tr class="odd">
<td>Funciones de trabajo</td>
<td>Las funciones de trabajo se usan para clasificar y filtrar planes de compensación para trabajos específicos.</td>
</tr>
<tr class="even">
<td>Tipos de trabajo</td>
<td>Los tipos de trabajo se usan para clasificar y filtrar planes de compensación para trabajos específicos.</td>
</tr>
<tr class="odd">
<td>Tipos de compensación variable</td>
<td>Los tipos de compensación variable, como una bonificación en acciones o en efectivo, se configuran en los planes de compensación variable.</td>
</tr>
<tr class="even">
<td>Cuadrículas de compensación</td>
<td>Las cuadrículas de compensación contienen la estructura de compensación.  Las cuadrículas de compensación las pueden usar uno o varios planes de compensación.</td>
</tr>
<tr class="odd">
<td>Planes de rendimiento</td>
<td>Los planes de rendimiento sirven para asociar el rendimiento a una matriz de asignación, de modo que pueda usarse el plan en una estrategia de pago de salario variable por rendimiento.</td>
</tr>
<tr class="even">
<td>Evaluación del rendimiento</td>
<td>Las evaluaciones del rendimiento se usan en los planes de rendimiento para determinar el importe de una prima por méritos o de una prima por rendimiento.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Procesar eventos
Los eventos de proceso se utilizan para calcular información de compensación para un período específico para todos los empleados inscritos en uno o varios planes de compensación fija o variable. Puede ejecutar un evento de proceso repetidamente, por ejemplo, para probar o actualizar los resultados de compensación calculados.

<a name="compensation-events"></a>Eventos de compensación
-------------------

Cada vez que se ejecuta un evento de proceso, se crea un evento de compensación.  Los eventos de compensación contienen los resultados del proceso de compensación para cada empleado incluido en ese evento de proceso.  Cuando los cálculos son correctos, puede cargar el evento de compensación para actualizar los registros de compensación para los empleados afectados por el evento de procesos.

## <a name="recommendations"></a>Recomendaciones
Después de ejecutar un evento de proceso, puede recomendar ajustes en la prima o en el aumento por méritos de un empleado, en función de las directrices calculadas a partir del evento de proceso. Para aplicar las recomendaciones para los empleados, debe habilitar las recomendaciones al configurar los planes de compensación o cuando configura el evento de proceso.



