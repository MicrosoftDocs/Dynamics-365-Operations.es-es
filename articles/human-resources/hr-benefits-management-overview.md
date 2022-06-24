---
title: Información general de administración de prestaciones
description: Este artículo proporciona información general sobre la función Administración de beneficios de Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f008c273a3088353c33ae8c4b0b3cbc6b274fbcf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901158"
---
# <a name="benefits-management-overview"></a>Información general de administración de prestaciones


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Para seguir siendo competitivo, debe ofrecer un amplio conjunto de prestaciones para atraer y retener a sus mejores empleados. Además de las prestaciones estándar como la cobertura médica y dental, es posible que también quiera ofrecer servicios ampliados como asistencia de adopción, programas de recreación y asignaciones de ropa. La administración de beneficios de Microsoft Dynamics 365 Human Resources ofrece una solución flexible que admite una amplia variedad de opciones de prestaciones. Recursos humanos también incluye una experiencia fácil de usar para los empleados que muestra sus ofertas.

- Los planes de prestaciones mejoradas le permiten crear y administrar planes de prestaciones únicas y admitir tablas complejas de tasas de prestaciones y niveles anidados. Puede crear fácilmente programas de beneficios, agrupaciones y reglas de inscripción automática para una experiencia más fácil para los empleados.
- Los programas de crédito flexible le permiten prorratear para asistir en la jubilación y otros eventos de la vida.
- Las extensas reglas de idoneidad garantizan que las prestaciones adecuadas estén disponibles para los empleados correctos.
- La inscripción de prestaciones en línea ofrece una experiencia fácil para sus empleados.
- El procesamiento calificado de eventos de vida admite eventos de vida futuros.

Si desea acceder a los datos de demostración, deberá volver a implementar su entorno de espacio aislado.

> [!NOTE]
> Ahora puede personalizar las páginas de administración de prestaciones. Se pueden agregar campos personalizados relacionados con las tasas de cobertura a la página **Opción de cobertura** para planes de prestaciones. Para obtener más información sobre el trabajo con campos personalizados, consulte [Campos personalizados](hr-developer-custom-fields.md).
>
> ![Campos personalizados de gestión de prestaciones](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Habilitar la administración de prestaciones

Este artículo describe cómo activar las características en Recursos humanos. También se explica qué características existentes en Human Resources son reemplazadas por la administración de prestaciones y qué características se desactivan tras activar la administración de prestaciones.

> [!IMPORTANT]
> Después de habilitar la gestión de prestaciones en un entorno de **Producción**, no puede deshabilitarlo. Recomendamos habilitar y probar la gestión de prestaciones en un entorno **Espacio aislado** antes de habilitarlo en un entorno de **Producción**. Existen diferencias significativas entre la funcionalidad de prestación heredada y la nueva funcionalidad de administración de prestaciones que requieren una configuración adicional y deben probarse antes de su puesta en producción.

Para obtener más información, vea [Administrar funciones](hr-admin-manage-features.md).

## <a name="process-overview"></a>Visión general del proceso

El proceso de configuración de prestaciones implica las siguientes tareas:

1.  Configure la información de prestaciones requerida.
2.  Configure la información de prestaciones opcional.
3.  Configurar planes de prestaciones.
4.  Configurar programas de crédito flexible (opcional).
5.  Configure la información requerida de los empleados.
6.  Configure la información opcional de los empleados.
7.  Procese a los empleados para determinar la elegibilidad.
8.  Los empleados seleccionan planes a través del autoservicio para empleados (opcional).
9.  Confirme las selecciones de planes de empleados.
10. Usar el procesamiento de eventos de vida (opcional).
11. Actualizaciones de tarifas (opcional).

## <a name="set-up-required-benefit-information"></a>Configure la información de prestaciones requerida

Antes de que los empleados puedan inscribirse en los planes, se deben configurar varios componentes:

- **Parámetros de gestión de prestaciones** - Estas configuraciones se comparten entre empresas. Puede establecer códigos de motivo predeterminados, habilite la opción **Salario anual de prestaciones**, establezca una frecuencia de pago predeterminada para las nuevas contrataciones y habilite los eventos de la vida. Para más información, vea [Establecer parámetros de gestión de prestaciones](hr-benefits-setup-parameters.md).
- **Opciones de elegibilidad de contacto personal** - Los contactos personales son las personas que serán dependientes o beneficiarios de los planes que se establezcan. Por lo general, son hijos, cónyuges u organizaciones fiduciarias. Para más información, consulte [Configurar las opciones de elegibilidad de contacto personal](hr-benefits-setup-contact-eligibility-options.md).
- **Opciones de cobertura** - Configure los tipos de cobertura que estarán disponibles para un plan. Específicamente, defina quién debe estar cubierto o cuánta cobertura está disponible. Para obtener más información, consulte [Crear opciones de cobertura](hr-benefits-setup-coverage-options.md).
- **Tipos de planes** - Configure los tipos de planes que estarán disponibles cuando cree un plan de beneficios. Ejemplos de tipos de planes incluyen **Dental**, **Visión**, y **Ahorros**. Algunas configuraciones importantes en el tipo de plan determinan las configuraciones que están disponibles en el plan de beneficios. Para obtener más información, consulte [Crear tipos de planes](hr-benefits-setup-plan-types.md).
- **Reglas de elegibilidad** - Las reglas de elegibilidad se utilizan para determinar si un empleado es elegible para un plan. Se debe asociar al menos una regla de elegibilidad con cada plan de beneficios. Para más información, consulte [Configurar las reglas y opciones de elegibilidad](hr-benefits-setup-eligibility-rules.md).
- **Frecuencias de pago** - Se requieren frecuencias de pago cuando se configuran las tasas de beneficios. La frecuencia de pago que se utiliza en una tasa ayuda a identificar la cantidad que el empleado y / o empleador debe semanalmente, mensualmente o anualmente. Para obtener más información, consulte [Configurar frecuencias de pago](hr-benefits-setup-payment-frequencies.md).
- **Tarifas** - Las tarifas definen cuánto le costará un beneficio al empleado o al empleador. Si se debe asignar dinero a un empleado (por ejemplo, un crédito para la pertenencia a un gimnasio), se ingresa una tasa negativa. Para obtener más información consulte [Configurar tasas](hr-benefits-setup-rates.md).
- **Nivel de tarifas** - Los niveles de tarifas se utilizan cuando una tarifa debe cambiar según algunos criterios. La tasa de nivel más común es un nivel único que se basa en la edad. Sin embargo, también se pueden configurar tarifas de doble nivel, donde la tarifa puede cambiar según el sexo, la edad u otros criterios.
- **Deducciones** - Las deducciones son básicamente la información / códigos de encabezado que se pasarán al sistema de nómina para identificar la deducción por el beneficio. Debe configurar estas deducciones, ya que serán necesarias en el plan de prestaciones. Para obtener más información consulte [Configurar deducciones](hr-benefits-setup-deductions.md).
- **Períodos de prestación** - Un período de prestación es el período en el que los empleados tendrán cobertura de prestaciones. También se conoce como año del plan. Los períodos de inscripción abierta también se configuran aquí.

## <a name="set-up-optional-benefit-information"></a>Configure la información de prestaciones opcional

No es necesario configurar los siguientes componentes para crear un plan de prestaciones:

- **Programas** - Un programa es un conjunto de prestaciones que se rigen por las mismas reglas de elegibilidad. Por ejemplo, todos en el departamento de ventas pueden obtener un teléfono celular.
- **Paquetes** - Un paquete es un grupo de prestaciones, donde se debe seleccionar un plan antes de que la opción para seleccionar planes adicionales esté disponible. Por ejemplo, un plan médico con deducible alto podría combinarse con un plan de cuenta de ahorros para la salud (HSA).
- **Tipos de eventos de la vida** - Los eventos de la vida son eventos que permiten un cambio en la cobertura de un empleado. Los tipos de eventos de la vida están vinculados a un tipo de plan. Por ejemplo, un tipo de plan médico puede permitir cambios en los planes debido a un nacimiento o adopción, o debido a un cambio en el estado civil. Sin embargo, es posible que un tipo de plan de seguro no permita ningún cambio debido a eventos de la vida. Para obtener más información, consulte [Configurar tipos de eventos de vida](hr-benefits-setup-life-event-types.md).
- **Días de espera y períodos de espera** - Se puede establecer un período de espera de cobertura en un plan de beneficios. Por ejemplo, un empleado recién contratado podría inscribirse en un 401 (k) solo después de tres meses de empleo. En este caso, el período de espera es de tres meses. Los días de espera se utilizan en el período de espera si las nuevas inscripciones se pueden procesar y enviar al proveedor solo en un día específico del mes. Por ejemplo, si las inscripciones al 401 (k) se pueden procesar solo el día quince del mes, después de tres meses de empleo, el período de espera que se establece es de tres meses y el día de espera es el día quince. Para más información, consulte [Configurar días de espera](hr-benefits-setup-waiting-days.md) y [Configurar periodos de espera](hr-benefits-setup-waiting-periods.md).
- **Códigos de motivo** - Los códigos de motivo se utilizan para explicar por qué un beneficio podría estar cambiando para un empleado. Para obtener más información, vea [Configurar códigos de motivo](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Configurar planes de prestaciones

Cuando configura un plan de prestaciones, debe completar los siguientes pasos antes de que los empleados puedan inscribirse:

- Asignar un período de prestación.
- Vincular opciones de cobertura.
- Establezca una fecha válida desde y hasta en la pestaña **General**.
- Asigne al menos una regla de elegibilidad.
- Seleccione el campo **Permitir / continuar la inscripción** en la pestaña **Configuración**.

Para obtener más información acerca de la configuración de planes de prestaciones, consulte [Configurar planes de prestaciones](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Configurar programas de crédito flexible (opcional)

Puede usar programas de crédito flexible para inscribir a los empleados en prestaciones de acuerdo con un número predeterminado de créditos flexibles. Los empleados pueden elegir cómo asignar sus créditos flexibles. Por ejemplo, si los empleados ya están cubiertos por el plan de seguro médico de su cónyuge, no tienen que usar sus créditos para cobertura médica. Por lo tanto, es posible que quieran usarlos para otros beneficios. Para obtener más información sobre los programas de crédito flexible, consulte [Configurar programas de crédito flexible](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Configure la información requerida de los empleados

Antes de poder inscribir a los empleados en las prestaciones, debe proporcionar la información requerida para ellos. 

El empleado debe tener asignada un **Puesto**. Se puede asignar un **Puesto** al empleado en las páginas **Trabajador** o **Puesto** actualizando la **Asignación de trabajadores**. 

Después, los empleados deben estar incluidos en un plan de compensación fijo en su fecha de inicio, o deben tener un importe de **Salario de prestaciones anual**. Antes de asignar una **Compensación fija** a un empleado, debe asignarse un **Puesto**. 

> [!NOTE] 
> La **Fecha de inicio de compensación fija** no puede ser anterior a la **Fecha de asignación del puesto**.

De forma alternativa, si tiene un empleado que recibe una compensación adicional como comisiones, puede agregar una cantidad **Salario anual de prestaciones** desde el registro del empleado. Recursos Humanos utilizará la cantidad **Salario anual de prestaciones** al determinar los importes de cobertura, en lugar del importe **Anual de compensación fija**. El **Salario anual de prestaciones** debe ser válido a partir de la fecha de inicio del empleado o del comienzo del período de prestaciones, lo que sea más reciente. Sin embargo, no se requiere un puesto para asignar el **Salario anual de prestaciones**. Para habilitar la característica de **Salario anual de prestaciones**, vaya a la página **Parámetros compartidos Human Resources**, en la pestaña **Administración de prestaciones**. Esta característica está desactivada de forma predeterminada.

> [!IMPORTANT]
> Si se introduce una **Compensación fija** y un importe de **Salario anual de prestaciones** para un empleado, el **Salario anual de prestaciones** se utilizará para determinar los importes de cobertura. En la sección **Detalles de Empleo** sección de la página **Trabajador**, debe seleccionar un valor en el campo **Frecuencia de pago de prestaciones**.

## <a name="configure-optional-employee-information"></a>Configure la información opcional de los empleados
Cuando crea un plan de prestaciones que utiliza tarifas que se basan en el sexo o la edad, debe ingresar una fecha de nacimiento y género del empleado para calcular el costo de la prestaciones.

## <a name="process-employees-to-determine-eligibility"></a>Procese a los empleados para determinar la elegibilidad
Antes de que los empleados puedan inscribirse en los planes, se ejecuta el proceso de elegibilidad para determinar para qué planes son elegibles. Puede ver los resultados del proceso de elegibilidad en el **visor de resultados del proceso**. Para obtener más información, consulte [Proceso de elegibilidad de inscripción](hr-benefits-process-enrollment-eligibility.md).

## <a name="employees-select-plans-using-employee-self-service-optional"></a>Los empleados seleccionan planes a través del **Autoservicio para empleados** (opcional)

Cuando se produce la inscripción abierta, se contrata a los empleados por primera vez o se produce un evento en la vida, los empleados pueden seleccionar o actualizar sus beneficios a través del **autoservicio para empleados**. Para más información, consulte [Configurar auto servicio de empleado](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Confirme las selecciones de planes de empleados

Los beneficios que seleccionen los empleados deben ser confirmados antes de que los empleados se consideren inscritos en ellos. Las prestaciones también se pueden seleccionar en nombre de un empleado. Para seleccionar o confirmar prestaciones, en la página **Empleado**, en la pestaña **Prestaciones**, seleccione **Planes de prestaciones para trabajadores**. Para seleccionar o confirmar prestaciones para varios empleados, use la página **Actualización masiva de planes de prestaciones para trabajadores**.

## <a name="life-event-processing-optional"></a>Usar el procesamiento de eventos de vida (opcional)

Durante el ciclo de vida del empleado, cada empleado puede experimentar varios eventos de la vida, como matrimonio, cambios en el empleo o cambios en dependientes o beneficiarios. Para usar eventos de la vida, debe habilitarlos en la página **Parámetros compartidos de recursos humanos**. Configure los tipos de eventos de la vida y las opciones de eventos de la vida para los tipos de planes.

Antes de poder procesar eventos de vida, debe haber ejecutado la inscripción abierta al menos una vez durante un periodo de contratación. En los Estados Unidos, la inscripción abierta suele ser una vez al año. Fuera de los Estados Unidos, la inscripción abierta puede realizarse al momento de la contratación. El procesamiento de eventos de vida no requiere que los trabajadores seleccionen un plan de beneficios. Sin embargo, los trabajadores deben haber sido incluidos en el proceso de inscripción abierta. Para obtener más información, consulte los siguientes temas:

- [Procesar eventos de vida](hr-benefits-process-life-events.md)
- [Procesar cambios de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Procesar idoneidad de eventos de vida](hr-benefits-process-life-event-eligibility.md)

## <a name="rate-updates-optional"></a>Actualizaciones de tarifas (opcional)

A veces, la tasa de un beneficio cambia durante el período del plan. Para actualizar las tarifas de los empleados que ya están inscritos en el plan, debe procesar los cambios de tarifas. Para obtener más información, consulte [Proceso de cambio de tarifa](hr-benefits-process-rate-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
