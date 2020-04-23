---
title: Visión general de administración de prestaciones
description: Visión general de la característica de administración de prestaciones en Dynamics 365 Human Resources. Ofrezca a sus empleados opciones de prestaciones ampliadas con una experiencia en línea fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 91a4425b4f020f90843bb3b0b280b7ee28463670
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230163"
---
# <a name="benefits-management-overview"></a>Visión general de la administración de prestaciones

Para seguir siendo competitivo, debe ofrecer un amplio conjunto de prestaciones para atraer y retener a sus mejores empleados. Además de las prestaciones estándar como la cobertura médica y dental, es posible que también quiera ofrecer servicios ampliados como asistencia de adopción, programas de recreación y asignaciones de ropa. La administración de prestaciones en Microsoft Dynamics 365 Human Resources le brinda una solución flexible que admite una amplia variedad de opciones de prestaciones. Recursos humanos también incluye una experiencia fácil de usar para los empleados que muestra sus ofertas.

- Los planes de prestaciones mejoradas le permiten crear y administrar planes de prestaciones únicas y admitir tablas complejas de tasas de prestaciones y niveles anidados. Puede crear fácilmente programas de beneficios, agrupaciones y reglas de inscripción automática para una experiencia más fácil para los empleados.

- Los programas de crédito flexible le permiten prorratear para asistir en la jubilación y otros eventos de la vida.

- Las extensas reglas de idoneidad garantizan que las prestaciones adecuadas estén disponibles para los empleados correctos.

- La inscripción de prestaciones en línea ofrece una experiencia fácil para sus empleados.

- El procesamiento calificado de eventos de vida admite eventos de vida futuros.

Si desea acceder a los datos de demostración, deberá volver a implementar su entorno de espacio aislado.

## <a name="benefits-management-known-issues"></a>Problemas conocidos de la gestión de beneficios

### <a name="flex-credit-programs"></a>Programas de crédito flexible

El valor de crédito total definido para un programa de crédito flexible no se muestra en el formulario **Planes de prestaciones del trabajador**. Además, si configura un programa de crédito flexible para tener una regla de prorrateo de **Ninguna**, obtiene un error en el formulario **Plan de prestaciones para el trabajador** al seleccionar y confirmar planes.

## <a name="enable-benefits-management"></a>Habilitar la administración de prestaciones

Este artículo describe cómo activar las características en Recursos humanos. También le indica qué características existentes en Human Resources reemplazan o deshabilitan la administración de prestaciones una vez que activa la administración de prestaciones.

> [!IMPORTANT]
> Después de habilitar la gestión de prestaciones en un entorno de **Producción**, no puede deshabilitarlo. Recomendamos habilitar y probar la gestión de prestaciones en un entorno **Espacio aislado** antes de habilitarlo en un entorno de **Producción**. Existen diferencias significativas entre la funcionalidad de prestación heredada y la nueva funcionalidad de administración de prestaciones que requieren una configuración adicional y deben probarse antes de su puesta en producción.

- [Administrar características](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Configurar información de empleados

Antes de poder inscribir a los empleados en las prestaciones, debe proporcionar la información requerida. Debe inscribir a un empleado en un **Plan de compensación fija** en su fecha de inicio, y debe seleccionar una **Frecuencia de pago de prestaciones** en **Detalles de empleo** en el formulario el **Trabajador**.

Cuando crea un plan de prestaciones que utiliza tarifas que se basan en el sexo o la edad, debe ingresar una fecha de nacimiento y género del empleado para calcular el costo de la prestaciones.

## <a name="configure-benefits-management"></a>Configurar la administración de prestaciones

Antes de poder crear planes de prestaciones para sus empleados, debe configurar las opciones para los planes.

- [Establecer parámetros de administración de prestaciones](hr-benefits-setup-parameters.md)
- [Configurar reglas y opciones de idoneidad](hr-benefits-setup-eligibility-rules.md)
- [Configurar las opciones de elegibilidad de contacto personal](hr-benefits-setup-contact-eligibility-options.md)
- [Crear opciones de cobertura](hr-benefits-setup-coverage-options.md)
- [Configurar frecuencias de pago](hr-benefits-setup-payment-frequencies.md)
- [Configurar tipos de eventos de vida](hr-benefits-setup-life-event-types.md)
- [Crear tipos de planes](hr-benefits-setup-plan-types.md)
- [Configurar códigos de motivos](hr-benefits-setup-reason-codes.md)
- [Configurar códigos de nivel](hr-benefits-setup-tier-codes.md)
- [Configurar tarifas](hr-benefits-setup-rates.md)
- [Configurar deducciones](hr-benefits-setup-deductions.md)
- [Configurar días de espera](hr-benefits-setup-waiting-days.md)
- [Configurar períodos de espera](hr-benefits-setup-waiting-periods.md)
- [Configurar reglas de redondeo](hr-benefits-setup-rounding-rules.md)
- [Crear categorías de empleo](hr-benefits-setup-employment-categories.md)
- [Configurar tipos de empleo](hr-benefits-setup-employment-types.md)
- [Configurar el autoservicio para empleados](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Crear planes de prestaciones

Estos artículos muestran cómo crear planes de prestaciones, incluidos agrupaciones y programas de crédito flexible.

- [Configurar planes de prestaciones](hr-benefits-plans-setup.md)
- [Configurar programas de crédito flexible](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Procesar planes de beneficios

Debe procesar algunos de sus cambios para activarlos.

- [Proceso de idoneidad para inscripción](hr-benefits-process-enrollment-eligibility.md)
- [Procesar eventos de vida](hr-benefits-process-life-events.md)
- [Procesar cambios de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Procesar idoneidad de eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Procesar tasas de cambios](hr-benefits-process-rate-changes.md)

