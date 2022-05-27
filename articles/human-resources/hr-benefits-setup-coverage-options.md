---
title: Crear opciones de cobertura
description: En este tema se describen las opciones de cobertura en Microsoft Dynamics 365 Human Resources para la elección de un participante en un plan o programa de prestaciones.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
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
ms.openlocfilehash: b6d35967e731f3618d932694b49c1952af9f93cf
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693931"
---
# <a name="create-coverage-options"></a>Crear opciones de cobertura


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Las opciones de cobertura determinan quién debe estar cubierto o cuánta cobertura está disponible en un plan de seguro. Por ejemplo, para un plan médico, es posible que tenga una opción **Solo empleado**, una opción **Empleado + 1** y una opción **Familia**. Para el seguro de vida, puede ofrecer cobertura para **1 x salario** o **2 x salario**.

Una vez las opciones de cobertura de prestación se definen, puede reutilizarlas. Puede asociar una opción con uno o más planes.

> [!IMPORTANT]
> Después de definir las opciones de cobertura, adjunte las opciones de cobertura a un tipo de plan de prestaciones. El tipo de plan se asocia con un plan o programa de prestaciones. Las opciones de cobertura asociadas con un tipo de plan están disponibles para todos los planes creados con ese tipo.

## <a name="create-coverage-options"></a>Crear opciones de cobertura
1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de cobertura**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Opción de cobertura** | Un nombre de opción de cobertura único. |
   | **Descripción** | Una descripción de la opción de cobertura. |
   | **Tipo de cobertura** | Los códigos de cobertura asignan importes mínimos y máximos para cada tipo de persona cubierta idónea. Un código de cobertura indica quién se ve afectado o el importe de cobertura permitido para un tipo de plan. Puede expresar el importe de la cobertura como un importe en dólares o un porcentaje. Por ejemplo:<ul><li>**Emp+1**: para poder optar, el empleado debe tener un dependiente seleccionado (si se selecciona más de uno, ya no se califica).</li><li>**Emp+familia**: para poder optar, el empleado debe tener al menos dos dependientes seleccionados.</li></ul> |
   | **Número máximo** | El número máximo de dependientes. |
   | **Estado** | El estado de la opción de cobertura. Si el estado de la opción de cobertura se establece en **Inactivo**, la opción de cobertura no se puede seleccionar en los tipos de planes. |
   | **Porcentaje** | El porcentaje del importe. Este campo solo está activo si se seleccionó Sueldo x % en el campo de código de cobertura. |
   | **Divisor** | El divisor que se usará en el cálculo cuando seleccione el código de cobertura Sueldo x %. |
   | **Porcentaje mínimo** | El porcentaje mínimo cuando selecciona el código de cobertura Porcentaje. |
   | **Porcentaje máximo** | El porcentaje máximo cuando selecciona el código de cobertura Porcentaje. |

4. En **Opciones de idoneidad de contacto personal**, adjunte la opción de idoneidad de contactos personales correspondiente a cada opción de cobertura.

5. En **Autoservicio**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Permitir importe de contribución del empleado** | Especifica si se permite a los empleados modificar el importe de la contribución en el autoservicio de prestaciones cuando seleccionan las prestaciones. Si activa esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de contribución que el empleado introduce en el autoservicio de prestaciones. |
   | **Permitir importe de cobertura del empleado** | Especifica si se permite a los empleados modificar el importe de la cobertura en el autoservicio de prestaciones cuando seleccionan las prestaciones. Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de cobertura que el empleado introduce en el autoservicio del empleado. |

6. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
