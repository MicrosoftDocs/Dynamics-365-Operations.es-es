---
title: Procesar eventos de vida
description: Durante el ciclo de vida de los empleados en Microsoft Dynamics 365 Human Resources, cada empleado puede sufrir varios cambios en los eventos de la vida.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e512422965fab4fa7a0c4c767ade16904ddb6eb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693154"
---
# <a name="process-life-events"></a>Procesar eventos de vida


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Durante el ciclo de vida de los empleados en Microsoft Dynamics 365 Human Resources, cada empleado puede sufrir varios cambios en los eventos de la vida. Por ejemplo, matrimonio, cambio de empleo o cambio de dependiente/beneficiario. Para usar eventos de vida, debe habilitar los eventos de vida en la página **Parámetros de prestaciones**, configurar los tipos de eventos de vida y configurar las opciones de eventos de vida para los tipos de planes.

Antes de poder procesar eventos de vida, ya debe haber ejecutado la inscripción abierta al menos una vez durante un periodo de contratación. En los Estados Unidos, la inscripción abierta suele ser una vez al año. Fuera de los Estados Unidos, la inscripción abierta puede realizarse al momento de la contratación. Un trabajador no necesita seleccionar un plan de prestaciones para que se procesen los eventos de la vida, pero debe haber sido incluido en el proceso de inscripción abierta. 

Utilice el procesamiento de eventos de vida cuando haya trabajadores que tengan eventos de la vida que tengan lugar en una fecha futura. Este evento procesará todos los eventos de la vida que no se hayan procesado (como eventos de vida futuros o eventos de vida que se hayan agregado que no son específicos de ningún trabajador, por ejemplo, una nueva prestación). Los eventos de vida en tiempo real están ocultos.

Por ejemplo, si hoy es 1 de febrero y está programado que el 14 de febrero el trabajador Joe Smith cambie de entidad jurídica, si ejecuta el procesamiento de eventos de vida para el 15 de febrero, el sistema procesa todos los eventos hasta el 15 de febrero. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de eventos de vida**.

2. En el cuadro de diálogo **Ejecutar proceso de evento de vida**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Período de inscripción** | El periodo de inscripción para procesar eventos de vida. |
   | **Entidad jurídica** | La entidad jurídica para procesar eventos de vida. |
   | **Fecha de evento de vida** | El sistema procesa todos los eventos durante el periodo de inscripción que ocurren hasta esta fecha. |
   | **Trabajador** | El trabajador para procesar eventos de vida. Si deja este campo en blanco, los eventos de vida se procesarán para todos los trabajadores. |

3. Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para proceso.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso se ejecutará con los parámetros que establezca.

4. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
