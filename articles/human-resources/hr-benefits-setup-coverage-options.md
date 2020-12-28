---
title: Crear opciones de cobertura
description: Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones.
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
ms.openlocfilehash: 8690dbe00c2316ccf745f5222c3cbaa9c3379f85
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420462"
---
# <a name="create-coverage-options"></a>Crear opciones de cobertura

Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones. Por ejemplo, las opciones de cobertura podrían incluir **Solo empleado** para un plan médico, o **2x salario** para un plan de seguro de vida. Una vez definido, puede reutilizar las opciones de cobertura de prestaciones. Puede asociar una opción con uno o más planes.

Después de definir las opciones de cobertura, adjunte las opciones de cobertura a un tipo de plan de prestaciones. El tipo de plan se asocia con un plan o programa de prestaciones. Las opciones de cobertura asociadas con un tipo de plan están disponibles para todos los planes creados con ese tipo de plan. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de cobertura**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Opción de cobertura** | Un nombre de opción de cobertura único. |
   | **Descripción** | Una descripción de la opción de cobertura. |
   | **Tipo de cobertura** | Los códigos de cobertura asignan importes mínimos y máximos para cada tipo de persona cubierta idónea. Un código de cobertura indica quién se ve afectado o el importe de cobertura permitido para un tipo de plan. Puede expresar el importe de la cobertura como un importe en dólares o un porcentaje. Por ejemplo:</br></br>- **Emp+1**: para calificarse, el empleado debe tener un dependiente seleccionado (si se selecciona más de uno, ya no se califica).</br></br>- **Emp+familia**: para calificarse, el empleado debe tener al menos dos dependientes seleccionados. |
   | **Número máximo** | El número máximo de dependientes. |
   | **Estado** | El estado de la opción de cobertura. Si el estado de la opción de cobertura se establece en inactivo, la opción de cobertura no se puede seleccionar en los tipos de planes. |
   | **Porcentaje** | El porcentaje del importe. Este campo solo está activo si se seleccionó Sueldo x % en el campo de código de cobertura. |
   | **Divisor** | El divisor a usar en el cálculo cuando selecciona el código de cobertura Sueldo x %. |
   | **Porcentaje mínimo** | El porcentaje mínimo cuando selecciona el código de cobertura Porcentaje. |
   | **Porcentaje máximo** | El porcentaje máximo cuando selecciona el código de cobertura Porcentaje. |

4. En **Opciones de idoneidad de contacto personal**, adjunte la opción de idoneidad de contactos personales correspondiente a cada opción de cobertura.

5. En **Autoservicio**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Permitir importe de contribución del empleado** | Especifica si se permite a los empleados modificar el importe de la contribución en el autoservicio de prestaciones cuando seleccionan las prestaciones. Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de contribución que el empleado introduce en el autoservicio de prestaciones. |
   | **Permitir importe de cobertura del empleado** | Especifica si se permite a los empleados modificar el importe de la cobertura en el autoservicio de prestaciones cuando seleccionan las prestaciones. Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de cobertura que el empleado introduce en el autoservicio del empleado. |

6. Seleccione **Guardar**. 
