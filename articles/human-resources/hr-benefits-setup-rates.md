---
title: Configurar tarifas
description: Las tasas en Microsoft Dynamics 365 Human Resources definen cuánto aportan los empresarios y los empleados para una prestación.
author: andreabichsel
manager: tfehr
ms.date: 06/22/2020
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
ms.openlocfilehash: 351364d6de250bad559b1704a928ed5274578151
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468428"
---
# <a name="configure-rates"></a>Configurar tarifas

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Las tasas en Microsoft Dynamics 365 Human Resources definen cuánto aportan los empresarios y los empleados para una prestación. El valor puede ser un importe o créditos flexibles, en función de su configuración.

Use tasas para determinar cuánto pagan los empleados y empresarios por cada prestación, en función de varios factores. Las tasas de cobertura son efectivas a partir de una fecha, por lo que puede mantener un registro histórico de tasas. 

## <a name="set-up-rates"></a>Configurar tasas

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tasas**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Tipo** | Un nombre único que identifica la tasa de beneficio. |
   | **Descripción** | Descripción de la tasa de beneficio. |
   | **Vigente** | La fecha en que la tasa tiene vigencia. La fecha actual del sistema es el valor predeterminado. 
   | **Caducidad** | La fecha final de la tasa. 12/31/2154 (que representa nunca) es el valor predeterminado. |
   | **Usar niveles** | El nivel que se utilizará para el cálculo de la tasa de beneficio. Nivel único para una tasa de beneficio de un nivel o doble nivel para una tasa de beneficio de dos niveles. Un ejemplo de un nivel doble es un nivel basado en el sexo y la edad. |
   | **Frecuencia de pago** | La frecuencia de pago que determina con qué frecuencia se paga la tasa de la prima de prestación al proveedor de beneficios. Por ejemplo, si la frecuencia de pago es mensual, la tasa de beneficio representa el importe del pago mensual. |
   | **Redondeo de la tasa de frecuencia de pago** | El método para redondear la tasa: Estándar o Truncado. |
   | **Importe del empleado si no es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si no es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe de la empresa si es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Gastos administrativos** | El importe administrativo cobrado por un administrador externo. Este es el importe que el empresario paga al administrador externo y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Tasa de crédito flexible** | El número de créditos flexibles que la prestación cuesta. Esto solo es aplicable a las tasas que son para planes de prestaciones asociados con programas de crédito flexible. Si usa tasas de nivel, la tasa de crédito flexible se define en Acciones> Tasas de nivel. |
   | **Fecha de vigencia del cambio** | La fecha en la que tendrá efecto el cambio de tasa de prestación. El sistema cambiará automáticamente la tasa de presentación y actualizará todos los planes de prestaciones asociados con esta tasa, siempre que ejecute el proceso de actualización de cambio de tasa. No establezca esta fecha a menos que desee que el sistema actualice automáticamente los planes de beneficios para empleados en función de esta tarifa. Esto se reserva normalmente al procesamiento automático de cambio de tasa futura. La fecha de vigencia del cambio debe estar dentro de las fechas de vencimiento y vigencia de tasa de prestación. |
   | **Cambio de tasa completado** | La casilla de **Cambio de tasa completado** se seleccionará automáticamente después de que se hayan completados los cambios de tasa de prestación por el procesamiento de actualización de cambio de tasa. |

4. Para realizar un seguimiento y mantener los cambios en la configuración de la tasa de prestaciones, seleccione **Acciones** y luego seleccione **Mantener versiones**.

5. Seleccione **Guardar**. 

## <a name="set-up-tier-rates"></a>Configurar tasas de niveles

Puede usar tasas de niveles en su configuración de tasas si la tasa varía en función de diversos factores. Por ejemplo, podría configurar tasas de niveles para indicar que si su edad es de hasta 34,99, el importe para no fumador es de 2. Si su edad es de hasta 39,99, el importe para no fumador es de 3.

También puede usar niveles dobles. Si selecciona **Nivel doble** para el valor de **Usar niveles** en el formulario **Configuración de tasas**, puede definir tasas basadas en dos dimensiones. Por ejemplo, podría configurar un sistema de nivel doble para indicar que si usted es hombre y su edad es de hasta 34,99, el importe para no fumador es de 2. Si es hombre y su edad es de hasta 39,99, el importe para no fumador es de 3. Si es mujer y su edad es de hasta 34,99, el importe para no fumador es de 1,8. Si es mujer y su edad es de hasta 39,99, el importe para no fumador es de 2,8.

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tasas**.

2. Seleccione una o más tasas en la lista, seleccione **Acciones** y luego seleccione **Tasas de nivel**.

3. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- | 
   | **Descripción** | El valor del campo **Descripción** se aplicará a partir de la descripción en el registro de configuración de tasas. Esto le ayuda a identificar a qué configuración de tasa están vinculadas las tasas de nivel. |
   | **Código de nivel** | Seleccione un código de nivel. Los códigos de nivel se definen en el formulario Códigos de niveles. El sistema mostrará automáticamente la descripción del código de nivel en la cuadrícula que se encuentra a la izquierda. |
   | **Tipo de nivel** | Especifica qué campo se debe utilizar como criterio de selección para el proceso de cálculo de la tasa de nivel. Por ejemplo:</br></br><ul><li>Si se utiliza **Edad**, el sistema usará la fecha de nacimiento del empleado en el proceso de cálculo de la tasa de prestación.</li><li>Si se utiliza **Salario**, el sistema usará el salario de beneficio anual del empleado en el proceso de cálculo de la tasa de prestación.</li><li>Si se usa el **Tipo de trabajo**, el sistema usará el registro de puesto activo actual del empleado para determinar el tipo de trabajo por el registro de trabajo vinculado al puesto.</li></ul></br></br>Los tipos de niveles son **Edad**, **Salario**, **Físico**, **Sexo**, **Equivalente de jornada completa**, **Tipo de trabajo**, **Región de compensación** y **Nivel**. | 
   | **Nivel** | El valor que se usará con el tipo de nivel durante el proceso de cálculo de la tasa de prestación. Por ejemplo:</br></br><ul><li>Si el tipo de nivel es **Edad**, este sería el valor de la edad.</li><li>Si el tipo de nivel es **Salario**, este sería el importe del salario.</li><li> Si el tipo de nivel es **Tipo de trabajo**, este sería el tipo de trabajo.</li></ul></br></br>Con un tipo de nivel de **Edad** o **Salario**, el valor en el campo **Nivel** representa el límite superior del nivel. Con un tipo de nivel de **Tipo de trabajo**, el sistema utiliza un enfoque de coincidencia exacta durante la selección de la tasa de nivel. |
   | **Tipo de cálculo** | Especifica cómo utilizar el importe del campo de importe de cálculo y qué cálculo matemático realizar si es necesario. Si el tipo de cálculo es un importe fijo, el sistema utiliza los campos de importe tal cual. Si el tipo de cálculo es por importe de $ de salario o cobertura, el sistema usa el importe de cálculo y la dirección de cálculo en su cálculo matemático.</br></br>Si el tipo de cálculo es por importe de $ de salario, el sistema usará la siguiente ecuación matemática:</br></br>El Salario anual de prestaciones dividido por el importe del cálculo (redondeado hacia arriba o hacia abajo) multiplicado por los importes para fumadores o no fumadores para empleados o empresario.</br></br>Si el tipo de cálculo es por importe de $ de cobertura, el sistema usará la siguiente ecuación matemática:</br></br>El importe de cobertura dividido por el importe del cálculo (redondeado hacia arriba o hacia abajo) multiplicado por los importes para fumadores o no fumadores para empleados o empresario.</br></br>En ambos cálculos, la dirección de Cálculo se usa para determinar si se debe redondear el Salario anual de prestaciones o el importe de la cobertura dividido por el importe del cálculo hacia arriba o hacia abajo. |
   | **Importe del cálculo** | El importe que se utilizará durante el proceso de cálculo de la tasa de beneficio. Esta cantidad será el divisor durante el cálculo matemático de la tasa de nivel. |
   | **Dirección de cálculo** | La dirección en la que se debe redondear el importe del resultado calculado. El sistema admite tres direcciones de cálculo: en blanco (método exacto), **Aumentar** y **Disminuir**.</br></br><ul><li>Si está en blanco, el sistema usará el cálculo exacto del importe del salario o la cobertura dividido por el importe del cálculo. Si este valor tiene una fracción, el sistema lo usará en su cálculo.</li><li>Si la opción es **Aumentar**, el sistema aumentará el cálculo matemático del importe del salario/cobertura dividido por el importe del cálculo al siguiente número entero, lo que significa que 12,25 aumentaría a 13.</li><li>Si la opción es **Disminuir**, el sistema disminuirá el cálculo matemático del importe del salario/cobertura dividido por el importe del cálculo al siguiente número entero actual, lo que significa que 12,25 disminuiría a 12.</li></ul> |
   | **Importe del empleado si no es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si no es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe de la empresa si es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Gastos administrativos** | El importe administrativo cobrado por un administrador externo. Este es el importe que el empresario paga al administrador externo y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Tasa de no fumador de crédito flexible** | El número de créditos flexibles de los costes de prestación, en función del cálculo definido para el nivel para no fumadores. Por ejemplo, si el tipo de cálculo es **Por importe de $ de cobertura**, el importe de cálculo es 10 000, y la tasa de crédito flexible para no fumadores es 6, eso significa que si un empleado no fumador elige 10 000 $ de cobertura, costará 6 créditos flexibles. Si eligen 20 000 $ de cobertura, costará 12 créditos flexibles, y así sucesivamente. |
   | **Tasa de fumador de crédito flexible** | El número de créditos flexibles de los costes de prestación, en función del cálculo definido para el nivel para fumadores. |

5. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]