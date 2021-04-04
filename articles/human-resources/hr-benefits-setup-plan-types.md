---
title: Crear tipos de planes
description: Un tipo de plan en Microsoft Dynamics 365 Human Resources es una agrupación de alto nivel de tipos específicos de prestaciones. Cada tipo de plan tiene un código de tipo de plan que determina reglas para el tipo de plan.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1d8db6900e6b697e988e2a7e9e31828b70e4ad0d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463921"
---
# <a name="create-plan-types"></a>Crear tipos de planes

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un tipo de plan en Microsoft Dynamics 365 Human Resources es una agrupación de alto nivel de tipos específicos de prestaciones. Cada tipo de plan tiene un código de tipo de plan que determina reglas para el tipo de plan. Por ejemplo, el tipo de plan Vida básica tendría el código de tipo de plan Vida porque es un tipo de plan de seguro de vida y debe cumplir las reglas establecidas para el código de tipo de plan de vida. Otro tipo de plan podría ser vida complementaria, también con el código de tipo de plan Vida.

Cada tipo de plan indica si un empleado puede inscribirse en un plan de su tipo o en varios. Por ejemplo, es probable que un empleado pueda inscribirse tanto en las directivas de vida básica como vida complementaria del tipo de plan Vida. Es probable que a un empleado se le permita inscribirse en una sola directiva de tipo médico.

Si un tipo de plan implica contactos, el tipo de plan indica si los contactos son beneficiarios o dependientes. Por ejemplo, un tipo de plan de vida básico tendría beneficiarios, mientras que un tipo de plan médico básico tendría dependientes. En algunos casos, es posible que un plan no tenga contactos personales. Por ejemplo, una cuenta de gastos flexible o una concesión de aparcamiento.

Un tipo de plan puede definir opciones de cobertura. Las opciones de cobertura se definen en el formulario de opción de cobertura. Una opción de cobertura puede especificar el importe del beneficio o los contactos que son aptos para el tipo de plan. Por ejemplo, si el tipo de contacto es Beneficiario, la opción de cobertura debe definir los términos para lo que el beneficiario es elegible para recibir cuando se utiliza la prestación. Si el tipo de contacto es Dependiente, la opción de cobertura debe definir la relación entre el dependiente y el empleado. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tipos de plan**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Tipo de plan** | Un nombre único que identifica el tipo de plan. |
   | **Descripción** | Una descripción del tipo de plan. |
   | **Código de tipo de plan** | Seleccione un código de tipo plan en la lista desplegable de valores. La lista de códigos de tipo de plan muestra todos los tipos de plan admitidos en la versión actual. |
   | **Inscripción simultánea** | Especifica si un empleado puede inscribirse en varios planes de prestaciones del mismo tipo de plan o solo un plan de prestaciones por tipo de plan. |
   | **Tipo de contacto** | Especifica el rol del contacto personal. Los valores son en blanco, Dependiente y Beneficiario. Puede dejar el **Tipo de contacto** en blanco si su tipo de plan no requiere un dependiente o beneficiario según la opción de cobertura. |

4. Para configurar las opciones de eventos de vida, seleccione **Acciones** y luego seleccione **Opciones de eventos de vida**. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Tipo de plan** | El tipo de plan para el que configurar opciones de eventos de vida. |
   | **Identificador del tipo de evento de vida** | El id. del tipo de evento de vida. |
   | **Permitir cancelación** | Especifica si un empleado puede cancelar un plan de prestaciones durante el evento de vida. |
   | **Cambiar opción de cobertura** | Especifica si un empleado puede cambiar opciones de cobertura durante el evento de vida. |
   | **Cambiar a un nuevo plan** | Especifica si un empleado puede cambiar planes durante el evento de vida. |
   | **Cancelar automáticamente el plan** | Especifica si se cancelará automáticamente el plan durante el evento de vida. |
   | **Volver a abrir automáticamente la comprobación de idoneidad** | Especifica si la comprobación de idoneidad de la inscripción en prestaciones se debe volver a abrir automáticamente durante el evento de vida. |
   | **Ventana de notificación** | Especifica la ventana de notificación, en días, del evento de vida. **Nota**: Si no introduce un importe, el sistema supone que la ventana de informes es cero y no procesará el evento de vida. |

5. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]