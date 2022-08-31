---
title: Configurar reglas y opciones de elegibilidad
description: En este artículo se describe cómo establecer reglas y opciones de idoneidad en la administración de prestaciones en Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5540a2c39b3f9f53600e5edd5c63c99cec1fb000
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337101"
---
# <a name="configure-eligibility-rules-and-options"></a>Configurar reglas y opciones de elegibilidad 

Después de configurar los parámetros necesarios para la administración de prestaciones, puede crear reglas de idoneidad, paquetes, periodos y programas que asociará con sus planes de prestaciones.

Reglas de elegibilidad - Las reglas de elegibilidad se utilizan para determinar si los empleados son elegibles para un plan. Los empleados deben cumplir con la condición de al menos una regla para ser considerados elegibles para la prestación. Por ejemplo, tiene dos reglas en un plan. La primera regla (línea 1) establece que el tipo de empleado debe ser **Empleado**. La segunda regla (línea 2) establece que el tipo de empleado debe ser empleado a tiempo completo. Por lo tanto, los empleados que cumplen con la regla 1 son elegibles incluso si están empleados solo a tiempo parcial.

Sin embargo, puede configurar una sola regla que tenga varias condiciones. En este caso, los empleados deben cumplir todas las condiciones de la regla para ser considerados elegibles para la prestación. Por ejemplo, tiene una regla que se llama **Empleado a tiempo completo**. Esta regla establece que el tipo de empleado debe ser **Empleado** *y* el empleado debe estar empleado a tiempo completo. Por lo tanto, los empleados deben cumplir con ambas condiciones de la regla para ser elegibles.

> [!IMPORTANT]
> Se debe asociar al menos una regla de elegibilidad con cada plan de beneficios. Puede asociar varias reglas con una prestación.

## <a name="create-an-eligibility-rule"></a>Crear regla de idoneidad

Las reglas de idoneidad definen qué empleados pueden inscribirse en cada plan de prestaciones. Después de definir las reglas de idoneidad, las asigna a los planes de prestaciones. Después puede procesar la idoneidad de inscripción para ver qué empleados son idóneos para cada plan. 

Durante la inscripción abierta, los empleados pueden seleccionar planes de prestaciones. Si dejan de ser idóneos para un plan de prestaciones en función de las reglas de idoneidad después haberse inscrito, no se anulan automáticamente. Por lo general, cuando ocurre un evento de vida que afecta la idoneidad del plan, se inicia un periodo de inscripción para que el empleado seleccione los planes para los que es idóneo. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Reglas y opciones de idoneidad**.

2. En la pestaña **Reglas de elegibilidad**, seleccione **Nueva** para crear una regla de elegibilidad. Para ver los planes asociados con una regla de idoneidad, seleccione **Planes adjuntos**.

3. Especifique valores para los campos siguientes.

   | Campo | Descripción |
   | --- | --- |
   | **Regla de idoneidad** | Un identificador único de la regla de idoneidad. |
   | **Descripción** | Una descripción de la regla de idoneidad. |
   | **Fecha y hora de inicio de validez** | La fecha inicial de la regla de idoneidad. | 
   | **Fecha y hora de fin de validez** | La fecha final de la regla de idoneidad. |
   | **Tipo de empleado usuario** | Especifica si se usa el tipo de empleado del empleado en la regla de idoneidad de prestaciones. |
   | **Tipo de trabajador** | El tipo de trabajador, si **Usar tipo de empleado** se establece en **Sí**. |
   | **Usar situación laboral** | Especifica si se usa el estado de empleo del empleado en la regla de idoneidad de prestaciones. |
   | **Estado** | Estado del empleado, si **Usar estado de empleado** se establece en **Sí**. Si **Usar estado de empleado** se establece en **No**, no se usa el campo. |
   | **Usar categoría laboral** | Especifica si se usa el valor del empleado **Categoría de empleo** como parte de la regla de idoneidad para prestaciones. | 
   | **Categoría laboral** | La categoría de empleo del empleado si **Usar categoría de empleo** se establece en **Sí**. |
   | **Usar nueva regla de contratación** | Especifica si se debe usar el valor del periodo de nueva contratación del nuevo empleado como parte de la regla de idoneidad de prestaciones. |
   | **Período de inscripción** | El periodo de tiempo en que se permite la inscripción de nuevos empleados. Si también configura esto en los parámetros, la configuración de los parámetros tiene prioridad sobre este. |
   | **Usar situación laboral anterior** | Especifica si se usa el estado de empleo previo de un empleado como parte de la regla de idoneidad para prestaciones. Por ejemplo, puede especificar una regla de elegibilidad que exima un período de espera de cobertura para todos los empleados que hayan pasado de un estado **Despedido** a un estado **Empleado** dentro de los 90 días de su empleo anterior. |

4. En **Criterios adicionales**, seleccione las siguientes opciones y agregue información según sea necesario.

   | Opción | Descripción |
   | --- | --- |
   | **Edad apta** | Especifica el rango de edad o rangos necesarios para satisfacer la regla de idoneidad. |
   | **Departamento apto** | Especifica el departamento o departamentos en los que debe estar un empleado para satisfacer la regla de idoneidad. |
   | **Tipo de empleo apto** | Especifica el tipo o tipos de empleo en los que debe estar un empleado para satisfacer la regla de idoneidad. Por ejemplo, a tiempo completo o parcial. |
   | **Trabajo apto** | Especifica el trabajo o trabajos que satisfacen la regla de idoneidad. Los trabajos están asociados con puestos y los puestos son ocupados por los empleados. |
   | **Función de trabajo apta** | Especifica la función o funciones de trabajo que satisfacen la regla de idoneidad. Por ejemplo, trabajadores de ventas o técnicos. |
   | **Tipo de trabajo apto** | Especifica el tipo o tipos de trabajos que satisfacen la regla de idoneidad. Por ejemplo, administrativo o ejecutivo. |
   | **Entidad jurídica apta** | Especifica la entidad jurídica o las entidades jurídicas que son válidas para la regla de idoneidad. Por ejemplo, Contoso Entertainment System USA. |
   | **Región de compensación apta** | Especifica la ubicación del empleado que cumple con la regla de idoneidad. Por ejemplo, el centro de EE. UU. |
   | **Puesto apto** | Especifica la posición o posiciones que satisfacen la regla de idoneidad. Por ejemplo, asistente de recursos humanos o jefe de recursos humanos. |
   | **Tipo de puesto apto** | Especifica el tipo o tipos de posición que satisfacen la regla de idoneidad. Por ejemplo, a tiempo completo. |
   | **Estado apto** | Especifica los estados o provincias que satisfacen la regla de idoneidad. Por ejemplo, Dakota del Norte, EE. UU., o Columbia Británica, Canadá. |
   | **Condiciones laborables aptas** | Especifica las condiciones de empleo que cumplen con la regla de idoneidad. Por ejemplo, a voluntad o contrato grupal. |
   | **Sindicato apto** | Especifica la membresía de sindicato que satisface la regla de idoneidad. Por ejemplo, Forklift Drivers of America.</br></br>Cuando se usa una regla de idoneidad basada en un sindicato, el registro del sindicato del trabajador debe tener la fecha de finalización completada. No se puede dejar en blanco. |
   | **Código postal idóneo** | Especifica los códigos postales que satisfacen la regla de idoneidad. Por ejemplo, 58104. |

5. En **Detalles adicionales**, puede ver los siguientes detalles adicionales.

   | Campo | Descripción |
   | --- | --- |
   | **Campo de usuario elegible** | Especifica reglas de idoneidad adicionales basadas en campos definidos por el cliente. |
   | **Tipo de idoneidad** | Especifica la categoría de criterio que seleccionó en **Criterios adicionales**. |
   | **Referencia de idoneidad** | Especifica los valores que seleccionó en **Criterios adicionales**. |
   | **Descripción** | La descripción que seleccionó en **Criterios adicionales**. |

6. Seleccione **Guardar**.

## <a name="using-custom-fields-in-eligibility-rules"></a>Usar campos personalizados en las reglas de elegibilidad

[Campos Personalizados](hr-developer-custom-fields.md) se puede crear dentro de Recursos Humanos para rastrear información adicional. Estos campos se pueden agregar directamente a la interfaz de usuario y una columna se agrega dinámicamente a la tabla subyacente.  

Los campos personalizados se pueden utilizar en el proceso de elegibilidad. Las reglas de elegibilidad pueden usar uno o más valores de campos personalizados para determinar la elegibilidad de un empleado.  Para agregar un campo personalizado a una regla existente o para crear una nueva regla, vaya a **Gestión de beneficios > Enlaces > Configuración > Reglas de elegibilidad> Elegibilidad de campos personalizados**. Dentro de esta página, puede crear una regla que utilice uno o varios campos personalizados, y puede definir varios valores para cada campo personalizado para determinar la elegibilidad.

Las siguientes tablas admiten campos personalizados que se pueden utilizar en el proceso de elegibilidad:

- Trabajador (HcmWorker)  
- Trabajo (HcmJob)  
- Puesto (HcmPosition)  
- Descripción del puesto (HcmPositionDetail)  
- Asignación del trabajador del puesto  
- Empleo (HcmEmployment)  
- Detalles de empleo (HcmEmploymentDetails)  
- Detalles del trabajo (HcmJobDetails)  

Los siguientes tipos de campo personalizado son compatibles con el proceso de elegibilidad:

- Texto  
- Lista de selección  
- Número  
- Decimal  
- Casilla  

La siguiente tabla muestra la información de los campos del formulario de elegibilidad de campos personalizados.

| Campo  | Descripción |
|--------|-------------|
| Nombre | Nombre del criterio que se está creando. |
| Nombre de la tabla | El nombre de la tabla que contiene el campo personalizado que se usa para la regla de elegibilidad. |
| Nombre de campo | El campo que se utilizará para la regla de elegibilidad. |
| Tipo de operador | Muestra el operador utilizado en la configuración de elegibilidad del campo personalizado. |
| Valor | Muestra el valor utilizado en la configuración de elegibilidad del campo personalizado. |

## <a name="eligibility-logic"></a>Lógica de elegibilidad

Las siguientes secciones describen cómo se procesa la elegibilidad para los beneficios.

### <a name="rules-assigned-to-a-plan"></a>Reglas asignadas a un plan 
Cuando se asignan varias reglas de elegibilidad a un plan de beneficios, un empleado debe cumplir con al menos una regla para ser elegible para inscribirse en el plan de beneficios.  En el siguiente ejemplo, el empleado debe cumplir con los requisitos de la regla **Tipo de empleo** o la regla **Empleados activos**.

![El empleado debe cumplir con los requisitos de la regla Tipo de empleo o la regla Empleados activos.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Criterios dentro de una regla de elegibilidad 
Dentro de una regla, usted define los criterios que conforman la regla. En el ejemplo anterior, los criterios para la regla **Tipo de empleo** es donde Tipo de trabajo = Directores. Por lo tanto, el empleado debe ser director para ser elegible. Esta es una regla en la que solo hay un criterio dentro de la regla.

Puede definir reglas que tengan varios criterios. Cuando define varios criterios dentro de una regla de elegibilidad, un empleado debe cumplir con todos los criterios dentro de la regla para ser elegible para el plan de beneficios. 

Por ejemplo, la regla anterior **Empleados activos** se compone de los siguientes criterios. Para que el empleado sea elegible según la regla **Empleados activos**, el empleado debe estar empleado en la entidad legal USMF *y* tener un tipo de puesto de tiempo completo.  

![Criterios dentro de una regla de elegibilidad.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Múltiples condiciones dentro de los criterios

Las reglas se pueden expandir aún más para usar múltiples condiciones dentro de un solo criterio. El empleado debe cumplir con al menos una condición para ser elegible. Para seguir con el ejemplo anterior, la regla **Empleados activos** se puede ampliar aún más para incluir a los empleados que también son empleados a tiempo parcial. Como resultado, ahora el empleado debe ser un empleado en USMF *y* ser un empleado a tiempo completo o parcial.  

![Múltiples condiciones dentro de los criterios.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Condiciones de elegibilidad dentro de un criterio de campo personalizado 
De manera similar a lo anterior, los campos personalizados se pueden usar al crear reglas de elegibilidad y funcionan de la misma manera. Por ejemplo, es posible que desee ofrecer un reembolso por Internet a los empleados de Fargo y Copenhagen que trabajan desde casa, ya que los costos de Internet son más altos en esos lugares. Para hacer esto, cree dos campos personalizados: **Ubicación de la oficina** (lista de selección) y **Trabajando desde casa** (casilla de verificación). Luego cree una regla llamada **Empleados de la FMH**. El criterio para la regla es donde **Ubicación de la oficina = Fargo** o **Copenhague** *y* donde **Trabajar desde casa = Sí**.

Las reglas de idoneidad personalizadas deberían configurarse como se indica en la siguiente imagen. 

![Condiciones de elegibilidad dentro de un criterio de campo personalizado.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Configurar agrupaciones

Las agrupaciones son un conjunto de planes de prestaciones relacionadas. Puede usar paquetes de prestaciones para agrupar planes de prestaciones que un empleado debe elegir para inscribirse en ciertos planes que pueden depender de otras inscripciones en los planes de prestaciones. Los ejemplos de situaciones en las que puede querer usar un paquete incluyen:

- Una agrupación de plan de salud que incluye un seguro de salud con deducible alto con una cuenta de ahorros de salud (HSA) asociada.

- Un plan de seguro de vida con un plan obligatorio de seguro de vida para empleados incluido en una agrupación con plan de vida dependiente. Así se garantizaría que un empleado no pueda seleccionar la cobertura de vida de los dependientes sin registrarse en la cobertura del empleado.

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Reglas y opciones de idoneidad**.

2. En la pestaña **Agrupaciones**, seleccione **Nueva** para crear una agrupación. Para ver los planes asociados con una agrupación, seleccione **Planes adjuntos**.

3. Especifique valores para los campos siguientes.

   | Campo | Descripción |
   | --- | --- |
   | **Agrupación de trabajos** | El identificador único para la agrupación. |
   | **Descripción** | Una descripción de la agrupación. |
   | **Embarque maestro** | Indica si uno de los planes de la agrupación debe estar marcado como plan maestro. El plan maestro debe seleccionarse durante la inscripción abierta como parte de la agrupación antes de que el administrador de prestaciones pueda confirmar las elecciones de prestaciones del empleado. |
   | **Fecha y hora de inicio de validez** | La fecha y hora en la que la agrupación estará activa. |
   | **Válido hasta** | La fecha de vencimiento de la agrupación. El valor predeterminado es 12/31/2154, que significa nunca. |

4. Seleccione **Guardar**.

## <a name="configure-periods"></a>Configurar periodos

Los períodos definen cuándo están vigentes las prestaciones y cuándo pueden inscribirse los empleados. Puede crear tantos periodos como desee para mantener las prestaciones de inscripción abiertas y los periodos de cobertura de prestaciones. Los años del plan de prestaciones pueden o no seguir un calendario natural. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Reglas y opciones de idoneidad**.

2. En la pestaña **Periodos**, seleccione **Nuevo** para crear un periodo. Para ejecutar un proceso que adjunte todos los planes de prestaciones activos válidos al periodo de prestaciones, seleccione **Adjuntar planes**. Para ver los planes asociados con una agrupación, seleccione **Planes adjuntos**. 

3. Especifique valores para los campos siguientes.

   | Campo | Descripción |
   | --- | --- |
   | **Periodo** | El identificador único para el periodo. |
   | **Fecha y hora de inicio de validez** | La fecha y hora de inicio a partir de las que el periodo de prestaciones está activo. |
   | **Fecha y hora de fin de validez** | La fecha y hora de inicio a partir de las que el periodo de prestaciones está inactivo. |
   | **Inicio de la inscripción** | Fecha inicial para el periodo de inscripción abierta. La inscripción abierta es cuando un empleado puede hacer elecciones de prestaciones en prestaciones de autoservicio. |
   | **Fin de la inscripción** | Fecha final para el periodo de inscripción abierta. |
   | **Abierta** | Indica si el periodo está abierto según la fecha del sistema y las fechas y horas válidas de inicio y fin. | 
   | **Período anterior** | Especifica el periodo de prestaciones que precede al periodo de prestaciones seleccionado. Esta información se utiliza durante la inscripción de idoneidad de prestaciones para asignar planes, opciones de cobertura y personas designadas de un año anterior. |
 
4. Seleccione **Guardar**.

## <a name="use-a-flex-credit-program"></a>Usar un programa de crédito flexible

Puede usar programas de crédito flexible para inscribir a los empleados en prestaciones de acuerdo con un número predeterminado de créditos flexibles. Los empleados pueden elegir cómo asignar sus créditos flexibles. Por ejemplo, si un empleado está cubierto por el plan de seguro de salud de su cónyuge, es posible que desee utilizar los créditos que de otro modo habrían utilizado en la cobertura de salud para otras prestaciones.

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Reglas y opciones de idoneidad**.

2. En la pestaña **Periodos**, seleccione **Programas de crédito flexible**.

3. Seleccione un programa de crédito flexible para aplicar. Los campos contienen la siguiente información.

   | Campo | Descripción |
   | --- | --- |
   | **Id. de crédito de prestación** | El identificador único del programa de crédito flexible. |
   | **Descripción** | Una descripción del programa de crédito flexible. | 
   | **A partir de la fecha** | La fecha en que se activa el programa de crédito flexible. |
   | **Hasta fecha** | La fecha en que finaliza el programa de crédito flexible. Puede dejar el valor predeterminado (31/12/2154) para indicar que el programa de crédito flexible no tiene un vencimiento programado. |
   | **Valor total del crédito** | La cantidad de créditos que cada empleado tendrá que usar para sus prestaciones. |
   | **Regla de prorrateo** | La regla a utilizar para prorratear los créditos flexibles cuando se contrata a un empleado en la mitad del periodo de crédito flexible. </br></br><ul><li>**Ninguno**: el empleado no recibe créditos flexibles si son contratados después de que comience el periodo del programa de crédito flexible.</li><li>**Crédito total**: el empleado recibe el importe total de créditos flexibles, independientemente de cuándo sean contratados.</li><li>**Prorrateo**: el empleado recibe un importe prorrateado de créditos flexibles en función de su fecha de inicio.</li></ul> |
   | **Fórmula de prorrateo de crédito flexible** | La regla a utilizar para prorratear los créditos flexibles para los empleados que se contratan en mitad de un periodo de prestaciones del programa de crédito flexible. El prorrateo se basa en la fecha de inicio del empleo. Este campo únicamente se usa si selecciona **Prorrateo** o **Regla de prorrateo** en el campo . </br></br><ul><li>**Diario**: se prorratea el número de créditos flexibles que recibe un empleado de forma diaria. El número total de créditos flexibles se divide por el número de días en el periodo. Por ejemplo, si su periodo de prestaciones es de 400 días, el sistema dividirá la cantidad total de créditos flexibles por 400 para calcular la cantidad de créditos flexibles que reciben los empleados por día.</li><li>**Mes actual**: se prorratea el número de créditos flexibles que recibe un empleado de forma mensual, redondeado al mes actual. El número total de créditos flexibles se divide por el número de meses en el periodo. Por ejemplo, si su periodo de prestaciones es de 15 meses, el sistema dividirá la cantidad total de créditos flexibles por 15 para calcular la cantidad de créditos flexibles que reciben los empleados por mes.</li><li>**Mes siguiente**: se prorratea el número de créditos flexibles que recibe un empleado de forma mensual, redondeado al mes siguiente. El número total de créditos flexibles se divide por el número de meses en el periodo. Por ejemplo, si su periodo de prestaciones es de 15 meses, el sistema divide la cantidad total de créditos flexibles por 15 para calcular la cantidad de créditos flexibles que reciben los empleados por mes.</li></ul> |
   
   Asegúrese de que cada plan de prestaciones esté inscrito en un solo programa de crédito flexible por periodo de prestaciones. De lo contrario, el sistema no sabrá qué programa de crédito flexible usar para otorgar créditos flexibles y le causará problemas. 

## <a name="configure-programs"></a>Configurar programas

Los programas son un conjunto de planes de prestaciones que comparten un conjunto común de reglas de idoneidad. Puede definir reglas de idoneidad para todo el programa en lugar de para cada plan individual. Por ejemplo, un programa de Contoso Canada FTE o un programa a nivel ejecutivo de Contoso Europa. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Reglas y opciones de idoneidad**.

2. En la pestaña **Programas**, seleccione **Nuevo** para crear un programa. Para hacer excepciones para los empleados que no cumplen con los requisitos de la regla de idoneidad, seleccione **Anulación de reglas de idoneidad**. Para ver los planes asociados con un programa, seleccione **Planes adjuntos**.

3. Especifique valores para los campos siguientes.

   | Campo | Descripción |
   | --- | --- |
   | **Programa** | Un identificador único del programa. |
   | **Descripción** | Una descripción del programa. | 
   | **Fecha y hora de inicio de validez** | La fecha y hora en la que el programa estará activo. |
   | **Fecha y hora de fin de validez** | La fecha y hora en la que el programa expira. El valor predeterminado es 12/31/2154, que significa nunca. |
   | **Período de espera de cobertura** | El periodo que un empleado debe esperar antes de que comience la cobertura del programa de prestaciones. |
   | **Período de espera de deducción** | El periodo que un empleado espera antes de que comiencen las deducciones del programa de prestaciones. |
   | **Reglas de idoneidad** | Seleccione las reglas de idoneidad para aplicar al programa de prestaciones. Usted define las reglas de idoneidad en la pestaña **Reglas de idoneidad** en esta página. |
   
4. Seleccione **Guardar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
