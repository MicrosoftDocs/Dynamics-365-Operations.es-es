---
title: Configurar tarifas
description: Las tasas en Microsoft Dynamics 365 Human Resources definen cuánto aportan los empresarios y los empleados para una prestación.
author: twheeloc
ms.date: 08/25/2021
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
ms.openlocfilehash: 2deb20646a532509c9e3a3e7a39f646bced2a3fb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693126"
---
# <a name="configure-rates"></a>Configurar tarifas


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Las tasas en definen cuánto aportan los empresarios y los empleados para una prestación. El valor puede ser un importe o un número de créditos flexibles, en función de su configuración.

Use tasas para determinar cuánto pagan los empleados y empresarios por cada prestación, en función de varios factores. Las tasas de cobertura son efectivas a partir de una fecha, por lo que puede mantener un registro histórico de tasas. 

## <a name="set-up-rates"></a>Configurar tasas

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tasas**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Tipo** | Un nombre único que identifica la tasa de beneficio. |
   | **Descripción** | Descripción de la tasa de beneficio. |
   | **Vigente** | La fecha de entrada en vigor de esta tasa. La fecha actual del sistema es el valor predeterminado. Esta fecha debe coincidir con su período de beneficios o antes. Una buena práctica es establecer esta fecha en la fecha del plan de prestaciones. |
   | **Caducidad** | La fecha final de la tasa. 12/31/2154 (que representa nunca) es el valor predeterminado. |
   | **Usar niveles** |  Use este campo si tiene lógica que deba usarse para determinar una tasa. Por ejemplo, si una tasa debe aumentar según la edad, seleccione un valor aquí. Seleccione **Nivel único** para una tasa de prestación de un nivel o **Doble nivel** para una tasa de prestación de dos niveles. Un ejemplo de un nivel doble es un nivel basado en el sexo y la edad. Después de seleccionar un valor, seleccione **Acciones** y luego seleccione **Tarifas de nivel**. Si tiene una tarifa fija que no cambia, deje este campo en blanco. |
   | **Frecuencia de pago** | Especifique la frecuencia con la que se debe pagar la tarifa de la prima de beneficios al proveedor de beneficios. Las tarifas que ingrese en la página que se describe más adelante en este tema se basarán en la frecuencia de pago que especifique aquí. Por ejemplo, si ingresa **Mensual** en este campo, e ingresa una tarifa de empleado de **100 $**, se supone que la prestación le costará al empleado 100 $ por mes. Sin embargo, a un empleado se le puede pagar dos veces al mes, según la frecuencia de pago de beneficios que se establece en el registro del empleado. En este caso, cuando el empleado se registre en el **autoservicio para empleados**, la cantidad que pagará será 50 $, porque la tarifa que muestra el **autoservicio para empleados** se basa en la frecuencia de pago del empleado. |
   | **Redondeo de la tasa de frecuencia de pago** | Los métodos para redondear la tasa son: estándar, truncado, normal, a la baja y al alza. </br></br><ul><li>**Estándar**: siempre redondea hacia arriba. Por ejemplo, 10,611 se redondeará a 10,62. -10,231 se redondeará a -10,23. </li><li>**Truncado** : siempre redondea hacia abajo. Por ejemplo, 10,619 se redondeará a 10,61. -10,231 se redondeará a -10,24. </li><li>**Normal**: los valores decimales que terminan en 5 o más se redondearán desde cero. Los valores decimales que terminan en 4 o menos se redondearán hacia cero. Por ejemplo, 10,615 se redondeará a 10,62. -10,235 se redondeará a -10,24. 10,614 se redondeará a 10,61. -10,234 se redondeará a -10,23. </li><li>**Hacia abajo**: redondea hacia cero. Por ejemplo, 10,619 se redondeará a 10,61. -10,231 se redondeará a -10,23. </li><li>**Redondeando**: redondea desde cero. Por ejemplo, 10,619 se redondeará a 10,62. -10,231 se redondeará a -10,24. |
   | **Importe del empleado si no es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si no es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe de la empresa si es fumador** | El importe que el proveedor de prestaciones cobra por un empleado que fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Gastos administrativos** | El importe administrativo cobrado por un administrador externo. Este es el importe que el empresario paga al administrador externo y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Tasa de crédito flexible** | El número de créditos flexibles que la prestación cuesta. Esto solo es aplicable a las tasas que son para planes de prestaciones asociados con programas de crédito flexible. Si usa tasas de nivel, la tasa de crédito flexible se define en Acciones> Tasas de nivel. |
   | **Fecha de vigencia del cambio** | La fecha en la que tendrá efecto el cambio de tasa de prestación. El sistema cambiará automáticamente la tasa de presentación y actualizará todos los planes de prestaciones asociados con esta tasa, siempre que ejecute el proceso de actualización de cambio de tasa. No establezca esta fecha a menos que desee que el sistema actualice automáticamente los planes de beneficios para empleados en función de esta tarifa. Esto se reserva normalmente al procesamiento automático de cambio de tasa futura. La **fecha de vigencia del cambio** debe estar dentro de las fechas de vencimiento y vigencia de tasa de prestación. |
   | **Cambio de tasa completado** | La casilla de **Cambio de tasa completado** se seleccionará automáticamente después de que se hayan completados los cambios de tasa de prestación por el procesamiento de actualización de cambio de tasa. |

4. Para realizar un seguimiento y mantener los cambios en la configuración de la tasa de prestaciones, seleccione **Acciones** y luego seleccione **Mantener versiones**.

5. Seleccione **Guardar**. 

## <a name="set-up-tier-rates"></a>Configurar tasas de niveles

Puede usar tasas de niveles en su configuración de tasas si la tasa varía en función de diversos factores. Por ejemplo, podría configurar tasas de niveles para indicar que si su edad es de hasta 34,99, el importe para no fumador es de 2. Si su edad es de hasta 39,99, el importe para no fumador es de 3.

También puede usar niveles dobles. Si selecciona **Nivel doble** para el valor de **Usar niveles** en el formulario **Configuración de tasas**, puede definir tasas basadas en dos dimensiones. Por ejemplo, podría configurar un sistema de nivel doble para indicar que si usted es hombre y su edad es de hasta 34,99, el importe para no fumador es de 2. Si es hombre y su edad es de hasta 39,99, el importe para no fumador es de 3. Si es mujer y su edad es de hasta 34,99, el importe para no fumador es de 1,8. Si es mujer y su edad es de hasta 39,99, el importe para no fumador es de 2,8.

> [!IMPORTANT]
> En el registro del trabajador, en **Informacion personal**, hay una opción que se utiliza para indicar si el empleado es fumador. Si el empleado está registrado como fumador, se utilizará la tasa de fumador. (La indicación de fumador nunca se muestra al empleado).
   
1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Tasas**.

2. Seleccione una o más tasas en la lista, seleccione **Acciones** y luego seleccione **Tasas de nivel**.

3. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- | 
   | **Descripción** | El valor del campo **Descripción** se aplicará a partir de la descripción en el registro de configuración de tasas. Esto le ayuda a identificar a qué configuración de tasa están vinculadas las tasas de nivel. |
   | **Código de nivel** | Seleccione un código de nivel. Los códigos de nivel se definen en la página **Códigos de niveles**. El sistema mostrará automáticamente la descripción del código de nivel en la cuadrícula que se encuentra a la izquierda. |
   | **Tipo de nivel** | Especifica qué campo se debe utilizar como criterio de selección para el proceso de cálculo de la tasa de nivel. Por ejemplo:</br></br><ul><li>Si se utiliza **Edad**, el sistema usará la fecha de nacimiento del empleado en el proceso de cálculo de la tasa de prestación.</li><li>Si se utiliza **Salario**, el sistema usará el salario de beneficio anual del empleado en el proceso de cálculo de la tasa de prestación.</li><li>Si se usa el **Tipo de trabajo**, se usa el registro de puesto activo actual del empleado para determinar el tipo de trabajo por el registro de trabajo vinculado al puesto.</li></ul></br></br>Los tipos de niveles son **Edad**, **Salario**, **Físico**, **Sexo**, **Equivalente de jornada completa**, **Tipo de trabajo**, **Región de compensación** y **Nivel**. | 
   | **Nivel** | El valor que se usará con el tipo de nivel durante el proceso de cálculo de la tasa de prestación. Por ejemplo:</br></br><ul><li>Si el tipo de nivel es **Edad**, este sería el valor de la edad.</li><li>Si el tipo de nivel es **Salario**, este sería el importe del salario.</li><li> Si el tipo de nivel es **Tipo de trabajo**, este sería el tipo de trabajo.</li></ul></br></br>Con un tipo de nivel de **Edad** o **Salario**, el valor en el campo **Nivel** representa el límite superior del nivel. Con un tipo de nivel de **Tipo de trabajo**, se usa un enfoque de coincidencia exacta durante la selección de la tasa de nivel. |
   | **Tipo de cálculo** | Especifica cómo utilizar el importe del campo de importe de cálculo y qué cálculo matemático realizar si es necesario. Si el tipo de cálculo es un importe fijo, se utiliza los campos de importe tal cual. Si el tipo de cálculo es por importe de $ de salario o cobertura, se usa el importe de cálculo y la dirección de cálculo en su cálculo matemático.</br></br>Si el tipo de cálculo es por importe de $ de salario, se usa la siguiente ecuación matemática:</br></br>El Salario anual de prestaciones dividido por el importe del cálculo (redondeado hacia arriba o hacia abajo) multiplicado por los importes para fumadores o no fumadores para empleados o empresario.</br></br>Si el tipo de cálculo es por importe de $ de cobertura, se usa la siguiente ecuación matemática:</br></br>El importe de cobertura dividido por el importe del cálculo (redondeado hacia arriba o hacia abajo) multiplicado por los importes para fumadores o no fumadores para empleados o empresario.</br></br>En ambos cálculos, la dirección de Cálculo se usa para determinar si se debe redondear el Salario anual de prestaciones o el importe de la cobertura dividido por el importe del cálculo hacia arriba o hacia abajo. |
   | **Importe del cálculo** | El importe que se utilizará durante el proceso de cálculo de la tasa de beneficio. Esta cantidad será el divisor durante el cálculo matemático de la tasa de nivel. |
   | **Dirección de cálculo** | La dirección en la que se debe redondear el importe del resultado calculado. El sistema admite tres direcciones de cálculo: en blanco (método exacto), **Aumentar** y **Disminuir**.</br></br><ul><li>Si está en blanco, el sistema usará el cálculo exacto del importe del salario o la cobertura dividido por el importe del cálculo. Si este valor tiene una fracción, todavía se usará en su cálculo.</li><li>Si la opción es **Aumentar**, el cálculo matemático aumentará el importe del salario/cobertura dividido por el importe del cálculo al siguiente número entero, lo que significa que 12,25 aumentaría a 13.</li><li>Si la opción es **Disminuir**, el cálculo matemático disminuirá el importe del salario/cobertura dividido por el importe del cálculo al siguiente número entero actual, lo que significa que 12,25 disminuiría a 12.</li></ul> |
   | **Importe del empleado si no es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si no es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe del empleado si es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Importe de la empresa si es fumador** | El importe que un proveedor de prestaciones cobra por un empleado que no fuma. Este es el importe que el empresario paga al proveedor de prestaciones y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Gastos administrativos** | El importe administrativo cobrado por un administrador externo. Este es el importe que el empresario paga al administrador externo y debe basarse en la frecuencia de pago para la configuración de la tasa. |
   | **Tasa de no fumador de crédito flexible** | El número de créditos flexibles de los costes de prestación, en función del cálculo definido para el nivel para no fumadores. Por ejemplo, si el tipo de cálculo es **Por importe de $ de cobertura**, el importe de cálculo es 10 000, y la tasa de crédito flexible para no fumadores es 6, eso significa que si un empleado no fumador elige 10 000 $ de cobertura, costará 6 créditos flexibles. Si eligen 20 000 $ de cobertura, costará 12 créditos flexibles, y así sucesivamente. |
   | **Tasa de fumador de crédito flexible** | El número de créditos flexibles de los costes de prestación, en función del cálculo definido para el nivel para fumadores. |

5. Seleccione **Guardar**. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
