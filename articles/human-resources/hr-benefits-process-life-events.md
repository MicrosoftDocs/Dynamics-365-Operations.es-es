---
title: Procesar eventos de vida
description: Durante el ciclo de vida de los empleados en Microsoft Dynamics 365 Human Resources, cada empleado puede sufrir varios cambios en los eventos de la vida.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 91812432ead4b0afccfba30f8023f014e216236a
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010478"
---
# <a name="process-life-events"></a>Procesar eventos de vida

[!include [banner](includes/preview-feature.md)]

Durante el ciclo de vida de los empleados en Microsoft Dynamics 365 Human Resources, cada empleado puede sufrir varios cambios en los eventos de la vida. Por ejemplo, matrimonio, cambio de empleo o cambio de dependiente/beneficiario. Para usar eventos de vida, debe habilitar los eventos de vida en el formulario de parámetros de prestaciones, configurar los tipos de eventos de vida y configurar opciones de eventos de vida para tipos de planes.

Antes de poder procesar eventos de vida, ya debe haber ejecutado la inscripción abierta al menos una vez durante un periodo de contratación. En los Estados Unidos, la inscripción abierta suele ser una vez al año. Fuera de los Estados Unidos, la inscripción abierta puede realizarse al momento de la contratación. Un trabajador no necesita seleccionar un plan de prestaciones para que se procesen los eventos de la vida, pero debe haber sido incluido en el proceso de inscripción abierta. 

Utilice el procesamiento de eventos de vida cuando haya trabajadores que tengan eventos de la vida que tengan lugar en una fecha futura. Este evento procesará todos los eventos de la vida que no se hayan procesado (como eventos de vida futuros o eventos de vida que se hayan agregado que no son específicos de ningún trabajador, por ejemplo, una nueva prestación). Los eventos de vida en tiempo real están ocultos.

Por ejemplo, si hoy es 1 de febrero y está programado que el 14 de febrero el trabajador Joe Smith cambie de entidad jurídica, si ejecuta el procesamiento de eventos de vida para el 15 de febrero, el sistema procesa todos los eventos hasta el 15 de febrero. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de eventos de vida**.

2. En el cuadro de diálogo **Ejecutar proceso de evento de vida**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | Período de inscripción | El periodo de inscripción para procesar eventos de vida. |
   | Entidad jurídica | La entidad jurídica para procesar eventos de vida. |
   | Fecha de evento de vida | El sistema procesa todos los eventos durante el periodo de inscripción que ocurren hasta esta fecha. |
   | Trabajador | El trabajador para procesar eventos de vida. Si deja este campo en blanco, los eventos de vida se procesarán para todos los trabajadores. |

3. Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para proceso.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso se ejecutará con los parámetros que establezca.

4. Seleccione **Aceptar**.
