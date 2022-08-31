---
title: Descripción general del tipo de plan
description: Un tipo de plan en Microsoft Dynamics 365 Human Resources es una agrupación de alto nivel de tipos específicos de prestaciones.
author: twheeloc
ms.date: 08/24/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6ca14156c165ca3f536fc0120ebd03883284eb18
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337077"
---
# <a name="plan-type-overview"></a>Descripción general del tipo de plan

[!include [banner](../includes/preview-banner.md)]

Un tipo de plan es una agrupación de alto nivel de tipos específicos de prestaciones. Cada tipo de plan tiene un código de tipo de plan que determina reglas para el tipo de plan. Por ejemplo, el tipo de plan **Vida básica** tendría el código de tipo de plan **Vida** porque es un tipo de plan de seguro de vida y debe cumplir las reglas establecidas para el código de tipo de plan de **Vida**. Otro tipo de plan podría ser **Vida suplementaria**. Este tipo de plan también tendrá el código de tipo de plan de **Vida** código de tipo de plan.

Cada tipo de plan indica si un empleado puede inscribirse en un plan de su tipo o en varios. Por ejemplo, es probable que un empleado pueda inscribirse tanto en las directivas de **vida básica** como **vida complementaria** del tipo de plan Vida. Es probable que a un empleado se le permita inscribirse en una sola directiva de tipo médico.

Si un tipo de plan implica contactos, el tipo de plan indica si los contactos son beneficiarios o dependientes. Por ejemplo, un tipo de plan de **vida básico** tendría beneficiarios, mientras que un tipo de plan médico básico tendría dependientes. En algunos casos, es posible que un plan no tenga contactos personales. Por ejemplo, una cuenta de gastos flexible o una concesión de aparcamiento.


Un tipo de plan puede definir opciones de cobertura. Las opciones de cobertura se definen en la página **Opciones de cobertura**. Una opción de cobertura puede especificar el importe del beneficio o los contactos que son aptos para el tipo de plan. Por ejemplo, si el tipo de contacto es **Beneficiario**, la opción de cobertura debe definir los términos para lo que el beneficiario es elegible para recibir cuando se utiliza la prestación. Si el tipo de contacto es **Dependiente**, la opción de cobertura debe definir la relación entre el dependiente y el empleado. 

> [!IMPORTANT]
> La página **Tipos de plan** incluye datos clave que afectan a las opciones que hay disponibles cuando se crea un nuevo plan de beneficios:
>
> - **Código de tipo de plan**: este campo afecta lo que se muestra en la pestaña **Configuración** cuando se configura la prestación real.  
> - **Inscripción concurrente**: este campo determina si se permiten múltiples inscripciones. (Para un plan médico, este campo generalmente se establece en **Una inscripción**).
> - **Tipo de contacto**: este campo permite agregar dependientes o beneficiarios a un plan. Si está configurado para **Ninguno**, los empleados que se inscriban en las prestaciones no tendrán la opción de seleccionar un beneficiario o un dependiente.
> - **Opciones de cobertura**: utilice este campo para vincular las opciones de cobertura con los tipos de planes. Define las personas que estarán cubiertas por este tipo de plan o los montos de cobertura que están disponibles para este tipo de plan. Por ejemplo, puede especificar que la cobertura para un tipo de plan médico estará disponible solo para el empleado, el empleado y otra persona, o el empleado y su familia.

## <a name="create-plan-types"></a>Crear tipos de planes

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
   | **Cambiar opción de cobertura** | Especifica si un empleado puede cambiar opciones de cobertura durante el evento de vida. |
   | **Cambiar a un nuevo plan** | Especifica si un empleado puede cambiar planes durante el evento de vida. |
   | **Volver a abrir automáticamente la comprobación de idoneidad** | Especifica si la comprobación de idoneidad de la inscripción en prestaciones se debe volver a abrir automáticamente durante el evento de vida. |
   | **Período de inscripción de evento de vida** | Especifica la ventana de notificación, en días, del evento de vida. **Nota**: Si no introduce un importe, el sistema supone que la ventana de informes es cero y no procesará el evento de vida. |
   | **Solo editable por administradores** | Especifica si los administradores pueden cancelar o editar un plan durante un evento de vida. El empleado no puede realizar cambios en el espacio de trabajo **Autoservicio para los empleados**. |
   | **Cancelar automáticamente el plan** | Especifica si se debe cancelar automáticamente el plan durante un evento de vida. Después de procesar los cambios de eventos de vida, la opción **Plan de cancelación automática** conservará la selección del plan. Solo el estado **Confirmado** o **Controlado** se eliminará. El plan permanece seleccionado. Por lo tanto, los empleados que no seleccionen un plan durante el período de inscripción del evento de vida no perderán la selección del plan. 

5. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
