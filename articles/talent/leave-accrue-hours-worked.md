---
title: Acumulación de licencias basada en las horas trabajadas
description: Este tema describe cómo los planes de licencia se pueden configurar para acumular tiempo libre basado en las horas trabajadas.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 938d2eea7b9e85b19e9c1e3e0930f625224b880d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898628"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Acumulación de licencias basada en las horas trabajadas

## <a name="overview"></a>Información general

Las organizaciones con empleados por horas pueden otorgar tiempo libre en función de las horas trabajadas en lugar de ocupación en la organización. Las datos de las horas trabajadas se almacenan normalmente en un sistema de asistencia y tiempo. En Talent: Core HR esas horas regulares y extras trabajadas pueden importarse y usarse como base para otorgar un premio a un empleado.

## <a name="leave-plans"></a>Planes de licencias

Dentro del plan de licencia, el tipo de acumulación puede ser de meses de servicio o de horas trabajadas. Cuando se seleccionan las horas trabajadas, hay dos tipos de horas que deben usarse para la provisión: regulares y horas extra.

Para configurar un plan de licencia para utilizar horas trabajadas, siga estos pasos:

1. En la página **Planes de bajas y ausencias**, haga clic en **Crear nuevo plan**.
2. Escriba un nombre para el plan de baja.
3. Seleccione la frecuencia de acumulación del plan.
5. Seleccione la fecha inicial del plan.
6. Elija la base del período de acumulación y seleccione la fecha específica del empleado, si procede.
7. En la programación de la acumulación, seleccione **Horas trabajadas** como tipo de acumulación.
8. Seleccione el tipo de horas que deben usarse para la acumulación.
9. Indique la cantidad de horas trabajadas y el importe de acumulación asociado, el saldo mínimo, y la transferencia máxima o el importe de concesión.

El procesamiento de la acumulación de los planes de horas trabajadas usa la frecuencia de acumulación, junto con la base del período de acumulación para determinar las horas que se acumularán.

## <a name="annual-accrual-frequency"></a>Frecuencia de acumulación anual

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2000                | 0                 |


## <a name="monthly-accrual-frequency"></a>Frecuencia de acumulación mensual

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 1/8/2018-31/8/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 1/8/2018-31/8/2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>Frecuencia de acumulación semimensual

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>Frecuencia de acumulación semanal

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Planes de licencias asignados al empleado

En los planes de la licencia asignados del empleado, se mostrará la base del nivel y el tipo de horas para los planes en los que las horas trabajadas se definen como el tipo de acumulación. Para los planes activos, las horas reales trabajadas para los períodos de acumulación a partir de la fecha actual también se muestran para la referencia. 

## <a name="loading-data"></a>Cargando datos

Las horas reales se pueden importar usando la entidad de horas de ausencia y baja trabajadas en administración de datos. Si utiliza calendarios de horario de trabajo, la importación validará que las horas normales trabajadas no superen las horas programadas en un día definidas mediante el calendario. La importación también comprueba que las horas trabajadas de un día determinado no superen 24 horas. 

La siguiente información se necesita para importar horas reales que se utilizarán en el proceso de acumulación de licencia:

+ Número de personal 
+ Fecha trabajada
+ Tipo
+ Horas

Una única fecha solo puede tener uno de cada tipo asociada a ella.

| NÚMERO PERSONAL       | FECHAS DE TRABAJO           | TIPO                  | HORAS                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Normal               | 8                    |       
| 000337                | 8/7/2018             | Normal               | 8                    |
| 000337                | 8/7/2018             | Horas extra              | 3                    |
| 000337                | 8/8/2018             | Normal               | 8                    |
| 000337                | 8/7/2018             | Normal               | 8                    |
| 000337                | 8/9/2018             | Normal               | 8                    |
