---
title: Visión general de la administración de prestaciones
description: Visión general de la característica de vista previa de administración de prestaciones en Dynamics 365 Human Resources. Ofrezca a sus empleados opciones de prestaciones ampliadas con una experiencia en línea fácil de usar.
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
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029472"
---
# <a name="benefits-management-overview"></a>Visión general de la administración de prestaciones

[!include [banner](includes/preview-feature.md)]

Para seguir siendo competitivo, debe ofrecer un amplio conjunto de prestaciones para atraer y retener a sus mejores empleados. Además de las prestaciones estándar como la cobertura médica y dental, es posible que también quiera ofrecer servicios ampliados como asistencia de adopción, programas de recreación y asignaciones de ropa. La característica de vista previa de administración de prestaciones en Microsoft Dynamics 365 Human Resources le brinda una solución flexible que admite una amplia variedad de opciones de prestaciones. Recursos humanos también incluye una experiencia fácil de usar para los empleados que muestra sus ofertas.

- Los planes de prestaciones mejoradas le permiten crear y administrar planes de prestaciones únicas y admitir tablas complejas de tasas de prestaciones y niveles anidados. Puede crear fácilmente programas de beneficios, agrupaciones y reglas de inscripción automática para una experiencia más fácil para los empleados.

- Los programas de crédito flexible le permiten prorratear para asistir en la jubilación y otros eventos de la vida.

- Las extensas reglas de idoneidad garantizan que las prestaciones adecuadas estén disponibles para los empleados correctos.

- La inscripción de prestaciones en línea ofrece una experiencia fácil para sus empleados.

- El procesamiento calificado de eventos de vida se integra con el autoservicio de los empleados y también es compatible con eventos de vida futuros.

Si desea acceder a los datos de demostración, deberá volver a implementar su entorno de espacio aislado.

Puede proporcionar comentarios directos o informar sobre problemas a: D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Problemas conocidos de la gestión de beneficios

### <a name="eligibility-processing"></a>Procesamiento de idoneidad

Al ejecutar la idoneidad para las prestaciones que usan un importe de cobertura de salario a 1-5X, % de salario e importe fijo, debe establecer la fecha de **Detalles de la prestación** para la **Fecha inicial del empleado** en **Historial del empleo**. También debe incluir **Horas trabajadas**, **Frecuencia de pago** y **Importe del salario de prestaciones anual**. Si el trabajador tiene una compensación fija, introduzca **Horas trabajadas** y **Frecuencia de pago**. Se calculará el importe del salario anual. Si el empleado es asalariado, no necesita introducir **Horas trabajadas**. Recomendamos que al crear nuevos trabajadores, ingrese primero una compensación fija. Para actualizar el registro de detalles de prestaciones, vaya a **Trabajador > Historial del trabajador > Detalles del empleo**. Ajuste la fecha a la fecha inicial del empleado.

### <a name="employee-self-service"></a>Autoservicio para empleados

El importe del empleado no se calcula al actualizar el importe de la cobertura del seguro de vida. Por ejemplo, cuando a un empleado se le ofrece un plan de seguro de vida, puede seleccionar hasta 50 000 USD en cobertura a un costo de 0,36 USD por 1000 USD de cobertura.  Cuando el empleado actualiza el monto de la cobertura, el costo asociado del empleado permanece en cero.

Para un plan de prestaciones que solo permite una única selección de ese tipo de plan, el usuario recibe un error si intenta renunciar a un plan después de seleccionarlo. Por ejemplo, un usuario selecciona un plan médico y lo coloca en su carrito. El usuario luego selecciona **Renunciar** para otro plan médico El usuario recibirá un error.

## <a name="enable-benefits-management"></a>Habilitar la administración de prestaciones

La administración de prestaciones es una característica de vista previa y solo está disponible en entornos de **Espacio abierto**. Estos artículos describen cómo activar las características de vista previa en Recursos humanos. También le indican qué características existentes en Recursos humanos reemplazan o deshabilitan la administración de prestaciones una vez que activa la administración de prestaciones.

- [Administrar características](hr-admin-manage-features.md)
- [Característica de vista previa: administración de prestaciones](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a>Configurar la administración de prestaciones

Antes de poder crear planes de prestaciones para sus empleados, debe configurar las opciones para los planes.

- [Establecer parámetros de administración de prestaciones](hr-benefits-setup-parameters.md)
- [Configurar reglas y opciones de idoneidad](hr-benefits-setup-eligibility-rules.md)
- [Configurar las opciones de idoneidad de contacto personal](hr-benefits-setup-contact-eligibility-options.md)
- [Crear opciones de cobertura](hr-benefits-setup-coverage-options.md)
- [Configurar frecuencias de pago](hr-benefits-setup-payment-frequencies.md)
- [Configurar tipos de eventos de vida](hr-benefits-setup-life-event-types.md)
- [Crear tipos de planes](hr-benefits-setup-plan-types.md)
- [Configurar códigos de motivos](hr-benefits-setup-reason-codes.md)
- [Configurar códigos de niveles](hr-benefits-setup-tier-codes.md)
- [Configurar tasas](hr-benefits-setup-rates.md)
- [Configurar deducciones](hr-benefits-setup-deductions.md)
- [Configurar días de espera](hr-benefits-setup-waiting-days.md)
- [Configurar periodos de espera](hr-benefits-setup-waiting-periods.md)
- [Configurar reglas de redondeo](hr-benefits-setup-rounding-rules.md)
- [Crear categorías de empleo](hr-benefits-setup-employment-categories.md)
- [Configurar tipos de empleo](hr-benefits-setup-employment-types.md)
- [Configurar el autoservicio para empleados](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Crear planes de prestaciones

Estos artículos muestran cómo crear planes de prestaciones, incluidos agrupaciones y programas de crédito flexible.

- [Configurar planes de prestaciones](hr-benefits-plans-setup.md)
- [Crear planes de prestaciones de trabajadores](hr-benefits-plans-worker.md)
- [Establecer programas de crédito flexible](hr-benefits-plans-flex-credit-programs.md)
- [Configurar de eventos de vida futuros](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Planes del proceso de prestaciones

Debe procesar algunos de sus cambios para activarlos.

- [Proceso de idoneidad para inscripción](hr-benefits-process-enrollment-eligibility.md)
- [Procesar eventos de vida](hr-benefits-process-life-events.md)
- [Procesar cambios de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Procesar idoneidad de eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Procesar tasas de cambios](hr-benefits-process-rate-changes.md)

