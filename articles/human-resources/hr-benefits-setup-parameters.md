---
title: Establecer los parámetros Administración de prestaciones y Autoservicio para empleados para todas las empresas
description: Configure los parámetros Administración de prestaciones y Autoservicio para empleados en Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
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
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "4962449"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Establecer los parámetros Administración de prestaciones y Autoservicio para empleados para todas las empresas

Para poder configurar planes de prestaciones en Microsoft Dynamics 365 Human Resources, debe configurar los parámetros de Administración de beneficios. Estos parámetros establecen valores predeterminados, códigos de motivo y otras opciones. 

## <a name="configure-general-parameters"></a>Configurar parámetros generales

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros compartidos de Human Resources**.

2. En la pestaña **Administración de prestaciones**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **País/región** | El campo **País/región** determina el orden de visualización de los códigos postales o estados. El país seleccionado aparece primero en la lista desplegable. |
   | **Código de motivo de la inscripción** | Seleccione un código de motivo predeterminado para usarlo cuando se crean planes de empleados durante el proceso de inscripción abierta. |
   | **Código de motivo de cancelación** | El código de motivo que se usará cuando se cancela un plan de beneficios para empleados. Se muestra en un cuadro de diálogo durante el proceso de cancelación. Los usuarios pueden cambiarlo en el **Código de motivo de cancelación** si necesario. |
   | **Código de motivo de reapertura** | El código de motivo que se usará cuando se vuelve a abrir un plan de beneficios para empleados. Se muestra en un cuadro de diálogo durante el proceso de cancelación. Los usuarios pueden cambiarlo en **Volver a abrir código de motivo** si necesario. | 
   | **Código de motivo de evento de vida** | El código de motivo que se usará cuando se produce un evento de vida. |
   | **Código de motivo del cambio de tasa** | El código de motivo que se usará al cancelar y volver a abrir un plan de beneficios para empleados durante el proceso de actualización de cambio de tasa. Indica qué registros se modificados por el proceso de actualización de cambio de tasa. |
   | **Salario anual de prestaciones** | Le permite establecer un importe de **Salario anual de prestaciones** para un empleado. Recursos Humanos utilizará la cantidad **Salario anual de prestaciones** al determinar los importes de cobertura, en lugar del importe anual de compensación fija. |
   | **Nueva contratación apta** | Especifica si los nuevos empleados son aptos. |
   | **Período de inscripción de nueva contratación** | El periodo de tiempo en que se permite la inscripción de nuevos empleados.</br></br>**Nota**: Esta configuración anula cualquier período de inscripción de nuevas contrataciones que establezca en la regla de idoneidad de planes. |
   | **Frecuencia de pago predeterminada** | La frecuencia de pago predeterminada para usar cuando se agregan nuevos trabajadores. |
   | **Eventos de vida habilitados** | Permite eventos de vida. |
   | **Ocultar formularios de prestaciones heredadas** | Le permite ocultar formularios de beneficios heredados. |
   | **Comprobación de prestación** | El texto de comprobación que se usará durante la comprobación de los beneficios de autoservicio. |
   | **Seleccionar automáticamente personas designadas** | Especifica si desea seleccionar automáticamente dependientes y beneficiarios según su idoneidad para las opciones del plan. |

3. Seleccione **Guardar**.

## <a name="configure-employee-self-service-parameters"></a>Configura parámetros de autoservicio para empleados

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de Human Resources**.

2. En la pestaña **Administración de prestaciones**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Comprobación de prestación** | El texto de comprobación que se usará durante la comprobación de los beneficios de autoservicio. |
   | **Seleccionar automáticamente personas designadas** | Especifica si desea seleccionar automáticamente dependientes y beneficiarios según su idoneidad para las opciones del plan. |

3. Seleccione **Guardar**.




[!INCLUDE[footer-include](../includes/footer-banner.md)]