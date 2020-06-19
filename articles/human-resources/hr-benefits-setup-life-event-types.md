---
title: Configurar tipos de eventos de vida
description: Microsoft Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos donde es válido actualizar la inscripción de prestaciones para empleados.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 9d2633e3ee7f785e3b32489f10d52c965d0c8930
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430012"
---
# <a name="configure-life-event-types"></a>Configurar tipos de eventos de vida

Microsoft Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos donde es válido actualizar la inscripción de prestaciones para empleados. Por ejemplo, casarse o tener un hijo. Cada id. de tipo de evento de vida solo puede asociarse con un tipo de evento de vida. Por ejemplo, si crea una id. de evento de vida llamada Cambio de dirección asociado con el tipo de evento de vida Cambio de dirección de empleado, no puede crear otra id. con la etiqueta Cambio de dirección de empleado y asociarla con el tipo de evento de vida Cambio de dirección de empleado. 

Después de crear tipos de eventos de vida, debe asociarlos con los tipos de planes. Para obtener más información, consulte [Crear tipos de planes](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > Después de crear un evento de vida, debe asociarlo con un tipo de plan. Para obtener más información, consulte [Crear tipos de planes](hr-benefits-setup-life-event-types.md).

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
| **Cambio de la situación laboral** | <ul><li>Trabajador > Empleo</li><li>Página del historial de empleo</li></ul> | Cambio en el estado de empleo |
| **Cambio de dirección del empleado** | <ul><li>Trabajador > Perfil > Direcciones </li><li>Trabajador > Información personal > Contactos personales > Dirección</li></ul> Dirección agregada, editada o eliminada |
| **Cambio de dependiente** | <ul><li>Trabajador > Perfil > Información personal > Contactos personales > Agregar o eliminar un dependiente</li><li>Autoservicio para empleados</li></ul> | Dependiente agregado o eliminado. La relación de contacto personal debe ser hijo, cónyuge, pareja doméstica o excónyuge. Actualizar la fecha **Válido desde** desencadena el evento de vida. Si no actualiza esa fecha, no se activará ningún evento de vida. |
| **Nacimiento o adopción (dependiente)** | <ul><li>Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente</li><li>Autoservicio para empleados</li></ul> | El campo **Fecha de adopción** se rellena. Se necesita la fecha de nacimiento del menor. |
| **Pérdida de cobertura (cónyuge/pareja)** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Pérdida de cobertura | **Pérdida de cobertura** seleccionada para un contacto personal, junto con **Fecha de vigencia** |
| Cambio de empleo de la pareja | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Empleado. | <ul><li>Registro de detalles del dependiente creado y cuadro de **Contacto personal empleado** = Sí</li><li>Caja de **Contacto personal empleado** modificada (Sí o No)</li></ul> |
| **Permiso para ausentarse (cónyuge/pareja)** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Permiso para ausentarse | <ul><li>Registro de detalles del dependiente creado y **EhrLOAEffectiveDate** rellenado</li><li>**personPrivateDetails.EhrIsLOA** se cambia (Sí o No)</li><li>**personPrivateDetails.EhrLOAEffectiveDate** se cambia</li></ul> |
| **Cambio en la cobertura (puesto)** | <ul><li>Haga clic en Trabajador -> Asignación de puestos -> Asignaciones de puesto de trabajador</li><li>Posiciones > Posiciones</li></ul> | <ul><li>Cambiar al puesto en los registros de asignación de puesto de trabajador</li><li>Cambiar de la asignación del trabajador en la posición</li></ul> |
| **Seguro médico (empleado/dependiente)** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Fecha de vigencia del seguro médico | No se activa automáticamente cuando un contacto personal entra en una fecha de vigencia. |
| **Ayuda ordenada por ley** | Trabajador > Perfil > Información personal > Contactos personales > Dependiente > Ayuda ordenada por ley (QMSCO/QDRO y fechas de vigencia | No activa ninguna actualización automática. No afecta a la idoneidad. Registra un evento de vida. |
| **Fallecido** | Trabajador > Perfil > Información personal > Fecha de fallecimiento | Se introduce una fecha de fallecimiento |
| **Prueba del seguro** | <ul><li>Trabajador > Trabajador > Versiones > Historial de empleo > Administrador de fechas > Detalles de prestaciones</li><li> Trabajador > Empleo > Detalles de prestaciones > Fecha de verificación</li></ul> | <ul><li>Un trabajador introduce una fecha de verificación</li><li>Un trabajador establece el campo EvidenceOfInsurability en **Sí**</li></ul> |
| **Beneficiario** | Trabajador > Perfil > Información personal > Contactos personales | Se agrega un contacto personal y las cajas **Beneficiario** y **Fecha de vigencia** se rellenan. El contacto personal debe ser de tipo **Hijo**, **Esposa**, **Pareja**, **Hermano**, **Contacto familiar**, **Otro contacto**, **Padre**, **Beneficiario**, **Organización beneficiaria** o **Beneficiario de fideicomiso**. |
| **Seguro médico para empleados** | Trabajador > Trabajador > Versiones > Historial de empleo > Administrador de fechas > Detalles de prestaciones | <ul><li>**EhrMedicareEligibilityDate** se cambia</li><li>**MedicareEligibile** se establece en **Sí**</li></ul> |
| **Cumpleaños** | Trabajador > Perfil > Información personal > Contactos personales > Detalles del dependiente > Fecha de nacimiento | Se agrega o actualiza una fecha de nacimiento (no después del procesamiento del cambio de evento de vida). Ejemplo: si **Opciones de idoneidad de contacto personal** para un niño se establece en Edad: 26 en Configuración > Beneficios > Opciones de idoneidad de contacto personal y si el personal de recursos humanos ejecuta el procesamiento de cambio de evento de vida cualquier día después de que el dependiente cumpla 26 años, aparece un mensaje advirtiéndoles que el dependiente ya no es idóneo para la cobertura. |
| **Cambio de idoneidad del trabajador (no específico de EE. UU.)** | <ul><li>Trabajador > Empleo</li><li>Trabajador > Trabajador > Versiones > Historial de empleo</li></ul> | <ul><li>El tipo de empleado, la categoría de empleo o los cinco campos de idoneidad definibles por el usuario cambian</li><li>**HcmEmploymentDetail.EhrEmploymentType** cambia (solo procesado para registros detallados de empleo *cambiados*, no procesados para registros de empleo *nuevos*, como recontratación y despido)</li></ul> |
| **Nueva anulación de idoneidad (no específica de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Prestaciones > Anulación de regla de idoneidad | Usar el procesamiento de eventos de vida | EhrBenefitEligibilityRuleOverride.ValidFrom |
| **Cambio de la anulación de la regla de idoneidad (no específica de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Prestaciones > Anulación de regla de idoneidad | Uso del procesamiento de eventos de vida (solo detecta cambios en los campos **ValidFrom** y **ValidTo** en la anulación de la regla de idoneidad) |
| **Expiración de la anulación de la regla de idoneidad (no específica de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Prestaciones > Anulación de regla de idoneidad | Usar el procesamiento de cambios de eventos de vida. Por ejemplo, si edita la fecha de vencimiento de anulación de la regla de idoneidad de un plan para que sea hoy a las 5:00 p. m. y en cualquier momento después de las 5:00 p. m. o los días siguientes ejecuta el proceso de cambio de evento de vida, aparece un mensaje que dice que la anulación de la regla de idoneidad ha expirado. |
| **Nuevo plan de prestaciones (no específico de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Planes > Nuevo | <ul><li>Las opciones de idoneidad se agregan a un plan actual</li><li>Se agrega un nuevo plan con opciones de idoneidad adjuntas</li></ul></br></br>El personal de recursos humanos debe ejecutar el proceso de idoneidad para eventos de vida en este caso. |
| **Cambio de la regla de idoneidad (no específica de EE. UU.)** | Recursos humanos avanzados > Prestaciones > Reglas y opciones > Reglas de idoneidad | Usar el procesamiento de idoneidad de eventos de vida. Registrado cuando los registros **EhrBenefitEligibilityRule** tienen los siguientes valores cambiados: **UseEmplCategory**, **UseEmplStatus** o **UseEmplType**. Solo actualiza las transacciones de eventos de vida que ya existen para una regla modificada o criterios de idoneidad. |
