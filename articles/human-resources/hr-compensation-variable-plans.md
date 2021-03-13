---
title: Cree planes de compensación variable
description: La compensación variable compone la paga irregular de un empleado, como bonificaciones o primas en acciones. Este artículo describe los componentes que se deben configurar para poder usar compensación variable e inscribir un empleado en un plan de compensación variable.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: f99bff8846cf95bc25f0396444a3920c48f73b1e
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115857"
---
# <a name="create-variable-compensation-plans"></a>Cree planes de compensación variable

La compensación variable compone la paga irregular de un empleado, como bonificaciones o primas en acciones. Este artículo describe los componentes que se deben configurar para poder usar compensación variable e inscribir un empleado en un plan de compensación variable.

El cálculo de los importes de compensación variable para sus empleados se puede basar en varios factores, como el rendimiento del empleado, el nivel de compensación del empleado y el rendimiento del departamento.

## <a name="variable-compensation-components"></a>Componentes de compensación variable
### <a name="create-compensation-types"></a>Crear tipos de compensación

Los **Tipos de compensación variable** es un componente obligatorio. Los tipos de compensación variable le permiten describir los tipos de compensación variable que concede su organización. También permiten especificar si la compensación será en efectivo o en un formulario no monetario, como existencias.

### <a name="describe-vesting-rules"></a>Describir reglas de atribución

Opcionalmente, las empresas pueden configurar **reglas de atribución**. Las reglas de atribución describen cómo la prima variable debe asignarse en el tiempo. Por ejemplo, una regla de atribución puede indicar que el empleado recibirá el 25 por ciento de la prima total cada año para los cuatro años próximos. Las reglas de atribución solo son informativas.

## <a name="variable-compensation-plans"></a>Planes de compensación variable
El **plan de compensación variable** contiene las reglas, los métodos de cálculo y los valores predeterminados para el cálculo de la compensación variable para los empleados inscritos. Al crear un plan de compensación variable, debe configurar el tipo de compensación variable. El tipo de compensación variable determina si el sistema calculará un importe de divisa o varias unidades como prima. También debe definir el método de cálculo:

-   **A partir de un momento específico**: el cálculo de prima variable se basa en la compensación fija que tenía el empleado en una fecha específica. Esta fecha se especifica en el evento de proceso cuando se procesan los nuevos importes de compensación.
-   **Compuesto**: se calcula un importe de la prima para cada índice salarial de compensación fija único que el empleado tenía entre la fecha inicial del ciclo y la fecha final del ciclo del evento de proceso. Después los índices se agregan conjuntamente para determinar la prima final. Por ejemplo, durante el ciclo, un empleado fue transferido a otro puesto que tenía una tarifa distinta de pago. En este caso, la prima variable se ajusta a la duración del tiempo en que el empleado tuvo cada índice salarial.

El importe de la prima variable se puede basar en un porcentaje de las ganancias base ordinarias del empleado o en un número establecido de unidades.

-   Seleccione la opción **Porcentaje de base** para escribir un porcentaje predeterminado y especificar si la base debe ser el índice salarial fijo del empleado o el punto de control para el nivel de compensación del empleado. El nivel de compensación se establece en el trabajo del empleado. Uno de los puntos de referencia de la estructura de compensación se puede establecer como punto de control en el plan de compensación fija. El sistema utilizará el nivel de compensación del trabajo del empleado y realizará una referencia cruzada con él con el punto de control que se muestra en el plan de compensación fija del empleado, para buscar el importe del punto de control para el nivel de compensación del empleado. Después, el importe del punto de control se usará en lugar del índice salarial fijo del empleado como base para la bonificación.
-   Seleccione la opción **Número de unidades** para especificar un número predeterminado de unidades, el valor de cada unidad y de la divisa del valor de unidad si el plan de compensación es para una prima que no es en efectivo (por ejemplo, 200 unidades de existencias con un valor de 40 USD) o solo el número de unidades si el plan de compensación es para una prima en efectivo. Para una prima en efectivo, el empleado recibirá el número de unidades de la divisa especificado que se usa para su plan de compensación fija (por ejemplo, 500 unidades de 1 USD). El control de la relación unívoca se puede usar para indicar si hay una asignación unívoca directa entre el número de unidades y el valor unitario. Al crear un plan de compensación variable para un plan de basado en efectivo usando el número de unidades, esta opción se bloquea automáticamente en **Sí** y el valor unitario es **1,0000**.

La configuración **Regla de contratación** le permite especificar si todos los empleados deben recibir el mismo aumento, independientemente de la fecha en que se les contrató (**Regla de contratación** = **Ninguna**), o si los empleados deben recibir un porcentaje de la prima, que se basa en la duración del empleo durante el ciclo (**Regla de contratación** = **Porcentaje**). 

**Endeudamiento** permite ajustar la prima de un empleado, en función del rendimiento del departamento del empleado. Las medidas de rendimiento se pueden establecer para cada departamento en la página **Departamentos**, en **Formularios relacionados** &gt; **Compensación** &gt; **Rendimiento**. El tipo de prima que los empleados del departamento reciben depende del valor del campo **Porcentaje del objetivo logrado**, que indica el rendimiento de departamento:

-   Si el rendimiento del departamento es del 100 por cien, la prima para los empleados de ese departamento se incluye en el porcentaje que se establece en el campo **Pago al 100%**.
-   Si el rendimiento del departamento es superior al 100 por cien, el sistema agrega el porcentaje que se establece en el campo **Por 1% por encima del objetivo** en el porcentaje que se establece en el campo **Pago al 100%** hasta que se alcance el valor que se establece en el campo **Pago máximo permitido**.
-   Si el rendimiento del departamento es inferior al 100 por cien, el sistema resta el porcentaje que se establece en el campo **Por 1% por debajo del objetivo** del porcentaje que se establece en el campo **Pago al 100%** hasta que se alcance el valor que se establece en el campo **Pago mínimo permitido**.

Puede establecer **niveles de tolerancia** en los porcentajes de umbral para que aparezca un mensaje de advertencia si el endeudamiento hace que el porcentaje se encuentre fuera del porcentaje del umbral. 

De forma predeterminada, el sistema busca el departamento definido en el puesto del empleado. Sin embargo, la prima de algunos empleados puede depender de rendimiento de varios departamentos. En este caso, los distintos departamentos y el porcentaje de la prima que se asigna al rendimiento de cada departamento se pueden establecer en la inscripción de compensación variable del empleado. Para obtener más información, consulte la sección “Inscripción de compensación variable” que se incluye a continuación. 

El endeudamiento se usa solo si la opción **Salario variable por rendimiento** está seleccionada al ejecuta el proceso de compensación. 

La ficha de **anulaciones de niveles** permite anular el porcentaje predeterminado o el número de unidades de prima, en función del nivel de compensación del empleado. Si **Habilitar anulaciones de niveles** se establece en **Sí** para empleados inscritos en el plan de compensación variable, el sistema toma el nivel de trabajo de un empleado y, a continuación, lo busca en la tabla de anulaciones de niveles para determinar el porcentaje o el número de unidades para dicho nivel. Si el nivel no se encuentra en la tabla de anulaciones de niveles, se usa el porcentaje predeterminado o el número de unidades de la ficha **General**. El porcentaje y el número de unidades también se pueden anular en la inscripción del empleado en el plan de compensación variable.

## <a name="variable-compensation-enrollment"></a>Inscripción de compensación variable
### <a name="determine-who-is-eligible-for-the-plan"></a>Determinar quién es apto para el plan

Cuando esté listo para inscribir a empleados en un plan de compensación variable, el primer paso es determinar quién es apto para la compensación que se especifica en el plan. No puede asignar el plan a ningún empleado a menos que determine la idoneidad. Para configurar la idoneidad, abra la página **Regla de idoneidad** para crea una nueva regla de idoneidad para su plan y, a continuación, defina los criterios que un empleado debe cumplir para ser apto para el plan de compensación. Puede limitar la idoneidad por departamento, sindicato, región de compensación (ubicación ), trabajo, función de trabajo, tipo de trabajo o nivel de compensación. Los empleados solo se pueden inscribir en un plan de compensación si cumplen **todos** los criterios que se establecen en la regla de idoneidad. 

**Nota:** Las reglas de idoneidad determinan la idoneidad tanto para planes de compensación fija como de compensación variable. Las reglas de idoneidad usan los siguientes campos de los registros de trabajo, puesto y empleado para determinar si un empleado es apto para un plan de compensación:

- En la página **Trabajo**:
  -   El campo **Trabajo**
  -   Los campos **Función** y **Tipo de trabajo** de la pestaña **Clasificación de trabajo**
  -   El campo **Nivel** de la pestaña **Compensación**
- En la página **Puestos**: los campos **Departamento** y **Región de compensación**
- En la página <strong>Empleados</strong>: la información acerca de los sindicatos que se asocia al empleado en <strong>Información personal</strong> &gt; <strong>Sindicatos</strong> en la pestaña *<strong><em>Trabajador</em></strong>*

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Habilitar la inscripción para el plan de compensación variable

En la página **Planes de compensación variable**, defina la opción **Habilitar inscripción** en **Sí** para permitir a los empleados aptos que se inscriban en el plan.

### <a name="enroll-the-employee"></a>Inscribir al empleado

Ahora puede inscribir a los empleados en el plan de compensación variable. Para inscribir a un empleado, vaya a la página **Empleados** y seleccione al empleado. A continuación, en el Panel de acciones, haga clic en **Compensación** &gt; **Inscripción de plan variable**. 

**Nota:** **Inscripción** debe establecerse en **Sí** en el plan de compensación variable. El campo **Plan** muestra solo planes para los que un empleado es apto según las reglas de idoneidad que se configuraron para dichos planes. Si no se ha configurado ninguna regla de elegibilidad para un plan, ningún empleado será apto para dicho plan. 

Asegúrese de que el campo **Fecha de vigencia** se haya definido correctamente. Si el plan de compensación variable usa el método de cálculo **Compuesto**, se puede considerar la fecha de vigencia de la inscripción durante el cálculo de la prima del empleado. 

Puede usar la ficha **Anulaciones** para anular los valores específicos para el empleado. Por ejemplo, si **Regla de contratación** está establecido en **Porcentaje** en el plan y debe usarse otra fecha de contratación durante el cálculo del porcentaje de contratación del empleado, puede establecer la fecha de contratación en el campo **Fecha de la regla de contratación**. También puede anular el valor de **Porcentaje de prima** o el valor de **Número de unidades** de un empleado específico, en función de la configuración del plan. Estos valores se seguirán factorizando según la regla de contratación, factores de rendimiento y otras opciones en el plan. 

**Anulación de unidades organizativas** se usa para basar la prima de un empleado en el rendimiento de uno o más departamentos. El porcentaje que se asigna entre todos los departamentos debe ascender al 100 por ciento. El rendimiento individual del empleado también se considera. Esta configuración se usa solo si la opción **Salario variable por rendimiento** está seleccionada al ejecutar el proceso de compensación.



