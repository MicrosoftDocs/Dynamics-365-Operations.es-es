---
title: Establecer parámetros de administración de beneficios
description: Configure los parámetros para la administración de beneficios en Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010475"
---
# <a name="set-benefits-management-parameters"></a>Establecer parámetros de administración de beneficios

[!include [banner](includes/preview-feature.md)]

Para poder configurar planes de licencia en Microsoft Dynamics 365 Human Resources, debe configurar los parámetros de administración de beneficios. Estos parámetros establecen valores predeterminados, códigos de motivo y otras opciones.

## <a name="configure-general-parameters"></a>Configurar parámetros generales

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros**.

2. En la pestaña **General**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **País/región** | El campo **País/región** determina el orden de visualización de los códigos postales o estados. El país seleccionado aparece primero en la lista desplegable. |
   | **Código de motivo de la inscripción** | Seleccione un código de motivo predeterminado para usarlo cuando se crean planes de empleados durante el proceso de inscripción abierta. |
   | **Código de motivo de cancelación** | El código de motivo que se usará cuando se cancela un plan de beneficios para empleados. Se muestra en un cuadro de diálogo durante el proceso de cancelación. Los usuarios pueden cambiarlo en el **Código de motivo de cancelación** si necesario. |
   | **Código de motivo de reapertura** | El código de motivo que se usará cuando se vuelve a abrir un plan de beneficios para empleados. Se muestra en un cuadro de diálogo durante el proceso de cancelación. Los usuarios pueden cambiarlo en **Volver a abrir código de motivo** si necesario. | 
   | **Código de motivo de evento de vida** | El código de motivo que se usará cuando se produce un evento de vida. |
   | **Código de motivo del cambio de tasa** | El código de motivo que se usará al cancelar y volver a abrir un plan de beneficios para empleados durante el proceso de actualización de cambio de tasa. Indica qué registros se modificados por el proceso de actualización de cambio de tasa. |
   | **Nueva contratación apta** | Especifica si los nuevos empleados son aptos. |
   | **Período de inscripción de nueva contratación** | El periodo de tiempo en que se permite la inscripción de nuevos empleados.</br></br>**Nota**: Esta configuración anula cualquier período de inscripción de nuevas contrataciones que establezca en la regla de idoneidad de planes. | 
   | **Mejora del salario anual** | Especifica si se calculará automáticamente el importe del **salario anual de prestaciones** en **Detalles de prestaciones de empleo**. Se basa en los campos **Tasa de pago de compensación fija**, **Promedio de horas**y **Frecuencia de pago** del empleado.</br></br>**Promedio de horas** x **Índice salarial fijo** x **Frecuencia de pago** (n.º de períodos de sueldo) = **Salario anual de prestaciones** </br></br>Si cambia cualquiera de los valores de los campos **Horas promedio**, **Tasa de pago de compensación fija** o **Frecuencia de pago**, el sistema vuelve a calcular automáticamente el importe de **Salario anual de prestaciones** del empleado en función de los valores modificados. El sistema crea un registro de **Fecha de vigencia** para identificar la fecha y la hora exactas en que ocurrió el cambio. Puede editar manualmente el importe de **Salario anual de prestaciones** si es necesario. |
   | **Eventos de vida habilitados** | Permite eventos de vida. |
   | **Ocultar formularios de prestaciones heredadas** | Le permite ocultar formularios de beneficios heredados. |

3. Seleccione **Guardar**.

## <a name="configure-employee-self-service-parameters"></a>Configura parámetros de autoservicio para empleados

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros**.

2. En la pestaña **Autoservicio para empleados**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Comprobación de prestación** | El texto de comprobación que se usará durante la comprobación de los beneficios de autoservicio. |
   | **Seleccionar automáticamente personas designadas** | Especifica si desea seleccionar automáticamente dependientes y beneficiarios según su idoneidad para las opciones del plan. |

3. Seleccione **Guardar**.
