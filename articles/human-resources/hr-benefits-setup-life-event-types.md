---
title: Configurar tipos de eventos de vida
description: Microsoft Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos donde es válido actualizar la actualización de prestaciones para empleados.
author: andreabichsel
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f04be1c0852970db337766757ff6f412bbf5c38
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921126"
---
# <a name="configure-life-event-types"></a>Configurar tipos de eventos de vida

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos donde es válido actualizar la inscripción de prestaciones para empleados, como al casarse o tener un hijo. Cada id. de tipo de evento de vida solo puede asociarse con un tipo de evento de vida. Por ejemplo, si crea una id. de evento de vida llamada Cambio de dirección asociado con el tipo de evento de vida Cambio de dirección de empleado, no puede crear otra id. con la etiqueta Cambio de dirección de empleado y asociarla con el tipo de evento de vida Cambio de dirección de empleado. Si un tipo de evento de vida no está asociado con un tipo de plan, el tipo de evento de vida no desencadenará un evento de vida. Para obtener más información, consulte [Crear tipos de planes](hr-benefits-setup-plan-types.md).

## <a name="create-a-life-event-type"></a>Crear un tipo de evento de vida

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tipos de eventos de vida**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Identificador del tipo de evento de vida** | El identificador único del tipo de evento de vida. |
   | **Descripción** | Una descripción del tipo de evento de vida. |
   | **Tipo de evento de vida** | Un catalizador para actualizar la inscripción de prestaciones de un empleado. Para obtener una lista de eventos de la vida, consulte [Eventos de vida](hr-benefits-setup-payment-frequencies.md?life-events) más abajo. |

4. Seleccione **Guardar**.

## <a name="view-attached-plans"></a>Ver los planes adjuntos

Puede ver una lista de planes adjuntos al tipo de evento de vida seleccionado. Los eventos de vida están asociados a un tipo de plan y los tipos de plan están asociados a un plan.

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tipos de eventos de vida**.

2. Seleccione **Acciones**.

3. Seleccione **Planes adjuntos**.

## <a name="life-events"></a>Eventos de vida

Puede elegir entre los siguientes eventos de vida cuando cree un tipo de evento de vida:

| Evento de vida | Ubicación | Activador |
| --- | --- | --- |
| **Cambio de estado civil** | Trabajador > Perfil > Información personal > Estado civil| Cambio en el estado civil |
| **Cambio de la situación laboral** | Trabajador > Empleo<br>Página del historial de empleo | Para un trabajador con un detalle de empleo existente, la creación de un nuevo detalle de empleo con un estado laboral diferente desencadenará un evento de vida.  La actualización de un detalle de empleado existente con un estado laboral diferente también desencadenará un evento de vida.  |
| **Cambio de dirección del empleado** | Trabajador > Perfil > Direcciones<br>Trabajador > Información personal > Contactos personales > Dirección | Cambio de domicilio. La dirección debe ser la principal para desencadenar un evento de vida. |
| **Cambio de dependiente** | Trabajador > Perfil > Información personal > Contactos personales<br>Autoservicio para empleados | Agregue un contacto personal especificándolo como dependiente y definiendo **Válido desde**. Información de **Válido hasta** de dependiente de un contacto personal. La relación de contacto personal debe ser hijo, cónyuge, pareja doméstica o excónyuge.  |
| **Nacimiento o adopción (dependiente)** | Trabajador > Perfil > Información personal > Contactos personales<br>Autoservicio para empleados > Editar datos personales > Contactos personales | La **Fecha de nacimiento** o la **Fecha de adopción** se agregan o actualizan. Se necesita la **Fecha de nacimiento** del hijo. |
| **Pérdida de cobertura (cónyuge/pareja)** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Pérdida de cobertura | **Pérdida de cobertura** seleccionada para un contacto personal, junto con **Fecha de vigencia** |
| Cambio de empleo de la pareja | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Empleado | Creación de un contacto personal y establecimiento de **Empleado** en **Sí**. Actualización de un contacto personal y cambio de **Empleado**.  |
| **Permiso para ausentarse (cónyuge/pareja)** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Permiso para ausentarse | Contacto personal creado y definida la **Fecha de vigencia del permiso de ausencia**. Se actualiza el **Permiso de ausencia** del contacto personal. Se actualiza la **Fecha de entrada en vigor del permiso de ausencia** del contacto personal.  |
| **Cambio en la cobertura (puesto)** | Haga clic en Trabajador -> Asignación de puestos -> Asignaciones de puesto de trabajador<br>Posiciones > Posiciones | Cambiar al puesto en los registros de asignación de puesto de trabajador. Cambio de la asignación del trabajador en la posición. |
| **Cambio en la cobertura (salario)** | Trabajador > Compensación > Plan fijo<br>Trabajador > Información personal > Salario anual de prestaciones | Si Gestión de prestaciones > Parámetros compartidos de recursos humanos > Prestaciones > Salario anual de prestaciones no está habilitado, la actualización de Trabajador > Compensación > Plan fijo creará un evento de vida. Si Gestión de prestaciones > Parámetros compartidos de recursos humanos > Prestaciones > Salario anual de prestaciones está habilitado, la actualización de Trabajador > Información personal > Salario anual de prestaciones. |
| **Seguro médico (empleado/dependiente)** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Fecha de vigencia del seguro médico | Agregar o actualizar la fecha de **Entrada en vigor de asistencia sanitaria** para un contacto personal crea este evento de vida. |
| **Ayuda ordenada por ley** | Trabajador > Perfil > Información personal > Contactos personales > Dependiente > Ayuda ordenada por ley (QMSCO/QDRO y fechas de vigencia | Al crear un contacto personal, se creará un evento de vida si **Manutención ordenada por tribunal** está en **Sí**. La actualización de **Manutención ordenada por tribunal** o **Fecha de vencimiento ordenada por tribuna** también desencadenará un evento de vida. |
| **Fallecido** | Trabajador > Perfil > Información personal > Fecha de fallecimiento | Se introduce o actualiza una fecha de fallecimiento. |
| **Prueba del seguro** | Trabajador > Trabajador > Versiones > Historial de empleo > Administrador de fechas > Detalles de prestaciones | **Prueba de asegurabilidad** se establece en **Sí**. **Prueba de la fecha de verificación de asegurabilidad** está definida. |
| **Beneficiario** | Trabajador > Perfil > Información personal > Contactos personales | Se agrega un contacto personal y las cajas **Beneficiario** y **Fecha de vigencia** se rellenan. El contacto personal debe ser de tipo **Hijo**, **Esposa**, **Pareja**, **Hermano**, **Contacto familiar**, **Otro contacto** o **Padre**. |
| **Seguro médico para empleados** | Trabajador > Trabajador > Versiones > Historial de empleo > Administrador de fechas > Detalles de prestaciones | **Idóneo para asistencia sanitaria** está establecido en **Sí**. **Fecha de idoneidad para asistencia sanitaria** se cambia. |
| **Cumpleaños** | Gestión de prestaciones > Procesamiento de cambios de eventos de vida | Estos eventos de vida se crean a partir de **Procesamiento de cambios de eventos de vida**. El proceso analiza el período elegido y la entidad jurídica, y encuentra trabajadores asociados. Calcula su último cumpleaños y crea un evento de vida de cumpleaños si aún no se ha creado uno. |
| **Cambio de idoneidad del trabajador (no específico de EE. UU.)** | Trabajador > Empleo<br>Trabajador > Trabajador > Versiones > Historial de empleo | Crea un evento de vida cuando:<br><ul><li>Se crea un nuevo empleo, hay un empleo anterior y el tipo de trabajador cambia.</li><li>Se crea un nuevo detalle de empleo, hay un detalle empleo anterior y el tipo de empleo o la categoría de empleo cambia.</li><li>Se definen la actualización de un registro de empleo y un tipo de trabajador diferente.</li><li>Se especifica la actualización de un registro de detalles de empleo y un tipo o categoría de empleo diferente.</li></ul> |
| **Nueva anulación de idoneidad (no específica de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Prestaciones > Anulación de regla de idoneidad | Usar el procesamiento de eventos de vida<br>La creación de una nueva anulación de idoneidad del plan de prestaciones para un trabajador desencadena este evento de vida.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Cambio de la anulación de la regla de idoneidad (no específica de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Prestaciones > Anulación de regla de idoneidad | La actualización de **Válido desde** o **Válido hasta** en una anulación de idoneidad del plan de beneficios desencadena este evento de vida. |
| **Expiración de la anulación de la regla de idoneidad (no específica de EE. UU.)** | Gestión de prestaciones > Procesamiento de cambios de eventos de vida  | Estos eventos de vida se crean a partir de **Procesamiento de cambios de eventos de vida**. El proceso analiza el período elegido y la entidad jurídica, y encuentra anulaciones de idoneidad de planes de prestaciones asociados. Crea eventos de vida si las anulaciones han expirado. |
| **Nuevo plan de prestaciones (no específico de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Nuevo | Las opciones de idoneidad se agregan a un plan actual. Se agrega un nuevo plan con opciones de idoneidad adjuntas.</br></br>El personal de recursos humanos debe ejecutar el proceso de idoneidad para eventos de vida en este caso. |
| **Cambio de la regla de idoneidad (no específica de EE. UU.)** | Gestión de beneficios > Reglas de idoneidad | Usar el procesamiento de idoneidad de eventos de vida. Registrado cuando los registros **BenefitEligibilityRule** tienen los siguientes valores cambiados: **UseEmplCategory**, **UseEmplStatus** o **UseEmplType**. Solo actualiza las transacciones de eventos de vida que ya existen para una regla modificada o criterios de idoneidad. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]